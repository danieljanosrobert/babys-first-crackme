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

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/50882b27-e5ec-43c5-b9a7-538e1121cffe)
![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/035b80e7-cb88-4e6f-877c-40e8737ebd7a)
![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/966b9766-ee29-48aa-b2f0-f4c86a867fb8)

## IDA Free - start
Megnyitásra kerül az a start pontunk. Ez lesz az első instrukció, ami le fog futni. Átugorhatjuk ezeket. Látjuk, betöltésre kerül az effektív address-e a main-nek az rdi-b mielőtt a start main hívásra kerül. 
Tudjuk, hogy az rdi az első paraméter egy függvényhíváskor és az rsi a második.
Duplaklikk a main-re

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/c99bd3a3-59a9-49cb-82d1-b2802ee238d0)
![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/6e45b262-f11f-402d-927c-8af9fdcaa17f)

## IDA Free - main

Ez a forráskódnak megfelelő dolog. Itt látjuk, hogy hívásra kerülnek az egyes függvények, mint a puts, ahol kiírjuk a welcome to your first crackme-t és a printf, ahol kiírjuk a what is the password-ot.

Tudjuk, hogy az első argumentum az rdi, a második az rsi. 

Látjuk, hogy az első argumentumba bekerül az rax. Rax-ra középsőklikk és látjuk az összes rax használatot kiemelve.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/8f3809c5-afc8-43c9-964e-c9bf57655ed5)

EAX azért kerül kijelölésre, mert az az alsó része az RAX-nek.
Felül látjuk, hogy load effective address hívódik az adott helyre. Mi lehet ez a hely?

Mivel effective address-t hív, ezért pointer kerül az adott helyre. Ez lesz a buffer nagy valószínűséggel.

Át is nevezhetjük a var_50-et buffer-nek.

Ahogy így haladunk egyre jobban rájövünk, hogy mit is csinál a program, szépen lassan a program, a malware, visszafejtjük a kódot szépen lassan.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/24e05b15-11b0-49ef-baf5-dc74af722ea0)

Hívjuk a scanf function-t, aztán hívjuk a subfunctiont. 
Ezután megnézzük, hogy a return value 0-e.
Jump zero, (ha false) (rdx-be kerül a visszatérési érték 64 biten), akkor return, ha nem 0, akkor meghívódik a piros út.
Valószínűleg a subfunction a getPass function. Duplaklikk erre.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/c73a6bc7-daf2-419d-bc7f-a24e8e100d51)

## Ida Free - sub_11A9

Mit is csinálunk? Összeállítjuk a stack-et, majd a stack + var-8-ra rakjuk az első paramétert. Ez a var legyen itt buffer. Ez a buffer-re egy pointer.
Vesszük a buffer-t, berakjuk rax-be, majd összehasonlítjuk az első byte pointer-t az eax-be. 
A1 az első byte az RAX/EAX-ből, ezt összehasonlítjuk a 63h értékkel (IDA megmondja, hogy ez a c).
Ha nem zero, akkor folytatjuk, ha zero, akkor return.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/2a844c18-ebbc-40b3-b73d-b073e9aced74)

Ha ezt követjük, akkor láthatjuk, hogy mi is lesz a jelszó.

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/f6f57f7c-d0fc-4cb8-9249-617bc46dde9d)

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/11804892-ffbd-408b-a6f2-0fe5448d5ba3)

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/59a68950-0aaf-4ffe-bce9-017acd208f44)

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/a4ff648a-a1e0-4edb-9300-148ee70beb94)

## Ellenőrzés

![image](https://github.com/danieljanosrobert/babys-first-crackme/assets/45608233/ea136940-9a2c-4511-9d75-ee5321375d57)

Egyébként objdump-al is meg tudtuk volna nézni, de ez sokkal biztosabb, főleg egy nehezebb feladatnál.

# Források

- [Low level learning – Baby’s First CrackMe – 2024-06-04](https://github.com/lowlevellearning/babys-first-crackme
)
- [Wikipedia – Cybersecurity – 2024-06-04](https://en.wikipedia.org/wiki/Computer_security )
- [Red Hat – What is IT security? – 2024-06-04](https://www.redhat.com/en/topics/security )
