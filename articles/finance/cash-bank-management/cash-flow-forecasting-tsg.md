---
title: Felsöka inställningar för kassaflödesprognoser
description: Detta ämne innehåller svar på frågor som du kan ha när du konfigurerar kassaflödesprognoser. Det avhandlar vanliga frågor och svar (FAQ) om hur du ställer in kassaflöde, uppdateringar av kassaflöde och Power BI-kassaflöde.
author: angelad116
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 807a1da1906bdefec38954cea02ed29b0157d69e
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151414"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>Felsöka inställningar för kassaflödesprognoser

[!include [banner](../includes/banner.md)]

Detta ämne innehåller svar på frågor som du kan ha när du konfigurerar kassaflödesprognoser. Det avhandlar vanliga frågor och svar (FAQ) om hur du ställer in kassaflöde, uppdateringar av kassaflöde och Power BI-kassaflöde.

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a>Varför visas kassaflöde endast för en enda juridisk person?

Kassaflödesprognoser konfigureras och beräknas per juridisk person. Power BI-rapporter och funktionen för kassaflödesprognoser i Finance Insights visar resultaten.

Kassaflödesprognoser måste ställas in för varje enskild juridisk person som du vill visa en prognos för. Granska konfigurationen för kassaflödesprognoser i alla dina juridiska personer. Du kan också granska konfigurationen för alla juridiska personer för kassaflödesprognos och kontrollera att dessa är inställda på det sätt som du har tänkt dig.

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a>Varför visar Power BI inte alla kassaflödesdata?

Flera steg måste utföras innan kassaflödesprognoser kan visas i Power BI-vyer. Granska följande checklista och se till att varje steg har slutförts:

- Ställ in kassaflödet för varje juridisk person.
- Ange systemets valuta och systemets valutakurstyp i redovisningsparametrarna.
- Ställ in redovisningsvalutan och valutakurstypen.
- Ange valutakurserna mellan transaktionsvalutan och redovisningsvalutan.
- Ange valutakurserna mellan redovisningsvalutan och systemvalutan.
- Ange valutakurserna mellan redovisningsvalutan och respektive bankvaluta.

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a>Varför fungerade kassaflödet i Power BI i tidigare versioner men är nu tomt?

Kontrollera att mätningarna "Kassaflödesmått V2" och "LedgerCovLiquidityMeasurement" från Entitetsarkivet har konfigurerats. Mer information om hur du gör en arbeta med data i enhetslagring, se [Power BI-integrering med enhetslagring](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md). Kontrollera att alla steg som behövs för att visa Power BI innehåll har slutförts. Mer information finns i [Kassaöversikt Power BI-innehåll](Cash-Overview-Power-BI-content.md).

## <a name="have-the-entity-store-entities-been-refreshed"></a>Har Entitetsarkivets entiteter uppdaterats?

Du måste uppdatera dina entiteter regelbundet för att se till att datan är aktuell och korrekt. Du uppdaterar en specifik entitet manuellt genom att gå till **Systemadministration \> Inställningar \> Entitetsarkiv**, välja eniteten och sedan **Uppdatera**. Det går också att uppdatera data automatiskt. På sidan **Entitetsarkiv** anger du alternativet **Automatisk uppdatering aktiverad** som **Ja**.

## <a name="which-calculation-method-should-be-used-when-calculating-cash-flow-forecasts"></a>Vilken beräkningsmetod ska användas vid beräkning av kassaflödesprognoser?

Beräkningsmetod för kassaflödesprognos har två viktiga alternativ. Med alternativet **Nytt** beräknas kassaflödesprognoser för nya dokument och dokument som har ändrats sedan det senaste batchjobbet kördes. Det här alternativet gör att processen blir snabbare eftersom den bearbetar en mindre delmängd av dokumenten. Alternativet **Summa** beräknar om kassaflödesprognoser för varje dokument i systemet. Det här alternativet tar längre tid eftersom det har mer arbete att slutföra.

### <a name="how-do-i-improve-the-performance-of-the-cash-flow-forecasting-recurring-batch-job"></a>Hur kan jag förbättra prestandan för kassaflödesprognoser för återkommande batchjobb?

Vi rekommenderar att du kör kassaflödesprognosen en gång om dagen när belastningen är låg med den **Nytt** beräkningsmetoden. Vi rekommenderar att du använder den här metoden sex dagar per vecka. Kör sedan en kassaflödesprognos en gång per vecka med hjälp av beräkningsmetoden **Summa** för dagen med den minsta aktivitetsmängden.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

