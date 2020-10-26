---
title: Skapa urvalskriterier för försäljningspris
description: I den här proceduren visas hur du skapar ett kriterier för urval för försäljningspris för attributbaserade försäljningsprismodeller.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4ae444008e550d808a02d55dad02cc1b52874f0d
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985471"
---
# <a name="create-sales-price-selection-criteria"></a>Skapa urvalskriterier för försäljningspris

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar ett kriterier för urval för försäljningspris för attributbaserade försäljningsprismodeller. Denna procedur kräver att minst en modell för försäljningspris är tillgänglig. I det här exemplet används prismodellen för försäljningsprismodellen Speaker solution i demonstrationdataföretaget USMF. Vanligtvis använder en produktchef denna procedur.


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Lägga till ett nytt kriterium för en befintlig försäljningsprismodell
1. Klicka på Definition av produktvariantmodell.
2. Klicka på Modeller för produktkonfiguration.
3. Markera raden för produktmodellen för Speaker solution i listan, men inte klicka på länken för modellnamn.
4. Klicka på Modell i åtgärdsfönstret.
5. Klicka på Price model criteria.
6. Klicka på Ny.
7. Ange "Customer group 10" i namnfältet.
    * Namnet på prismodellvillkoret används för att hjälpa dig identifiera underliggande urvalskriterier.  
8. Ange eller välj ett värde i fältet Price model.
9. Välj Sales order i fältet Order type.
    * Ordertypen bestämmer vilka databasfält som ska vara tillgängliga för urvalsförfrågan.  
10. Ange ett datum i fältet för Valid from.
11. Ange ett datum i fältet Expire by.
12. Klicka på Spara.

## <a name="create-the-query-for-the-selection-criteria"></a>Skapa frågan för urvalskriterierna
1. Klicka på Redigera.
2. Markera Customers i fältet Table. 
3. Välj Customer Group i fältet Field.
    * I det här exemplet används en specifik kundgrupp för urvalskriterierna.  
4. Välj Customer group 10 i fältet Criteria. 
5. Klicka på OK.

