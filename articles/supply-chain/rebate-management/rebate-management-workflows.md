---
title: Arbetsflöden för rabatthantering
description: I det här avsnittet beskrivs hur du ställer in ett arbetsflöde för rabatthantering när du vill godkänna och aktivera erbjudanden.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 8436842b4f07ba000649075198bdef43ad508f8f
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270967"
---
# <a name="rebate-management-deal-workflows"></a>Arbetsflöden för rabatthantering

[!include [banner](../includes/banner.md)]

Om du vill godkänna rabatterbjudanden använder Rabatthantering samma arbetsflödesplattform som andra Finance and Operations-appar. Två jobbprocesser associeras med varje arbetsflöde:

- Ett element i arbetsflödet godkänner erbjudandet.
- Ett element i arbetsflödet aktiverar affären så att användaren eller arbetsflödesprocessen kan godkänna transaktionerna.

Innan du kan använda ett rabattavtal måste det vara aktivt i modulen **Rabatthantering**. Om du vill aktivera ett erbjudande måste du först skapa och konfigurera ett arbetsflöde för *rabatthantering*.

Användarna kan inte godkänna erbjudanden manuellt. Arbetsflödet måste alltid användas.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Skapa och hantera arbetsflöden för rabatthantering

För att arbeta med dina arbetsflöden för rabatthantering, gå till **Rabatthantering \> Inställningar \> Arbetsflöden för rabatthantering**. Där kan du visa, skapa och uppdatera arbetsflöden efter behov. Endast ett arbetsflöde av denna typ kan vara aktiv åt gången. Mer information om arbetsflöden, hur du arbetar med sidan **Arbetsflöden för rabatthantering** och hur du skapar arbetsflöden finns i [översikten över arbetsflödessystem](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) och dess relaterade avsnitt.

## <a name="use-a-workflow-to-activate-a-deal"></a>Använd ett arbetsflöde för att aktivera ett erbjudande

Om du vill aktivera ett erbjudande via ett arbetsflöde öppnar du erbjudandet (till exempel på sidan **Alla rabatthanteringserbjudanden**). Sedan i åtgärdsfönstret, välj **Arbetsflöde \> Skicka**. När det nya erbjudandet har bearbetats och godkänts i arbetsflödet är den aktiv och klar att användas.

När ett erbjudande har aktiverats kan du inte ändra dess inställningar. Om du måste ändra ett aktivt erbjudande, inaktivera det och skapa sedan ett nytt erbjudande. Om den nya affären ska liknar det gamla erbjudandet kan du skapa det genom att kopiera det gamla erbjudandet.

Du kan ändra följande inställningar för en deal när den har aktiverats:

- Stäm av
- Ackumulerad garanti
- Bokföringsprofil
- Bokföringsprofil för garanti
- Dokumentnoteringar
- Valuta
- Från-datum
- Till-datum

Dessutom kan rabattrader tas bort.
