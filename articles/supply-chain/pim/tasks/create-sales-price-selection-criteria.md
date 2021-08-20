---
title: Skapa urvalskriterier för försäljningspris
description: I den här proceduren visas hur du skapar ett kriterier för urval för försäljningspris för attributbaserade försäljningsprismodeller.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 47ea7ea2093c540a88d9fd7249b470009c7595d40e2a727d8fcd3bb4b5d74bac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750086"
---
# <a name="create-sales-price-selection-criteria"></a>Skapa urvalskriterier för försäljningspris

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar ett kriterier för urval för försäljningspris för attributbaserade försäljningsprismodeller. Denna procedur kräver att minst en modell för försäljningspris är tillgänglig. I det här exemplet används prismodellen för försäljningsprismodellen Speaker solution i demonstrationdataföretaget USMF. Vanligtvis använder en produktchef denna procedur.

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Lägga till ett nytt kriterium för en befintlig försäljningsprismodell

1. Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.
1. Markera raden för produktmodellen för högtalarlösning i listan, men markera inte länken för modellnamn.
1. Klicka på **Modell** i åtgärdsfönstret.
1. Välj **Prismodellkriterier**.
1. Välj **Ny**.
1. I fältet **Namn** anger du "Kundgrupp 10".
    * Namnet på prismodellvillkoret används för att hjälpa dig identifiera underliggande urvalskriterier.  
1. Ange eller välj ett värde i fältet **Prismodell**.
1. I fältet **Ordertyp** väljer du *Försäljningsorder*.
    * Ordertypen bestämmer vilka databasfält som ska vara tillgängliga för urvalsförfrågan.  
1. Ange ett datum i fältet **Giltigt från**.
1. Ange ett datum i fältet **Löp ut den**.
1. Välj **Spara**.

## <a name="create-the-query-for-the-selection-criteria"></a>Skapa frågan för urvalskriterierna

1. Välj **Redigera**.
2. I fältet **Register** väljer du *Kunder*.
3. I fältet **Fält** väljer du *Kundgrupp*.
    * I det här exemplet används en specifik kundgrupp för urvalskriterierna.  
4. I fältet **Kriterier** väljer du *Kundgrupp 10*.
5. Välj **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]