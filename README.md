# Brandos darbo aprašo šablonas: produkto kūrimas

**2026–2027 mokslo metams. Patikrinta 2026-11-01.**

Šis paketas atnaujina pateiktą 2023 m. informatikos šabloną. Jis skirtas mokiniui,
kuriančiam konkretų produktą ir rašančiam jo aprašą. Tai mokytojo pritaikytas
LaTeX šablonas, ne NŠA patvirtinta forma ir ne atlikto darbo pavyzdys.
Pavyzdiniai klausimai, lentelės ir priedų formos turi būti pakeisti tikru mokinio darbu.

## Pradžia

1. Išskleiskite visą ZIP arba importuokite jį į Overleaf. Pagrindinis dokumentas – `main.tex`.
2. Rinkitės **XeLaTeX**, bibliografijai – **Biber**. Failų koduotė – UTF-8.
3. Faile `nustatymai.tex` įrašykite mokinio, vadovo ir darbo duomenis. Mokykla ir miestas
   palikti iš senojo šablono; dalyko pavadinimas pakeistas į „Informatika“.
   Vadovo vardas paliktas pildomas. Pagal nutylėjimą darbas pateikiamas 2027 m.
4. Pildykite skyrius, savo iliustracijas dėkite į `media/`, šaltinius – į `sources.bib`.
5. Prieš pateikdami įjunkite `\Gairesfalse`, pakeiskite visus `\pildyti{...}` laukus
   savo tekstu, pašalinkite nereikalingus pavyzdžius ir iš naujo sukurkite PDF.

Gairių išjungimas **nepašalina neužpildytų laukų**, pavyzdinių lentelių ar schemos
rėmelio. Tai sąmoningai palikta matoma, kad neužbaigtos vietos neliktų nepastebėtos.
Pradiniame PDF matote instrukcijas, o ne 2 000–3 000 žodžių atlikto darbo aprašą.

### Šriftai ir kompiliavimas

Naudojamas Times New Roman, jei jis įdiegtas sistemoje. Kitoje aplinkoje į `fonts/`
galima įkelti keturis teisėtai turimus šrifto failus: `times.ttf`, `timesbd.ttf`,
`timesi.ttf`, `timesbi.ttf`. Šriftai su šablonu neplatinami.

Jei Times New Roman nepasiekiamas, dokumentas sukompiliuojamas su TeX Gyre Termes,
o žurnale atsiranda įspėjimas. Tai leidžia tęsti redagavimą, tačiau prieš galutinį
pateikimą reikia naudoti Times New Roman pagal NŠA maketo gaires.

Vietinėje TeX Live ar MiKTeX aplinkoje:

```text
xelatex main.tex
biber main
xelatex main.tex
xelatex main.tex
```

Overleaf turi paleisti bibliografijos tvarkymą automatiškai. Jei matote klaustukus
vietoje nuorodų, patikrinkite citavimo raktus ir perkompiliuokite iš naujo.
Paketas naudoja `biblatex` ir Biber; nereikia senojo `lithuanian-apa.lbx` ar
`csquotes.cfg`. Nedidelis `lithuanian.lbx` išverčia dažniausius bibliografijos žymenis.
Bibliografija yra numerinė, rikiuojama pagal autorių, metus, pavadinimą, taikant
lietuvišką lokalę. Rečiau naudojamų šaltinių tipų aprašus peržiūrėkite atskirai.

Trumpam, sprendimą paaiškinančiam kodo fragmentui galima naudoti `listings`:

```latex
\begin{lstlisting}[language=Python,caption={Įvesties patikra},label={lst:patikra}]
def tinkamas_kiekis(kiekis):
    return kiekis >= 0
\end{lstlisting}
```

Tai sintaksės pavyzdys, ne siūlomas darbo turinys. Didelį kodą pateikite produkto
failuose, o tekste aptarkite tik reikšmingus fragmentus. Bibliografijos nuorodos:
`\autocite{raktas}`, konkrečios vietos nuoroda – `\autocite[12]{raktas}`.
Lentelių ir paveikslų nuorodoms naudokite `\label{...}` ir `\ref{...}`.

## Kas oficialu, o kas siūloma šiame šablone

**Vertinimo pagrindas:** NŠA instrukcijos 1 priedas taikomas tyrimui ir kuriamam
produktui. Produkto kūrimas nėra tas pats vertinimo variantas kaip meninis
kūrybinis darbas. Produktui rengiamas ir aprašas; vien produkto failų neužtenka. [1, 2]

| Dalykas | Patikrintas pagrindas |
|---|---|
| Aprašo apimtis | 2 000–3 000 žodžių, be priedų; instrukcijos 1 priedo rezultato vertinimas. |
| Proceso vertinimas | Iki 18 taškų, 40 %. |
| Rezultato vertinimas | Iki 18 taškų, 40 %. |
| Pristatymo vertinimas | Iki 9 taškų, 20 %. |
| Bendra suma | Iki 45 taškų. |
| Temos kalbos | Mokyklos tvirtinama tema nurodoma lietuviškai ir angliškai; pakeitimo 2 punktas. |

Tai nėra papildoma 2026–2027 m. vertinimo sistema. Taikytas NŠA puslapyje
patikros dieną skelbiamas 2024-09-26 dokumentas Nr. VK-853 kartu su
2025-03-10 pakeitimu Nr. VK-220. Pakeitimas nėra visos instrukcijos suvestinis tekstas.
Mokytojas prieš galutinį naudojimą turėtų patikrinti, ar NŠA nepaskelbė naujesnės redakcijos.

**NŠA metodinė medžiaga:** maketas, bendroji aprašo sandara, neprivalomos dalys,
literatūros sąrašo tvarka ir refleksija perimti iš šiuo metu NŠA puslapyje pateikiamų
metodinių lapų. Tai seniau rengta metodinė medžiaga; vien 2025 m. įkėlimo katalogas
nereiškia, kad dokumentas tąmet buvo iš naujo patvirtintas. [3–7]

**Šablono metodiniai pasirinkimai:** keturi numeruoti pagrindiniai skyriai,
R1/T1 žymenys, analogų lentelė, žurnalo forma, testų forma ir produkto perdavimo
instrukcija yra siūlomos darbo priemonės. NŠA nereikalauja būtent tokių pavadinimų,
lentelių ar eilučių skaičiaus. Pritaikykite juos konkrečiam produktui.

DI naudojimo atskleidimo laukai yra skaidrumo priemonė, o ne teiginys, kad NŠA
nustatė būtent tokią DI deklaracijos formą. Konkrečias leistino naudojimo ribas
suderinkite pagal mokyklos ir vadovo taikomą tvarką.

## Pildymo sandara

| Failas | Paskirtis |
|---|---|
| `nustatymai.tex` | Titulinio duomenys ir pasirenkamų dalių jungikliai. |
| `2_intro.tex` | Problema, paskirtis, tikslas, uždaviniai, metodai, ribos, etika. |
| `3_analize.tex` | Šaltinių ir analogų analizė, pagrindžianti produkto poreikį. |
| `4_projektavimas.tex` | Reikalavimai, patikrinami kriterijai, sandara, sprendimų pagrindimas. |
| `5_kurimas.tex` | Įgyvendinimas, prototipai, pakeitimai ir mokinio indėlis. |
| `6_vertinimas.tex` | Patikros metodika, faktiniai rezultatai, analizė ir ribotumai. |
| `7_isvados.tex` | Atsakymai į įvado uždavinius. |
| `8_isivertinimas.tex` | Proceso ir mokymosi refleksija; paliekama pagrindiniame tekste. |
| `10_saltiniai.tex`, `sources.bib` | Naudotų šaltinių sąrašas ir bibliografiniai duomenys. |
| `11_priedai.tex` | Planas, proceso įrodymai, patikros duomenys, produkto naudojimas. |

Anotacija, terminų žodynas ir rekomendacijos iš pradžių išjungti.
Jie įjungiami atitinkamai `\Anotacijatrue`, `\Terminaitrue` ir
`\Rekomendacijostrue`. Anotacija, jei paliekama, pateikiama prieš turinį.
Jei yra konsultantas, įjunkite `\Konsultantastrue` ir įrašykite jo duomenis.

### Apimties planavimas

Pirmiausia planuokite argumentų ir įrodymų apimtį, ne puslapius.
Galimas **neprivalomas** maždaug 2 400 žodžių teksto biudžetas:

| Dalis | Orientyras |
|---|---:|
| Įvadas | 250 |
| Problemos ir šaltinių analizė | 400 |
| Projektavimas | 400 |
| Kūrimo eiga | 500 |
| Patikra ir rezultatų analizė | 500 |
| Išvados | 150 |
| Įsivertinimas | 200 |

Jei įtraukiate anotaciją ar rekomendacijas, perskirstykite biudžetą.
Oficiali formuluotė yra „aprašo tekstas (be priedų)“; šablonas nenustato
papildomų nepatvirtintų išimčių. Skaičiuokite jau užpildytą tekstą be šablono
gairių. Dėl lentelių, bibliografijos ir kitų parateksto elementų skaičiavimo
vadovaukitės mokykloje suderintu būdu. Prireikus pasilikite atsargą iki viršutinės ribos.
Word count / TeXcount yra pagalbinis skaičiavimas, ne automatinis atitikties patvirtinimas.

## Procesas ir pristatymas

Aprašą rengti pradėkite kartu su produktu. Pildykite planą ir kaupkite tarpinius
įrodymus viso darbo metu. Kuriant grupėje turi būti aiškus kiekvieno mokinio indėlis.

Instrukcijos 20–21 punktuose numatyta aprašo autentiškumo patikra: įkėlimas iki
vasario 8 d., išvadų pateikimas vadovams iki vasario 20 d., koreguoto aprašo
pakartotinis įkėlimas iki kovo 3 d. Baigiant darbą 2026–2027 m. m. tai yra
2027 m. datos, jei tvarka nebus pakeista. Mokinio pateikimo vadovui terminas
turi būti suderintas anksčiau; datos paliktos pildomos 1 priede. Tai nėra
leidimas pradėti naują darbą praleidus oficialų pasirinkimo terminą. [1]

Pristatymo ir vertinimo datą nustato vertinimo centras. Šablone neįrašyta
nepatvirtinta universali pristatymo trukmė. Su vadovu ar centru suderinkite
trukmę ir pasiruoškite parodyti:

- problemą ir produkto naudotoją;
- tikslą, uždavinius ir esminius projektavimo pasirinkimus;
- veikiantį produktą ar jo pagrindinę funkciją;
- tikrus bandymų rezultatus, įskaitant ribotumus;
- savo indėlį, išvadas ir įsivertinimą.

Tai siūloma pristatymo eiga, ne nauja vertinimo lentelė. Atskirą skaidrių failą
mokinys rengia pagal savo darbą. Pasiruoškite atsarginę demonstravimo medžiagą.

## Paskutinė peržiūra

- Neliko pilkų gairių, laužtinių pildymo laukų, pavyzdinės schemos ir nenaudotų priedų.
- Tema, tikslas, reikalavimai, bandymai ir išvados susiję tarpusavyje.
- Faktiniai rezultatai atskirti nuo planų; nesėkmių duomenys neišgalvoti ir nenutylėti.
- Aišku, ką mokinys sukūrė pats ir ką perėmė; nurodyti šaltiniai ir licencijos.
- Patikrinta žodžių apimtis, kalba, šriftas, turinys, paveikslų ir lentelių nuorodos.
- Produktas pateiktas kartu su aprašu ir naudojimo instrukcija; prieiga veikia.
- Asmens duomenys, prisijungimo slaptažodžiai ir API raktai nepateko į pateikiamus failus.
- Išsaugoti proceso įrodymai ir pasirengta pristatymui.

## Šaltiniai ir patikros ribos

1. [NŠA, Brandos darbo vykdymo ir vertinimo instrukcija, VK-853, 2024-09-26](https://www.nsa.smsm.lt/wp-content/uploads/2025/09/BD_VYKDYMO_VERTINIMO_INSTRUKCIJA.pdf).
   Naudoti 13–14, 20–21, 25, 27–32 punktai ir 1 priedas.
2. [NŠA, instrukcijos pakeitimas, VK-220, 2025-03-10](https://www.nsa.smsm.lt/wp-content/uploads/2025/09/ISAK_BD_vykdymo_ir_vertinimo_instrukcijos_pakeitimai_VK-220_2025-03-10.pdf).
   Pakeista ir meninio kūrybinio darbo sistema; jos 50 taškų modelis šiame produkto šablone netaikomas.
3. [NŠA, Reikalavimai aprašo maketui](https://www.nsa.smsm.lt/wp-content/uploads/2025/09/7729_Reikalavimai_apraso_maketui.pdf).
4. [NŠA, Aprašo struktūra](https://www.nsa.smsm.lt/wp-content/uploads/2025/09/7711_Apraso_struktura.pdf).
5. [NŠA, Brandos darbo veiklos pobūdis](https://www.nsa.smsm.lt/wp-content/uploads/2025/09/7699_BD_veiklos_pobudis.pdf).
6. [NŠA, Literatūros šaltinių sąrašas](https://www.nsa.smsm.lt/wp-content/uploads/2025/09/7725_Literaturos_saltiniu_sarasas.pdf).
7. [NŠA, Įsivertinimas](https://www.nsa.smsm.lt/wp-content/uploads/2025/09/7749_Isivertinimas.pdf).
8. [ŠMSM, įsakymo V-240 oficiali kortelė](https://e-seimas.lrs.lt/portal/legalAct/lt/TAD/d3e76c10d67911ee9269b566387cfecb).
   Paieškos rodyklėje matoma suvestinė redakcija nuo 2025-01-16; tiesioginė
   viso registro teksto prieiga patikros metu buvo ribota. Konkrečios šio
   šablono nuostatos tikrintos pagal prieinamus NŠA dokumentus [1–7].
9. [2025–2026 ir 2026–2027 mokslo metų bendrieji ugdymo planai, 105 punktas](https://e-seimas.lrs.lt/rs/actualedition/d286b943367a11f0a19dcea0bcc863ad/yKevtSxSei/format/ISO_PDF/).
   Oficialaus šaltinio paieškos ištraukoje nurodyta galimybė pasirinkti brandos darbą.

Aktualių nuorodų pradžia: [NŠA Brandos darbo puslapis](https://www.nsa.smsm.lt/ugdymo-departamentas/ugdymas-ir-prevencija/brandos-darbas/).

Pateiktas [edtalk straipsnis](https://edtalk.lt/blog/brandos-darbas-2026) perskaitytas,
bet jo teiginiai nelaikyti oficialiais reikalavimais. Visuotinis BD privalomumas
nesutampa su [9]; 60/40 vertinimas ir puslapių apimtis nepakeičia [1] nustatytų
produkto vertinimo dalių ir žodžių apimties. Straipsnio teiginiai apie stojimo
balus, fiksuotą šaltinių skaičių ar gynimo trukmę į šabloną neperkelti.
