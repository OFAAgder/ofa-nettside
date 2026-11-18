# OFA-nettside – prosjektregler

## Tilgjengelighet (WCAG 2.1, nivå AA)

Nettsiden skal følge WCAG 2.1 nivå AA. Dette gjelder alt arbeid fremover, ikke bare det som er fikset per 2026-11-18:

- Behold alltid logisk overskriftshierarki (ingen hopp fra `<h1>` til `<h3>` uten `<h2>` imellom).
- Nye sider skal ha en skip-link (`<a href="#main-content" class="skip-link">Hopp til hovedinnhold</a>`) rett etter `<body>`, og `<main>` skal ha `id="main-content"`.
- Tabeller skal bruke `<th scope="col">` for kolonneoverskrifter og `<th scope="row">` der første kolonne fungerer som radoverskrift.
- Scrollbare elementer (f.eks. `.table-wrap` ved brede tabeller) skal ha `tabindex="0"` og en beskrivende `aria-label`/`role="region"` slik at tastaturbrukere kan nå og forstå dem.
- Alle bilder skal ha beskrivende `alt`-tekst; rent dekorative bilder (ikoner med tekst ved siden av) skal ha `alt=""`.
- Tekst skal ha kontrast på minst 4,5:1 mot bakgrunnen (3:1 for stor tekst). Sjekk dette når farger/design fastsettes endelig.
- Ikke fjern standard fokusmarkering (`outline`) uten å erstatte med en tydelig alternativ fokusstil.
- Lenker skal skilles fra vanlig tekst med mer enn bare farge (f.eks. understreking), og aktiv side i menyen skal markeres med mer enn bare farge (f.eks. også fet skrift).

**Status:** Strukturelle avvik (overskriftshierarki, manglende skip-link, tabell-semantikk, tastaturfokus) er fikset. Kontrasten på bildeteksten (`.photo-credit`) er foreløpig for lav (~3,25:1) og venter på at endelig fargepalett velges – se prosjektminnet for detaljer.
