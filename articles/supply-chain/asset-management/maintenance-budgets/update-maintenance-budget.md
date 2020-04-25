---
title: Uppdatera underhållsbudgetar
description: I det här avsnittet beskrivs hur du uppdaterar en underhållsbudget i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e43abd4644eec8c91606ec48bbecf30f12600856
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205286"
---
# <a name="update-maintenance-budgets"></a>Uppdatera underhållsbudgetar

[!include [banner](../../includes/banner.md)]

 

På sidan **Budgetrader för underhåll** visas alla budgetrader som har skapats för den budget som valts på sidan **Underhållsbudgetar**. (Mer information finns i [skapa underhållsbudgetar](create-maintenance-budget.md).) Du kan omberäkna och justera underhållsbudgetrader tills underhållsbudgeten har godkänts. När budgetperioden har passerat och kostnaderna har bokförts i Tillgångshantering kan du också uppdatera budgetraderna med faktiska kostnader.

## <a name="recalculate-a-maintenance-budget"></a>Beräkna om en underhållsbudget

Du kan beräkna om en underhållsbudget på sidan **Budgetrader för underhåll**. När du beräknar om en underhållsbudget raderas befintliga budgetrader och en ny beräkning görs.

1. Välj **Beräkna om** på sidan **Budgetrader för underhåll**.
2. I dialogrutan **Beräkna om budget** gör du de ändringar som krävs för den nya beräkningen och väljer **OK**.

Nya budgetrader skapas enligt de värden du anger.

## <a name="adjust-budget-lines"></a>Justera budgetrader

I stället för att omberäkna hela underhållsbudgeten kan du justera valda rader är relaterade till budgetkostnader.

1. På sidan **Budgetrader för underhåll** väljer du de rader som budgetkostnaden ska uppdateras för.
2. Välj **Justera**.
3. Om du vill lägga till ett belopp på de markerade raderna markerar du kryssrutan **Lägg till kostnad** och anger sedan värdet i fältet **Lägg till värde**.
4. Om du vill multiplicera budgetkostnaden för de valda budgetraderna med en faktor markerar du kryssrutan **Multiplicera kostnad** och anger faktorn i fältet **Multipliceringsvärde**.

    Om du till exempel anger **1,2** i fältet **Multipliceringsvärde**, ökar du budgetkostnaden på de valda raderna med 20 procent. Om du anger **0,7** minskar du budgetkostnaden på de valda raderna med 30 procent.

5. Välj **OK**.

De valda budgetraderna uppdateras enligt värdena som du angav i steg 3 eller 4.

## <a name="update-actual-costs"></a>Uppdatera faktiska kostnader

När datumen på budgetraderna har passerat och faktiska kostnader har bokförts i Tillgångshantering kan du också uppdatera underhållsbudgeten med faktiska kostnader.

1. Välj **Uppdatera kostnad** på sidan **Budgetrader för underhåll**.
2. Välj **OK** i dialogrutan **Beräkna faktisk kostnad**.

Fälten **Faktisk kostnad** på budgetraderna uppdateras om de faktiska kostnaderna har bokförts. Nya budgetrader kan skapas om nya tillgångstyper har skapats sedan du skapade budgeten, och om dessa tillgångstyper har använts på tillgångar som arbetsorder har skapats för och relaterade kostnader har bokförts för. Nya budgetrader visar bara faktiska kostnader, eftersom inga budgetkostnader har beräknats för dem.

> [!NOTE]
> Om du vill se en översikt över faktiska kostnader uppdelade på förebyggande, korrigerande och investeringskostnader kan du utföra en beräkning för samma period på sidan **Kostnadskontroll för tillgång**. 

## <a name="manually-add-budget-lines"></a>Lägga till budgetrader manuellt

På sidan **Budgetrader för underhåll** kan du manuellt lägga till en ny budgetrad genom att välj **Ny** och sedan göra val på raden. Här följer några exempel på situationer där den här metoden kan vara användbar:

- Du vet att reparation av vissa tillgångar för närvarande pågår under planeringsfasen, men relaterade jobb har ännu inte skapats i Tillgångshantering. Du vill dock att budgetkostnader för dessa jobb ska inkluderas i underhållsbudgeten.
- Nya tillgångar eller tillgångstyper har skapats sedan du gjorde underhållsbudgeten, men underhållsplanerna har inte ställts in för dessa tillgångar eller tillgångstyper. Du vill dock att budgetkostnader för dessa tillgångstyper ska inkluderas i underhållsbudgeten.
