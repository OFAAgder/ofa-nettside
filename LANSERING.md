# Sjekkliste for lansering

Dette er oppgavene som må gjøres idet nettsiden lanseres for alvor (blir synlig og søkbar for publikum). Se også BYGGEPLAN.md, særlig seksjonene "Lansering – noindex og publiseringsmekanikk" og "Aktuelt-siden", for bakgrunn og begrunnelse.

- [ ] Fjern `noindex, nofollow` fra alle sider unntatt 404, slik at nettstedet blir synlig i søkemotorer.
  - Gjelder de 7 innholdssidene (index.html, om-ofa.html, fagene-vare.html, for-laerebedrifter.html, for-laerlinger.html, kontakt.html, personvern.html) – og aktuelt.html når den er flettet inn igjen, se under.
  - **Unntak:** `404.html` skal beholde `noindex, nofollow` for alltid. Det er vanlig praksis for feilsider, og hindrer at feilsiden selv dukker opp som treff i søk.
- [ ] Oppdater eller fjern `robots.txt` (ligger i prosjektroten og disallower i dag alt med `Disallow: /`).
- [ ] Sjekk `aktuelt`-branchen: er lanseringsbetingelsen oppfylt (minst to ekte, publiserte saker)?
  - Hvis ja: flett `aktuelt`-branchen inn i `main`, og legg tilbake menylenkene (header-nav og footer-sidelenker) til Aktuelt på alle 8 sider, i samme push.
  - Rett plassholderteksten i aktuelt.html om Instagram-innhold til en ren lenke før fletting – den er i strid med regelen om at sosiale medier kun skal lenkes til, aldri innebygges (se CLAUDE.md).
  - Hvis nei: la aktuelt.html bli liggende på egen branch, og vent til neste lanseringsvurdering.
- [ ] Gå gjennom alle `<!-- SJEKK -->`-markeringer i kodebasen og bekreft at informasjonen stemmer (telefon, org.nr., priser, frister, prosesser), eller rett den. Fjern markeringen når innholdet er bekreftet.
- [ ] Bytt ut de tre plassholderbildene på fagene-vare.html med ekte bilder (samtykke og bruksrett avklart med bedriftene).
- [ ] Ved overgang til eget domene: avklar om nettsiden fortsatt driftes av GitHub Pages (eget domene peker dit) eller flyttes til et webhotell. Ved flytting skal avsnittet om logger i personvern.html skrives om med ny driftsleverandør, og avsnittet om overføring til USA vurderes på nytt.
- [ ] Vurder om gjenstående punkter i BYGGEPLAN.md ("Gjenstår" og "Forslag til rekkefølge") bør fullføres før lansering, eller kan tas etterpå.
