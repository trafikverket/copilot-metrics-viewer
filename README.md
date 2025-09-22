# GitHub Copilot Metrics Viewer

Detta repo innehåller webbappen GitHub Copilot Metrics Viewer från [github.com/github-copilot-resources/copilot-metrics-viewer](https://github.com/github-copilot-resources/copilot-metrics-viewer). För dokumentation om detta, se filen [COPILOT_METRICS_VIEWER.md](./COPILOT_METRICS_VIEWER.md).

## Uppbyggnad

Detta projekt är skapat genom att klona ovan nämnt repo samt följande modifikationer och tillägg:

- Lagt till dotenvx för hantering av hemligheter i kod.
- Tagit bort beroenden som försöker ladda hem innehåll från internet.
- Lagt till biome för formattering.
- Lagt till en `.npmrc`-fil för att npm ska installera paket från ProGet.
- Lagt till denna dokumentation.

## Kom igång

### Hentera hemligheter i kod med dotenvx

För att underlätta hantering av hemligheter används dotenvx. Se följande guide för hur du använder detta verktyg: [https://dotenvx.com/docs/quickstart](https://dotenvx.com/docs/quickstart). Kortfattat så används följanbde kommandon för att manuellt avkryptera och kryptera `.env`-filerna.

- Avkryptera fil: `dotenvx decrypt -f .env`
- Kryptera fil: `dotenvx encrypt -f .env`
- Kör kommando och injicera hemligheter: `dotenvx run -f .env -- npm run dev`

För att ändra en hemlighet, sätt önskat värde för en miljövariabeln och kryptera om filen efter ändring.

Innan appen kan startas behöver du lägga in en dekrypteringsnyckel för hemligheterna som behövs i runtime. Gör detta genom att skapa filen `.env.keys`:

```env
#/------------------!DOTENV_PRIVATE_KEYS!-------------------/
#/ private decryption keys. DO NOT commit to source control /
#/     [how it works](https://dotenvx.com/encryption)       /
#/----------------------------------------------------------/
# .env.production
DOTENV_PRIVATE_KEY_PRODUCTION="HEMLIGNYCKELHÄR"
```

### Starta appen lokalt

1. Installera beroenden: `npm install`
2. Starta app
    - Produktionsbygge: `npm run build && dotenvx run -f .env -- node .output/server/index.mjs`
    - Devserver med hot reload: `dotenvx run -f .env -- npm run dev`

### Kör i produktion

Fyll på instruktioner här.
