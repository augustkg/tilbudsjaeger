# tilbudsjæger

Claude Code plugin der finder den billigste samlede pris på et produkt i det danske marked.

Tjekker systematisk:
- Pris-aggregatorer (PriceRunner.dk) og direkte hos store DK-forhandlere
- Tyske/franske/italienske forhandlere med automatisk moms-justering ved DK-levering
- Nyhedsbrevs-rabatter og rabatkoder — inkl. kendte fælder (designermærker, kampagnevarer)
- Brugerens egne medlemskaber: PlusKort, Forbrugsforeningen, Coop Plus, FDM, premium kreditkort, ISIC

## Installation

Repoet er både en marketplace og selve pluginet, så installation er to trin:

```bash
/plugin marketplace add augustkg/tilbudsjaeger
/plugin install tilbudsjaeger@tilbudsjaeger
```

### Lokalt (udvikling)

Fra repoets rod:

```bash
claude --plugin-dir .
```

Når Claude Code starter, kan du teste skillen direkte uden at gå via marketplacen.

## Brug

Når pluginet er installeret, kan du bruge skillen via slash-kommando:

```
/tilbudsjaeger:find-pris Ingo Maurer Floatation 75cm
```

Eller bare beskriv hvad du leder efter — Claude vælger selv skillen når dit prompt matcher:

```
Find den billigste Sony WH-1000XM5 jeg kan få i DK
```

## Hvad pluginet gør

Følger en fast 7-trins-proces:

1. **Identificér produkt** — model, variant (størrelse, farve, generation)
2. **Spørg om medlemskaber** — PlusKort, Forbrugsforeningen, Coop Plus, FDM, premiumkort, ISIC
3. **Søg PriceRunner.dk** som primær aggregator
4. **Cross-check 2-3 direkte DK-forhandlere** afhængig af kategori
5. **Tjek 1-2 EU/Nordic-forhandlere** for cross-border-arbitrage (med moms-justering)
6. **Anvend rabat-mekanikker** baseret på valgte medlemskaber + nyhedsbrevsregler
7. **Output rangeret resultat på dansk** med "billigst på papir" og "billigst i praksis"

## Hvad pluginet IKKE gør

- Dagligvarer (Coop-app/Nemlig.com har det)
- Ejendom eller finansielle produkter
- Pris-monitorering over tid (kun engangs-snapshot)
- Automatisk udfyldning af nyhedsbrevsformularer eller checkout (du gør de sidste klik selv)

## Struktur

```
tilbudsjaeger/
├── .claude-plugin/
│   ├── plugin.json          # plugin-manifest
│   └── marketplace.json     # marketplace-katalog (peger på pluginet i roden)
├── skills/
│   └── find-pris/
│       ├── SKILL.md
│       └── references/
│           ├── retailers.md
│           ├── memberships.md
│           ├── output-template.md
│           └── learnings.md  # verificerede mønstre fra brug — opdateres løbende
├── LICENSE
└── README.md
```

## Bidrag

Forhandlere ændrer sig, kampagner kommer og går. Hvis du opdager:
- En ny relevant forhandler i en kategori → tilføj til `skills/find-pris/references/retailers.md`
- En ny eller ændret rabat-mekanik (procent, undtagelser, regler) → opdatér `skills/find-pris/references/memberships.md`
- Et generelt mønster Claude bør lære (som "kampagnevarer afviser rabatkoder") → tilføj til `skills/find-pris/SKILL.md` under "Gotchas"

Husk: pluginet er kun så godt som de mønstre det er instrueret i. Når du opdager noget, så skriv det ind.

## Licens

MIT — se [LICENSE](LICENSE)
