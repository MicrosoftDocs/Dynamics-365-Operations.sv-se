---
title: Lagerföråldringsrapport
description: I det här avsnittet beskrivs de funktioner som gör att du kan köra en lagerföråldringsrapport och göra utdata tillgängliga som ett formulär och ett diagram.
author: AndersGirke
manager: AnnBe
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 21411c104c854224ff3689dc8e080b88d9fc7d23
ms.sourcegitcommit: 9267608347c9781fb4ba70f1384ca24da69c716d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2019
ms.locfileid: "2810261"
---
# <a name="inventory-aging-report"></a>Lagerföråldringsrapport


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

I Microsoft Dynamics 365 Supply Chain Management kan du köra en **Lagerföråldringsrapport** och göra utdata tillgängliga som ett formulär och ett diagram. I formuläret justeras kolumner och aggregerade saldon dynamiskt, beroende på vilken layout som har konfigurerats. Diagrammet innehåller en visuell översikt som stöder filtrering och gör att du kan öka detaljnivån. Dessutom kan du med hjälp av en dataentitet som kallas **Lagerföråldringsrapport** exportera resultaten av en körning av **Lagerföråldringsrapport** till format som t.ex. Microsoft Excel-fil eller PDF-fil.

Den här metoden för att köra en **Lagerföråldringsrapport** är användbar i fall där utdata innehåller många rader. Till exempel kommer udata att innehålla många rader om du har 50 000 artiklar och 300 butiker som har skapats som lagerställen och du begär lagerföråldring per artikel, plats och lagerställe.

## <a name="run-an-inventory-aging-report"></a>Kör en lagerföråldringsrapport

1. Gå till **kostnadshantering \>förfrågningar och rapporter \>lagring av lagerföråldringsrapport**.
1. Välj **Ny**.
1. I fältet **Identifierare för process – Namn** anger du ett unikt namn för rapporten.
1. Välj rapporten **Identifiering – ID** och filtrera efter behov.

    Rapportkörningen görs alltid i ett batchjobb.

1. När batchjobbet är klart visas utdata på sidan **lagring av lagerföråldringsrapport**.
1. Om du vill visa resultatet som ett formulär med en traditionell rutig layout väljer du **Visa detaljer**. Om du vill visa resultatet som ett aggregerat diagram väljer du **Visa diagram**.

    > [!NOTE]
    > Formuläret innehåller delsummor som definieras i rapportlayouten.

Dataentiteten **Lagerföråldringsrapport** låter dig exportera resultatet av **Lagerföråldringsrapport** genom att använda ett filter för fältet **Identifierare för process – Namn** till ett format som datahanteringen stöder.
