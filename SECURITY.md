# Sikkerhedspolitik

Gælder **alle** Koadic-repoer. GitHub viser den her fil på ethvert repo, der
ikke har sin egen — så en ny sikkerhedskontakt skrives ét sted, ikke syvogtredive.

## Rapportér en sårbarhed

**kontakt@koadic.dk** — ikke via et offentligt Issue.

Skriv hvad du fandt, hvordan det kan gentages, og hvad du mener konsekvensen
er. Du får svar inden for to hverdage.

Er du i tvivl om, hvorvidt noget tæller som en sårbarhed: send det. Det er
billigere for os at læse en mail for meget end at opdage det samme et halvt år
senere.

## Hvad der er i scope

| System | Adresse |
|---|---|
| Koadic | koadic.dk |
| Login | auth.koadic.dk |
| Medarbejderplatform | medarbejder.koadic.dk · workspace.koadic.dk |
| Portal | portal.koadic.dk |
| CRM | crm.koadic.dk |
| Helpdesk | helpdesk.koadic.dk |
| Fakturering | faktura.koadic.dk |
| Driftsstatus | status.koadic.dk |
| Designsystem | design.koadic.dk |
| Kundeudkast | vis.koadic.dk |
| Sikkerhedsplatform | security.koadic.dk |

**Ikke i scope:** `pr-*-*.koadic.dk`. Det er forhåndsvisninger af åbne pull
requests — kode, der endnu ikke er gennemgået. Fund der kun gælder dem, er
interessante for os internt, men de er ikke en sårbarhed i drift.

## Hvad vi beder om

- **Ingen automatiserede scannere** mod produktionen. De vælter en lille
  opsætning, og vi kan ikke skelne dem fra et angreb.
- **Rør ikke data, der ikke er dine.** Har du adgang til noget, du ikke burde,
  så stop dér og skriv — vi tror på dig.
- **Giv os tid til at rette**, før det bliver offentligt.

## Hvad vi gør selv

- Alle repoer kræver en pull request til `main`, også for ejeren
- CI skal være grøn før merge — se `CONTRIBUTING.md`
- Dependabot holder øje med afhængigheder
- To-faktor er påkrævet for alle i organisationen
- Hemmeligheder ligger i `/etc/*.env` på serveren, ejet af root. De står
  aldrig i git, og udrulningen kan ikke læse dem

---
© 2026 Koadic Developments
