<!--
Husk før du opretter:
  Ansvarlig · Label · Type · Milepæl · Projekt
Alle fem felter sættes i højre side. Et issue eller en PR uden dem bliver væk.
-->

### Hvad ændrer denne PR

<!-- Kort og i klar tekst. Hvad kan systemet nu, som det ikke kunne før? -->

### Hvorfor

<!-- Hvilket problem løser det? Link til issuet: Closes #  -->

Closes #

### Sådan er det testet

<!-- Hvad har du konkret kørt eller klikket dig igennem? Skriv resultatet, ikke kun at du testede. -->

- [ ] Kodekontrollen er grøn
- [ ] Testet lokalt eller på staging
- [ ] Ingen ændringer i konfiguration eller database der mangler at blive kørt
- [ ] Har jeg skrevet en ny prøve: har jeg set den **fejle**, før den blev grøn?
- [ ] Har jeg **åbnet siden** — ikke kun set CI være grøn?

<!--
De to sidste er ikke pynt. Grøn CI beviser noget om CI's maskine, ikke om
serverens: VPS'en kører PHP uden dom og xml, og en gitignoreret fil når aldrig
derover. Og en prøve, der aldrig har været rød, beviser ingenting.
Se CONTRIBUTING.md, trin 2 og 5.
-->

### Skal der gøres noget efter merge

<!-- Migration, cron, indstilling, deploy-rækkefølge — eller "nej". -->

### Skærmbilleder

<!-- Ved ændringer i brugerfladen: før og efter. -->
