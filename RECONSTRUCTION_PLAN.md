# Podklady pro rekonstrukci Gynostema

Stav průzkumu: 13. 9. 2026. Základ je [snímek úvodní stránky z 8. 6. 2026](https://web.archive.org/web/20260608115219/https://gynostema.cz/). Ostatní podstránky Wayback při požadavku na stejné datum přesměroval na nejbližší dostupné snímky; jejich datum je uvedeno níže. Jde o inventuru, nikoli o schválený obsah k publikaci.

## Stránky a navigace

| Původní stránka | Obsah a viditelné sekce | Dostupný snímek |
| --- | --- | --- |
| [O nás](/) | Představení ordinace, rozsah péče, ON-LINE služby a odkaz SmartMEDIX.net, pravidla objednávek, oznámení o dovolené, ordinační hodiny, fotografie ordinace | [8. 6. 2026](https://web.archive.org/web/20260608115219/https://gynostema.cz/) |
| [Služby](https://gynostema.cz/index.php/sluzby) | Seznam služeb, smluvní pojišťovny, „Co hradí pojišťovna?“, „Co nehradí pojišťovna?“, „Ceník výkonů nehrazených zdravotní pojišťovnou“, „Potvrzení do práce, školy apod.“ | [13. 3. 2026](https://web.archive.org/web/20260313234247/https://gynostema.cz/index.php/sluzby) |
| [Personál](https://gynostema.cz/index.php/personal) | Medailony MUDr. Radka Wohlgemutha, MUDr. Milana Cihláře a Michaely Koníčkové; fotografie a profesní chronologie | [10. 9. 2024](https://web.archive.org/web/20240910050319/https://gynostema.cz/index.php/personal) |
| [Kontakt](https://gynostema.cz/index.php/kontakt) | Kontaktní údaje, adresa a poloha ambulance, cesta autem a veřejnou dopravou, ordinační hodiny | [17. 6. 2026](https://web.archive.org/web/20260617062705/https://www.gynostema.cz/index.php/kontakt) |

Hlavní navigace: **O nás → Služby → Personál → Kontakt**. Opakované postranní části: **Aktuality** a **Personál** (seznam lékařů a sestry). V HTML jsou také odkazy na přihlášení a obnovu účtu Joomla; nejsou součástí veřejné obsahové navigace. Externí odkazy: SmartMEDIX.net a Facebook.

## Redigovatelné oblasti a návrh pro Astro / Pages CMS

- Samostatné obsahové soubory `src/content/pages/{o-nas,sluzby,personal,kontakt}.md` s titulkem, textem, případně seznamem fotografií; jednoduché stránky generovat přes Astro routy.
- `src/content/aktuality/*.md` pro časově omezená oznámení s datem a příznakem zveřejnění; stará oznámení nepřenášet automaticky mezi aktuální sdělení.
- `src/content/data/ordinace.yaml` pro telefon, e-mail, adresu, ordinační hodiny, personál, pojišťovny a odkazy; `src/content/data/cenik.yaml` pro jednotlivé položky a ceny. Tyto údaje mohou být v Pages CMS samostatná editovatelná pole.
- `public/images/` a `public/documents/` pro ověřené soubory. Navigaci a opakované části zobrazovat ze sdílených dat, aby se údaje mezi stránkami nerozcházely. Struktura je návrh pro další krok, nyní se nezavádí.

## Zjištěné obrázky a soubory

V archivním HTML jsou odkazy na `images/logo/Logo.png.jpg`, `images/foto/ilustracni/girl-18918_640.jpg`, `images/foto/ambulance-1.jpg`, portréty `images/foto/wohlgemuth2.jpg`, `cihlar.JPG`, `konickova2.JPG`, obrázek odkazu `images/smnet.jpg` a galerii `images/widgetkit/DSCF2516.JPG`, `DSCF2527.JPG`, `DSCF2491.JPG`, `DSCF2512.JPG`. Logo, úvodní ilustrace a `DSCF2516.JPG` při samostatném ověření v archivu vracely obrazový soubor; ostatní zatím mají potvrzený pouze odkaz v HTML. Na prohlédnutých čtyřech obsahových stránkách nebyl nalezen odkaz na PDF, DOC, XLS ani ZIP ke stažení; úplnost příloh nelze bez úplného indexu archivu potvrdit.

## Chybějící obsah a kontrola před zveřejněním

- Přímý požadavek na `/index.php/aktuality` vrací 404. Starší jednotlivý článek [„dovolená“ z 12. 4. 2022](https://www.gynostema.cz/index.php/aktuality/29-dovolena-11) je indexován, ale soupis všech aktualit ani jejich červnový stav nebyl ověřen.
- Pro **Personál** nebyl při požadavku na červen 2026 nalezen blízký snímek; archiv vydal rok 2024. Na novějších stránkách je v postranním seznamu navíc MUDr. Tereza Wohlgemuthová a MUDr. Barbora Möhwaldová, bez jejich medailonů. Zápis příjmení Barbory se mezi stránkami liší (`Möhwaldová` / `Mohlwaldová`).
- Úvodní stránka obsahuje oznámení „Dovolena 27.12.-2.1.2026“, jednorázový poplatek 300 Kč za ON-LINE služby a penále 300 Kč za nezrušenou objednávku. Potvrdit datum, pravidla, funkčnost SmartMEDIX a aktuální znění před publikací.
- Ordinační hodiny se mezi úvodní stránkou a kontaktem liší (např. pondělní odpoledne 12.30–17.00 vs. 13.00–17.00). Potvrdit rozpis, telefon, e-mail, adresu a aktuální personál přímo u ordinace. E-mail na kontaktu je v archivovaném textu skrytý za JavaScriptem; v HTML úvodu je odkaz `info@gynostema.cz`.
- Ceník, seznam pojišťoven, tvrzení o úhradách a veškerá medicínská sdělení vyžadují odborné potvrzení. U položky Mirena / Levosert je archivní tabulka sloučená do jedné řádky se dvěma cenami, proto při převodu nelze bezpečně přiřadit cenu bez ověření.
