# Koadic Developments

**Dansk udviklingshus.** Vi bygger og driver Koadics egne systemer — fra medarbejderplatform
og sikkerhed til CRM, helpdesk og selvhostet AI. Alt kører på egen infrastruktur.

---

## Hvad vi bygger

### Drift og medarbejdere
| System | Hvad det gør |
|---|---|
| **Medarbejderplatform** | Vagtplan, tidsregistrering, løn, fravær og kontrakter |
| **Medarbejder-app** | iOS-app til stempling, vagtplan og godkendelser |
| **Management Panel** | Internt kontrolpanel for produkter, infrastruktur og drift |

### Kunder og support
| System | Hvad det gør |
|---|---|
| **CRM** | Kunder, kontrakter og fakturering |
| **Helpdesk** | Samlet indbakke med mail, telefon og sager |
| **Kundeportal** | Selvbetjening for Koadics kunder |
| **Ticketsystem** | Sagsstyring på tværs af produkter |

### Platform
| System | Hvad det gør |
|---|---|
| **Security Platform** | WAF, bot-beskyttelse og angrebsdetektion |
| **KoaBot** | 100 % selvhostet AI — ingen data forlader vores servere |
| **Workspace** | Mail, drev, chat og kalender i én app |
| **API System** | Fælles API-lag på tværs af produkterne |

---

## Sådan arbejder vi

**Alt gennem pull requests.** Ingen skriver direkte til `main`. Hver ændring starter som et
issue, bliver til en pull request, og skal bestå den automatiske kontrol før den kan merges.

**Automatisk kodekontrol.** Hver pull request testes for syntaksfejl og gennemgås, før den når
produktion. Fejler kontrollen, kan den ikke merges — uanset hvem der har skrevet den.

**Hemmeligheder slipper ikke ud.** Alle repositories har secret scanning med push-beskyttelse:
forsøger nogen at sende en API-nøgle eller adgangskode med, bliver det afvist med det samme.

**Selvhostet, hvor det tæller.** AI, database og baggrundsjobs kører på egen infrastruktur.
Vi køber standardværktøj og bygger selv det, der er vores produkt.

---

## Roller

| Team | Adgang |
|---|---|
| **Ledelse** | Fuld kontrol over repositories og indstillinger |
| **Udviklere** | Kan pushe til feature-branches og oprette pull requests |
| **Gennemsyn** | Læser kode og godkender pull requests |
| **Læseadgang** | Kun læseadgang — revisorer og eksterne samarbejdspartnere |

---

## Kontakt

**Web** · [koadic.dk](https://koadic.dk)
**Udvikling** · development@koadic.dk
**Sikkerhed** · Fundet et sikkerhedsproblem? Skriv til development@koadic.dk — vi svarer hurtigt.

<sub>Alle repositories er private. Koadic Developments · Danmark</sub>
