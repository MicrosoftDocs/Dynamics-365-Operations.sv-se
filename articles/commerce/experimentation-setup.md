---
title: Konfigurera ett experiment
description: I det här avsnittet beskrivs hur du ställer in ett experiment i en tredjepartstjänst.
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
ms.openlocfilehash: 9976ca461f7e988c32b81565fa2d084709e5ad6e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792520"
---
# <a name="set-up-an-experiment"></a><span data-ttu-id="bc12f-103">Konfigurera ett experiment</span><span class="sxs-lookup"><span data-stu-id="bc12f-103">Set up an experiment</span></span>

<span data-ttu-id="bc12f-104">När du har [definierat en hypotes och bestämmer vilka mått du vill använda](experimentation-identify.md), måste du ställa in experimentet i tredjeparttjänsten.</span><span class="sxs-lookup"><span data-stu-id="bc12f-104">After you [define a hypothesis and determine what success metrics you want to use](experimentation-identify.md), you'll need to set up your experiment in the third-party service.</span></span> <span data-ttu-id="bc12f-105">I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bc12f-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="bc12f-106">Ytterligare steg beskrivs i olika avsnitt.</span><span class="sxs-lookup"><span data-stu-id="bc12f-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="bc12f-107">[ ![Experimentets användarresa – Inställning](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="bc12f-107">[ ![Experimentation user journey - Setup](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span></span>


## <a name="set-up-your-experiment-in-the-third-party-service"></a><span data-ttu-id="bc12f-108">Ställa in experimentet i tredjepartstjänsten</span><span class="sxs-lookup"><span data-stu-id="bc12f-108">Set up your experiment in the third-party service</span></span>
<span data-ttu-id="bc12f-109">Nu bör du ha valt att köra och övervaka din tredjepartstjänst och sedan ställa in experimentanslutningen.</span><span class="sxs-lookup"><span data-stu-id="bc12f-109">By now you should have chosen your third-party service to run and monitor your experiment, and set up the experimentation connector.</span></span> <span data-ttu-id="bc12f-110">Dessa förutsättningar är listade vid [experiment i Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bc12f-110">These prerequisites are listed in  [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="bc12f-111">Följ de steg som krävs för att skapa experimentet i den tredjepartstjänsten.</span><span class="sxs-lookup"><span data-stu-id="bc12f-111">Follow the steps required to create your experiment in the third-party service.</span></span> <span data-ttu-id="bc12f-112">Om anslutningen är korrekt konfigurerad visas den fullständiga listan över experiment som du ställer in i tredjepartstjänst i Commerce webbplatsskaparen inom cirka 5 minuter.</span><span class="sxs-lookup"><span data-stu-id="bc12f-112">If the connector is configured properly, the complete list of experiments you set up in the third-party service will appear in Commerce site builder within about 5 minutes.</span></span>

## <a name="set-up-your-success-metrics"></a><span data-ttu-id="bc12f-113">Ställ in dina mätvärden för framgång</span><span class="sxs-lookup"><span data-stu-id="bc12f-113">Set up your success metrics</span></span>
<span data-ttu-id="bc12f-114">Varje experiment behöver mätvärden för att mäta effekterna av varianterna och för att validera hypotesen.</span><span class="sxs-lookup"><span data-stu-id="bc12f-114">Every experiment needs metrics to measure the impact of the variations and to validate the hypothesis.</span></span> <span data-ttu-id="bc12f-115">Följ instruktionerna nedan för att aktivera beräkningen av mått i tjänsten från tredje part med hjälp av händelser för direkt telemetri från Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bc12f-115">Follow the steps below to enable the computation of metrics in the third-party service using live telemetry events from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="bc12f-116">Följ dessa steg för att ställa in dina mätvärden för framgång.</span><span class="sxs-lookup"><span data-stu-id="bc12f-116">To set up your success metrics, follow these steps.</span></span>

1. <span data-ttu-id="bc12f-117">I Commerce webbplatsskaparen väljer du fliken **Sidor** i det vänstra navigeringsfönstret och väljer sedan den sida som du vill samla in mått för.</span><span class="sxs-lookup"><span data-stu-id="bc12f-117">In Commerce site builder, select **Pages** in the left navigation pane, and then select the page that you want to collect metrics for.</span></span> 
1. <span data-ttu-id="bc12f-118">Gå till avsnittet **händelse-ID för att spåra** i egenskapsrutan till höger på den sida eller modul som du vill spåra.</span><span class="sxs-lookup"><span data-stu-id="bc12f-118">Go to the **Event IDs to track** section in the right property pane of the page or module you want to track.</span></span>
1. <span data-ttu-id="bc12f-119">Välj **Vy**.</span><span class="sxs-lookup"><span data-stu-id="bc12f-119">Select **View**.</span></span> <span data-ttu-id="bc12f-120">En lista över alla händelse-ID:n visas.</span><span class="sxs-lookup"><span data-stu-id="bc12f-120">A list of all event IDs is displayed.</span></span> <span data-ttu-id="bc12f-121">Kopiera den händelse som du vill spåra och klistra in händelsenyckeln i den angivna platsen i tredjepartstjänsten.</span><span class="sxs-lookup"><span data-stu-id="bc12f-121">Copy the event you want to track, and paste the event key into the designated location in the third-party service.</span></span> <span data-ttu-id="bc12f-122">Om du behöver fler än en händelse kopierar du tangenterna en i taget.</span><span class="sxs-lookup"><span data-stu-id="bc12f-122">If you need more than one event, copy the keys one at a time.</span></span> 
    - <span data-ttu-id="bc12f-123">Mer information om hur du visar alla tillgängliga händelser och attribut, inklusive sidvyer och intäktsspårning, finns i [Commerce-komponenthändelser för diagnostik och felsökning](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="bc12f-123">To learn how to view all of the available events and attributes, including page views and revenue tracking, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>
1. <span data-ttu-id="bc12f-124">Vidta alla andra steg för att följa upp mätvärden som krävs i tjänsten för tredje part.</span><span class="sxs-lookup"><span data-stu-id="bc12f-124">Take any other steps for tracking metrics as required in the third-party service.</span></span>

## <a name="previous-step"></a><span data-ttu-id="bc12f-125">Föregående steg</span><span class="sxs-lookup"><span data-stu-id="bc12f-125">Previous step</span></span>
[<span data-ttu-id="bc12f-126">Identifiera en hypotes och fastställa mätvärden för ett experiment</span><span class="sxs-lookup"><span data-stu-id="bc12f-126">Identify a hypothesis and determine metrics for an experiment</span></span>](experimentation-identify.md) 


## <a name="next-step"></a><span data-ttu-id="bc12f-127">Gå vidare</span><span class="sxs-lookup"><span data-stu-id="bc12f-127">Next step</span></span>
[<span data-ttu-id="bc12f-128">Ansluta till och redigera ett experiment</span><span class="sxs-lookup"><span data-stu-id="bc12f-128">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]