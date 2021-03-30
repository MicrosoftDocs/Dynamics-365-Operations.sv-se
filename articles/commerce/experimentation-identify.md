---
title: Identifiera en hypotes och fastställa mätvärden för ett experiment
description: I det här avsnittet beskrivs hur du identifierar hypotesen och mätvärden för framgång för ett experiment som du ska köra på en näthandelssajt i Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 91614cda804cae4574fce4c9cfb31c63d876f19b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238640"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a><span data-ttu-id="61aff-103">Identifiera en hypotes och fastställa mätvärden för framgång för ett experiment</span><span class="sxs-lookup"><span data-stu-id="61aff-103">Identify a hypothesis and determine success metrics for an experiment</span></span>
<span data-ttu-id="61aff-104">Den första fasen i testcykeln omfattar att identifiera hypotesen för experimentet och fastställa vilka mått du ska spåra för att utvärdera framgång.</span><span class="sxs-lookup"><span data-stu-id="61aff-104">The first phase in the experimentation lifecycle includes identifying the hypothesis for the experiment and determining the metrics you'll track to evaluate success.</span></span> <span data-ttu-id="61aff-105">I bilden nedan visas alla steg som ingår när du [ställer in och kör ett experiment](experimentation-overview.md) på en näthandelssajt i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="61aff-105">The following diagram shows all of the steps involved in [setting up and running an experiment](experimentation-overview.md) on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="61aff-106">Ytterligare steg beskrivs i olika avsnitt.</span><span class="sxs-lookup"><span data-stu-id="61aff-106">Additional steps are covered in separate topics.</span></span> 

<span data-ttu-id="61aff-107">[ ![Experimentets användarresa – identifiera](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="61aff-107">[ ![Experimentation user journey - Identify](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span></span>

<span data-ttu-id="61aff-108">En hypotes är ett utdrag där du förutsäger resultatet av experimentet.</span><span class="sxs-lookup"><span data-stu-id="61aff-108">A hypothesis is a statement where you predict the outcome of the experiment.</span></span> <span data-ttu-id="61aff-109">Många faktorer är till för att definiera en hypotes, t.ex. forskning om användarbeteende och webbdata som du har samlat in.</span><span class="sxs-lookup"><span data-stu-id="61aff-109">Many factors go into defining a hypothesis, for example, research about user behavior and website data you've collected.</span></span> <span data-ttu-id="61aff-110">Med hypotesen ska du definiera det antagande eller den teori du vill validera med experimentet.</span><span class="sxs-lookup"><span data-stu-id="61aff-110">With the hypothesis, you'll define the assumption or theory you want to validate with your experiment.</span></span> <span data-ttu-id="61aff-111">Ett exempel på hypotes för experimentet kan vara "*en bild av en vit t-shirt på startsidan kommer att ge en högre klickhastighet än en marinblå tröja under sommarmånaderna eftersom personer vill kunna bära något lätt och ljust färgat på sommaren.*"</span><span class="sxs-lookup"><span data-stu-id="61aff-111">An example of a hypothesis for your experiment may be "*a picture of a white t-shirt on my home page will drive a higher clickthrough rate than a navy sweater during summer months because people want to wear something lightweight and light colored in the summer.*"</span></span> <span data-ttu-id="61aff-112">I så fall skapar du varianter som omfattar en vit t-shirt och en marinblå tröja och publicerar båda samtidigt.</span><span class="sxs-lookup"><span data-stu-id="61aff-112">In that case, you'll create variations that include a white t-shirt and a navy sweater, and publish both at the same time.</span></span>

<span data-ttu-id="61aff-113">För att validera en hypotes bör ett experiments framgång eller misslyckande kopplas direkt till användarens handlingar. till exempel om webbplatsanvändaren klickar på en länk eller knapp.</span><span class="sxs-lookup"><span data-stu-id="61aff-113">To validate a hypothesis, the success or failure of an experiment should be directly tied to user actions; for example, if the website user clicks on a link or button.</span></span> <span data-ttu-id="61aff-114">Dessa åtgärder måste motsvara händelser som ska rapporteras till tjänsten för tredje part när experimentet spåras.</span><span class="sxs-lookup"><span data-stu-id="61aff-114">These actions must correspond with events that will be reported to the third-party service tracking the experiment.</span></span> <span data-ttu-id="61aff-115">Med tiden kommer procentandelen användare som utför åtgärden att summeras som ett mätvärde som du kan använda för att generera rapporter och utföra analyser.</span><span class="sxs-lookup"><span data-stu-id="61aff-115">Over time, the percentage of users that take the action will be tallied as a metric you can use to generate reports and conduct analyses.</span></span> <span data-ttu-id="61aff-116">För att granska alla tillgängliga händelser och attribut, se [Commerce-komponenthändelser för diagnostik och felsökning](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="61aff-116">To review all of the available events and attributes, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>

## <a name="previous-step"></a><span data-ttu-id="61aff-117">Föregående steg</span><span class="sxs-lookup"><span data-stu-id="61aff-117">Previous step</span></span>
[<span data-ttu-id="61aff-118">Experiment i Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="61aff-118">Experimentation in Dynamics 365 Commerce</span></span>](experimentation-overview.md)


## <a name="next-step"></a><span data-ttu-id="61aff-119">Gå vidare</span><span class="sxs-lookup"><span data-stu-id="61aff-119">Next step</span></span>
[<span data-ttu-id="61aff-120">Konfigurera ett experiment</span><span class="sxs-lookup"><span data-stu-id="61aff-120">Set up an experiment</span></span>](experimentation-setup.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]