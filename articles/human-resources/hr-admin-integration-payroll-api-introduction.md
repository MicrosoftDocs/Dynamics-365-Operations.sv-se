---
title: Introduktion till API för löneintegrering
description: Detta ämne beskriver API för löneintregrering i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4c71d31d7045c73097b81671793181a29dcac3b5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8064951"
---
# <a name="payroll-integration-api-introduction"></a>Introduktion till API för löneintegrering


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta dokument beskriver API för löneintregrering i Dynamics 365 Human Resources. Med API:t kan du effektivisera kompletta integreringar mellan Personal och associerade lönesystem. Den integrerade erfarenheten startar i Personal med medarbetarprofil, löne- och avdragsinformation och bidragsinformation. När du anställer en medarbetare och anger den nödvändiga profil- och löneinformationen i Personal hämtar lönesystemet denna information i samband med bearbetning av löner. Eventuella uppdateringar av medarbetar- eller löneinformationen kan också användas vid senare lönekörningar.

[![Löneintegreringsflöde.](media/hr-admin-integration-payroll-api-introduction-flow.png)](media/hr-admin-integration-payroll-api-introduction-flow-2.png#lightbox)

För att aktivera integreringen lägger Personal till följande komponenter:

- [Funktion för att markera en medarbetare som betalningsredo.](hr-compensation-payroll.md)
- Ett integrations-API som öppnar den nya funktionen för integrering av program.

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Detta API bygger på Microsoft Dataverse (tidigare Common Data Service). All RESTful-interaktion med denna API sker via webb-API för Microsoft Dataverse, som använder OData. Detta API är en underuppsättning av webb-API för Dataverse. Webb-API för Dataverse definierar egenskaper såsom autentisering, serviceavtal, batch, samtidighetskontroll och felhantering.

Mer allmän information om webb-API för Microsoft Dataverse finns här:

- [Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)
- [Använd webb-API för Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)
- [Utvecklarguide för Microsoft Dataverse](/powerapps/developer/data-platform)

Dokumentationen innehåller information och utvecklarvägledning för användning av webb-API för Dataverse, bland annat följande ämnen:

- [Autentisera till Microsoft Dataverse med hjälp av webb-API:t](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [Utföra åtgärder med hjälp av webb-API:t](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [Använda Postman med webb-API:t](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [Använda ändringsspårning för att synkronisera data med externa system](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Virtuella register för Personal i Dataverse

Slutpunkterna för API för löneintegrering använder plattformsfunktionerna för virtuellt register i Microsoft Dataverse. Som standard distribueras inte de virtuella registren och deras associerade API-slutpunkter för Personal-miljöer, vilket låter organisationer avgöra vilka OData-slutpunkter som ska visas för miljön. Om du vill använda API:t måste de virtuella registren för Personal-entiteterna genereras för miljön.

Information om hur du genererar virtuella register för API:et finns i [Konfigurera virtuella Dataverse-register](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="data-model"></a>Datamodell

Följande diagram visar relationer inom API:t. Flera typer har utländska nycklar till andra, befintliga entiteter i Personal som inte visas här. Detta dokument innehåller information om entiteter som är specifika för löneintegreringsscenarier. Det finns emellertid många andra entiteter i webb-API:t för Dataverse för Personal som också kan vara relevanta för din integrering. Vissa av dessa entiteter refereras till i relationer med sekundärnycklar eller navigeringsegenskaper.

[![API-datamodell för löneintegrering.](media/hr-admin-payroll-api-data-model.png)](media/hr-admin-payroll-api-data-model.png#lightbox)

## <a name="payroll-employee-and-related-entities"></a>Lönemedarbetare och relaterade entiteter

Enheter:

- [Lönemedarbetare](hr-admin-integration-payroll-api-payroll-employee.md)
- [Lönearbetarens adress](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [Kompensationsplan med fast lön](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md)
- [Löneplan för variabel kompensation](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md)
- [Lönebefattningsjobb](hr-admin-integration-payroll-api-payroll-position-job.md)
- [Lönebefattning](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a>Se även

[Generera och granska lönelisteentiteter](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[Konfigurera Personalparametrar](hr-setup-parameters.md)<br>
[Konfigurera delade Personalparametrar](hr-setup-shared-parameters.md)<br>
[Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Använd webb-API för Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
