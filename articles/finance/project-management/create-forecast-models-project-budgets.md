---
title: Skapa prognosmodeller för projektbudgetar
description: I det här avsnittet beskrivs hur du skapar en prognosmodell för återstående budgetar.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
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
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321789"
---
# <a name="create-forecast-models-for-project-budgets"></a>Skapa prognosmodeller för projektbudgetar 

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en prognosmodell för återstående budgetar. Ett projekt som omfattas av budgetkontroll använder två typer av budgetar: ursprunglig och återstående. När du skapar en projektbudget måste du ange ursprungliga och återstående budgeterade prognosmodeller som har skapats på sidan **Prognosmodeller**. Projektbudgetar baserade på de angivna modellerna, skapas när du på Genomför projektbudgeten.

> [!NOTE]
> En prognosmodell som används för budgetkontroll, kan inte ha en delmodell och den kan inte användas som en delmodell.

1. Välj **Projekthantering och redovisning** > **Inställningar** > **Prognoser**  > **Prognosmodeller**.
2. Välj **Ny** för att skapa en ny prognosmodell och ange sedan ett modell-ID-nummer och ett namn för den nya modellen. 
3. Ställ in alternativet **Stoppad** som **Ja** för att förhindra att prognosraderna i prognosmodellen ändras. 
4. Om prognosraderna som modellen är kopplad till ska generera kassaflödesprognoser i redovisningen ställer du in **Inkludera i kassaflödesprognos** som **Ja**. 
5. Om du vill använda projektdatumet som fakturadatum ställer du in **Prognosens fakturadatum** som **Ja**. 
6. Välj en av följande modelltyper i fältet **Budgettyp**:

   - **Ursprunglig budget**: Använd ursprungligt budgetbelopp från när ursprunglig budget skapas och godkänns.
   - **Återstående budget**: Använd återstående budgetbelopp under resten av projektets livslängd. Saldona i den här prognosmodell minskas med faktiska transaktioner och ökas eller minskas med budgetändringar.
   - **Överförd**: Använd överförda budgetbelopp för projektet. Överföring är en valfri process som kan köras för att överföra oanvända budgetbelopp från ett räkenskapsår till en annan.

7. Ställ in följande alternativ efter behov:

   - Aktivera **Prognosens fakturadatum** för att använda projektdatum som fakturadatum.
   - Aktivera **Prognos med PIA** för prognos baserad på resurser i arbete (PIA) och välj sedan typ av PIA. 
   - Du kan behålla standard **Budgettyp** som **Ingen** eller ange en ny typ. Budgettypen kan inte ändras när du har ändrat en post.     
    > [!NOTE]
    > Om du ändrar standardbudgettypen blir inga andra alternativ tillgängliga för uppdateringar och du kan inte återanvända den här prognosmodellen. 
   


 

