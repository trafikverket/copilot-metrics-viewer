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

1. Innan appen kan startas behöver du lägga in en dekrypteringsnyckel för hemligheterna som behövs i runtime. Gör detta genom att skapa filen `.env.keys`:

    ```env
    #/------------------!DOTENV_PRIVATE_KEYS!-------------------/
    #/ private decryption keys. DO NOT commit to source control /
    #/     [how it works](https://dotenvx.com/encryption)       /
    #/----------------------------------------------------------/

    # .env.production
    DOTENV_PRIVATE_KEY_PRODUCTION="HEMLIGNYCKELHÄR"
    ```

2. Starta appen och injektera hemligheterna: `dotenvx run -f .env -- npm run dev`

### Produktion i Containerplattformen (Pågående)

Fyll på instruktioner här.

## Uppbyggnad

Detta projekt är skapat genom att klona ovan nämnt repo samt följande modifikationer och tillägg:

- Lagt till dotenvx för hantering av hemligheter i kod.
- Tagit bort beroenden som försöker ladda hem innehåll från internet.
- Lagt till biome för formattering.
- Lagt till en `.npmrc`-fil för att npm ska installera paket från ProGet.
- Lagt till denna dokumentation.
