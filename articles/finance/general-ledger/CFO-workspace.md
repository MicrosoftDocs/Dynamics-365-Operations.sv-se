---
title: Lägg till ekonomiska dimensioner i arbetsyta för ekonomichef
description: Det här avsnittet beskriver hur du lägger till ekonomiska dimensioner till arbetsytan ekonomichef så att den kan användas för redovisnings- och budgettransaktionerna.
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 3acff8a0cf36ee6958effd9c5384895df20c180499437c43feddce31c884dbbf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6729592"
---
# <a name="add-financial-dimensions-to-the-cfo-workspace"></a>Lägg till ekonomiska dimensioner i arbetsyta för ekonomichef

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du lägger till ekonomiska dimensioner till arbetsytan för ekonomichef så att den kan användas för redovisnings- och budgettransaktionerna. Arbetsytan CFO har en flik kallad **Översikt** och en flik kallad **Finance**. Rapporterna på dessa båda flikar backas upp av två åtgärder: MåttFör Redovisningsaktivitet och MåttFörBudgetaktivitet. Det finns en relation mellan dessa två mått och entiteten DimensionCombinationEntity. Därför kan du välja dimensioner.

1. I Finance på sidan **Entitetsbutiken** kan du uppdatera måtten **LedgerActivityMeasure** och **BudgetActivityMeasure**.
2. Öppna Programutforskaren i Visual Studio och sök efter **LedgerCFO**.
3. Under **resurser** öppnar du **LedgerCFOWorkspacePBIX**.
4. När resursen öppnas i Microsoft Power BI Desktop väljer du **Hämta data**, väljer **SQL Server database** och väljer sedan **Anslut**.
5. Ange servernamn och ange **AxDW** som databasen. Välj **DirectQuery** och sedan **OK**.
6. Leta upp och markera **LedgerActivityMeasure\_DimensionCombination**, och välj sedan **lasta**.

    > [!TIP]
    > I listan **fält** byter du namn på tabellen **ekonomiska dimensioner**, så att den blir lätt att identifiera.

7. Välj **hantera relationer**, och välj sedan **ny**.
8. I första fältet väljer du **redovisningsaktiviteter**, och väljer sedan **LedgerDimension**.
9. I det andra fältet väljer du **LedgerActivityMeasure\_DimensionCombination** (eller **ekonomiska dimensioner** om du byter namn på tabellen). Välj rubriken **DimensionCombinationRECID**.
10. I fältet **kardinalitet** väljer du **många till en**.
11. Ändra värdet **Korsfilterriktning** till **enkel**.
12. Markera både **aktivera den här relationen** och **anta referensintegritet**, markera **OK**, och välj sedan **nära**.

    [![Skapa en relation.](./media/Create-relationship.png)](./media/Create-relationship.png)

13. I listan **fält** bör du se tabellen och de ekonomiska dimensionerna som är tillgängliga. Dra de ekonomiska dimensioner som du vill använda till rapportnivåfilter.
14. Spara ändringarna.
15. Högerklicka på projektet i programobjektträdet (AOT) och välj sedan **synkronisera**.
16. Bygg ditt projekt och öppna sedan programmet för att visa resultaten.

    [![Slutförd arbetsyta.](./media/workspace.png)](./media/workspace.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]