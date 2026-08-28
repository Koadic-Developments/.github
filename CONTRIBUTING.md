# Sådan ændrer vi noget

Gælder alle Koadic-repoer. Seks trin, ingen genveje — hvert trin fanger noget,
det forrige ikke kan.

Trinnene er ikke skrevet ud fra en lærebog. Hver enkelt står der, fordi noget
gik galt uden den.

---

## 1 · Aldrig direkte på `main`

Enhver ændring starter som en gren. Navnet siger **hvad**, ikke hvem:

```
kds/soeg-efter-kunden      ja
adam-fix                   nej
```

Om et halvt år er det grenens navn, der står i historikken.

## 2 · Vagtposten før koden

Retter du en fejl, så skriv først prøven, der fanger den — og **se den fejle**.
En prøve, der aldrig har været rød, beviser ingenting.

Det er den enkeltregel, der har fanget mest i huset:

- et nøglemønster, der slap et linjeskift igennem, fordi `$` i PHP matcher
  lige før et afsluttende `\n` — `"1234567890\n"` blev til en filsti
- en knap, der var sort på sort i ét tema; prøven fandt straks to temaer mere,
  som ikke kunne ses med det blotte øje
- en prøveløkke, der meldte alt grønt, fordi `$(basename $t)` nulstillede
  statuskoden, før den blev læst. Fire prøver fejlede.

## 3 · PR med en begrundelse, ikke en liste

Teksten skal svare på **hvorfor**, og hvad der blev målt.

> «Rettede knappen» er ikke en PR-tekst.
> «Knappen var sort på sort i Avis; prøven fandt to temaer mere, jeg ikke kunne
> se med øjet» er.

Skabelonen står i `.github/PULL_REQUEST_TEMPLATE.md` og udfyldes automatisk.

## 4 · CI skal være grøn — og grøn skal betyde noget

Et trin, der ikke kan fejle, er ikke et tjek.

Vi har haft en udrulning, der stod grøn, mens systemet var rødt: den ledte
efter `"ok": true` i et svar, hvor de enkelte deltjek også indeholdt den
tekstbid. Og en prøve, der bestod i CI og fatalede på serveren, fordi CI's PHP
har `dom` og serverens ikke.

**Skriver du et nyt tjek: bryd koden med vilje og se det fange det.**

## 5 · Se det køre, før du merger

Grøn CI er ikke «det virker».

- CI kører en anden PHP end serveren. VPS'en har hverken `dom` eller `xml`.
- En `.gitignore`d fil når aldrig serveren, uanset hvor grønt bygget var.
- En rettelse i et ark, der ikke er `<link>`et ind, fejler fuldstændig tavst.

Åbn siden. Klik på knappen.

## 6 · Merge, udrul — og hent filen tilbage

Efter udrulningen: hent den fil, du ændrede, **fra serveren**, og se at den er
din.

Grøn udrulning betyder ikke «ude». Det har kostet huset en forkert
sikkerhedskonklusion én gang: koden var merget, deployet var grønt, og den
gamle fil lå der stadig.

---

## Hvad der er spærret automatisk

| Regel | Håndhæves af |
|---|---|
| Ingen direkte push til `main` | Grenbeskyttelse på GitHub |
| CI skal være grøn før merge | Påkrævede status-tjek |
| PR-teksten stiller de rigtige spørgsmål | `PULL_REQUEST_TEMPLATE.md` |
| Issues får ansvarlig, label og milepæl | `.github/workflows/tildel-issues.yml` |

Godkendelse fra en anden person er **ikke** påkrævet. Vi er tre, og et sådant
krav ville betyde, at en hasterettelse en lørdag ikke kan udrulles.
Spærringen er mod utilsigtede pushes, ikke mod hinanden.
