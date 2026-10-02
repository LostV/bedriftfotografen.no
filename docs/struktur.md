# bedriftfotografen.no – struktur og konsept (før valg av rammeverk)

## Kontekst
Det som ligger i mappen nå (`index.html`, `styles.css`, `script.js`) er en generisk mal med «frostet glass»-kort, oppdiktede tall og sitater, feil kontaktinfo (en adresse i Oslo) og bilder som mangler. Den skal ikke bygges videre. Målet er en porteføljeside med bestilling for Bedriftsfotografen, en underenhet av Næring i Nord (nin.no). Siden skal:
- skille seg tydelig fra kjedelige oppsett med bokser og info, men fortsatt være lett å finne fram i
- løse at Daniel Waleniussen reiser rundt i hele landet, slik at et besøk ikke kan skje «om en uke»
- fungere godt på alle skjermstørrelser
- kunne oppdateres av dere selv uten kode

Dette er bestemt: bestilling skjer ved at kunden «blir med på ruten», ruten vises offentlig på regionnivå, siden viser ingen priser (bare tilbud), og dere redigerer innholdet selv.

---

## 1. Det bærende konseptet: «Ruten»
Det som skiller dere fra konkurrentene er ikke en fotoskole eller et studio. Det er at **fotografen kommer til deg, uansett hvor i landet du er**. Det gjør vi til identiteten til hele siden, i stedet for å gjemme det i en FAQ.

- **Ruten** er et levende kart over Norge med Daniels kommende turer, for eksempel «Salten – uke 44–45» og «Tromsø – november». Ingen kundenavn vises.
- Det løser bestillingsproblemet og blir samtidig et salgsargument: «Han er i nærheten om tre uker – bli med».
- Kunder i regioner uten planlagt tur kan **melde interesse**. Når mange nok har meldt seg, setter dere opp en tur. Dette blir en kø dere kan lese ut av for å planlegge turer.

## 2. Visuell retning (bort fra bokser, men fortsatt oversiktlig)
Den visuelle stilen kaller jeg **«feltlogg» eller «kontaktark»**: fotografens eget arbeidsmateriale brukes som designspråk.
- Bilder i full bredde fra kant til kant, ikke i kort. Teksten ligger *på* eller *ved siden av* bildene.
- Typografien låner fra kamera og kontaktark: bildenummer (`#014`), sted og koordinater, beskjæringsmerker, korte bildetekster i EXIF-stil (`Mo i Rana · 35mm · Kjøkken`).
- Det er bevegelse i stedet for statiske rutenett: horisontale «filmruller» per tjeneste, bilder som skarpstilles når du scroller, og kartlinjen som tegnes mens du scroller.
- **Oversikten sikres med tre faste ankere:** en enkel toppmeny med maks 4 punkter, en «Bestill besøk»-knapp som alltid er synlig, og en tydelig indeks over tjenestene. Det kreative ligger i innholdet. Navigasjonen er bevisst helt vanlig.
- Video er en del av alt dere leverer, så videoklipp spilles av lydløst i loop direkte i filmrullene.

## 3. Sidestruktur (sitemap)
```
/                       Forside
/arbeid                 Portefølje (alle prosjekter, kan filtreres)
/arbeid/[kunde]         Ett prosjekt som case
/tjenester              Indeks over tjenestene
/tjenester/[tjeneste]   Én tjeneste (f.eks. ansattportretter)
/ruten                  Kartet over kommende turer + bestilling
/bestill                Bestillingsflyt (kan også åpnes fra kartet)
/om                     Daniel, Næring i Nord, slik jobber vi
```
Toppmeny: **Arbeid · Tjenester · Ruten · Om**, pluss knappen **Bestill besøk**.

### Forsiden, fra topp til bunn
1. **Åpningsbilde:** et bilde eller videoklipp i full skjerm som byttes ut ofte, med en kort påstand («Vi kommer til dere. Hele landet.») og to knapper: *Se arbeid* og *Når er vi i nærheten?*
2. **Rutestripe:** en smal stripe med neste 2–3 turer (region + periode) og lenke til `/ruten`. Dette er den viktigste salgsflaten.
3. **Tjenester som kapitler:** hver tjeneste er en egen seksjon med filmrull, ikke et kort.
4. **Utvalgte case:** 2–3 kunder vist stort, med en kort historie om hva de trengte og hva de fikk.
5. **Slik foregår det:** 4 steg vist som en tidslinje: Meld behov → Vi legger dere på ruten → Fotodag → Levering.
6. **Avslutning:** Næring i Nord, kontaktinfo og knappen *Bestill besøk*.

## 4. Tjenester (strukturert for kunden)
Lista deres er grei, men blander *hva* som fotograferes med *hvor*. For kunden er det lettere å gruppere etter **hva de skal bruke bildene til**. Alt leveres som både foto og video.

| Gruppe | Innhold |
|---|---|
| **Folk** | Ansattportretter, team, ledelse, folk i arbeid |
| **Arbeid & tjenester** | Tjeneste/arbeid i praksis, prosjekter, anlegg/byggeplass |
| **Steder** | Kontor, butikk, butikkfront, interiør, anlegg |
| **Produkt & mat** | Produktbilder, mat, detaljbilder |

Mulige tillegg dere kan vurdere ut fra hva kunder etterspør:
- **Rekrutteringspakke:** portretter + arbeidsmiljø + kort video
- **Bildebank-abonnement:** fast besøk 1–2 ganger i året, passer godt med ruten
- **Arrangement/åpning**
- **Dronebilder** av anlegg og eiendom (krever sertifisering)
- **Innhold til sosiale medier** (korte vertikale videoer)

Tjenestene er data i CMS-et, så lista kan utvides uten ny kode.

## 5. Bestillingsflyten «Bli med på ruten»
Skjemaet går over flere steg, ett spørsmål om gangen, og er laget for mobil først.
1. **Hvor er dere?** Kunden skriver postnummer eller sted, eller velger på kartet. Siden matcher dette mot regionene og viser:
   - *Planlagt tur:* «Daniel er i Salten uke 44–45» → kunden velger det tidsrommet som passer.
   - *Ingen tur planlagt:* «Meld interesse, så gir vi beskjed når vi setter opp en tur hit.» Kunden kan også velge «Haster – vi ønsker egen tur», og dere sender tilbud med reisekostnad.
2. **Hva trenger dere?** Kunden krysser av for tjenestegrupper (flere valg) og kan legge til et fritekstfelt.
3. **Kontaktinfo:** firma, organisasjonsnummer (valgfritt), navn, e-post og telefon.
4. **Bekreftelse:** «Vi tar kontakt innen 2 virkedager med forslag til dag og et tilbud.»

**Internt hos dere:** forespørselen lagres i CMS-et med status (ny / tilbud sendt / bekreftet / fullført), og det går ut en e-post til kontakt@nin.no. Ingen betaling eller automatisk booking. Dere bekrefter alltid selv.

## 6. Innhold dere styrer selv (CMS-modell)
- **Tur:** region, fra/til-periode, status (planlagt/full), synlig ja/nei
- **Region:** navn, postnummerområder, punkt på kartet
- **Prosjekt/case:** kunde, sted, tjenester, bilder/video, kort tekst, utvalgt ja/nei
- **Tjeneste:** navn, gruppe, tekst, tilhørende prosjekter
- **Forespørsel:** feltene fra bestillingsflyten, status og interne notater
- **Innstillinger:** kontaktinfo (kontakt@nin.no, +47 76 94 00 00, Ankenesveien 179) og bilde til forsiden

## 7. Krav som påvirker valget av rammeverk senere
- Bildetung side som må laste raskt: automatisk optimalisering av bilder (AVIF/WebP, responsive størrelser) og strømming av video.
- CMS med visuell redigering for folk uten teknisk bakgrunn, inkludert innlegging av turer og arbeid med forespørsler.
- Kart over Norge, gjerne en egen stilisert SVG i stedet for Google Maps, slik at det passer med «feltlogg»-stilen og laster raskt.
- God SEO per tjeneste og region (f.eks. «bedriftsfotograf Bodø»). Turene kan gi egne regionsider.
- Universell utforming (WCAG 2.1 AA). Animasjonene må respektere `prefers-reduced-motion`.

*(Valg av rammeverk og CMS, for eksempel Astro/Next + Sanity, tar vi som eget steg når strukturen er godkjent.)*

## 8. Neste steg etter godkjenning
1. Lage en klikkbar skisse (wireframe) av forsiden, `/ruten` og bestillingsflyten for å teste konseptet før design. Den kan publiseres som en side dere kan dele internt.
2. Samle ekte materiale: 20–40 av de beste bildene og videoene, fordelt på tjenestegruppene, pluss 2–3 kunder som godtar å bli vist som case.
3. Bestemme rammeverk og CMS ut fra kravene i punkt 7.
4. Mappen gjenbrukes: de gamle filene (`index.html`, `styles.css`, `script.js`, `.DS_Store`) slettes før det nye prosjektet settes opp (bekreftet av deg).

## Verifisering av strukturen
- Gå gjennom 3 typiske kunder på papir eller i skissen: (a) en butikk i Narvik når det er planlagt tur dit, (b) et anlegg i Finnmark uten planlagt tur, (c) en markedssjef som bare vil se arbeid. Hver av dem skal finne det de leter etter med maks 2 klikk fra forsiden.
- Test skissen på mobil først (375 px), deretter på nettbrett og desktop.
- Vis skissen til Daniel og 1–2 eksisterende kunder før design og koding begynner.
