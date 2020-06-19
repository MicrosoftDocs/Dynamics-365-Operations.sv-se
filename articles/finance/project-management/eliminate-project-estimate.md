---
title: Eliminera en projektuppskattning
description: I det här avsnittet finns information om hur du eliminerar en projektuppskattning när den är slutförd.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
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
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410266"
---
# <a name="eliminate-a-project-estimate"></a><span data-ttu-id="88a62-103">Eliminera en projektuppskattning</span><span class="sxs-lookup"><span data-stu-id="88a62-103">Eliminate a project estimate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88a62-104">Projektuppskattningar ger den ekonomiska vyn för arbete som är uppskattat och planerat för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="88a62-104">Project estimates provide the financial view for work that is estimated and scheduled for a project.</span></span> <span data-ttu-id="88a62-105">För att arbeta med uppskattningar för ett projekt måste du koppla projektet till ett uppskattningsprojekt.</span><span class="sxs-lookup"><span data-stu-id="88a62-105">To work with estimates for a project, you must attach the project to an estimate project.</span></span> <span data-ttu-id="88a62-106">Ett uppskattningsprojekt är alltid baserat på ett befintligt projekt, men flera projekt kan referera till ett enskilt uppskattningsprojekt.</span><span class="sxs-lookup"><span data-stu-id="88a62-106">An estimate project is always based on an existing project, however multiple projects can refer to a single estimate project.</span></span> <span data-ttu-id="88a62-107">Endast projekt med fastpris och investeringsprojekt kan kopplas till uppskattningsprojekt och dessa projekt måste tillhöra samma projektgrupp som uppskattningsprojektet.</span><span class="sxs-lookup"><span data-stu-id="88a62-107">Only fixed-price and investment projects can be attached to estimate projects, and those projects must belong to the same project group as the estimate project.</span></span>

<span data-ttu-id="88a62-108">Om du vill ta bort ett uppskattningsprojekt måste det vara fullständigt.</span><span class="sxs-lookup"><span data-stu-id="88a62-108">To eliminate an estimate project, it must be complete.</span></span> <span data-ttu-id="88a62-109">I följande steg förklaras hur du eliminerar en uppskattning.</span><span class="sxs-lookup"><span data-stu-id="88a62-109">The following steps explain how to eliminate an estimate.</span></span>

1. <span data-ttu-id="88a62-110">Gå till **Projekthantering och redovisning** > **Alla projekt** och öppna projektet.</span><span class="sxs-lookup"><span data-stu-id="88a62-110">Go to **Project management and accounting** > **All Projects** and open the project.</span></span> 
2. <span data-ttu-id="88a62-111">På fliken **Hantera** väljer du **Uppskattningar** och på sidan **Uppskattning** väljer du **eliminera**.</span><span class="sxs-lookup"><span data-stu-id="88a62-111">On the **Manage** tab, select **Estimates**, and on the **Estimate** page select **Eliminate**.</span></span>
3. <span data-ttu-id="88a62-112">På fliken **Eliminera uppskattning** på fliken **Allmänt** anger du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="88a62-112">On the **Eliminate estimate** page on the **General** tab, set the following options:</span></span>

   - <span data-ttu-id="88a62-113">**Periodkod**: Välj periodkoden när du vill välja lämpliga uppskattningsprojekt.</span><span class="sxs-lookup"><span data-stu-id="88a62-113">**Period code**: Select the period code to choose the appropriate estimate projects.</span></span> 
   - <span data-ttu-id="88a62-114">**Uppskattat datum**: Välj lämpligt uppskattat datum för eliminering.</span><span class="sxs-lookup"><span data-stu-id="88a62-114">**Estimate date**: Select the appropriate estimate date for elimination.</span></span>
   - <span data-ttu-id="88a62-115">**Eliminera med PIA-varningar**: aktivera det här alternativet om du vill att en uppskattning som är associerad med en pågående PIA ska elimineras.</span><span class="sxs-lookup"><span data-stu-id="88a62-115">**Eliminate with WIP warnings**: Enable this option to provide notification when an estimate that is associated with a work in progress (WIP) will be eliminated.</span></span> <span data-ttu-id="88a62-116">Om det här alternativet inte är aktiverat kan eliminering inte fortsätta om det finns icke uppskattade transaktioner.</span><span class="sxs-lookup"><span data-stu-id="88a62-116">When this option is not enabled, elimination can’t continue if any non-estimated transactions exist.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="88a62-117">Det här alternativet är endast tillgängligt när eliminering används på ett uppskattningsprojekt.</span><span class="sxs-lookup"><span data-stu-id="88a62-117">This option is available only when elimination is applied to an estimate project.</span></span> <span data-ttu-id="88a62-118">Den är inte tillgänglig om du använder periodiska bokföringar.</span><span class="sxs-lookup"><span data-stu-id="88a62-118">It is not available if you are using periodic postings.</span></span> <span data-ttu-id="88a62-119">Den här inställningen fungerar med inställningarna på fliken **Uppskatta** på sidan **Projektparametrar** i fältgruppen **Tillåt eliminering när det inte finns uppskattade transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="88a62-119">This setting works with the settings on the **Estimate** tab on the **Project parameters** page, in the **Allow elimination when non-estimated transactions exist** field group.</span></span>
   - <span data-ttu-id="88a62-120">**Sätt steget till färdigt**: aktivera det här alternativet om du vill att uppskattningsprojektets fas ska **slutföras** när du har kört elimineringen.</span><span class="sxs-lookup"><span data-stu-id="88a62-120">**Set stage to Finished**: Enable this option to set the estimate project’s stage to **Finished** after you run the elimination.</span></span>
   - <span data-ttu-id="88a62-121">**Skriv ut uppskattningslista**: Välj vilken information som ska inkluderas när uppskattningslistan skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="88a62-121">**Print estimate list**: Select the information to be included when the estimate list is printed.</span></span>
   - <span data-ttu-id="88a62-122">**Visa informationslogg**: aktivera det här alternativet om du vill visa informationsloggen.</span><span class="sxs-lookup"><span data-stu-id="88a62-122">**Show Infolog**: Enable this option to display the Infolog.</span></span>
   - <span data-ttu-id="88a62-123">**Bokföringsdatum**: Välj bokföringsdatumet för uppskattningen.</span><span class="sxs-lookup"><span data-stu-id="88a62-123">**Posting date**: Choose the ledger posting date of the estimate.</span></span>

4.  <span data-ttu-id="88a62-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88a62-124">Select **OK**.</span></span>
5. <span data-ttu-id="88a62-125">När elimineringsprocessen har slutförts visas det eliminerade uppskattningsprojektet med ett negativt värde.</span><span class="sxs-lookup"><span data-stu-id="88a62-125">After the elimination process is complete, the eliminated estimate project is displayed with a negative value.</span></span> 

<span data-ttu-id="88a62-126">Om du inte har för avsikt att ta bort en uppskattning kan du markera den eliminerade uppskattningen och välja **återför eliminering**.</span><span class="sxs-lookup"><span data-stu-id="88a62-126">If you did not intend to eliminate an estimate, you can select the eliminated estimate and select **Reverse elimination**.</span></span>   
