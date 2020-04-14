---
title: Överför projektbudgetar vid räkenskapsårets slut
description: Den här artikeln innehåller inoformation om hur du överför resterande budgetbelopp till framtida år och skapar budgetregisterdetaljer.
author: RadhikaRS
manager: AnnBe
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 41e985825a24de2d6510938cf3d61715c35f9939
ms.sourcegitcommit: 2ea5ff784500d5be9203e9a1560eabd4fea46f4e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172340"
---
# <a name="transfer-project-budgets-at-fiscal-year-end"></a>Överför projektbudgetar vid räkenskapsårets slut

[!include [banner](../includes/banner.md)]

När du arbetar med ett projekt med flera år kanske du har resterande budget vid slutet av räkenskapsåret. Du kan överföra de återstående budgetbeloppen för framtida år och skapa budgetregisterdetaljer för beloppen i associerad redovisning. Innan du överför de återstående beloppen bör du granska och analysera de resterande budgetbeloppen.

## <a name="review-and-analyze-remaining-budget-amounts"></a>Granska och analysera återstående budgetbelopp

Gör på följande sätt om du vill granska årsslutsbudgetbeloppen för projekt, men du är inte klar att föra beloppen framåt.

1. Gå till **projekthantering och redovisning** > **periodisk** > **budgetar** > **överföra budgetar**. 
2. På sidan **Överföringsprocess för projektbudget** på fliken **Årsslutsalternativ**, kontrollera att **Överför återstående projektbudgetbelopp** inte är aktiverat.
3. På fliken **Parametrar** i fältet **projektbudgetår**, välj det räkenskapsår som du vill visa det återstående budgetbeloppet för. 
4. Välj fältet **Ingående räkenskapsår** väljer du det räkenskapsår du vill visa det återstående budgetbeloppet för. 
5. I fältet **från prognosmodell** väljer du **resterande budget**. 
6. Om du vill inkludera projekt som uppfyller dina valda kriterier och inte har någon resterande budget, väljer du **Visa noll återstående**.  
7. På fliken **Välj budget** väljer du **Hämta alla budgetar** för att läsa in alla budgetar som matchar dina valda kriterier och väljer **process**. 
8. För att utforma en databasfråga som läser in en viss uppsättning projektbudgetar till fönstret, välj **Hämta valda budgetar**.

Mer information om en viss rad i fönstret får du om du markerar raden och sedan väljer **Visa budgetdetaljer** eller **visa konton**.

## <a name="carry-forward-remaining-budget-amounts"></a>Överför återstående budgetbelopp 

När du bearbetar återstående budgetbelopp, kan du skapa transaktioner i redovisningen för beloppen som du överför. Du skapar redovisningstransaktioner genom att följa stegen i avsnittet, [Överför budgetbelopp och skapa redovisningstransaktioner](#carry-forward). 

> [!NOTE]
> Budgetbelopp som överförs, överförs till den prognosmodell som är markerad på sidan **Prognosmodeller** som överföringsprognosmodell.  

## <a name="carry-forward-budget-amounts-and-create-general-ledger-transactions"></a><a name="carry-forward"></a>Överför budgetbelopp och skapa redovisningstransaktioner

1.  Välj **projekthantering och redovisning** > **periodisk** > **budgetar** > **överföra budgetar**. 
2. På sidan **Överföringsprocess för projektbudget** välj **Årsslut** och aktivera sedan **Överför återstående projektbudgetbelopp** och **Skapa budgetregisterposter i redovisningen**. 
3. På fliken **Parametrar** i fältgruppen **Projektparametrar** välj följande:

   - **Projektbudgetår**: Välj början på det räkenskapsår som du vill visa de återstående budgetbeloppen för. 
   - **Vinst och förlust**: Skapa resultaträkningstransaktioner i redovisningen. 
   -  **PIA**: skapa PIA-transaktioner (pågående arbete) i redovisningen.
   -  **Lön**: Skapa löneallokeringstransaktioner i redovisningen. 

5. I fältgruppen **redovisning** ange följande information: 

   - I fältet **Ingående räkenskapsår** välj det räkenskapsår som du vill överföra återstående budgetbelopp för projekten. Standardvärdet är ett år efter värdet för fältet **Projektbudgetår**.
   -  I fältet **Överföringsperiod** väljer du den period du vill skapa information om budgetregistret för i redovisningen. Detta är normalt den första perioden i den öppnande räkenskapsåret.

6. I fältgruppen **Kopiera från/till** ange följande information:

   - I fältet **från prognosmodell** välj den projektprognosmodellen som associeras med de återstående budgetbeloppen du vill överföra för projekten. 
   - Välj den redovisningsbudgetprognosmodell som associeras med budgetbeloppen som du vill överföra till redovisningen i fältet **Till redovisningsbudgetmodell**. 
   -  Markera **Överför försäljningsvaluta** om du vill använda projektets försäljningsvaluta för redovisningstransaktioner som skapas när du överför budgetbeloppen för projekt. Om alternativet inte är valt använder transaktionerna redovisningsvalutan. 
   -  Välj **Visa noll återstående** för att inkludera projekt som inte har några återstående budgetbelopp, men som uppfyller de andra kriterierna som du väljer i de projekt som visas i den nedre rutan.

7. På fliken **Välj budget** väljer du **Hämta alla budgetar** för att läsa in alla budgetar som matchar dina valda kriterier. Om du föredrar att utforma en databasfråga som läser in en viss uppsättning projektbudgetar till fönstret, välj **Hämta valda budgetar**.
8. Markera alternativet i början av raden för projektet För varje projekt, som du vill bearbeta.

    > [!TIP]
    > Markera alla eller de flesta av projekten genom att markera kryssrutan högst upp till vänster i det övre vänstra hörnet. Avmarkera kryssrutan för projektet om du vill undanta bearbetning av ett projekt.

9. Om du vill överföra de återstående budgetbeloppen för valda projekt till valt räkenskapsår och skapa budgetregisterdetaljer i redovisningen väljer du **Process**

## <a name="carry-forward-budget-amounts-without-creating-general-ledger-transactions"></a>Överför budgetbelopp utan att skapa redovisningstransaktioner

1. Gå till **projekthantering och redovisning** > **periodisk** > **budgetar** > **överföra budgetar**.
2. På sidan **Överföringsprocess för projektbudget** i fältet **Årsslutsalternativ**, välj **Överför återstående projektbudgetbelopp**.
3. I gruppen **Parametrar** i fältet **projektbudgetår**, välj det räkenskapsår som du vill visa det återstående budgetbeloppen.
4. I gruppen **Kopiera från/till** ange följande information:

   - I fältet **från prognosmodell** välj den projektprognosmodellen som associeras med de återstående budgetbeloppen du vill överföra för projekten. 
   - Välj **Visa noll återstående** om du vill inkludera projekt som inte har några återstående budgetbelopp, men som uppfyller de andra kriterierna du valt.
   - I gruppen **Välj budget** väljer du **Hämta alla budgetar** för att läsa in alla budgetar som matchar dina valda kriterier. För att utforma en databasfråga som läser in en viss uppsättning projektbudgetar till fönstret, välj **Hämta valda budgetar**.

5. Markera alternativet i början av raden för projektet För varje projekt, som du vill bearbeta. 
6. Välj **Process** om du vill överföra återstående budgetbeloppen för valda projekten till valt räkenskapsår.

