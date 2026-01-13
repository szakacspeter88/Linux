Installing and running Waydroid on Arch Linux is not complicated, but since Arch is a "rolling release" distribution, there are a few specific steps to keep in mind (especially regarding kernel and network settings).

Here is a step-by-step guide:

1. Prerequisites: The Right Kernel

Waydroid requires the ashmem and binder modules. For most Arch users, the easiest solution is to use the linux-zen kernel, which includes these by default.

Installation:

Bash
```
sudo pacman -S linux-zen linux-zen-headers
```
Important: Reboot your computer and select the ZEN kernel from the GRUB/boot menu!
2. Installing Waydroid

Waydroid is available via the AUR (Arch User Repository). Use an AUR helper like yay or paru:
Bash
```
yay -S waydroid
```
3. Initialization (Downloading Images)

Before starting, you need to download the Android system files. You can choose between the plain version (Vanilla) or the version with Google Services (GAPPS):
Bash
```
sudo waydroid init
```
(If you want GAPPS, use sudo waydroid init -s GAPPS).
4. Starting the Service

Waydroid uses a background process (container). You must start this before running the application:
Bash
```
sudo systemctl start waydroid-container
```
(To make it run automatically at boot: sudo systemctl enable waydroid-container)
5. Launching Waydroid

You can now launch the application from your menu or the terminal:
Bash
```
waydroid show-full-ui
```
Common Issues and Solutions

No Network: If Android has no internet, run the following command to enable IP forwarding (firewall settings): 
```
sudo sysctl net.ipv4.ip_forward=1
```

Graphics Issues (NVIDIA): Waydroid primarily works well with Intel and AMD. On NVIDIA, it currently only runs with software rendering or specific patches, as Waydroid is built on Wayland.

ARM Applications: Many mobile apps (e.g., Instagram, games) are built for ARM architecture. To run these on an x86 PC, you need an "libndk" or "libhoudini" translator (I recommend the Waydroid-Script GitHub project).

The Golden Rule: Waydroid must be started as a regular user, not root! The root user does not have access to the graphical interface (Wayland session), which causes DBus errors.

Fixing Current Errors
1. Fix "RuntimeError: mount"

This error occurs because previous attempts as root "stuck" the environment. Clean it up:
Bash
```
sudo waydroid session stop
sudo systemctl restart waydroid-container
waydroid session start

2. Install waydroid-script Correctly

If you get a "command not found" error, it's likely because makepkg was attempted as root. Do it with your own user:
Bash

cd /tmp
git clone https://aur.archlinux.org/waydroid-script-git.git
cd waydroid-script-git
makepkg -si  # DO NOT use sudo before makepkg!
```
Alternatively, use yay to handle dependencies automatically:

Bash
```
yay -S waydroid-script-git
```
3. Check Wayland Environment

Waydroid only runs under Wayland. If you are using X11 (e.g., default KDE or XFCE with old settings), it won't start. Check with: echo $XDG_SESSION_TYPE If the result is x11, you must switch to a Wayland session or run it within a compositor like weston.
Post-Installation: Enhancing Android

Once waydroid-extras (the script) is installed, run it to add essential features:

Bash
```
sudo waydroid-extras
```
Recommended options (Select with Space):

libndk: Crucial for running ARM (mobile) apps on x86.

widevine: Required for streaming services like Netflix.

GAPPS or MicroG: For Play Store functionality.

Final Clean Boot Sequence:

If you encounter a "Module not found" or "loop" error, reboot your computer first (to fix kernel-module mismatches). Then run:
Bash

```
sudo modprobe loop
sudo systemctl restart waydroid-container
waydroid session start &
# Wait 15 seconds
waydroid show-full-ui
```

If you see a black screen: Force software rendering:
Bash

```
waydroid prop set persist.waydroid.gles_driver software
sudo systemctl restart waydroid-container
```

Would you like me to help you generate a bash script to automate this entire cleanup and launch process?


Hungarian translation:

Waydroid telepítése és futtatása Arch Linuxon nem bonyolult, de mivel az Arch egy "rolling release" disztribúció, van néhány specifikus lépés, amire figyelni kell (különösen a kernel és a hálózati beállítások terén).

Itt egy lépésről lépésre követhető útmutató:
1. Előfeltételek: A megfelelő Kernel

A Waydroidnak szüksége van az ashmem és binder modulokra. A legtöbb Arch felhasználó számára a legegyszerűbb megoldás a linux-zen kernel használata, amely alapból tartalmazza ezeket.

Telepítés:

```
sudo pacman -S linux-zen linux-zen-headers
```
    
Fontos: Indítsuk újra a gépet, és a GRUB/boot menüben válaszd a ZEN kernelt!

2. A Waydroid telepítése

A Waydroid elérhető az AUR-ból (Arch User Repository). Használj egy AUR segédet (pl. yay vagy paru):

```
yay -S waydroid
```

3. Inicializálás (Képek letöltése)

Mielőtt elindítanád, le kell töltened az Android rendszert tartalmazó fájlokat. Választhatsz a sima (Vanilla) vagy a Google-szolgáltatásokkal (GAPPS) ellátott verzió között:

```
sudo waydroid init
```

(Ha GAPPS-ot szeretnél, használjuk a sudo waydroid init -s GAPPS parancsot).

4. A szolgáltatás elindítása

A Waydroid egy háttérfolyamatot (konténert) használ. Ezt el kell indítanod a program futtatása előtt:

```
sudo systemctl start waydroid-container
```

(Ha azt szeretnénk, hogy minden gépindításkor fusson: sudo systemctl enable waydroid-container)
5. Waydroid indítása

Most már indíthatjuk magát az alkalmazást a menüből vagy terminálból:

```
waydroid show-full-ui
```

Gyakori hibák és megoldások

Hálózat hiánya: Ha az Androidon nincs internet, futtassuk az alábbi parancsokat a tűzfal beállításához (IP forwarding):

```
sudo sysctl net.ipv4.ip_forward=1
```

Grafikus hiba (NVIDIA): A Waydroid elsősorban Intel és AMD kártyákkal működik jól. NVIDIA kártyán jelenleg csak szoftveres rendereléssel vagy specifikus foltokkal indul el, mivel a Waydroid a Waylandre épül.

ARM alkalmazások: Sok mobil app (pl. Instagram, játékok) ARM architektúrára készült. Ahhoz, hogy ezek fussanak x86-os gépen, szükséged lesz egy "libndk" vagy "libhoudini" fordítóra (erre a Waydroid-Script nevű GitHub projektet javaslom).

A legfontosabb szabály: A Waydroidot sima felhasználóként kell indítani, nem root-ként! A root felhasználónak nincs hozzáférése a grafikus felülethez (Wayland session), ezért kaphatunk a DBus hibákat.

Itt a megoldás a jelenlegi állapotodra:
1. Javítsd ki a "RuntimeError: mount" hibát

Ez a hiba azért van, mert az előző root-ként való próbálkozások miatt "beragadt" a környezet. Tisztítsuk meg:

```
sudo waydroid session stop
sudo systemctl restart waydroid-container
waydroid session start
```

(Ha a session start fut, nyissunk egy új terminált a következő lépéshez.)

2. A waydroid-script telepítése helyesen

A hibaüzeneted szerint a parancs nem található, mert a makepkg root-ként nem futott le. Ezt saját felhasználóval kell megtenned:

```
cd /tmp
git clone https://aur.archlinux.org/waydroid-script-git.git
cd waydroid-script-git
makepkg -si  # Itt NE használj sudo-t a makepkg elé!
```

Ezután már elérhető lesz a waydroid-script parancs az ARM fordító (libndk) telepítéséhez.
3. Wayland környezet ellenőrzése

A Waydroid csak Wayland alatt fut. Ha X11-et (pl. alapértelmezett KDE vagy XFCE régi beállítással) használsz, nem fog elindulni.

Ellenőrizd: echo $XDG_SESSION_TYPE

Ha az eredmény x11, akkor vagy át kell jelentkezned egy Wayland munkamenetbe, vagy telepítened kell a weston kompozitort és azon belül futtatni.

4. Végső indítási sorrend (Így csináld):

    Konténer indítása (csak egyszer kell): sudo systemctl start waydroid-container

    Session indítása (saját felhasználóval!): waydroid session start &

    UI megnyitása (pár másodperc várakozás után): waydroid show-full-ui

Miért nem működött a "waydroid init"?

A naplód szerint az init sikeres volt (már letöltötte a képeket), a hiba ott volt, hogy a root terminálból próbáltad a grafikus felületet indítani. Az Android egy konténerben fut, amihez a felhasználódnak kell csatlakoznia a Wayland protokollon keresztül.

1. A makepkg javítása

Töröld a hibás jogosultságú mappát, majd próbáljuk újra saját felhasználóként:

```
sudo rm -rf /tmp/waydroid-script-git
cd /tmp
git clone https://aur.archlinux.org/waydroid-script-git.git
cd waydroid-script-git
makepkg -si
```

2. A "RuntimeError: mount" hiba végleges megoldása

Ez a hiba azért makacs, mert valamiért a korábbi csatolás (mount) nem szakadt meg rendesen, vagy a mappa foglalt. Próbáld meg kényszerítve lecsatolni:

```
sudo umount -l /var/lib/waydroid/rootfs
sudo systemctl restart waydroid-container
```

Ha ezután is hibát kapunk, ellenőrizzük, hogy a zen kernelben vagyunk-e, mert a sima Arch kernelhez extra beállítások kellenek: uname -r (Ha nem látjuk benne a "zen" szót, indítsd újra a gépet a Zen kernellel).
3. Miért fontos a felhasználói mód?

A Waydroid két részből áll, és a hibaüzeneteid nagy része ebből a félreértésből adódik:

Alkatrész,                  Felhasználó,               Feladata
Container,                  root (systemd),            Az Android kernel-szintű futtatása.
Session,                    saját felhasználó,         A grafikus felület és a hang összekötése.

Mit tegyél, ha a makepkg kész?

Ha sikeresen felment a waydroid-script-git, akkor telepítsük az ARM fordítót, hogy ne csak a "vason" futó alkalmazások induljanak el:

```
sudo waydroid-script install libndk
```

Ha a makepkg nem találja a függőségeket az alap Arch tárolókban. Ez azért van, mert a python-inquirerpy szintén egy AUR csomag, amit a pacman önmagában nem tud letölteni.

Mivel már van yay telepítve a rendszerünkön, a legegyszerűbb, ha rábízzuk a teljes folyamatot. A yay automatikusan letölti a Waydroid-scriptet és az összes hiányzó függőségét is az AUR-ból.
1. A Waydroid-script telepítése (a helyes úton)

Futtassuk ezt a parancsot:

```
yay -S waydroid-script-git
```

(Ha kérdezi, válasszuk az alapértelmezett opciókat, és haggyuk, hogy telepítse a python-inquirerpy, python-tqdm és lzip csomagokat.)

2. A "Mount" hiba javítása

A korábbi RuntimeError miatt még mindig fennállhat a csatolási hiba. Futtassuk az alábbiakat, hogy "tiszta lapot" kapjon a Waydroid:

```
# Állítsunk le minden futó folyamatot
sudo waydroid session stop
sudo systemctl stop waydroid-container

# Kényszerített lecsatolás, ha valami beragadt
sudo umount -l /var/lib/waydroid/rootfs

# Indítsuk újra a szolgáltatást
sudo systemctl start waydroid-container
```

3. Libndk (ARM fordító) telepítése

Ha a yay végzett a telepítéssel, jöhet az ARM támogatás, hogy ne csak x86-os appok fussanak:

```
sudo waydroid-script install libndk
```

4. A Waydroid elindítása (Sima felhasználóként!)

Végül próbáljuk meg elindítani a felületet:

```
waydroid show-full-ui
```

Fontos megjegyzés: Ha a waydroid show-full-ui parancsra még mindig a DBUS_SESSION_BUS_ADDRESS hibát kapjuk, az azt jelenti, hogy a terminálunk nem látja a grafikus környezetet. Ezt elkerülhetjük, ha nem a terminálba írjuk be, hanem a Start menüből / Alkalmazásindítóból kattintunk a "Waydroid" ikonra.

Ha a yay paranccsal nem sikerült feltelepíteni a scriptet, vagy ott is elakadt valamelyik függőségnél, akkor:

két apró akadály maradt: 
a waydroid-script még nincs a rendszereünkön, és a Wayland-kapcsolatot még sínre kell tennünk.

Mivel a makepkg korábban a függőségek miatt leállt, a parancs nem jött létre. Használjuk a yay-t, ami elintézi helyettünk a függőségek (pl. python-inquirerpy) vadászatát is.

1. A Script telepítése (yay-el)

Futtassuk ezt a parancsot, ez minden hiányzó darabot a helyére tesz:

```
yay -S waydroid-script-git
```

(Ha kész, ellenőrizhetjük a which waydroid-script paranccsal, hogy megvan-e.)
2. Az ARM fordító (libndk) telepítése

Ha a fenti parancs lefutott, most már működnie kell:

```
sudo waydroid-script install libndk
```

3. A Waydroid indítása (A legfontosabb lépés)

A korábbi hibaüzeneteid alapján a terminálod "elveszítette" a kapcsolatot a grafikus felülettel. Ahelyett, hogy terminálból küzdenénk a DBus változókkal, próbáld meg a következőt:

    Nyisd meg az Arch Linuxod alkalmazásmenüjét (KDE, GNOME vagy amilyen felületet használsz).

    Keresd meg a Waydroid ikont.

    Kattints rá.

Ha mégis terminált szeretnél használni, kötelező ebben a sorrendben:

```
# 1. Konténer elindítása (ha még nem fut)
sudo systemctl start waydroid-container

# 2. Session indítása SAJÁT felhasználóként (Várj 5-10 másodpercet, amíg elindul)
waydroid session start &

# 3. UI megnyitása
waydroid show-full-ui
```

Mi van, ha még mindig hibát kapsz?

Ha a waydroid show-full-ui parancsra még mindig azt írja, hogy Using X11 for dbus-daemon autolaunch was disabled, akkor az azt jelenti, hogy:

Vagy X11 munkamenetben vagy (Wayland helyett).

Vagy NVIDIA kártyád van, amihez trükközni kell.

Kérlek, futtasd le ezt a parancsot, és írd meg az eredményt, hogy lássam, jó felületen vagy-e: echo $XDG_SESSION_TYPE

(Illetve írd meg, hogy a yay -S waydroid-script-git sikeresen lefutott-e!)

Mivel Wayland munkamenetben vagy és a waydroid-script is fent van, már csak az indítási sorrendet kell tisztáznunk.

A korábbi RuntimeError: mount hiba általában azért marad meg, mert a rendszer úgy érzi, a konténer már "félúton" fut. Takarítsunk ki egy utolsó parancssorral, aztán indítsuk el az ARM támogatást és a felületet.
1. ARM támogatás (libndk) telepítése

Most már mennie kell a parancsnak:

```
sudo waydroid-script install libndk
```

(Ez fontos, mert enélkül a legtöbb Play Áruházas app vagy játék el sem indulna az x86-os Archodon.)
2. A Waydroid "tiszta" indítása

Kérlek, pontosan ebben a sorrendben futtasd a parancsokat (ne root-ként, csak ahol írom!):

Szolgáltatás újraindítása:
```
sudo systemctl restart waydroid-container
```

Munkamenet (Session) indítása: (Várj kb. 10 másodpercet a parancs után, amíg az Android "bebootol" a háttérben)

```
waydroid session start &
```

Ablak megnyitása:

```
waydroid show-full-ui
```

Mit tegyél, ha még mindig "mount" hibát látsz?

Ha a waydroid session start parancsra még mindig azt mondja, hogy nem tudja csatolni a system.img-t, próbáld meg ezt a kényszerített törlést:

```
sudo waydroid session stop
sudo umount -l /var/lib/waydroid/rootfs
sudo rm -rf /var/lib/waydroid/rootfs/*
sudo systemctl restart waydroid-container
waydroid show-full-ui
```

3. Extra tipp: Google Play Áruház (ha szükséged van rá)

Mivel korábban a Vanilla (GAPPS nélküli) verziót inicializáltuk, nincs rajta Play Áruház. Ha szeretnél Google szolgáltatásokat:

```
sudo waydroid-script install gapps
```

Megjegyzés: A Gapps telepítése után az Android készüléket regisztrálnod kell a Google-nél (a script ki fogja írni az ID-t és a linket, ahol ezt megteheted).

Ha sikerült elindulnia az Android ablaknak a waydroid show-full-ui parancs után, akkor a yay sikeres telepítést jelzett. Valószínűleg a csomag nem egy waydroid-script nevű binárist rakott a rendszerútvonalba (PATH), hanem magát a Python fájlt, vagy más néven érhető el.

Nézzük meg, pontosan hová kerültek a fájlok, és javítsuk ki!
1. Keresd meg a parancsot

Futtasd ezt a parancsot, hogy lásd, mi lett telepítve:

```
pacman -Ql waydroid-script-git | grep bin
```

Ha látsz olyat, hogy /usr/bin/waydroid-extras, akkor használd azt a waydroid-script helyett.

Ha nincs találat, próbáld meg így futtatni (néha csak waydroid_script aláhúzással): waydroid-extras vagy waydroid_script

2. Ha még mindig nem találja, használd a közvetlen Python hívást

A legtöbb AUR-os verzió a /usr/lib/waydroid-script/main.py helyre települ. Próbáld meg így:
```
sudo python /usr/lib/waydroid-script/main.py install libndk
```
3. A leggyorsabb alternatíva (ha a fentiek nem mennek)

Ha nem akarunk a névvel küzdeni, töltsd le a scriptet közvetlenül a GitHubról futtathatóként:

```
cd /tmp
curl https://raw.githubusercontent.com/casualsnek/waydroid_script/main/main.py -o waydroid-script.py
chmod +x waydroid-script.py
sudo python3 waydroid-script.py install libndk
```

Miért nem indul el a Waydroid felülete?

Amíg a libndk telepítésével küzdünk, nézzük meg, miért nem indult el az ablakod. A korábbi mount hiba miatt próbáld meg ezt a "brutális" tisztítást, ami alaphelyzetbe állítja a csatolási pontokat:

```
# Mindent állítsunk le
waydroid session stop
sudo waydroid container stop

# Kényszerített lecsatolás (ha hibaüzenetet kapsz, ne törődj vele, menj tovább)
sudo umount -l /var/lib/waydroid/rootfs
sudo umount -l /var/lib/waydroid/images

# Indítsuk el tisztán
sudo systemctl restart waydroid-container
waydroid session start &
# Várj 10 másodpercet...
waydroid show-full-ui
```

A csomag nem waydroid-script néven, hanem waydroid-extras néven telepítette a futtatható fájlt a /usr/bin/ mappába.

Így tudod most befejezni a folyamatot:
1. Az ARM támogatás (libndk) telepítése

Használd a helyes parancsnevet:

```
sudo waydroid-extras
```

A parancs elindítása után egy interaktív menüt kell kapnod. Ott válaszd ki az Install -> libndk opciót. (Ha nem ad menüt, próbáld meg így: sudo waydroid-extras install libndk).
2. A Waydroid elindítása (A mount hiba végleges orvoslása)

Mivel korábban láttuk a RuntimeError: Command failed: % mount hibát, végezzük el a tiszta indítást. Másold be ezeket a sorokat egymás után:

```
# Állítsunk le mindent, ami beragadhatott
sudo waydroid container stop
sudo umount -l /var/lib/waydroid/rootfs

# Indítsuk el a háttérszolgáltatást
sudo systemctl start waydroid-container

# Indítsuk el a felhasználói munkamenetet (NEM sudo-val!)
waydroid session start &
```

Várj kb. 10-15 másodpercet, amíg a háttérben az Android elindul.
3. Az ablak megnyitása

Végül nyisd meg a grafikus felületet:
```
waydroid show-full-ui
```

Mit tegyél, ha fekete képernyőt látsz?

Ha az ablak megnyílik, de fekete marad, az gyakran grafikus gyorsítási hiba. Arch Linuxon ilyenkor ezt a parancsot érdemes megpróbálni (egy új terminálban, miközben fut a Waydroid):

```
waydroid prop set persist.waydroid.gles_driver-software
```

Ezután indítsd újra a konténert (sudo systemctl restart waydroid-container).

Itt tudod testreszabni az Android rendszeredet, hogy teljes értékű legyen.

A következőket javaslom kijelölni (a Space billentyűvel tudod őket beikszelni):

    libndk: Ez a legfontosabb. Ez teszi lehetővé, hogy az ARM-re (mobilra) írt appok fussanak az Arch Linuxodon.

    widevine: Ha néznél Netflixet vagy más védett streaminget, ez szükséges hozzá.

    magisk (opcionális): Ha "root" jogot szeretnél az Androidon belül (például speciális rendszereszközökhöz).

Mi a helyzet a Google Play-jel?

Itt két utad van, válaszd azt, amelyik szimpatikusabb:

    A "Hivatalos" út (gapps): Ha a valódi Google Play Áruházat akarod használni. Hátránya: Regisztrálnod kell az eszközazonosítót a Google-nél (a script segíteni fog benne), és lassíthatja kicsit a rendszert.

    A "Privacy" út (microg): Ez helyettesíti a Google szolgáltatásokat (nyílt forráskódú), kevesebb adatot küld a Google-nek és gyorsabb. Mellé érdemes az fdroidpriv-et is bejelölni.

A folyamat:

    Jelöld ki a kívánt elemeket a Szóköz (Space) gombbal (legyen ott egy csillag vagy pipa).

    Nyomj Enter-t.

    Várd meg, amíg a script letölti és integrálja a csomagokat a Waydroid képmásba (ez eltarthat pár percig a netsebességedtől függően).

Utolsó lépés a telepítés után:

Miután a script végzett, a Waydroid-ot újra kell indítani, hogy az új funkciók (főleg a libndk) élesedjenek:

```
sudo waydroid container stop
sudo systemctl restart waydroid-container
waydroid session start &
# Várj kicsit, majd:
waydroid show-full-ui
```

1. A loop modul betöltése

Először ellenőrizzük, hogy be van-e töltve a szükséges modul:

```
sudo modprobe loop
```

Ha ez hiba nélkül lefut, próbáld meg újra a Waydroid indítását. Ha hibát kapsz (pl. module not found), az azt jelenti, hogy a jelenlegi kerneled nem támogatja alapból, vagy frissítés után nem indítottad újra a gépet.
2. Ha ZEN kernelt használsz (ajánlott)

Mivel az Arch-on vagy, a legbiztosabb megoldás a linux-zen kernel, mert abban minden Waydroidhoz szükséges modul (binder, ashmem, loop) engedélyezve van.

Ellenőrizd a kerneled: uname -r

Ha nem ZEN: Telepítsd fel és indítsd újra a gépet: sudo pacman -S linux-zen

3. A loop eszközök számának növelése (ha szükséges)

Ha a modul be van töltve, de még mindig nem megy, adjunk neki több eszközt:

```
sudo zsh -c 'echo "options loop max_loop=256" > /etc/modprobe.d/loop.conf'
```

Ezután indítsuk újra a gépet.
A "tiszta" indítási kísérlet (miután a fentiek megvannak):

Ha a modprobe loop lefutott, csináljuk ezt:

Szüntessük meg a beragadt csatolásokat:
```
sudo umount -l /var/lib/waydroid/rootfs 2>/dev/null
sudo waydroid container stop
```
Indítsuk újra a konténert:
```
sudo systemctl restart waydroid-container

```

Indítsd a felhasználói session-t:

```
waydroid session start &
# Várj 10 másodpercet, amíg az Android feláll
waydroid show-full-ui
```

Ha valami más verzió van fennt, akkor a terminál a sudo modprobe loop parancsra, valami frissitési hibaüzenetet ir ki:

Ha a helyzet pl a következő: frissítettük a rendszert (vagy a kernelt), és a jelenleg futó kernelünk verziója pl.: (6.18.2-arch2-1) már nem létezik a lemezen, mert a Pacman felülírta egy újabb verzióval. A rendszer ezért nem tudja betölteni a loop modult (vagy bármi mást), amíg újra nem indítod a gépet.

A megoldás lépései:

1. Indítsuk újra a számítógépet! Ez a legfontosabb lépés. Újraindításkor az Arch a legfrissebb kernelt fogja betölteni, amihez már tartoznak modulok.

2. Ellenőrizzük a modult az újraindítás után: Ha újra beléptünk, futtassuk le újra:

```
sudo modprobe loop
```

Ha nem kapunk hibaüzenetet, akkor minden rendben.

3. Waydroid indítása: Most, hogy a loop modul aktív, a Waydroid már képes lesz felcsatolni (mount) az Android fájlrendszerét:

```
sudo systemctl start waydroid-container
waydroid session start &
# Várj 10 másodpercet
waydroid show-full-ui
```

Miért történt ez? (Röviden)

Az Arch Linux nem tartja meg a régi kernel modulokat frissítés után. Amíg nem indítod újra a gépet, a rendszer a memóriában lévő (régi) kernelt használja, de a fájlrendszerben már csak az újabb verzió moduljai vannak meg. Ezt hívják "kernel-module mismatch"-nek.
Mit tegyél, ha újraindítás után is ezt írja?

Ritka esetben előfordulhat, hogy a kernel telepítése nem volt teljes. Ekkor ezt futtasd:

```
sudo pacman -Syu linux
# vagy ha korábban a ZEN-t raktad fel:
sudo pacman -Syu linux-zen
```

Majd ismét egy újraindítás.

Kérlek, indítsd újra a gépedet, és próbáld meg a waydroid show-full-ui parancsot.

Ha nem sikerült eljutnod az Android kezdőképernyőig, akkor semmi gond, a zsh csak egy parancsértelmező (mint a bash), és valószínűleg nincs telepítve, de nincs is rá feltétlenül szükség. Ugyanezt meg tudjuk tenni a sima bash-sel is, ami minden Arch Linuxon ott van.

Azonban a legfontosabb: mindenképpen indítsd újra a gépet, mielőtt bármi mást tennél, mert a korábbi "Module not found" hiba azt jelzi, hogy a rendszered frissítésre vár.
1. A parancs helyesen (bash-sel):

Ha mégis be akarod állítani a loop eszközök számát (ami hasznos a Waydroidnak), használd ezt:

```
sudo bash -c 'echo "options loop max_loop=256" > /etc/modprobe.d/loop.conf'
```

2. A folyamat az újraindítás után:

Miután újraindítottad a gépet, a következő lépésekkel élesítheted a Waydroidot:

```
sudo modprobe loop
```
(Ha nem ír semmit, az a jó jel!)

Tisztítás és indítás: Mivel korábban sokszor próbáltuk, érdemes egy tiszta indítást csinálni:

```
sudo waydroid session stop
sudo systemctl restart waydroid-container
waydroid session start &
```

Várjunk kb. 15 másodpercet, amíg az Android konténer teljesen feláll a háttérben.

Ablak megnyitása:
```
waydroid show-full-ui
```
Mi van, ha még mindig fekete a kép?

Ha az ablak megjelenik, de nem látunk semmit, akkor valószínűleg a videókártyánk (pl. NVIDIA) és a Wayland nem barátkoznak. Ebben az esetben próbáld ki a szoftveres renderelést:


```
waydroid prop set persist.waydroid.gles_driver software
sudo systemctl restart waydroid-container
```

Ilyenkor már általában sikerül  az újraindítás után megnyitni a  waydroid show-full-ui -t
