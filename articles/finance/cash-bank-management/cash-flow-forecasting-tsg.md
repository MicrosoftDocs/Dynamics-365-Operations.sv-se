---
title: Felsöka inställningar för kassaflödesprognoser
description: Detta ämne innehåller svar på frågor som du kan ha när du konfigurerar kassaflödesprognoser. Det avhandlar vanliga frågor och svar (FAQ) om hur du ställer in kassaflöde, uppdateringar av kassaflöde och Power BI-kassaflöde.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 89eb2f1bcfc73a6a7171a275532b2356e858e87c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985297"
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

Kontrollera att mätningarna "Kassaflödesmått V2" och "LedgerCovLiquidityMeasurement" från Entitetsarkivet har konfigurerats. Mer information om hur du arbetar med data i Entitetsarkivet finns i [Power BI-integrering med Entitetsarkivet](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Kontrollera att alla steg som behövs för att visa Power BI-innehåll har slutförts. Mer information finns i [Kassaöversikt Power BI-innehåll](Cash-Overview-Power-BI-content.md).

## <a name="have-the-entity-store-entities-been-refreshed"></a>Har Entitetsarkivets entiteter uppdaterats?

Du måste uppdatera dina entiteter regelbundet för att se till att datan är aktuell och korrekt. Du uppdaterar en specifik entitet manuellt genom att gå till **Systemadministration \> Inställningar \> Entitetsarkiv**, välja eniteten och sedan **Uppdatera**. Det går också att uppdatera data automatiskt. På sidan **Entitetsarkiv** anger du alternativet **Automatisk uppdatering aktiverad** som **Ja**.
