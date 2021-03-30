---
title: Lagring av Lagerföråldringsrapport
description: I det här avsnittet beskrivs de funktioner som gör att du kan köra en lagerföråldringsrapport och göra utdata tillgängliga som ett formulär och ett diagram.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 40b15448677f319c650c667cd7c4981c343f7a02
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205356"
---
# <a name="inventory-aging-report-storage"></a>Lagring av Lagerföråldringsrapport

[!include [banner](../includes/banner.md)]

I Microsoft Dynamics 365 Supply Chain Management kan du köra en **lagring av lagerföråldringsrapport** och göra utdata tillgängliga som ett formulär och ett diagram. I formuläret justeras kolumner och aggregerade saldon dynamiskt, beroende på vilken layout som har konfigurerats. Diagrammet innehåller en visuell översikt som stöder filtrering och gör att du kan öka detaljnivån. Dessutom kan du med hjälp av en dataentitet som kallas **Lagerföråldringsrapport** exportera resultaten av en körning av **Lagring av Lagerföråldringsrapport** till format som t.ex. Microsoft Excel-fil eller PDF-fil.

Den här metoden för att köra en **Lagring av Lagerföråldringsrapport** är användbar i fall där utdata innehåller många rader. Till exempel kommer udata att innehålla många rader om du har 50 000 artiklar och 300 butiker som har skapats som lagerställen och du begär lagerföråldring per artikel, plats och lagerställe.

## <a name="enable-the-inventory-value-storage-report-feature"></a>Aktivera funktionen lagringsrapport för lagervärde

Innan du kan använda den här funktionen måste du aktivera den i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Här visas funktionen i listan:

- **Modul** - Kostnadshantering
- **Funktionsnamn** - Lagring av Lagerföråldringsrapport

## <a name="run-an-inventory-aging-report-storage"></a>Kör en lagring av Lagerföråldringsrapport

1. Gå till **kostnadshantering \>förfrågningar och rapporter \>lagring av lagerföråldringsrapport**.
1. Välj **Ny**.
1. I fältet **Identifierare för process – Namn** anger du ett unikt namn för rapporten.
1. Välj rapporten **Identifiering – ID** och filtrera efter behov.

    Rapportkörningen görs alltid i ett batchjobb.

1. När batchjobbet är klart visas utdata på sidan **lagring av lagerföråldringsrapport**.
1. Om du vill visa resultatet som ett formulär med en traditionell rutig layout väljer du **Visa detaljer**. Om du vill visa resultatet som ett aggregerat diagram väljer du **Visa diagram**.

    > [!NOTE]
    > Formuläret innehåller delsummor som definieras i rapportlayouten.

Dataentiteten **Lagerföråldringsrapport** låter dig exportera resultatet av **Lagring av Lagerföråldringsrapport** genom att använda ett filter för fältet **Identifierare för process – Namn** till ett format som datahanteringen stöder.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]