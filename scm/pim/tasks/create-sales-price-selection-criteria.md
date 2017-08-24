--- 
title: "Skapa urvalskriterier för försäljningspris"
description: "I den här proceduren visas hur du skapar ett kriterier för urval för försäljningspris för attributbaserade försäljningsprismodeller."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 633628e6250baa74df544e814ce6e9656a2f0b06
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-sales-price-selection-criteria"></a>Skapa urvalskriterier för försäljningspris

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


