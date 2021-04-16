---
title: Granska status för ett experiment
description: Det här ämnet förklarar vilken status ett experiment har i testcykeln i Dynamics 365 Commerce.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: f7bdd292893ee42d49bdf977a55d8b10896ca1cd
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792449"
---
# <a name="review-the-status-of-an-experiment"></a><span data-ttu-id="af75d-103">Granska status för ett experiment</span><span class="sxs-lookup"><span data-stu-id="af75d-103">Review the status of an experiment</span></span>
<span data-ttu-id="af75d-104">Det finns många steg när du ställer in och kör ett experiment i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="af75d-104">There are many steps involved in setting up and running an experiment in Dynamics 365 Commerce.</span></span> <span data-ttu-id="af75d-105">Mer information om livscykeln för experiment finns i avsnittet [Experiment i Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="af75d-105">For information about the experimentation lifecycle, see [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="af75d-106">Om du vill veta var ett experiment är i livscykeln i Commerce webbplatsskaparen väljer du **Experiment** i vänster navigeringsfönster.</span><span class="sxs-lookup"><span data-stu-id="af75d-106">To learn where an experiment is in the lifecycle, in Commerce site builder select **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="af75d-107">En lista med experiment visas med status för varje experiment i både Commerce och den tredjepartstjänst som används för att skapa experiment, tilldela varianter och analysera data.</span><span class="sxs-lookup"><span data-stu-id="af75d-107">A list of experiments is displayed with the status of each experiment in both Commerce and the third-party service that is being used to enable the creation of experiments, assign variations, and analyze data.</span></span>

<span data-ttu-id="af75d-108">I kolumnen **Commerce-status** kan följande värden visas:</span><span class="sxs-lookup"><span data-stu-id="af75d-108">In the **Commerce status** column, the following values may be displayed.</span></span> 
- <span data-ttu-id="af75d-109">**Utkast** – experimentet ansluts till en sida eller ett fragment i Commerce och redigeras.</span><span class="sxs-lookup"><span data-stu-id="af75d-109">**Draft** - The experiment is connected to a page or fragment in Commerce and is being edited.</span></span>
- <span data-ttu-id="af75d-110">**Publicerad** – experimentvarianterna är klara att visas på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="af75d-110">**Published** - The experiment variations are ready to be displayed on your website.</span></span> <span data-ttu-id="af75d-111">Om experimente kör- i tredjepartstjänsten kommer webbplatsanvändarna att se en variant av sidan eller fragmentet som det har valts av tjänsten från tredjepartstjänst.</span><span class="sxs-lookup"><span data-stu-id="af75d-111">If the experiment is running in the third-party service, website users will see a variation of the page or fragment as selected by the third-party service.</span></span>
- <span data-ttu-id="af75d-112">**Opublicerad** – experimentet är inte längre tillgängligt på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="af75d-112">**Unpublished** - The experiment is no longer available on your website.</span></span> <span data-ttu-id="af75d-113">Webbplatsanvändare ser endast standardversionen av sidan eller fragmentet även om experimentet körs i tredjepartstjänst.</span><span class="sxs-lookup"><span data-stu-id="af75d-113">Website users will only see the default version of the page or fragment even if the experiment is running in the third-party service.</span></span>
- <span data-ttu-id="af75d-114">**Slutförd** – experimentet har utfört kursen och en variant har befordrats till publicerat för alla webbplatsanvändare.</span><span class="sxs-lookup"><span data-stu-id="af75d-114">**Completed** - The experiment has run its course and a variation was promoted to live for all website users.</span></span>

<span data-ttu-id="af75d-115">På liknande sätt i kolumnen **tredje parts status** kan följande värden visas för att ange vilken i status experimenten är i tredjepartstjänsten.</span><span class="sxs-lookup"><span data-stu-id="af75d-115">Similarly, in the **third-party status** column, the following values may be displayed to indicate what status the experiments are in the third-party service.</span></span>
- <span data-ttu-id="af75d-116">**Utkast** – experimentet ställs in i tjänsten för tredje part, men har inte startats.</span><span class="sxs-lookup"><span data-stu-id="af75d-116">**Draft** - The experiment is set up in the third-party service but hasn't been started.</span></span>
- <span data-ttu-id="af75d-117">**Körs** – experimentet har startats i tjänsten från tredje part och samlar in data.</span><span class="sxs-lookup"><span data-stu-id="af75d-117">**Running** - The experiment was started in the third-party service and is collecting data.</span></span>
- <span data-ttu-id="af75d-118">**Pausad** – experimentet pausas och data samlas inte in.</span><span class="sxs-lookup"><span data-stu-id="af75d-118">**Paused** - The experiment is paused and not collecting data.</span></span> <span data-ttu-id="af75d-119">Du måste återuppta experimentet för att samla in data på nytt.</span><span class="sxs-lookup"><span data-stu-id="af75d-119">You must resume the experiment for it to collect data again.</span></span>
- <span data-ttu-id="af75d-120">**Arkiverad** – experimentet har varit självklart och har katalogiserats i den tredjepartstjänst för framtida bruk.</span><span class="sxs-lookup"><span data-stu-id="af75d-120">**Archived** - The experiment has run its course and has been cataloged in the third-party service for future reference.</span></span>

<span data-ttu-id="af75d-121">I diagrammet nedan visas båda uppsättningarna med status och hur de relaterar till varandra.</span><span class="sxs-lookup"><span data-stu-id="af75d-121">The diagram below shows both sets of statuses and how they relate to each other.</span></span>

<span data-ttu-id="af75d-122">[ ![Experimentstatus](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="af75d-122">[ ![Experimentation statuses](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]