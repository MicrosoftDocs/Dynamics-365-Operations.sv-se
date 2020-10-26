---
title: Konfigurera ett experiment
description: I det här avsnittet beskrivs hur du ställer in ett experiment i en tredjepartstjänst.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 0f7db0ce009f6ee7603952891aacfdc16fcde016
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930292"
---
# <a name="set-up-an-experiment"></a><span data-ttu-id="1381e-103">Konfigurera ett experiment</span><span class="sxs-lookup"><span data-stu-id="1381e-103">Set up an experiment</span></span>

<span data-ttu-id="1381e-104">När du har [definierat en hypotes och bestämmer vilka mått du vill använda](experimentation-identify.md), måste du ställa in experimentet i tredjeparttjänsten.</span><span class="sxs-lookup"><span data-stu-id="1381e-104">After you [define a hypothesis and determine what success metrics you want to use](experimentation-identify.md), you'll need to set up your experiment in the third-party service.</span></span> <span data-ttu-id="1381e-105">I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en e-handelswebbplats i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1381e-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="1381e-106">Ytterligare steg beskrivs i olika avsnitt.</span><span class="sxs-lookup"><span data-stu-id="1381e-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="1381e-107">[ ![Experimentets användarresa - Inställning](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1381e-107">[ ![Experimentation user journey - Setup](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span></span>


## <a name="set-up-your-experiment-in-the-third-party-service"></a><span data-ttu-id="1381e-108">Ställa in experimentet i tredjepartstjänsten</span><span class="sxs-lookup"><span data-stu-id="1381e-108">Set up your experiment in the third-party service</span></span>
<span data-ttu-id="1381e-109">Nu bör du ha valt att köra och övervaka din tredjepartstjänst och sedan ställa in experimentanslutningen.</span><span class="sxs-lookup"><span data-stu-id="1381e-109">By now you should have chosen your third-party service to run and monitor your experiment, and set up the experimentation connector.</span></span> <span data-ttu-id="1381e-110">Dessa förutsättningar är listade vid [experiment i Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1381e-110">These prerequisites are listed in  [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="1381e-111">Följ de steg som krävs för att skapa experimentet i den tredjepartstjänsten.</span><span class="sxs-lookup"><span data-stu-id="1381e-111">Follow the steps required to create your experiment in the third-party service.</span></span> <span data-ttu-id="1381e-112">Om anslutningen är korrekt konfigurerad visas den fullständiga listan över experiment som du ställer in i tredjepartstjänst i webbplatsskaparen inom cirka 5 minuter.</span><span class="sxs-lookup"><span data-stu-id="1381e-112">If the connector is configured properly, the complete list of experiments you set up in the third-party service will surface in site builder within about 5 minutes.</span></span>

## <a name="set-up-your-success-metrics"></a><span data-ttu-id="1381e-113">Ställ in dina mätvärden för framgång</span><span class="sxs-lookup"><span data-stu-id="1381e-113">Set up your success metrics</span></span>
<span data-ttu-id="1381e-114">Varje experiment behöver mätvärden för att mäta effekterna av varianterna och för att validera hypotesen.</span><span class="sxs-lookup"><span data-stu-id="1381e-114">Every experiment needs metrics to measure the impact of the variations and to validate the hypothesis.</span></span> <span data-ttu-id="1381e-115">Följ instruktionerna nedan för att aktivera beräkningen av mått i tjänsten från tredje part med hjälp av händelser för direkt telemetri från Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1381e-115">Follow the steps below to enable the computation of metrics in the third-party service using live telemetry events from Dynamics 365 Commerce.</span></span>

1. <span data-ttu-id="1381e-116">I webbplatsskaparen väljer du fliken **Sidor** i det vänstra navigeringsfönstret och väljer sedan den sida som du vill samla in mått för.</span><span class="sxs-lookup"><span data-stu-id="1381e-116">In site builder, select the **Pages** tab in the left navigation pane and then select the page that you want to collect metrics on.</span></span> 
1. <span data-ttu-id="1381e-117">Gå till avsnittet **händelse-ID för att spåra** i egenskapsrutan till höger på den sida eller modul som du vill spåra.</span><span class="sxs-lookup"><span data-stu-id="1381e-117">Go to the **Event IDs to track** section in the right property pane of the page or module you want to track.</span></span>
1. <span data-ttu-id="1381e-118">Välj **Vy**.</span><span class="sxs-lookup"><span data-stu-id="1381e-118">Select **View**.</span></span> <span data-ttu-id="1381e-119">En lista över alla händelse-ID:n visas.</span><span class="sxs-lookup"><span data-stu-id="1381e-119">A list of all event IDs is displayed.</span></span> <span data-ttu-id="1381e-120">Kopiera den händelse som du vill spåra och klistra in händelsenyckeln i den angivna platsen i tredjepartstjänsten.</span><span class="sxs-lookup"><span data-stu-id="1381e-120">Copy the event you want to track, and paste the event key into the designated location in the third-party service.</span></span> <span data-ttu-id="1381e-121">Om du behöver fler än en händelse kopierar du tangenterna en i taget.</span><span class="sxs-lookup"><span data-stu-id="1381e-121">If you need more than one event, copy the keys one at a time.</span></span> 
    - <span data-ttu-id="1381e-122">Mer information om hur du visar alla tillgängliga händelser och attribut, inklusive sidvyer och intäktsspårning, finns i [Commerce-komponenthändelser för diagnostik och felsökning](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="1381e-122">To learn how to view all of the available events and attributes, including page views and revenue tracking, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>
1. <span data-ttu-id="1381e-123">Vidta alla andra steg för att följa upp mätvärden som krävs i tjänsten för tredje part.</span><span class="sxs-lookup"><span data-stu-id="1381e-123">Take any other steps for tracking metrics as required in the third-party service.</span></span>

## <a name="previous-step"></a><span data-ttu-id="1381e-124">Föregående steg</span><span class="sxs-lookup"><span data-stu-id="1381e-124">Previous step</span></span>
[<span data-ttu-id="1381e-125">Identifiera en hypotes och fastställa mätvärden för ett experiment</span><span class="sxs-lookup"><span data-stu-id="1381e-125">Identify a hypothesis and determine metrics for an experiment</span></span>](experimentation-identify.md) 


## <a name="next-step"></a><span data-ttu-id="1381e-126">Gå vidare</span><span class="sxs-lookup"><span data-stu-id="1381e-126">Next step</span></span>
[<span data-ttu-id="1381e-127">Ansluta till och redigera ett experiment</span><span class="sxs-lookup"><span data-stu-id="1381e-127">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)
