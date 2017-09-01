---
title: "Lägg till ekonomiska dimensioner i arbetsyta för ekonomichef"
description: "Det här avsnittet beskriver hur du lägger till ekonomiska dimensioner till arbetsytan ekonomichef så att den kan användas för redovisnings- och budgettransaktionerna."
author: aolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.2.0
ms.translationtype: HT
ms.sourcegitcommit: 9953d2f29a67b35f4bb43f577df1c4d910e379a1
ms.openlocfilehash: 05fd7ce5293b3a300aabc073a6e492c5804d1897
ms.contentlocale: sv-se
ms.lasthandoff: 08/03/2017

---

# <a name="add-financial-dimensions-to-the-cfo-workspace"></a>Lägg till ekonomiska dimensioner i arbetsyta för ekonomichef

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver hur du lägger till ekonomiska dimensioner till arbetsytan för ekonomichef så att den kan användas för redovisnings- och budgettransaktionerna. Arbetsytan för ekonomichef har fliken **översikt** och fliken **ekonomi**. Rapporterna om dessa två flikar stöds av två mått: LedgerActivityMeasure och BudgetActivityMeasure. I Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, uppdatering juli 2017 finns en relation mellan dessa två mått och entiteten DimensionCombinationEntity. Därför kan du välja dimensioner.

1. I Finance and Operations på sidan **Entitetsbutiken** kan du uppdatera måtten **LedgerActivityMeasure** och **BudgetActivityMeasure**.
2. Öppna Programutforskaren i Microsoft Visual Studio och sök efter **LedgerCFO**.
3. Under **resurser** öppnar du **LedgerCFOWorkspacePBIX**.
4. När resursen öppnas i desktop Microsoft Power BI Desktop väljer du **hämta data**, väljer **SQL Server-databas** och väljer sedan **Anslut**.
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

    [![Skapa en relation](./media/Create-relationship.png)](./media/Create-relationship.png)

13. I listan **fält** bör du se tabellen och de ekonomiska dimensionerna som är tillgängliga. Dra de ekonomiska dimensioner som du vill använda till rapportnivåfilter.
14. Spara ändringarna.
15. Högerklicka på projektet i programobjektträdet (AOT) och välj sedan **synkronisera**.
16. Bygg ditt projekt och öppna sedan programmet för att visa resultaten.

    [![Slutförd arbetsyta](./media/workspace.png)](./media/workspace.png)
