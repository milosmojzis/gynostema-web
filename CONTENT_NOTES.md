# Obsah a podklady pracovní verze

Web má statické trasy `/`, `/sluzby/`, `/personal/` a `/kontakt/`. `npm run build` generuje `dist/` bez databáze a serverové aplikace. Vývojový server se podle projektových instrukcí spouští `npx astro dev --background`, kontroluje `npx astro dev status` a zastavuje `npx astro dev stop`.

V `src/content/data/` jsou samostatné JSON soubory: `obsah.json` (úvod, online služby, galerie), `aktuality.json`, `hodiny.json`, `ordinace.json` (kontakt a cesta), `persona.json`, `sluzby.json` (služby, pojišťovny, úhrady) a `cenik.json`. Všechny mají formuláře v `.pages.yml`. Pages CMS používá Git repozitář; k provozu veřejného webu se nespouští. Nové obrázky může editor vložit do `public/images/`. Rozpis v `hodiny.json` odkazuje na stálá ID v `persona.json`, takže jména se upravují pouze u personálu; při přidání lékaře je nutné použít jeho ID v rozpisu.

Neověřené informace mají v datech `vyzadujeOvereni` a `poznamkaKOvereni`. Rozpor mezi archivními rozpisy je popsán v `hodiny.json`; veřejné stránky nyní ukazují verzi z úvodu 8. 6. 2026. Archivní dovolená je uložena v `aktuality.json` s `zobrazit: false`, protože její platnost není potvrzena.

## Obrázky a přílohy

Z Wayback Machine byly obnoveny `public/images/logo.jpg`, `uvod.jpg`, `smartmedix.jpg` a `ordinace-{2516,2527,2491,2512}.jpg`. Každý stažený soubor byl ověřen jako obrazová odpověď.

Nepodařilo se obnovit `images/foto/ambulance-1.jpg` a portréty `images/foto/wohlgemuth2.jpg`, `cihlar.JPG`, `konickova2.JPG`. Odkazy ve snímcích existují, ale obrazové požadavky vrátily 404 a hledání v CDX žádný záznam neukázalo. Proto mají lidé v `persona.json` prázdné `foto`. Na čtyřech zkoumaných stránkách nebyl nalezen odkaz na dokument ke stažení; úplnost archivovaných příloh nelze potvrdit.

Zdroje: [O nás 8. 6. 2026](https://web.archive.org/web/20260608115219/https://gynostema.cz/), [Služby 13. 3. 2026](https://web.archive.org/web/20260313234247/https://gynostema.cz/index.php/sluzby), [Personál 10. 9. 2024](https://web.archive.org/web/20240910050319/https://gynostema.cz/index.php/personal), [Kontakt 17. 6. 2026](https://web.archive.org/web/20260617062705/https://www.gynostema.cz/index.php/kontakt).
