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
# <a name="create-forecast-models-for-project-budgets"></a><span data-ttu-id="20ee9-103">Skapa prognosmodeller för projektbudgetar</span><span class="sxs-lookup"><span data-stu-id="20ee9-103">Create forecast models for project budgets</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="20ee9-104">I det här avsnittet beskrivs hur du skapar en prognosmodell för återstående budgetar.</span><span class="sxs-lookup"><span data-stu-id="20ee9-104">This topic describes how to create a forecast model for remaining budgets.</span></span> <span data-ttu-id="20ee9-105">Ett projekt som omfattas av budgetkontroll använder två typer av budgetar: ursprunglig och återstående.</span><span class="sxs-lookup"><span data-stu-id="20ee9-105">A project that is subject to budget control uses two types of budgets: original and remaining.</span></span> <span data-ttu-id="20ee9-106">När du skapar en projektbudget måste du ange ursprungliga och återstående budgeterade prognosmodeller som har skapats på sidan **Prognosmodeller**.</span><span class="sxs-lookup"><span data-stu-id="20ee9-106">When you create a project budget, you must specify the original and remaining budget forecast models that were created in the **Forecast models** page.</span></span> <span data-ttu-id="20ee9-107">Projektbudgetar baserade på de angivna modellerna, skapas när du på Genomför projektbudgeten.</span><span class="sxs-lookup"><span data-stu-id="20ee9-107">Project budgets based on the specified models are created when you commit the project budget.</span></span>

> [!NOTE]
> <span data-ttu-id="20ee9-108">En prognosmodell som används för budgetkontroll, kan inte ha en delmodell och den kan inte användas som en delmodell.</span><span class="sxs-lookup"><span data-stu-id="20ee9-108">A forecast model that is used for budget control can’t have a submodel or be used as a submodel.</span></span>

1. <span data-ttu-id="20ee9-109">Välj **Projekthantering och redovisning** > **Inställningar** > **Prognoser**  > **Prognosmodeller**.</span><span class="sxs-lookup"><span data-stu-id="20ee9-109">Select **Project management and accounting** > **Setup** > **Forecasts**  > **Forecast models**.</span></span>
2. <span data-ttu-id="20ee9-110">Välj **Ny** för att skapa en ny prognosmodell och ange sedan ett modell-ID-nummer och ett namn för den nya modellen.</span><span class="sxs-lookup"><span data-stu-id="20ee9-110">Select **New** to create a new forecast model, and then enter a model ID number and name for the new model.</span></span> 
3. <span data-ttu-id="20ee9-111">Ställ in alternativet **Stoppad** som **Ja** för att förhindra att prognosraderna i prognosmodellen ändras.</span><span class="sxs-lookup"><span data-stu-id="20ee9-111">Set the **Stopped** option to **Yes** to prevent any changes to the forecast lines for the forecast model.</span></span> 
4. <span data-ttu-id="20ee9-112">Om prognosraderna som modellen är kopplad till ska generera kassaflödesprognoser i redovisningen ställer du in **Inkludera i kassaflödesprognos** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="20ee9-112">If the forecast lines that the model is associated with should generate cash flow forecasts in the general ledger, set **Include in Cash flow forecasts** to **Yes.**</span></span> 
5. <span data-ttu-id="20ee9-113">Om du vill använda projektdatumet som fakturadatum ställer du in **Prognosens fakturadatum** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="20ee9-113">To use the project date as the invoice date, set **Forecast Invoice date** to **Yes**.</span></span> 
6. <span data-ttu-id="20ee9-114">Välj en av följande modelltyper i fältet **Budgettyp**:</span><span class="sxs-lookup"><span data-stu-id="20ee9-114">In the **Budget type** field, select one of the following model types:</span></span>

   - <span data-ttu-id="20ee9-115">**Ursprunglig budget**: Använd ursprungligt budgetbelopp från när ursprunglig budget skapas och godkänns.</span><span class="sxs-lookup"><span data-stu-id="20ee9-115">**Original budget**: Use the original budget amounts that are committed when the initial budget is created and approved.</span></span>
   - <span data-ttu-id="20ee9-116">**Återstående budget**: Använd återstående budgetbelopp under resten av projektets livslängd.</span><span class="sxs-lookup"><span data-stu-id="20ee9-116">**Remaining budget**: Use the remaining budget amounts during the life of the project.</span></span> <span data-ttu-id="20ee9-117">Saldona i den här prognosmodell minskas med faktiska transaktioner och ökas eller minskas med budgetändringar.</span><span class="sxs-lookup"><span data-stu-id="20ee9-117">The balances in this forecast model are reduced by actual transactions and increased or decreased by budget revisions.</span></span>
   - <span data-ttu-id="20ee9-118">**Överförd**: Använd överförda budgetbelopp för projektet.</span><span class="sxs-lookup"><span data-stu-id="20ee9-118">**Carry-forward**: Use the carry-forward budget amounts for the project.</span></span> <span data-ttu-id="20ee9-119">Överföring är en valfri process som kan köras för att överföra oanvända budgetbelopp från ett räkenskapsår till en annan.</span><span class="sxs-lookup"><span data-stu-id="20ee9-119">Carry-forward is an optional process that can be run to transfer unused budget amounts from one fiscal year to another.</span></span>

7. <span data-ttu-id="20ee9-120">Ställ in följande alternativ efter behov:</span><span class="sxs-lookup"><span data-stu-id="20ee9-120">Set the following options as required:</span></span>

   - <span data-ttu-id="20ee9-121">Aktivera **Prognosens fakturadatum** för att använda projektdatum som fakturadatum.</span><span class="sxs-lookup"><span data-stu-id="20ee9-121">Enable **Forecast invoice date** to use the project date as the invoice date.</span></span>
   - <span data-ttu-id="20ee9-122">Aktivera **Prognos med PIA** för prognos baserad på resurser i arbete (PIA) och välj sedan typ av PIA.</span><span class="sxs-lookup"><span data-stu-id="20ee9-122">Enable **Forecast with WIP** to forecast based on work in progress (WIP), and then select the type of WIP.</span></span> 
   - <span data-ttu-id="20ee9-123">Du kan behålla standard **Budgettyp** som **Ingen** eller ange en ny typ.</span><span class="sxs-lookup"><span data-stu-id="20ee9-123">You can keep the default **Budget type** as **None** or enter a new type.</span></span> <span data-ttu-id="20ee9-124">Budgettypen kan inte ändras när du har ändrat en post.</span><span class="sxs-lookup"><span data-stu-id="20ee9-124">The budget type can't be changed after you change a record.</span></span>     
    > [!NOTE]
    > <span data-ttu-id="20ee9-125">Om du ändrar standardbudgettypen blir inga andra alternativ tillgängliga för uppdateringar och du kan inte återanvända den här prognosmodellen.</span><span class="sxs-lookup"><span data-stu-id="20ee9-125">If you change the default budget type, all other options will become unavailable for updates, and you can't reuse this forecast model.</span></span> 
   


 

