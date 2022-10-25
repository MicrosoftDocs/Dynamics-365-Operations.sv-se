---
title: Göra färdiga varor fysiskt tillgängliga före bokföring i journaler
description: När en tillverkad artikel rapporteras som färdig registreras den som tillgänglig för ytterligare fysisk bearbetning och en eller flera journaler bokförs. I den här artikeln beskrivs hur du inaktiverar journalbokföring genom att aktivera dem för bearbetning av ett batchjobb i en meddelandekö.
author: johanhoffmann
ms.date: 08/02/2022
ms.topic: article
ms.search.form: ProdParameters, JmgProdParameters, InventLocation, JmgMES3PMessageProcessorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-08-02
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: ee767a5d7c3dca2681861802ae42d7a07217c54d
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689351"
---
# <a name="make-finished-goods-physically-available-before-posting-to-journals"></a>Göra färdiga varor fysiskt tillgängliga före bokföring i journaler

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

När en arbetare rapporterar en tillverkad artikel som färdig registrerar systemet den som tillgänglig för ytterligare fysisk bearbetning (t.ex. försändelse eller artikelinförsel). Under den här processen bokförs också en eller flera journaler (till exempel rapporten som färdig journal, plocklistejournal och flödeskortjournal). Om du vill göra dina artiklar fysiskt tillgängliga innan alla bokföringar har bearbetats kan du ställa in systemet för att inaktivera journalbokföringarna. Uppskjuten bokföringar hanteras sedan av ett batchjobb som bearbetar bokföringarna så som systemresurser tillåter.

I följande bild visas hur processer för bokföring av journaler startas både med och utan uppskjuten bokföring.

![Processen rapportera som färdig med och utan uppskjuten journalbokföring.](media/deferred-posting-flowchart.png "Processen rapportera som färdig med och utan uppskjuten journalbokföring")

## <a name="turn-on-deferred-journal-posting-for-your-system"></a>Aktivera uppskjuten journalbokföring för ditt system

Innan du kan använda uppskjuten journalbokföring måste den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *produktionskontroll*
- **Funktionsnamn:** *(Förhandsversion) Göra färdiga varor fysiskt tillgängliga före bokföring i journaler*

## <a name="set-up-journal-posting-options-for-reporting-as-finished"></a>Ställ in alternativ för journalbokföring för rapportering som färdigt

Arbetare kan rapportera artiklar som färdiga med någon av följande klienter:

- Webbklient
- Mobilappen Warehouse Management
- Körningsgränssnittet för produktionsgolvet

Webbklienten använder samma bokföringsmetodkonfiguration som mobilappen Lagerstyrning. Bokföringsmetoden som används i produktionsgolvskörningsgränssnittet måste dock konfigureras separat.

### <a name="set-journal-posting-options-for-the-web-client-and-the-warehouse-management-mobile-app"></a>Ställ in alternativ för journalbokföring för webbklienten och mobilappen Warehouse Management

I mobilappen rapporterar arbetare objekt som slutförda genom att öppna ett menyalternativ för en mobil enhet där värdet **Process för att skapa arbete** är *Rapportera som färdig* eller *Rapportera som färdig och inlagrad*. I webbklienten rapporterar arbetare artiklar som färdiga från listsidan **Alla tillverkningsorder** eller sidan **Tillverkningsorder (detaljer)**. Du kan konfigurera en standardmetod som gäller för hela företaget och du kan även ställa in åsidosättningar som är specifika för lagerstället efter behov.

Gör på följande sätt när du vill konfigurera en standardbokföringsmetod för hela företaget för att rapportera artiklar som färdiga från webbklienten eller i mobilappen Warehouse Management.

1. Gå till **Produktionskontroll \> Inställningar \> Produktionskontrollparametrar**.
1. På fliken **Journaler** i avsnittet **Rapportera journal som färdig** ange fältet **Bokföringsmetod** till något av följande värden:

    - *Omedelbar* – När en artikel rapporteras som färdig bearbetar systemet alla relaterade journalbokföringar innan den markerar den färdiga artikeln som fysiskt tillgänglig.
    - *Uppskjutet* – När en artikel rapporteras som färdig markerar systemet den färdiga artikeln som fysiskt tillgänglig och lägger till journalbokningarna i en meddelandekö. Systemet väntar inte förrän bokföringarna bearbetas fullständigt innan det markerar den färdiga artikeln som fysiskt tillgänglig.

Gör på följande sätt när du vill konfigurera lagerställespecifika åsidosättningar för standardbokföringsmetoden som är konfigurerad på sidan **Parametrar för produktionskontroll**.

1. Gå till **Warehouse Management \> Konfiguration \> Lagerindelning \> Lagerställen**.
1. Välj det lagerställe som ska ställas in.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **Lagerställe** i avsnittet **Produktionsorder** ange fältet **Bokföringsmetod** till något av följande värden:

    - *Ärva* – Det valda lagerstället ärver inställningen från sidan **Produktionskontrollparametrar**.
    - *Omedelbar* – När en artikel rapporteras som färdig bearbetar systemet alla relaterade journalbokföringar innan den markerar den färdiga artikeln som fysiskt tillgänglig.
    - *Uppskjutet* – När en artikel rapporteras som färdig markerar systemet den färdiga artikeln som fysiskt tillgänglig och lägger till journalbokningarna i en meddelandekö. Systemet väntar inte förrän bokföringarna bearbetas fullständigt innan det markerar den färdiga artikeln som fysiskt tillgänglig.

### <a name="set-journal-posting-options-for-the-production-floor-execution-interface"></a>Ställ in alternativ för journalbokföring för körningsgränssnittet för produktionsgolvet

Använd följande procedur för att konfigurera bokföringsmetoden som används när artiklar rapporteras som färdiga från gränssnittet för produktionsgolvskörning.

1. Gå till **Produktionsstyrning \> Inställningar \> Tillverkningskörning \> Standarder för produktionsorder**.
1. På fliken **Rapportera som färdigt** i avsnittet **Rapportera journal som färdig** ange fältet **Bokföringsmetod** till något av följande värden:

    - *Omedelbar* – När en artikel rapporteras som färdig bearbetar systemet alla relaterade journalbokföringar innan den markerar den färdiga artikeln som fysiskt tillgänglig.
    - *Uppskjutet* – När en artikel rapporteras som färdig markerar systemet den färdiga artikeln som fysiskt tillgänglig och lägger till journalbokningarna i en meddelandekö. Systemet väntar inte förrän bokföringarna bearbetas fullständigt innan det markerar den färdiga artikeln som fysiskt tillgänglig.

## <a name="schedule-the-message-processor-batch-job-to-process-deferred-postings"></a>Tidsplanering av batchjobbet för meddelandeprocessen för bearbetning av uppskjutna bokföringar

Batchjobbet för meddelandeprocessorn ansvarar för bearbetningen av journalbokföringarna efter att de har köat. För att säkerställa att dina journalbokföring bearbetas måste du konfigurera det här jobbet så att det körs regelbundet. Använd följande procedur när du ställer in önskat batchjobb.

1. Gå till **Systemadministration \> Meddelandeprocessor \> Meddelandeprocessor**.
1. Ställ in **Parametrar** anges till **Meddelandekö** till *Produktion*.
1. På snabbfliken **Kör i bakgrunden** ange alternativet **Batchbearbetning** till *Ja*. Konfigurera sedan ett återkommande schema och konfigurera andra inställningar efter behov. Inställningarna fungerar precis som de fungerar för andra typer av [bakgrundsjobb](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Microsoft Dynamics 365 Supply Chain Management.

## <a name="track-the-progress-of-your-deferred-postings"></a>Spåra förloppet för de uppskjutna bokföringarna

Uppskjutna journalbokföringar köas som *Meddelandeprocessormeddelanden* som väntar tills de bearbetas av *meddelandeprocessorn*. Meddelandeprocessorn bör ställas in för att köras som ett tidsplanerat batchjobb. För att se de uppskjutna inläggsmeddelanden som har eller kommer att behandlas av meddelandebehandlaren, gå till **Produktionskontroll \> Produktionsorder \> Bokföring av uppskjuten produktionsorder**.

### <a name="message-grid-columns-and-filters"></a>Kolumner och filter i meddelanderutnät

Med hjälp av fälten högst upp på sidan **Bokföring av uppskjuten produktionsorder** för att hitta specifika meddelanden som du letar efter.

Följande filter är tillgängliga:

- **Meddelandetyp** – Ange den typ av meddelanden som visas i rutnätet.
- **Meddelandets tillstånd** – Ange den typ av meddelanden som visa i rutnätet. Följande statuslägen finns:

    - *Köad* – Meddelandet är klart att bearbetas av meddelandeprocessorn.
    - *Bearbetades* – Meddelandet har bearbetats av meddelandeprocessorn.
    - *Annullerat* – Meddelandet misslyckades att bearbetas under det slutliga försöket och avbröts sedan av användaren.
    - *Misslyckat* – Meddelandet kunde inte bearbetas under det senaste försöket. Meddelanden som inte kunnat försöka igen försöks tre gånger. Det ger sedan upp och låter meddelandet vara *misslyckat*. Observera att du inte kan avbryta eller redigera ett meddelande manuellt förrän efter det sista av dessa tre försök.

- **Meddelandeinnehåll** – Detta filter genomför en fulltextsökning av meddelandeinnehåll. (meddelandeinnehållet visas inte i rutnätet). Filtret behandlar de flesta specialtecken (exempelvis bindestreck) som blanksteg, och behandlar alla blanksteg som booleska OR-operatorer. Till exempel om du söker efter en specifik `journalid` värde som är lika *USMF-123456*, kommer systemet att hitta alla meddelanden som innehåller "USMF" eller "123456". I så fall kommer listan med resultat troligen att vara lång. Därför är det bättre att enbart ange *123456* eftersom detta ger mer specifika resultat.

Du kan också sortera och filtrera listan genom att välja någon av kolumnrubrikerna och ange kriterier i dialogrutan.

### <a name="view-the-message-log-message-content-and-details"></a>Visa meddelandelogg, meddelandeinnehåll och detaljerad information

Du hittar detaljerad information om ett meddelande genom att markera det i rutnätet och sedan välja fliken **Logg** eller **Råinnehåll** under meddelanderutnätet, där respeltive bearbetningshändelse visas.

Verktygsfältet på fliken **Logg** innehåller följande knappar:

- **Logg** – Välj den här knappen om du vill visa bearbetningsresultaten. Den här knappen är särskilt användbar när meddelanden har ett värde för **Bearbetningsresultat** som *Misslyckat* som inte kunde användas och du vill ta reda på orsakerna till att bearbetningen misslyckades.
- **Bunt** – Flera funktioner för meddelandebearbetning kan köras som en del i samma batchprocess. Välj den här knappen om du vill visa denna detaljerade information. Du kan till exempel se om det finns beroenden som kräver en specifik bearbetningsordning för vissa meddelanden.

### <a name="manually-process-or-cancel-a-message"></a>Bearbeta eller avbryta ett meddelande manuellt

Om det behövs kan du manuellt bearbeta eller avbryta ett meddelande, beroende på dess aktuella status. Detta gör du genom att markera meddelandet i rutnätet och sedan välja **Bearbeta** eller **Avbryt** i åtgärdsfönstret.

### <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Ställa in affärshändelser för leverans av notifieringar för misslyckade bearbetningsresultat

Du kan ställa in [affärshändelser](../../fin-ops-core/dev-itpro/business-events/home-page.md) som varnar dig om misslyckade bearbetningsresultat. Gå till **Systemadministration \> Inställningar \> Affärshändelser \> Katalog för affärshändelser** och aktivera affärshändelsen som är namngiven *Meddelandeprocessormeddelande bearbetat*.

Under aktiveringsprocessen uppmanas du att ange om händelsen är specifik för en juridisk person eller gäller för alla juridiska personer. Du uppmanas också att ange ett värde för **slutpunktsnamn**. Detta värde måste definieras först.

> [!NOTE]
> Om fältet **När en affärshändelse inträffar** anges som *Microsoft Power Automate* (i stället för exempelvis *HTTPS*) kommer värdet **Slutpunktsnamn** automatiskt att skapas i Supply Chain Management baserat på *Microsoft Power Automate*-inställningarna.
