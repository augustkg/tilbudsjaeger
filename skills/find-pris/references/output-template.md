# Output-skabelon

Brug dette format konsekvent i Trin 7. Det matcher mønsteret fra den inspirerende samtale: dansk, klar rangering, klar anbefaling, ingen unødvendigt fyld.

---

## Skabelon

```markdown
**[Produktnavn + variant]** (vejl. pris [valuta + beløb] hvis kendt)

| Forhandler | Pris | Efter rabat | Leveringstid | Note |
|---|---|---|---|---|
| [Forhandler 1] | [pris] | [pris efter rabat] | [på lager / X dage / Y uger] | [rabat anvendt, lagerstatus] |
| [Forhandler 2] | [pris] | [pris efter rabat] | [...] | [...] |
| ... |

**Billigst på papir:** [Forhandler X] — [pris] efter [rabat anvendt]. [Kort note om hvorfor.]

**Billigst i praksis:** [Forhandler Y] — [pris]. [Kort note om hvorfor det er nemmest / sikrest / hurtigst, hvis forskelligt fra "papir".]

**Caveats du skal vide:**
- [14-dages returret nævnt hvis relevant]
- [Trustpilot-leveringsstatus hvis skrøbeligt eller dyrt produkt]
- [Kampagne-udløbsdato hvis kampagnedrevet pris]
- [Eventuelle forsendelses- eller moms-overraskelser]
- [Hvis koden ikke er testet i kurv: marker eksplicit "test selv før betaling"]

**Næste skridt:**
1. [Konkret handling — fx "Læg i kurv på X.dk og test rabatkode YYY i checkout"]
2. [Konkret handling — fx "Tilmeld nyhedsbrev hos Z for 10% kode, kommer i mail inden for 5 min"]
3. [Konkret handling — fx "Bekræft fragtomkostning i checkout før betaling"]
```

---

## Hvorfor leveringstid er en obligatorisk kolonne

Lære fra tidligere søgninger: forskellen mellem "Ready to Ship" (1 uge) og "8-10 uger" er ofte vigtigere for brugeren end de sidste 200 kr. i besparelse. Ved at gøre leveringstid til en fast kolonne, undgår du at brugeren først opdager forskellen ved at læse "Note"-kolonnen.

Standardformater:
- "På lager" eller "Klar til afsending" — for varer der sendes inden for få dage
- "X-Y dage" — for kortere ventetider
- "X-Y uger" — for længere ventetider (bestilling fra leverandør)
- "Kontakt for tidsestimat" — hvis ikke vist

---

## Eksempel (Moustache Bold Chair Blue, maj 2026)

```markdown
**Moustache Bold Chair, Blue** (vejl. pris €480 / ~DKK 3.580)

| Forhandler | Pris | Efter rabat | Leveringstid | Note |
|---|---|---|---|---|
| Mohd Shop (IT) | 3.668,83 kr. | **2.935,06 kr.** | 22-29 maj | STOCK20 (-20%) virker, gratis fragt DK, 25% DK moms inkl. |
| Smallable (FR) | 3.265 kr. (€438,20) | 3.265 kr. | På lager (få tilbage) | Sale -20%, kuponer afvises |
| Silvera (FR) | €480 | ~3.690 kr. (€495) | 8-10 uger | SPRING15 (-15%), €70 fragt til DK |
| Moustache.fr | €480 | ~3.725 kr. | Spørg producent | Officiel, ingen offentlige rabatter |

**Billigst på papir:** Mohd Shop — 2.935 kr. efter STOCK20. Verificeret i kurv. Bemærk: skal vælge Blue i finish-dropdown.

**Billigst i praksis:** Mohd Shop — samme. Også hurtigst leveringstid (på lager, levering ~en uge), gratis fragt og solid Trustpilot.

**Caveats du skal vide:**
- 14-dages returret gælder ved fjernsalg i EU
- Default farve på Mohd er "Sparkling Red" — du SKAL vælge Blue manuelt
- Verificér Blue er "Ready to Ship" (ikke alle farver er på lager)
- STOCK20 vilkår: "Coupons cannot be combined" → vælg STOCK20, ikke nyhedsbrevs-rabat

**Næste skridt:**
1. Gå til shop.mohd.it/en/chair-bold-moustache.html?country=DK&currency=DKK
2. Vælg Blue i "Choose the Finish" → Add to cart
3. I kurv: indtast STOCK20 → Apply → verificér 20% rabat anvendt
4. Betal gerne med AmEx Platinum / premium-kort for forlænget garanti
```

---

## Stil-noter

- **Hold tabellen tæt** — maks 4-5 forhandlere. Inkluder kun dem brugeren realistisk kan bruge.
- **Skriv priser i hele kroner** — afrunding gør tabellen scanbar. Brug komma eller punktum konsekvent (dansk konvention: 2.935,06 kr.).
- **Marker fed på "Efter rabat"-prisen** for den vindende række — gør hurtigt-scan nemt.
- **Vis altid både "på papir" og "i praksis"** — den ene er kroner-i-hånden, den anden er nemhed/sikkerhed/leveringstid. De er sjældent samme forhandler. Hvis de ER samme, sig det ("samme forhandler vinder begge").
- **Caveats skal være specifikke**, ikke generiske. "Tjek Trustpilot" er svagt; "Trustpilot viser 3.9 — enkelte forsinkelses-klager på store pakker" er stærkt.
- **Markér tydeligt om en kupon er testet i kurv eller blot foreslået**:
  - ✅ "Verificeret i kurv" = kode er testet og virker
  - ⚠️ "Test før betaling" = kode er fundet i kilde men ikke testet
- **Næste skridt skal være kommandoer, ikke spørgsmål.** "Læg i kurv på X og test koden" — ikke "Du kunne overveje at..."
- **Ingen emojis** medmindre brugeren bruger dem først.
