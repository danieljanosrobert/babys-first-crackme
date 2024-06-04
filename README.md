# Cybersecurity - Reverse engineering

@danielj

# Tartalomjegyzék
- [Cybersecurity - Reverse engineering](#cybersecurity---reverse-engineering)
- [Tartalomjegyzék](#tartalomjegyzék)
- [Cybersecurity](#cybersecurity)
  - [Mi az a kiberbiztonság?](#mi-az-a-kiberbiztonság)
  - [A Kiberbiztonság Fontossága](#a-kiberbiztonság-fontossága)
  - [A Kiberbiztonsági Fenyegetések Típusai](#a-kiberbiztonsági-fenyegetések-típusai)
- [Védelmi Mechanizmusok](#védelmi-mechanizmusok)
  - [Védelmi Mechanizmusok](#védelmi-mechanizmusok-1)
  - [A Kiberbiztonsági Szakemberek Szerepe](#a-kiberbiztonsági-szakemberek-szerepe)
  - [White Hat Hackerek](#white-hat-hackerek)
- [CTF](#ctf)
  - [Kiberbiztonság és CTF Feladatok](#kiberbiztonság-és-ctf-feladatok)
  - [CTF Feladatok Típusai](#ctf-feladatok-típusai)
  - [Reverse Engineering](#reverse-engineering)
  - [Reverse Engineering - Tippek](#reverse-engineering---tippek)
- [Gyakorlati példa](#gyakorlati-példa)
  - [Forráskód](#forráskód)
  - [xxd, strings parancsok](#xxd-strings-parancsok)
  - [objdump -d -Mintel](#objdump--d--mintel)
  - [IDA Free](#ida-free)
  - [IDA Free - start](#ida-free---start)
  - [IDA Free - main](#ida-free---main)
  - [Ida Free - sub\_11A9](#ida-free---sub_11a9)
  - [Ellenőrzés](#ellenőrzés)
- [Források](#források)

# Cybersecurity

## Mi az a kiberbiztonság?

A kiberbiztonság a számítógépes rendszerek, hálózatok és adatok védelme a digitális támadások ellen.

A támadások célja lehet adatok ellopása, módosítása vagy megsemmisítése, valamint a rendszerek működésének megzavarása. A kiberbiztonság ez ellen véd.

## A Kiberbiztonság Fontossága

- Adatvédelem
  - Az érzékeny információk, például személyes adatok, pénzügyi adatok és egészségügyi adatok védelme kritikus fontosságú.
- Üzletmenet Folytonossága
  - A vállalatok működési képességének fenntartása a támadásokkal szemben.
- Jogszabályi Megfelelés
  - A különböző iparági szabályozások és törvények betartása érdekében.
- Gazdasági Hatások
  - A kiberbiztonsági támadások gazdasági veszteségeket okozhatnak, beleértve az adatlopást, üzletmenet megszakítását és hírnévromlást.
  
## A Kiberbiztonsági Fenyegetések Típusai

A kiberbiztonsági fenyegetések különböző formákban jelentkezhetnek. Ezek közé tartoznak a malware-ek, phishing támadások, ransomware-ek és a DDoS támadások. Mindegyik fenyegetés különböző módon károsíthatja a rendszereinket és adatainkat. A social engineering például az emberek megtévesztésére alapul, hogy érzékeny információkat szerezzenek meg.
- Malware: Kártékony szoftverek, amelyek célja a rendszer károsítása.
  - Vírusok: Önmásoló kódok, amelyek más programokba épülnek.
  - Trójaiak: Káros programok, amelyek hasznos alkalmazásnak álcázzák magukat.
  - Féreg: Önmásoló programok, amelyek hálózati kapcsolatokon keresztül terjednek.
- Phishing: Adathalászat, ahol az áldozatokat csaló e-mailekkel vagy - weboldalakkal tévesztik meg.
  - Spear Phishing: Célzott adathalászat egy konkrét személy vagy szervezet ellen.
- Ransomware: Zsarolóvírusok, amelyek titkosítják az adatokat és váltságdíjat - követelnek.
- DDoS Támadások: Elosztott szolgáltatásmegtagadás támadások, amelyek túlterhelik - a rendszereket.
- Social Engineering: Az emberek megtévesztése, hogy érzékeny információkat - szerezzenek meg.

# Védelmi Mechanizmusok

## Védelmi Mechanizmusok

A kiberbiztonsági védelmi mechanizmusok célja a rendszerek és adatok védelme a támadások ellen. A tűzfalak és antivírus szoftverek szűrik és eltávolítják a kártékony forgalmat, míg a titkosítás és hozzáférés-szabályozás biztosítja az adatok védelmét. Emellett fontos a felhasználók biztonsági oktatása is, hogy tudják, hogyan védekezhetnek a fenyegetésekkel szemben.

- Tűzfalak
- Antivírus szoftverek
- Titkosítás
- Hozzáférés-szabályozás
- Biztonsági oktatás

## A Kiberbiztonsági Szakemberek Szerepe

A kiberbiztonsági szakemberek kulcsszerepet játszanak a szervezetek informatikai biztonságának fenntartásában. Feladataik közé tartozik:
- **Biztonsági Rések Azonosítása**: A szakemberek különböző módszerekkel (pl. penetration testing, vulnerability scanning) azonosítják a rendszerekben található sérülékeny pontokat. Ezek a biztonsági rések olyan hibák vagy gyengeségek, amelyeket a támadók kihasználhatnak a rendszer kompromittálására.
- **Támadások Megelőzése**: A támadások megelőzése érdekében a szakemberek proaktív intézkedéseket hoznak, mint például a tűzfalak és behatolásérzékelő rendszerek beállítása, rendszeres biztonsági frissítések telepítése, erős jelszavak használata, valamint a hozzáférési jogosultságok megfelelő kezelése. Céljuk, hogy a támadók ne jussanak be a rendszerbe vagy ne férjenek hozzá érzékeny adatokhoz.
- **Incidenskezelés**: Amikor egy biztonsági incidens történik, például adatszivárgás vagy rendszerbehatolás, a kiberbiztonsági szakemberek gyorsan és hatékonyan reagálnak. Az incidenskezelés magában foglalja az incidens észlelését, a kiváltó okok azonosítását, az érintett rendszerek izolálását és helyreállítását, valamint az incidens utólagos elemzését és jelentését. Céljuk, hogy minimalizálják a károkat és megakadályozzák a jövőbeli incidensek bekövetkezését.

## White Hat Hackerek
- Etikus Hackerek: Olyan szakemberek, akik engedéllyel tesztelik a rendszerek biztonságát.
- Cél: Sérülékenységek azonosítása és kijavítása, mielőtt a rosszindulatú hackerek kihasználnák azokat.

# CTF

## Kiberbiztonság és CTF Feladatok

A CTF feladatok kiberbiztonsági kihívások, amelyek valós helyzeteket szimulálnak. Ezek a feladatok segítik a szakembereket a valós támadások és védekezési technikák gyakorlásában, fejlesztik a problémamegoldó képességeiket és technikai tudásukat.

## CTF Feladatok Típusai

A CTF feladatok különböző típusokba sorolhatók. Minden típus különböző készségeket és tudást igényel, amelyek fontosak a kiberbiztonsági szakemberek számára.

- Pwn - Exploitálás és sérülékenységek kihasználása
- Reverse engineering - Programok visszafejtése
- Crypto - Kriptográfiai kihívások
- Web - Alkalmazások biztonsági hibáinak kihasználása
- Forensics - Digitális nyomozás és adatelemzés

## Reverse Engineering

A kódvisszafejtés – vagy reverse engineering – az a folyamat, amely során egy készterméket, például szoftvert, hardvert vagy adatokat visszafejtenek az eredeti tervezési dokumentáció vagy forráskód nélkül.

Célok
- Biztonsági rések azonosítása és kihasználása
- Malware elemzése és eltávolítása
- Interoperabilitás biztosítása különböző rendszerek között

Eszközök
- Disassembler *(Ghidra, IDA Pro)*
- Debugger *(OllyDbg)*
- Hex Editor *(HxD)*

## Reverse Engineering - Tippek

Alapvető Lépések

1. Környezet Beállítása: Állítsuk be a megfelelő eszközöket és környezetet (pl. virtuális gépek).
2. Elsődleges Elemzés: Vizsgáljuk meg a program működését alapvető eszközökkel.
3. Mélységi Elemzés: Használjuk a disassembler-eket és debugger-eket a részletes kódvizsgálathoz.
4. Felfedezés: Keressük meg a kulcsfontosságú funkciókat és változókat.
5. Exploits: Próbáljuk megkerülni a védelmi mechanizmusokat és hozzáférni a védett funkciókhoz.
   
Fontos tippek
- Dokumentáció: Jegyezzük fel az elemzés során talált fontos információkat.
- Etikus Magatartás: Tartsuk be az etikai irányelveket és a jogszabályokat.
- Folyamatos Tanulás: Kövessük a legújabb kutatásokat és technikákat.

# Gyakorlati példa

Ajánlott disassembler: [IDA Free](https://hex-rays.com/ida-free/)

Lépések
1. Töltsük le és futtassuk a programot.
2. Elemezzük a program működését dissassembler segítségével.
3. Azonosítsuk a program gyenge pontjait és fejtsük vissza a szükséges jelszót.

## Forráskód
Kód írásakor, vagy ha a forráskód megvan, akkor értelmes kulcsoknak, értelmes függvényneveknek köszönhetően számomra olvasható ez a kód. Megvan a visszatérési érték, megvan a függvény neve, vannak változók, stb. Ezek mind olvashatóak most és ebből össze tudom rakni, hogy mit csinál ez a forráskód. Pl van egy buffer-em, ebbe a felhasználótól bekérek értéket, amit egy ismert jelszóval fogok összehasonlítani és ha ez sikerül, akkor kiíratom, hogy a jelszó helyes.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/d12eff8b-bfae-46eb-807b-ca08ed59c61c)


## xxd, strings parancsok

Forráskód hiányában, mikor csak a binárissal rendelkezünk, akkor már sokkal nehezebb feladatunk van, hiszen minden, ami itt van az felfoghatatlan hex számok tömkelege. És rengeteg számról van szó.
Strings-el megnézhetjük, hogy milyen olyan karaktersorozatok szerepelnek a kódban, amelyeknek a hossza nagyobb, mint 5, de a mi esetünkben ez nem segít, mert a buffer valószínűleg nem egy megadott szöveggel hasonlítja össze az inputot.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/d1acefa5-8ca3-4334-b807-1d6b44565ca4)

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/6a13bc79-2d3b-4204-a1da-6854915c93d4)

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/73e9e00b-ce95-481a-80f0-9cdc79e74c8e)


## objdump -d -Mintel

Szerencsére tanultuk, hogy léteznek disassemblerek. Linux használatakor van lehetőségünk object dumpot használni, ez generál nekünk egy valamivel jobban olvasható programkódot, de még így is eléggé nehéz a dolgunk, hiszen objdump-al még nem egyszerű dolgozni. Lemegyünk a text részhez, ami tartalmazza a binárisunk kódját (a processor ezeket a futtatható biteket fogja futtatni).

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/5d5ca106-54db-474d-9416-29163341f4dc)

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/3edf2fc3-367d-450c-8312-f7c95f559bd9)


## IDA Free
Szerencsére van jobb disassemblerrel lehetőségünk dolgozni. Importáljuk a bináris fájlunkat. Az ELF64 tökéletes lesz. 

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/1325015a-37d8-4643-9ed2-1a9e592f6d6b)

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/2ee1c91c-e7aa-4abb-b0c9-ab8baf229a5c)

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/37ea05e3-8916-443d-8812-97d9146384a4)

## IDA Free - start
Megnyitásra kerül az a start pontunk. Ez lesz az első instrukció, ami le fog futni. Átugorhatjuk ezeket. Látjuk, betöltésre kerül az effektív address-e a main-nek az rdi-b mielőtt a start main hívásra kerül. 
Tudjuk, hogy az rdi az első paraméter egy függvényhíváskor és az rsi a második.
Duplaklikk a main-re

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/68a20c95-849a-4cb5-81fe-25c0a8d0c435)
![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/281e906b-0a48-4c5b-be54-cc495322c060)

## IDA Free - main

Ez a forráskódnak megfelelő dolog. Itt látjuk, hogy hívásra kerülnek az egyes függvények, mint a puts, ahol kiírjuk a welcome to your first crackme-t és a printf, ahol kiírjuk a what is the password-ot.

Tudjuk, hogy az első argumentum az rdi, a második az rsi. 

Látjuk, hogy az első argumentumba bekerül az rax. Rax-ra középsőklikk és látjuk az összes rax használatot kiemelve.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/9087b47a-3d37-4f6a-a777-ca9a6d4ba073)

EAX azért kerül kijelölésre, mert az az alsó része az RAX-nek.
Felül látjuk, hogy load effective address hívódik az adott helyre. Mi lehet ez a hely?

Mivel effective address-t hív, ezért pointer kerül az adott helyre. Ez lesz a buffer nagy valószínűséggel.

Át is nevezhetjük a var_50-et buffer-nek.

Ahogy így haladunk egyre jobban rájövünk, hogy mit is csinál a program, szépen lassan a program, a malware, visszafejtjük a kódot szépen lassan.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/f5e75657-3a10-4fb2-bc11-0d900a3ebb1e)

Hívjuk a scanf function-t, aztán hívjuk a subfunctiont. 
Ezután megnézzük, hogy a return value 0-e.
Jump zero, (ha false) (rdx-be kerül a visszatérési érték 64 biten), akkor return, ha nem 0, akkor meghívódik a piros út.
Valószínűleg a subfunction a getPass function. Duplaklikk erre.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/7429aaca-9926-4384-8a82-3608e981a4a7)


## Ida Free - sub_11A9

Mit is csinálunk? Összeállítjuk a stack-et, majd a stack + var-8-ra rakjuk az első paramétert. Ez a var legyen itt buffer. Ez a buffer-re egy pointer.
Vesszük a buffer-t, berakjuk rax-be, majd összehasonlítjuk az első byte pointer-t az eax-be. 
A1 az első byte az RAX/EAX-ből, ezt összehasonlítjuk a 63h értékkel (IDA megmondja, hogy ez a c).
Ha nem zero, akkor folytatjuk, ha zero, akkor return.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/16a01fea-5cb9-4ab9-a0d3-52053e5b6982)

Ha ezt követjük, akkor láthatjuk, hogy mi is lesz a jelszó.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/8b2cfd55-20a0-41a8-a655-2f88dfe070ed)

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/d4c6d5fd-3552-431e-b992-b3250c3f8f3a)

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/0306b545-d73e-4dab-963b-07bfa02674da)

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/42255158-0be4-4359-9828-15ee05e8e483)

## Ellenőrzés

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/e5267ced-8ae3-4488-80b5-1ee490557420)

Egyébként objdump-al is meg tudtuk volna nézni, de ez sokkal biztosabb, főleg egy nehezebb feladatnál.

# Források

- [Low level learning – Baby’s First CrackMe – 2024-06-04](https://github.com/lowlevellearning/babys-first-crackme
)
- [Wikipedia – Cybersecurity – 2024-06-04](https://en.wikipedia.org/wiki/Computer_security )
- [Red Hat – What is IT security? – 2024-06-04](https://www.redhat.com/en/topics/security )
