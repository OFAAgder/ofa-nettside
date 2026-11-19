# BYGGEPLAN.md

Dette er byggeplanen for struktur på OFA-nettsiden. Den er fasiten: endringer i sidestruktur, rekkefølge eller seksjonstyper gjøres her først, deretter i koden.

## Sider (fasit for struktur)

### 1. index.html
1. Hero – Sidetopp – forside (type 1)
2. "Våre tjenester" – Lenkekort (type 5) + CTA-knapp

### 2. om-ofa.html
1. H1 + bilde + bildetekst – Sidetopp – underside (type 2)
2. "OFA – Opplæringskontor for FBIE i Agder" – Tekstseksjon (type 10)
3. "Hva gjør vi?" – Tekstkort (type 4)
4. "Vi samarbeider med" – Tekstkort (type 4)

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

### 6. aktuelt.html
1. H1 + intro – Sidetopp – underside (type 2)
2. "Siste nytt" – Tekstkort (type 4)
3. Instagram-avsnitt – Tekstseksjon (type 10) — se merknad under "Aktuelt-siden": teksten er i strid med den nye regelen om sosiale medier.

### 7. kontakt.html
1. H1 + intro – Sidetopp – underside (type 2)
2. "Kontaktpersoner" – Personkort (type 6)
3. "Ta kontakt" – Kontaktboks (type 9) + Tekstseksjon (advarselstekst)

### 8. personvern.html
1. H1 + ingress – Sidetopp – underside (type 2)
2. Behandlingsansvarlig – Tekstseksjon (type 10)
3. E-post og telefon – Tekstseksjon (type 10)
4. Informasjonskapsler, statistikk og logger – Tekstseksjon (type 10)
5. Sosiale medier (nytt avsnitt) – Tekstseksjon (type 10)
6. Dine rettigheter – Tekstseksjon (type 10)
7. Lærlinger og lærebedrifter – Tekstseksjon (type 10)
8. Sist oppdatert – Tekstseksjon (type 10)

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
- Valgfritt element: bilde med bildetekst (`.about-photo` + `.photo-credit`), brukt i dag kun på om-ofa.html.
- CSS-regelen `.sidetopp` er foreløpig tom (ingen visuell endring nå) – reservert for avstands-/skriftstørrelsesskalaen i punkt 5.
- **To sider krevde reell oppdeling av `<section>`**, ikke bare et klassenavn, siden sidetopp-innholdet lå sammen med neste seksjon i samme tag:
  - **om-ofa.html**: H1+bilde+bildetekst skilt ut fra "OFA – Opplæringskontor..."-avsnittet (nå egen tekstseksjon).
  - **kontakt.html**: H1 skilt ut fra "Kontaktpersoner"-personkortene (nå egen seksjon), og fikk en ny plassholder-ingress: `[Plassholder: Kort setning om hvordan man tar kontakt]`.
  - **Synlig avstandsendring som følge av oppdelingen (målt, ikke rettet nå – tas i punkt 5):** på om-ofa.html økte gapet mellom bildeteksten og "OFA – Opplæringskontor..."-overskriften fra ca. 20px til 40px. På kontakt.html er gapet mellom den nye plassholder-ingressen og "Kontaktpersoner"-overskriften tilsvarende 40px (mot et direkte H1→H2-gap på ca. 21px før oppdelingen, som nå i tillegg har fått en synlig tekstlinje mellom seg).

### 3. Fag-seksjon (`.fag-section`)
- Brukes: fagene-vare, for-laerebedrifter, for-laerlinger.
- Endring: ingen strukturell endring – allerede én versjon. Fungerer som ramme rundt andre seksjonstyper (tekstseksjon, tekstkort, tidslinje). Navnet vurderes på nytt, se "Gjenstår".

### 4. Tekstkort (navngitt `.card-grid`/`.card`-variant)
- Brukes: om-ofa, for-laerebedrifter, for-laerlinger, aktuelt (tas med nå).
- Endring: ingen markup-endring nødvendig. Gi varianten et offisielt navn i kodekommentar/dokumentasjon slik at den ikke blandes sammen med lenkekort eller personkort senere.

### 5. Lenkekort
- Brukes: kun index.html (3 kort med "Les mer →").
- Endring: ingen konsolidering nødvendig, men gi den et eget navn/modifikator-klasse så den ikke glir sammen med tekstkort senere.

### 6. Personkort
- Brukes: kontakt.html (med telefon i dag) og for-laerlinger.html sin kontaktperson-rad (uten telefon i dag).
- Endring: legg til telefonnummer i for-laerlinger.html sine to personkort (Anne Lene Gabrielsen 902 27 388, Tonje Skomedal Ramse 911 41 299), slik at personkort alltid viser bilde + navn + rolle + telefon.

### 7. Snarveier (`.snarveier`)
- Brukes: for-laerebedrifter, for-laerlinger.
- Endring: ingen – allerede én versjon.

### 8. Tidslinje (`.tidslinje`)
- Brukes: for-laerebedrifter, for-laerlinger.
- Endring: ingen strukturell endring her. Skriftvekt-spørsmålet i `.tidslinje-steg` ligger under "Gjenstår".

### 9. Kontaktboks (`.kontaktboks`)
- Brukes i dag: for-laerebedrifter, for-laerlinger.
- Endring: kontakt.html sin "Ta gjerne direkte kontakt"-seksjon bygges om til `.kontaktboks` (telefon + e-post-knapp i ramme). Advarselsteksten om sensitive opplysninger beholdes som eget avsnitt (tekstseksjon) rett under/utenfor boksen.

### 10. Tekstseksjon (h2 + avsnitt/liste)
- Brukes: personvern.html (alle avsnitt), fagene-vare.html (fagtekstene), for-laerebedrifter.html ("Andre muligheter", "Hva koster det?"), for-laerlinger.html ("Andre veier" m.fl.), avsluttende kryss-lenker på lærer-sidene, m.fl.
- Endring: ingen strukturell endring – gi den et offisielt navn (Tekstseksjon) slik at den ikke forveksles med Sidetopp eller andre typer ved fremtidig arbeid.

## Footer – sosiale medier (nytt)

- Footeren på alle 8 sider skal få lenker til OFAs Instagram- og Facebook-konto.
- Ingen innebygd innhold fra Instagram/Facebook – kun utgående lenker, ingen embeds/widgets.
- Ikonene lagres lokalt som SVG i prosjektmappen; ingen ressurser lastes fra Meta.
- Hver lenke skal ha synlig tekst eller `aria-label` (f.eks. "OFA på Instagram").
- Selve lenke-adressene markeres med `<!-- SJEKK -->` inntil de er bekreftet av bruker.
- Personvern.html får et tilhørende avsnitt (se "Sider" → personvern.html, punkt 5, og "Aktuelt-siden" for sammenhengen): det skal stå at nettsiden lenker til OFAs kontoer på Instagram og Facebook, at ingen opplysninger sendes dit før besøkeren selv klikker, og at Metas vilkår gjelder der.

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

## Aktuelt-siden (samlet)

- Tas med i denne runden, men kun det strukturelle: nyhetskortene standardiseres som tekstkort (type 4), og plassholderteksten rettes til `[Plassholder: ...]`-format.
- Selve nyhetsinnholdet (overskrifter, tekst, datoer) er ikke klart ennå og skrives ikke nå – det fylles inn når det er bestemt, uavhengig av lansering. Strukturen er klar til å ta imot innholdet når den tid kommer.
- **Lanseringsbetingelse:** Aktuelt skal bare finnes på den publiserte nettsiden dersom den har minst to ekte, publiserte saker. Inntil da er siden *skjult* – det betyr at **aktuelt.html ikke publiseres/pushes til den live siden i det hele tatt**, ikke bare at menylenkene (header-nav og footer-sidelenker, alle 8 sider) fjernes. Når minst to saker er klare, publiseres filen og lenkene legges tilbake samtidig på alle 8 sider.
- **Merknad – konflikt med ny regel:** Aktuelt.html sin nåværende plassholdertekst ("her kan vi senere vise innhold fra Instagram-kontoen til OFA") er i strid med den nye regelen om at sosiale medier kun skal lenkes til, aldri innebygges. Formuleringen må rettes (f.eks. til en ren lenke til OFAs Instagram) når innholdet skrives.

## Avstand og størrelse – observasjoner til punkt 5

- om-ofa.html: gapet mellom bildeteksten (`.photo-credit`) og den påfølgende h2 ("OFA – Opplæringskontor...") økte fra ca. 20px til 40px da sidetopp-seksjonen ble delt ut.
- kontakt.html: gapet mellom den nye ingressen i sidetoppen og "Kontaktpersoner"-overskriften er 40px.

## Gjenstår (teknisk rydding, egen runde)

- Fjern dødt CSS: `.hero-image-placeholder` (style.css, linje 209–219) og all `form`/`form label`/`form input, textarea`-styling (linje 371–391) – ingen HTML-fil bruker lenger disse.
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
10. Rett før lansering: sjekk om Aktuelt har minst to ekte saker. Publiser filen og menylenken sammen hvis ja; hold begge tilbake hvis nei.
