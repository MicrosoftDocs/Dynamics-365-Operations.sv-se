---
title: Parametrar för Tillgångshantering
description: I Tillgångshantering måste allmänna parametrar som hänför sig till tillgångar, arbetsorder och schemaläggning av arbetsorder ställas in.
author: johanhoffmann
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 750776412ce9d87389a635ef108a34cffe12b68b
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015824"
---
# <a name="asset-management-parameters"></a>Parametrar för Tillgångshantering

[!include [banner](../../includes/banner.md)]

I Tillgångshantering måste allmänna parametrar som hänför sig till tillgångar, arbetsorder och schemaläggning av arbetsorder ställas in. Denna artikel innehåller information om hur du konfigurerar dem. Välj **Tillgångshantering** > **inställningar** > **Tillgångshanteringsparametrar** för att öppna sidan.

> [!NOTE]
> Om du vill konfigurera ett system som innehåller demodata för att testa funktionerna för Tillgångshantering läser [distribuera en demomiljö](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) för instruktioner.

## <a name="the-assets-tab"></a>Fliken Tillgångar

På fliken **Tillgångar** finns följande inställningar:

- **Standardfunktionsplats plats** är standardfunktionsplats, som väljs automatiskt på tillgångar när du skapar nya tillgångar.  
- I den **standardkalender** väljer du en kalender som ska användas för att beräkna tillgångens KPI:er, om ingen resurs har valts på en tillgång.  
- I fältet **Visa** väljer standardvy som visas när du öppnar **Tillgångsvy** (**Tillgångshantering** > **Allmänt** > **Tillgångar**).
- **Standardbegärandetyp** är standardtypen för underhållsbegäran som väljs automatiskt när du skapar en ny begäran.  
- Prognoser för jobbtyper lagras i det projekt som valts i fältet **prognosprojekt**. För varje jobbtyp skapas en ny aktivitet automatiskt i prognosprojektet. Prognoser för jobbtypen sparas sedan i prognosprojektet.  
- I fältet **modell** väljer du den prognosmodell som används för jobbtyp och arbetsorderprognoser.

## <a name="the-work-orders-tab"></a>Fliken Arbetsorder

På fliken **Arbetsorder** finns följande inställningar:

- **Standardarbetsordertyp** definierar standardinställningar när du skapar en arbetsorder.  
- **Förebyggande arbetsordertyp** definierar den arbetsordertyp som används när du skapar arbetsorder från underhållsplaner. Om fältet lämnas tomt används arbetsordertypen i fältet **standardarbetsordertyp**.  
- I fältet **relaterad arbetsordermask** definierar du det maximala antalet arbetsorder som kan relateras till en arbetsorder. Till exempel ## låter dig ha upp till 99 relaterade arbetsorder. Om du definierar en mask enligt beskrivningen här kommer relaterade arbetsorder att numreras [arbetsorder-ID för arbetsordern som en arbetsorder är relaterad till]-01, -02, -03 och så vidare. Om du inte definierar en mask i det här fältet kommer en relaterad arbetsorder att få nästa sekventiella arbetsorder-ID.  
- Välj **Ja** för **Kopieringsfel** som du automatiskt vill kopiera fel som registrerade på underhållsförfrågningar till relaterade arbetsorder. 
- I fältet **nivå** definierar du den funktionsplatsnivå som infogas automatiskt på en arbetsorder om alla relaterade arbetsorderjobb refererar till samma funktionsplats. Om inte alla arbetsorderjobb relaterar till samma funktionsplats på den definierade nivån, lämnas fältet **funktionsplats** tomt på arbetsordern. Om du till exempel infogar siffran "1" i det här fältet är det den översta nivån i en funktionsplatsstruktur. Om du infogar siffran "0" i det här fältet har du inte definierat en specifik funktionsplatsnivå, endast att alla arbetsorderjobb på en arbetsorder måste relateras till samma funktionsplats för att funktionsplatsen ska läggas till i arbetsordern.  
- Journaler som används vid bokföring av förbrukning på en arbetsorder kan väljas på snabbfliken **allmänt** i fälten **timme**, **artikel** och **utgift**.  
- I fältet **produktensspråkkälla** väljer du vilket språk som ska användas för produktnamn i Tillgångshanteringsrapporter. Du kan välja det språk som ställts in på företagskontot eller det språk som ställts in för den inloggade användaren.  
- Välj **Ja** på **Uppdateringar i realtid** om du vill att ändringar automatiskt ska uppdateras till standardvärden för jobbtyp, underhållsplaner och underhållsomgångar.
  - Om du väljer **Nej** uppdateras inte ändringar av standardvärden för jobbtyp, underhållsplaner och underhållsomgångar automatiskt i tillgångshanteraren.
  - Välj **nej** om du har stora mängder data som ska synkroniseras, till exempel många tillgångar eller funktionsplatser som ställts in på underhållsplaner eller underhållsomgångar eller ett stort antal underhållsplaner eller rundor.  
  - Om du gör ändringar i standardvärden för jobbtyp eller underhållsplaner eller underhållsomgångar och du har valt **nej** till uppdatering i realtid visas kanske inte en varning om ändringarna påverkar:
    - Funktionsplatser som ställts in på underhållsplaner eller omgångar  
    - Objekt som ställts in på underhållsplaner eller -omgångar  
    - Inställningar för underhållsplaner  
    - Inställningar för underhållsomgångar  
- På snabbfliken **kategori** kan standardkategorier som relaterar till förbrukning på arbetsorder definieras.  

## <a name="the-work-order-scheduling-tab"></a>Fliken Schemaläggning av arbetsorder

På fliken **Schemaläggning av arbetsorder** finns följande inställningar på snabbfliken **Allmänt**:

- **Tidsplanera tidsgräns** definierar period i dagar, beräknad från det förväntade startdatumet för arbetsordern, under vilken arbetsorderjobb planeras.  
- **Huvudplanen** relaterar till resurser i modulen **Organisationsadministration**. Om du väljer en huvudplan i det här fältet kan du se kapacitetsreservationer som är relaterade till arbetsorder i **Kapacitetsreservationer** (**Organisationsadministration** > **Resurser** > **Resurser** fliken > Välj resurs > **Resurs** > knappen **Kapacitetsreservationer**). Om du lämnar detta fält tomt, kommer du att kunna se kapacitetsbelastning relaterad till arbetsorder i **Kapacitetsbeläggning** (**Organisationsadministration** \> **Resurser** \> **Resurser** \> välj resurser \> fliken **Resurs** knappen \> **Kapacitetsbeläggning**).  

>[!NOTE]
>Valet om att använda en huvudplan i modulen **Tillgångshantering** och det relaterade formuläret som används för att få en översikt över kapacitetsreservationer eller kapacitetsbeläggning är standardinställningar. Beroende på inställningarna i fältet **Huvudplan** kommer du att kunna komma åt kapacitetsinformation i antingen **kapacitetsreservationer** eller **kapacitetsbeläggning** i modulen **organisationsadministration**. Det går inte att skapa en inställning där kapacitetsreservationer visas i båda vyerna.  

Fälten som beskrivs i följande lista relaterar till beräknade bedömningspoäng, som används för att beräkna arbetsorderprioritet under arbetsorderplanering.

- **Prioritet**- en bedömningspoäng som beräknats tillsammans med poängen i fälten **allvarlighetsgrad** och **startdatum**. Numret i det här fältet divideras med numret i fältet **prioritet** på en arbetsorder. För exempel om värdet "5,00" infogas i det här fältet och en arbetsorder har prioritet "20", är bedömningspoängen för prioritet 0,25.  
- **Allvarlighetsgrad**- en bedömningspoäng som beräknats tillsammans med poängen i fälten **Prioritet** och **Startdatum**. Numret i det här fältet multipliceras divideras med numret i fältet **Allvarlighetsgrad** på en arbetsorder. Om till exempel värdet "10,00" infogas i det här fältet och en arbetsorder har allvarlighetsgrad "5", är bedömningspoängen för allvarlighetsgrad 50.  
- **Startdatum**- en bedömningspoäng som beräknats tillsammans med poängen i fälten **Prioritet** och **Allvarlighetsgrad**. I det här fältet anges den dagliga poängen som ett negativt värde och jämförs med fältet **förväntad start** på en arbetsorder. Om till exempel värdet "10,00" infogas i det här fältet och det förväntade startdatumet för en arbetsorder är tre dagar från nu, är bedömningsresultatet minus 30,00. Lägga till resultaten av 0,25 och 50 från exemplen i fälten **prioritet** och **allvarlighetsgrad** som beskrivs ovan ger totalt plus 20,25. Det numret jämförs med alla andra bedömningspoäng för arbetsorder under planering av arbetsorder och de högsta bedömningspoängen planeras sedan först.  
- **Ansvarig arbetar** - ett bedömningspoäng som beräknats tillsammans med **ansvarig arbetargrupp**, **önskad arbetare**, **önskad arbetargrupp**, **tillgångsplats** och **startdatum** för bedömningspoängvärden. Om värdet "50,00" infogas i det här fältet och en ansvarig arbetare har valts på en arbetsorder, får arbetaren 50 poäng i den totala arbetarberäkningen under arbetsorderplaneringen.  
- **Ansvarig arbetargrupp** - ett bedömningspoäng som beräknats tillsammans med **ansvarig arbetare**, **önskad arbetare**, **önskad arbetargrupp**, **tillgångsplats** och **startdatum** för bedömningspoängvärden. Om värdet "50,00" infogas i det här fältet och en ansvarig arbetare har valts på en arbetsorder, får arbetaren 50 poäng i den totala arbetarberäkningen under arbetsorderplaneringen.  
- **Gräns för ansvarig** begränsar antalet arbetare som är tillgängliga för planering av arbetsorder. Välj **nej** om du vill beräkna en poäng för alla arbetare, oavsett att de är inställda som ansvariga arbetare eller en del av en ansvarig arbetsgrupp. Välj **Ja** om du vill beräkna en poäng för arbetare som har ställts in som ansvarig arbetare på arbetsordern och/eller ingår i en ansvarig arbetsgrupp som valts på arbetsordern.  
- **Önskad arbetare** - ett bedömningspoäng som beräknats tillsammans med **ansvarig arbetare**, **önskad arbetare**, **önskad arbetargrupp**, **tillgångsplats** och **startdatum** för bedömningspoängvärden. De fyra bedömningspoängen beräknas och läggs ihop för att ge en poäng som används för att välja vilken arbetare som ska tilldelas till vilken arbetsorder under arbetsorderplaneringen. Om värdet "10,00" infogas i det här fältet och en arbetare har valts som önskad arbetare på en arbetsorder, får arbetaren 10 poäng i den totala arbetarberäkningen under arbetsorderplaneringen.  
- **Önskad arbetargrupp** - ett bedömningspoäng som beräknats tillsammans med **ansvarig arbetare**, **önskad arbetare**, **önskad arbetargrupp**, **tillgångsplats** och **startdatum** för bedömningspoängvärden. Om värdet "10,00" infogas i det här fältet och en arbetare har tilldelats en önskad arbetargrupp som valts på en arbetsorder, får arbetaren 10 poäng i den totala arbetarberäkningen under arbetsorderplaneringen.  
- **Gräns för önskad** begränsar antalet arbetare som är tillgängliga för planering av arbetsorder. Välj **nej** om du vill beräkna en poäng för alla arbetare, oavsett att de är inställda som önskade arbetare eller en del av en önskad arbetsgrupp. Välj **ja** om du bara vill beräkna en poäng för alla arbetare som är inställda som önskade arbetare och/eller inkluderade i en önskad arbetsgrupp.  
- **Plats** - ett bedömningspoäng som beräknats tillsammans med **ansvarig arbetare**, **önskad arbetare**, **önskad arbetargrupp**, **tillgångsplats** och **startdatum** för bedömningspoängvärden. Om värdet "3 000,00" infogas i det här fältet får en arbetare 3 000 poäng i beräkningen om arbetaren finns i samma fabrik eller anläggning som den tillgång som ett jobb ska tidsplaneras.  
  - Om ditt företag använder funktionsplatser får arbetarna full poäng om de finns på den funktionsplats som är relaterad till tillgången. Om funktionsplatsen för tillgången har en överordnad tillgång, får arbetare på funktionsplatsen 1/2 poäng. Om den platsen också har en överordnad får arbetare på den platsen 1/3 poäng. Om den platsen också har en överordnad får arbetare på den platsen 1/4 poäng, osv.  
  - Om ditt företag använder tillgångsplats, som vi inte rekommenderar, används plats, område och zon för att beräkna platspoäng. Arbetare får full poäng om de finns på platsen och området och zonen som är relaterade till tillgången. Om arbetsplatsen endast matchar plats och område, är poängen för arbetaren 2/3 av hela poängen. Om arbetsplatsen endast matchar plats är poängen för arbetaren 1/3 av hela poängen.  
- **Gräns för plats** begränsar antalet arbetare som är tillgängliga för planering av arbetsorder. Välj **Nej** om du vill beräkna en poäng för alla arbetare över alla funktionsplatser. Välj **Ja** om du bara vill beräkna en poäng för arbetare som är associerade med arbetsorderns funktionsplats.

>[!NOTE]
>De tre fälten "gränsen till" introduceras för att öka hastigheten på arbetsorderplaneringen genom att begränsa antalet poäng som beräknas för arbetare.

**Arbetares startdatum** - ett bedömningspoäng som beräknats tillsammans med **ansvarig arbetare**, **önskad arbetare**, **önskad arbetargrupp**, **tillgångsplats** och **startdatum** för bedömningspoängvärden. I det här fältet anges den dagliga poängen som ett negativt värde och jämförs med fältet **förväntad start** på en arbetsorder. Om värdet "10,00" infogas i det här fältet och det förväntade startdatumet för en arbetsorder är imorgon, är bedömningsresultatet minus 10,00.

  - Om du antar att ingen ansvarig arbetare och ansvarig arbetargrupp har valts på en arbetsorder som ska tidsplaneras lägger du till och subtraherar värdena för bedömningspoängvärderingen i exemplen i **önskad arbetare** i **önskad arbetargrupp** och **tillgångens plats** och **startdatum** ovan får du totalt 3 010,00. Det innebär en hög poäng för arbetaren som redan har valts som önskad arbetare samt inkluderas i den önskade arbetargruppen på arbetsordern, och arbetaren finns också i samma anläggning som tillgångenför ett jobb som behöver tidsplaneras. Det innebär detta att det finns en god chans att arbetare i fråga kommer att väljas för att slutföra jobbet under tidsplaneringen av arbetsordern.  
  - Om värdet "0,00" infogas i något av de åtta fälten ovan, används inte bedömningspoängen undertidsplaneringen av arbetsordern.  

## <a name="the-document-types-tab"></a>Fliken Dokumenttyper

Välj de dokumenttyper som ska vara tillgängliga för utskrift av bilagor relaterade till en arbetsorderrapport. Detta görs genom att välja en dokumenttyp i avsnittet **tillgängliga** och välja ![framåtpilknappen.](media/15-setup-for-objects.png). Om du vill ta bort en vald dokumenttyp väljer du dokumenttypen i avsnittet **Markerade** och klickar på ![bakåtpilknappen](media/16-setup-for-objects.png).

## <a name="the-number-sequences-tab"></a>Fliken Nummerserie

Välj de nummerserier som krävs i det här avsnittet. Det finns två nummerserier för tillgångar: en för manuellt skapade tillgångar och en för tillgångar som skapats via väntande tillgångar.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
