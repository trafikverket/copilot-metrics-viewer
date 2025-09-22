# GitHub Copilot Metrics Viewer

Detta repo innehåller webbappen GitHub Copilot Metrics Viewer från [github.com/github-copilot-resources/copilot-metrics-viewer](https://github.com/github-copilot-resources/copilot-metrics-viewer). För dokumentation om detta, se filen [COPILOT_METRICS_VIEWER.md](./COPILOT_METRICS_VIEWER.md).

## Kom igång

## Hentera hemligheter i kod med dotenvx

För att underlätta hantering av hemligheter används dotenvx. Se följande guide för hur du använder detta verktyg: [https://dotenvx.com/docs/quickstart](https://dotenvx.com/docs/quickstart). Kortfattat så används följanbde kommandon för att manuellt avkryptera och kryptera `.env`-filerna.

- Avkryptera fil: `dotenvx decrypt -f .env`
- Kryptera fil: `dotenvx encrypt -f .env`
- Kör kommando och injicera hemligheter: `dotenvx run -f .env -- npm run dev`

För att ändra en hemlighet, sätt önskat värde för en miljövariabeln och kryptera om filen efter ändring.

### Utveckling

1. Innan appen kan startas behöver du lägga in en dekrypteringsnyckel för hemligheterna som behövs i runtime.
2. Starta appen och injektera hemligheterna: `dotenvx run -f .env -- npm run dev`

### Produktion i Containerplattformen (Pågående)

Fyll på instruktioner här.
