# BYGGEPLAN.md

Dette er byggeplanen for struktur på OFA-nettsiden. Den er fasiten: endringer i sidestruktur, rekkefølge eller seksjonstyper gjøres her først, deretter i koden.

## Sider (fasit for struktur)

### 1. index.html
1. Hero – Sidetopp – forside (type 1)
2. "Våre tjenester" – Lenkekort (type 5) + CTA-knapp

### 2. om-ofa.html
1. H1 + bildeplassholder (lokalene, bilde kommer senere) + Snarveier (type 7, 4 knapper) – Sidetopp – underside (type 2)
2. Brødtekst om OFA (historikk, uten egen overskrift) – Tekstseksjon (type 10)
3. "Hvem møter du?" – bilde av Anne Lene og Tonje (flyttet fra sidetoppen) + to profiltekster (Tonje, Anne Lene) + lenke til kontaktsiden
4. "Hva gjør vi?" – Tekstkort (type 4)
5. "Vi samarbeider med" – Tekstseksjon (type 10)

### 3. fagene-vare.html
1. H1 + intro – Sidetopp – underside (type 2)
2. Frisørfaget – Tekstseksjon (type 10), i fag-seksjon-ramme (type 3)
3. Blomsterdekoratørfaget – Tekstseksjon (type 10), i fag-seksjon-ramme
4. Salgsfaget – fagbrev nr. 2 – Tekstseksjon (type 10), i fag-seksjon-ramme
5. Avsluttende lenker (til lærling-siden/kontakt) – Tekstseksjon (type 10)

### 4. for-laerebedrifter.html
1. H1 + intro – Sidetopp – underside (type 2) + Snarveier (type 7)
2. "Bli lærebedrift" – Tidslinje (type 8), i fag-seksjon-ramme
3. "Dere har lærling hos oss" – Tekstkort (type 4), i fag-seksjon-ramme
4. "Andre muligheter" – Tekstseksjon (type 10), i fag-seksjon-ramme
5. "Hva koster det?" – Tekstseksjon (type 10) + Kontaktboks (type 9)
6. Avsluttende kryss-lenke (til for-laerlinger.html) – Tekstseksjon (type 10)

### 5. for-laerlinger.html
1. H1 + intro – Sidetopp – underside (type 2) + Snarveier (type 7)
2. "Jeg vil bli lærling" – Tekstseksjon (intro + 1+3-modell) + Tidslinje (type 8) + Tekstseksjon ("Søk læreplass"), i fag-seksjon-ramme
3. "Jeg er lærling hos OFA" – Tekstseksjon (intro) + Tekstkort (type 4, fordeler) + Tekstseksjon (Fagbrev.io + "Har du spørsmål") + Personkort (type 6), i fag-seksjon-ramme
4. "Andre veier" – Tekstseksjon (type 10), i fag-seksjon-ramme
5. "Kontakt oss" – Kontaktboks (type 9)
6. Avsluttende kryss-lenke (til for-laerebedrifter.html) – Tekstseksjon (type 10)

### 6. aktuelt.html (flyttet til egen branch, ikke i main)
Ligger ikke i `main` lenger – se "Aktuelt-siden" og "Lansering" for mekanikken. Strukturen i seg selv er uendret og ligger slik på branchen `aktuelt`:
1. H1 + intro – Sidetopp – underside (type 2)
2. "Siste nytt" – Tekstkort (type 4)
3. Instagram-avsnitt – Tekstseksjon (type 10) — se merknad under "Aktuelt-siden": teksten er i strid med den nye regelen om sosiale medier.

### 7. kontakt.html
1. H1 "Kontakt" + intro – Sidetopp – underside (type 2)
2. "Kontaktpersoner" – Personkort (type 6), med kontaktområder som eget felt
3. "Sentralbord og e-post" – Kontaktboks (type 9) + Tekstseksjon (advarselstekst)
4. "Besøk oss" – Tekstseksjon (type 10): adresse + lenke til Google Maps-søk (åpnes i ny fane, ingen innebygd kart)

### 8. personvern.html
1. H1 + ingress – Sidetopp – underside (type 2)
2. Behandlingsansvarlig – Tekstseksjon (type 10)
3. E-post og telefon – Tekstseksjon (type 10)
4. Informasjonskapsler, statistikk og logger – Tekstseksjon (type 10)
5. Sosiale medier (nytt avsnitt) – Tekstseksjon (type 10)
6. Dine rettigheter – Tekstseksjon (type 10)
7. Lærlinger og lærebedrifter – Tekstseksjon (type 10)
8. Sist oppdatert – Tekstseksjon (type 10)

### 9. 404.html (ny, gjennomført)
1. H1 "Siden finnes ikke" + forklarende tekst + to knapper (Til forsiden, Kontakt oss) – Sidetopp – underside (type 2) + Snarveier (type 7)

## Beslutninger lagt til grunn

1. To topptyper: forsidetopp (`.hero`) og en ny klasse for sidetopp på undersidene.
2. Tre korttyper med egne navn: tekstkort, lenkekort, personkort. Personkort viser alltid bilde, navn, rolle og telefon.
3. Kontaktsiden (kontakt.html) skal bruke `.kontaktboks` som de andre sidene.
4. Plassholdere skrives alltid `[Plassholder: ...]`. `<!-- SJEKK -->` brukes på alt faktainnhold, også telefon og org.nr.
5. Aktuelt-siden tas med i denne runden (se eget avsnitt).
6. Kontrasten på `.photo-credit` rettes nå til minst 4,5:1 – utsettes ikke lenger til fargepaletten er endelig valgt.

## Seksjonstyper (10 stk, hver skal kun finnes i én versjon)

### 1. Sidetopp – forside (`.hero`)
- Brukes: index.html.
- Endring: ingen. Blir stående som egen variant kun for forsiden.

### 2. Sidetopp – underside (`.sidetopp`, gjennomført)
- Brukes nå på den første `<section>` på alle 7 undersider: om-ofa, fagene-vare, for-laerebedrifter, for-laerlinger, aktuelt, kontakt, personvern. `.snarveier` ligger fortsatt inni denne seksjonen der den finnes (de to lærer-sidene) – egen, valgfri komponent, ikke en egen toppvariant.
- Valgfritt element: bilde med bildetekst (`.about-photo` + `.photo-credit`) – flyttet på om-ofa.html fra sidetoppen til "Hvem møter du?". Sidetoppen på om-ofa.html bruker nå i stedet en bildeplassholder (`.hero-image-placeholder`, gjenbrukt – se Gjenstår) i påvente av et bilde av lokalene.
- CSS-regelen `.sidetopp` er foreløpig tom (ingen visuell endring nå) – reservert for avstands-/skriftstørrelsesskalaen i punkt 5.
- **To sider krevde reell oppdeling av `<section>`**, ikke bare et klassenavn, siden sidetopp-innholdet lå sammen med neste seksjon i samme tag:
  - **om-ofa.html**: H1+bilde+bildetekst skilt ut fra "OFA – Opplæringskontor..."-avsnittet (nå egen tekstseksjon).
  - **kontakt.html**: H1 skilt ut fra "Kontaktpersoner"-personkortene (nå egen seksjon), og fikk en ny plassholder-ingress: `[Plassholder: Kort setning om hvordan man tar kontakt]`.
  - **Synlig avstandsendring som følge av oppdelingen (målt, ikke rettet nå – tas i punkt 5):** på om-ofa.html økte gapet mellom bildeteksten og "OFA – Opplæringskontor..."-overskriften fra ca. 20px til 40px. På kontakt.html er gapet mellom den nye plassholder-ingressen og "Kontaktpersoner"-overskriften tilsvarende 40px (mot et direkte H1→H2-gap på ca. 21px før oppdelingen, som nå i tillegg har fått en synlig tekstlinje mellom seg).

### 3. Fag-seksjon (`.fag-section`)
- Brukes: fagene-vare, for-laerebedrifter, for-laerlinger.
- Endring: ingen strukturell endring – allerede én versjon. Fungerer som ramme rundt andre seksjonstyper (tekstseksjon, tekstkort, tidslinje). Navnet vurderes på nytt, se "Gjenstår".

### 4. Tekstkort (navngitt `.card-grid`/`.card`-variant)
- Brukes: om-ofa ("Hva gjør vi?"), for-laerebedrifter, for-laerlinger, aktuelt (tas med nå).
- Endring: ingen markup-endring nødvendig. Gi varianten et offisielt navn i kodekommentar/dokumentasjon slik at den ikke blandes sammen med lenkekort eller personkort senere.

### 5. Lenkekort
- Brukes: kun index.html (3 kort med "Les mer →").
- Endring: ingen konsolidering nødvendig, men gi den et eget navn/modifikator-klasse så den ikke glir sammen med tekstkort senere.

### 6. Personkort (gjennomført)
- Brukes: kontakt.html og for-laerlinger.html sin kontaktperson-rad. Begge viser nå bilde + navn + rolle + telefon.
- Telefonnumre: Anne Lene Gabrielsen 902 27 388, Tonje Skomedal Ramse 911 41 299 – begge som klikkbare `tel:+47...`-lenker, bekreftet av bruker, ingen SJEKK-merking.
- Valgfritt felt: en kort beskrivelse av kontaktområder/hva personen kan hjelpe med, som eget avsnitt mellom rolle og telefon. Brukt på kontakt.html ("Kontaktområder: ...") og i lignende form på for-laerlinger.html ("Kontakt Tonje/Anne Lene om ...").

### 7. Snarveier (`.snarveier`)
- Brukes: for-laerebedrifter, for-laerlinger, om-ofa (4 knapper: Om OFA, Hvem møter du?, Hva gjør vi?, Vi samarbeider med).
- Endring: ingen – allerede én versjon. Samme knappefarge (`.btn` / `var(--accent)`) brukt overalt.

### 8. Tidslinje (`.tidslinje`)
- Brukes: for-laerebedrifter, for-laerlinger.
- Endring: ingen strukturell endring her. Skriftvekt-spørsmålet i `.tidslinje-steg` ligger under "Gjenstår".

### 9. Kontaktboks (`.kontaktboks`, gjennomført)
- Brukes: for-laerebedrifter, for-laerlinger, kontakt.html. kontakt.html sin "Ta gjerne direkte kontakt"-seksjon er bygget om til `.kontaktboks` (telefon + e-post-knapp i ramme), med advarselsteksten om sensitive opplysninger stående som eget avsnitt rett utenfor boksen.
- Alle tre instansene bruker nå telefonnummeret som en klikkbar `tel:+4793490216`-lenke (internasjonalt format), ikke bare ren tekst.

### 10. Tekstseksjon (h2 + avsnitt/liste)
- Brukes: personvern.html (alle avsnitt), fagene-vare.html (fagtekstene), for-laerebedrifter.html ("Andre muligheter", "Hva koster det?"), for-laerlinger.html ("Andre veier" m.fl.), avsluttende kryss-lenker på lærer-sidene, om-ofa.html (brødteksten om OFA, uten egen overskrift, og "Vi samarbeider med"), m.fl.
- Endring: ingen strukturell endring – gi den et offisielt navn (Tekstseksjon) slik at den ikke forveksles med Sidetopp eller andre typer ved fremtidig arbeid.
- **Kulepunktstil (gjennomført):** vanlige `<ul>`-lister inni `<main>` (tidligere kun stylet inni `.tidslinje`) bruker nå samme lille, terrakotta-fargede kulepunkt overalt – `main ul` i style.css. Gjelder bl.a. "Vi samarbeider med" (om-ofa.html), "Søk læreplass" (for-laerlinger.html) og "E-post og telefon" (personvern.html).
- **Liste-semantikk for skjermlesere (gjennomført):** alle fire `<ul>`-elementene i `<main>` (om-ofa.html, for-laerlinger.html, for-laerebedrifter.html, personvern.html) har fått `role="list"`. Årsak: `list-style: none` er kjent for å fjerne liste-semantikken i VoiceOver/Safari (ikke i Chrome/NVDA/JAWS) med mindre rollen settes eksplisitt. Ikke testet med ekte VoiceOver, kun bekreftet via Chromiums eget tilgjengelighetstre. Gjelder foreløpig kun lister i `<main>` – `nav ul` og `.footer-col ul` har samme `list-style: none` og samme teoretiske risiko, men er bevisst holdt utenfor denne runden.

## Footer – sosiale medier (nytt)

- Footeren på alle 8 sider skal få lenker til OFAs Instagram- og Facebook-konto.
- Ingen innebygd innhold fra Instagram/Facebook – kun utgående lenker, ingen embeds/widgets.
- Ikonene lagres lokalt som SVG i prosjektmappen; ingen ressurser lastes fra Meta.
- Hver lenke skal ha synlig tekst eller `aria-label` (f.eks. "OFA på Instagram").
- Selve lenke-adressene markeres med `<!-- SJEKK -->` inntil de er bekreftet av bruker.
- Personvern.html får et tilhørende avsnitt (se "Sider" → personvern.html, punkt 5, og "Aktuelt-siden" for sammenhengen): det skal stå at nettsiden lenker til OFAs kontoer på Instagram og Facebook, at ingen opplysninger sendes dit før besøkeren selv klikker, og at Metas vilkår gjelder der.
- Footerens kontaktspalte ("Kontakt") har i tillegg fått en linje med org.nr. (983 572 073) på alle 8 sider, rett under e-postadressen. Bekreftet av bruker, ingen SJEKK-merking.

## Header – Fagbrev.io-lenke (gjennomført)

- Logoikonet ved siden av "Fagbrev.io" i toppmenyen har fått `alt="Fagbrev.io"` på alle 8 sider (var `alt=""`).
- **Merk – mulig tilgjengelighetskonflikt:** CLAUDE.md sier at rent dekorative bilder (ikoner med tekst ved siden av) skal ha `alt=""`, nettopp for å unngå at skjermlesere leser opp samme tekst to ganger. Her følger lenken nå ikonet med `alt="Fagbrev.io"` rett etterfulgt av den synlige teksten "Fagbrev.io", så en skjermleser vil kunne lese "Fagbrev.io Fagbrev.io" for denne ene lenken. Endret på eksplisitt instruks – vurder å sette `alt=""` tilbake dersom dette oppleves som et problem.

## Plassholder- og SJEKK-konvensjon (gjelder alle sider)

- All plassholdertekst skal skrives `[Plassholder: ...]`. Aktuelt.html sin avvikende notasjon ("[Overskrift på nyhet]", "[Kort tekst om nyheten. Dato kommer her.]") rettes til samme format.
- `<!-- SJEKK -->` skal merkes på alt faktainnhold, ikke bare lønn/frister/kostnader på lærer-sidene. Nye markeringer trengs på:
  - Telefonnumre og organisasjonsnummer i personvern.html ("Behandlingsansvarlig")
  - Telefonnumre i kontakt.html (personkort + ny kontaktboks)
  - Telefonnummer i footer på alle 8 sider
  - Adresse (Kartheia 5) der den forekommer
  - Lenke-adressene til Instagram/Facebook i footer

## Kontrastfiks – `.photo-credit` (gjennomført)

- `.photo-credit` står alltid på vanlig side-/kortbakgrunn (`--bg`, #FBF9F5), rett under bildet – aldri oppå selve bildet.
- Den tidligere vurderingen (~3,25–3,6:1) gjaldt en eldre fargeverdi (`rgba(28,28,28,0.5)`, satt under WCAG-revisjonen 2026-11-18) som senere ble endret til `rgba(44,34,30,0.68)` i en urelatert commit samme dag, uten at kontrasten ble regnet på nytt. Reelt målt kontrast for den nyere verdien var 5,29:1 – allerede over AA-kravet.
- Løsning: i stedet for å innføre en ny gråtone, gjenbrukes den eksisterende `#6a675e` (fra footer-teksten, målt 5,38:1 mot `--bg`) som ny CSS-variabel `--muted-text` i `:root`. Både `.photo-credit` og `footer` bruker nå `color: var(--muted-text);`.
- Ingen andre farger er rørt.

## Aktuelt-siden (samlet, gjennomført – flyttet til egen branch)

- aktuelt.html er tatt ut av `main` (`git rm`) og ligger nå kun på en egen branch kalt `aktuelt`, opprettet fra `main` før filen ble fjernet. Menylenkene (header-nav og footer-sidelenker) til Aktuelt er fjernet på alle 7 gjenværende sider.
- **Hvorfor en branch, ikke bare fjerning:** siden GitHub Pages bygger hele `main` ved push, er dette den eneste måten å garantere at siden ikke er nåbar på sin direkte URL før den skal være det – å bare fjerne menylenkene er ikke nok (se "Lansering" under).
- **Ved lansering:** når lanseringsbetingelsen er oppfylt (minst to ekte, publiserte saker – skrives inn på `aktuelt`-branchen når innholdet er klart, uavhengig av når selve lanseringen skjer), flettes `aktuelt`-branchen inn i `main` igjen, og menylenkene legges tilbake på alle 8 sider, i samme push.
- Strukturen i seg selv er uendret og klar til å ta imot innholdet når den tid kommer (se "Sider" → aktuelt.html).
- **Merknad – konflikt med ny regel:** Aktuelt.html sin plassholdertekst på `aktuelt`-branchen ("her kan vi senere vise innhold fra Instagram-kontoen til OFA") er i strid med den nye regelen om at sosiale medier kun skal lenkes til, aldri innebygges. Formuleringen må rettes (f.eks. til en ren lenke til OFAs Instagram) når innholdet skrives, før branchen flettes inn.

## Lansering – noindex og publiseringsmekanikk

- **404.html (gjennomført):** egen feilside i OFAs utseende ("Siden finnes ikke" + lenker til forsiden og kontaktsiden), lagt i prosjektroten. GitHub Pages viser denne automatisk for alle ugyldige adresser, i stedet for GitHubs standard enhjørning-side. Bruker samme relative lenker (`css/style.css`, `index.html` osv.) som resten av sidene, for konsistens med resten av prosjektet.
  - **Kjent begrensning:** relative lenker i `404.html` løses av nettleseren ut fra adressen som faktisk ble forsøkt besøkt, ikke ut fra hvor filen ligger. For feilsider på toppnivå (f.eks. en gammel lenke til `aktuelt.html`, eller en feilstavet sidenavn) fungerer dette likt som på alle andre sider i prosjektet. For en adresse med ekstra mapper i stien (f.eks. `/ofa-nettside/noe/som-ikke-finnes/`) vil lenkene og stilarket kunne brytes, selv om selve teksten "Siden finnes ikke" fortsatt vises. Vurder absolutte stier senere dersom dette blir et reelt problem – men ikke før endelig domene er valgt, siden en sti som `/ofa-nettside/...` uansett må endres ved overgang til eget domene (se under).

- Alle 8 sider har fått `<meta name="robots" content="noindex, nofollow">` i `<head>`, og det er lagt til en `robots.txt` ved prosjektroten som disallower alt (`Disallow: /`). Dette hindrer søkemotorer i å indeksere siden mens den er under arbeid.
- **Fjernes ved lansering:** `noindex`-taggen på de 7 innholdssidene og `robots.txt` må fjernes/oppdateres idet siden lanseres for alvor – ellers forblir siden usynlig i søk permanent. **Unntak:** `noindex` på `404.html` skal *stå* for alltid, også etter lansering – det er vanlig praksis for feilsider, og hindrer at feilsiden selv dukker opp som treff i søk.
- **Viktig forbehold:** `noindex`/`robots.txt` hindrer kun *ny* indeksering fra søkemotorer. De gjør ikke siden utilgjengelig for noen som har den direkte URL-en, og fjerner ikke allerede indeksert innhold retroaktivt.
- **Aktuelt.html og "push = publisering" (gjennomført):** GitHub Pages bygger hele `main`-branchen ved hver push, så det er ikke mulig å pushe resten av nettsiden uten at aktuelt.html blir med, med mindre filen (og nav-/footer-lenkene til den) fysisk er fjernet fra det som pushes. Løsningen: aktuelt.html er flyttet til en egen branch (`aktuelt`), fjernet fra `main`, og menylenkene er fjernet på alle 7 gjenværende sider. Se "Aktuelt-siden" for detaljer om fletting ved lansering.
- **Tidligere funn, nå løst (gjennomført):** aktuelt.html hadde vært en del av `main`-branchen – og dermed trolig allerede live på https://ofaagder.github.io/ofa-nettside/aktuelt.html – siden lenge før denne byggeplanen, med plassholderinnhold. Fjerningen er pushet, og filen er ikke lenger en del av den live siden.
- **Ved overgang til eget domene:** avklar om nettsiden fortsatt driftes av GitHub Pages (eget domene peker dit) eller flyttes til et webhotell. Ved flytting skal avsnittet om logger i personvern.html skrives om med ny driftsleverandør, og avsnittet om overføring til USA vurderes på nytt.

## Avstand og størrelse – observasjoner til punkt 5

- om-ofa.html: gapet mellom bildeteksten (`.photo-credit`) og den påfølgende h2 ("OFA – Opplæringskontor...") økte fra ca. 20px til 40px da sidetopp-seksjonen ble delt ut.
- kontakt.html: gapet mellom den nye ingressen i sidetoppen og "Kontaktpersoner"-overskriften er 40px.

## Gjenstår (teknisk rydding, egen runde)

- Fjern dødt CSS: all `form`/`form label`/`form input, textarea`-styling (linje 371–391) – ingen HTML-fil bruker lenger disse. (`.hero-image-placeholder` er nå tatt i bruk igjen på om-ofa.html, se "Sider".)
- `#6a675e` er nå samlet i `--muted-text` (se Kontrastfiks over). Gjør `#e0dcd3` (border-fargen, 5 hardkodede forekomster) om til en tilsvarende CSS-variabel (f.eks. `--border`).
- Rett skriftvekt i `.tidslinje-steg` slik at den bruker samme font (Poppins) som resten av de fete elementene i komponenten, eller dokumenter bevisst hvorfor den skal bruke brødtekstfonten.
- Konverter bilder til WebP (krav i PROSJEKTBRIEF.md, ikke oppfylt i dag – bildene er komprimert JPG).
- Vurder nytt navn på `.fag-section`, siden den i praksis brukes som en generell rammeseksjon (ikke bare for "fag"-sider) rundt flere seksjonstyper (tekstseksjon, tekstkort, tidslinje).

## Forslag til rekkefølge (ikke bindende)

1. Kontrastfiks `.photo-credit` – liten og isolert, kan gjøres først og alene.
2. Sidetopp-underside – ny klasse på de 7 undersidene.
3. Personkort – legg til telefon i for-laerlinger.html.
4. Kontaktboks på kontakt.html.
5. Felles skala for avstander og skriftstørrelser: egne CSS-variabler for avstander (f.eks. `--space-xs/sm/md/lg/xl`) og for skriftstørrelser (h1, h2, h3, brødtekst, små tekster), brukt av `.snarveier`, `.tidslinje`, `.tidslinje ul`, `.card-grid`, `.kontaktboks`, `.footer-inner` og overskrifter/tekst generelt i stedet for frittstående rem-verdier.
   - Når vi kommer hit: bruker gir en liste over hva som ikke er bra med dagens avstander/skriftstørrelser. Basert på den listen foreslås konkrete skalaverdier, forslaget vises, og det ventes på godkjenning før noe endres.
6. Footer: sosiale medier-ikoner/lenker (alle 8 sider) + nytt avsnitt i personvern.html.
7. Plassholder/SJEKK-opprydding (aktuelt.html, personvern.html, kontakt.html, footer).
8. Teknisk rydding (dødt CSS, skriftvekt i tidslinje, navn på `.fag-section`).
9. WebP-konvertering.
10. Rett før lansering: sjekk om `aktuelt`-branchen har minst to ekte saker. Hvis ja: flett branchen inn i `main` og legg menylenkene tilbake på alle 8 sider, i samme push. Hvis nei: la branchen stå urørt og ikke flett den inn ennå.
11. Ved selve lanseringen: fjern `noindex`-taggen fra alle 8 sider og oppdater `robots.txt`, samtidig som punkt 10 sjekkes – de to bør gjøres i samme push.
