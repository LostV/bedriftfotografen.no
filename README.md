# Bedriftsfotografen

Porteføljeside med bestilling for **bedriftfotografen.no**, en del av [Næring i Nord](https://nin.no).

> Status: klikkbar skisse (wireframe). Ikke ferdig design. Alle bilder, turer, datoer og kundecase er eksempeldata.

## Innhold

- [`skisse/index.html`](skisse/index.html) – klikkbar skisse av forside, rute/dekning, bestilling, arbeid, tjenester og om
- [`docs/struktur.md`](docs/struktur.md) – konsept, sidestruktur og innholdsmodell

## Se skissen

Åpne skissen via en enkel lokal server (navigering mellom sidene virker ikke ved å dobbeltklikke på filen i alle nettlesere):

```bash
python3 -m http.server 4173 --directory skisse
```

Gå så til <http://localhost:4173>.

## Varianter for gjennomgang

Den gule linjen øverst bytter mellom tre bestillingsløsninger:

| Variant | Kort fortalt |
|---|---|
| **Ruten** | Kunden blir med på en forhåndsplanlagt tur med Daniel. Står på vent til rutinene for turene er på plass. |
| **Møtebooking** | Kunden booker et planleggingsmøte på 20 min. Fotograf (Daniel eller fra nettverket) avklares i møtet. |
| **Kombinert** | Daniels tur når han er i nærheten (lavest reisekostnad), ellers møte og fotograf fra nettverket. |

Knappen «Skjul notater» skjuler de gule forklaringene.
