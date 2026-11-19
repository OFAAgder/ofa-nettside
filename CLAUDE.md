# OFA-nettside – prosjektregler

- Svar alltid på norsk bokmål, også i korte kommentarer.

## Arbeidsregler

- BYGGEPLAN.md er fasit for struktur. Endringer i rekkefølge eller innhold gjøres der først, deretter i koden.
- Alle sider bygges av de faste seksjonstypene i BYGGEPLAN.md. Ikke lag nye varianter uten å spørre.
- Før større endringer: legg fram en plan og vent på godkjenning.
- Etter hver godkjent endring: lag en git-commit med kort beskrivelse på norsk.
- Sjekk alltid mobilvisning først.
- Personvern: ingen tredjepartsinnhold eller ekstern sporing. Ingen CDN-er, eksterne fonter, eksterne skript, skjemaer eller innebygd innhold fra tredjeparter (f.eks. Instagram, YouTube, kart). Lenk til slike tjenester i stedet. Kontakt skjer via mailto.
- Sosiale medier: kun lenker, aldri innebygd innhold. Ikoner lagres lokalt.
- Plassholdertekst skrives alltid [Plassholder: ...].
- Alt faktainnhold som ikke er bekreftet (telefon, org.nr., priser, frister, prosesser) markeres med <!-- SJEKK -->.
- Bilder lagres som WebP.
- Avstander følger en felles skala (fastsettes i ryddingen; inntil da: ikke innfør nye verdier).

## Tilgjengelighet (WCAG 2.1, nivå AA)

Nettsiden skal følge WCAG 2.1 nivå AA. Dette gjelder alt arbeid fremover, ikke bare det som er fikset per 2026-11-18:

- Behold alltid logisk overskriftshierarki (ingen hopp fra `<h1>` til `<h3>` uten `<h2>` imellom).
- Nye sider skal ha en skip-link (`<a href="#main-content" class="skip-link">Hopp til hovedinnhold</a>`) rett etter `<body>`, og `<main>` skal ha `id="main-content"`.
- Tabeller skal bruke `<th scope="col">` for kolonneoverskrifter og `<th scope="row">` der første kolonne fungerer som radoverskrift.
- Scrollbare elementer (f.eks. `.table-wrap` ved brede tabeller) skal ha `tabindex="0"` og en beskrivende `aria-label`/`role="region"` slik at tastaturbrukere kan nå og forstå dem.
- Alle bilder skal ha beskrivende `alt`-tekst; rent dekorative bilder (ikoner med tekst ved siden av) skal ha `alt=""`.
- Tekst skal ha kontrast på minst 4,5:1 mot bakgrunnen (3:1 for stor tekst). Sjekk ved alle fargeendringer.
- Ikke fjern standard fokusmarkering (`outline`) uten å erstatte med en tydelig alternativ fokusstil.
- Lenker skal skilles fra vanlig tekst med mer enn bare farge (f.eks. understreking), og aktiv side i menyen skal markeres med mer enn bare farge (f.eks. også fet skrift).

**Status og gjenstående arbeid:** se Gjenstår i BYGGEPLAN.md.
