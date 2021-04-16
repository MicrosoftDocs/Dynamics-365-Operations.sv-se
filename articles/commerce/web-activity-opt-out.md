---
title: Välj bort insamling av webbaktivitetshändelser
description: I det här avsnittet beskrivs hur du kan låta besökare på webbplatsen välja bort insamling av webbaktivitetshändelser i Microsoft Dynamics 365 Commerce.
author: aamiral
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86f475cc0b78c620309301516b6c3b525b640637
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791567"
---
# <a name="opt-out-of-web-activity-event-collection"></a><span data-ttu-id="b43f1-103">Välj bort insamling av webbaktivitetshändelser</span><span class="sxs-lookup"><span data-stu-id="b43f1-103">Opt out of web activity event collection</span></span>
[!include [banner](includes/banner.md)]

<span data-ttu-id="b43f1-104">I det här avsnittet beskrivs hur du kan låta kunderna välja bort insamling av webbaktivitetshändelser i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b43f1-104">This topic explains how you can let customers opt out of web activity event collection in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b43f1-105">Dynamics 365 Commerce låter webbplatsadministratörer analysera webbaktiviteten bland användarna av deras näthandelssidor.</span><span class="sxs-lookup"><span data-stu-id="b43f1-105">Dynamics 365 Commerce lets site administrators analyze the web activity of users of their e-commerce sites.</span></span> <span data-ttu-id="b43f1-106">På så sätt kan de bättre förstå hur deras webbplatser används och kan optimera webbplatserna så att dessa ger en förbättrad användarupplevelse och uppfylla affärsmål.</span><span class="sxs-lookup"><span data-stu-id="b43f1-106">In that way, they can better understand how their sites are used, and they can optimize the sites to provide an improved user experience and meet business objectives.</span></span>


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a><span data-ttu-id="b43f1-107">Sätt för administratörer att implementera en avanmälningsupplevelse</span><span class="sxs-lookup"><span data-stu-id="b43f1-107">Ways for administrators to implement an opt-out experience</span></span>

<span data-ttu-id="b43f1-108">Administratörer har tre sätt att implementera en avanmälningsupplevelse.</span><span class="sxs-lookup"><span data-stu-id="b43f1-108">Administrators have three ways to implement an opt-out experience.</span></span>

### <a name="opt-out-on-behalf-of-users"></a><span data-ttu-id="b43f1-109">Avanmälning för användarnas räkning</span><span class="sxs-lookup"><span data-stu-id="b43f1-109">Opt out on behalf of users</span></span>

<span data-ttu-id="b43f1-110">Under Kontohantering i Commerce headquarters (HQ) kan administratörer avanmäla sig för användarnas räkning.</span><span class="sxs-lookup"><span data-stu-id="b43f1-110">In Account management in Commerce headquarters (HQ), administrators can opt out on behalf of users.</span></span>

1. <span data-ttu-id="b43f1-111">Sök efter samt välj en kund på sidan **Alla kunder** i HQ-klienten.</span><span class="sxs-lookup"><span data-stu-id="b43f1-111">In the HQ client, on the **All customers** page, search for and select a customer.</span></span>
1. <span data-ttu-id="b43f1-112">I snabbfliken **Detaljhandel** på sidan för kundinformation, i avsnittet **Sekretess**, anger du alternativet **Spåra inte webbaktivitet** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b43f1-112">On the customer details page, on the **Retail** FastTab, in the **Privacy** section, set the **Do not track web activity** option to **Yes**.</span></span>

    ![Sekretessinställningar](media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="b43f1-114">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="b43f1-114">Select **Save**, and then close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="b43f1-115">Modulbaserad avanmälningsupplevelse</span><span class="sxs-lookup"><span data-stu-id="b43f1-115">Module-based opt-out experience</span></span>

<span data-ttu-id="b43f1-116">Administratörer kan låta autentiserade användare själva säga upp insamling av webbaktivitetshändelser.</span><span class="sxs-lookup"><span data-stu-id="b43f1-116">Administrators can let authenticated users opt out of web activity event collection by themselves.</span></span> <span data-ttu-id="b43f1-117">För att tillhandahålla den här avanmälningsupplevelsen lägger du till avanmälningsmodulen i profilsidor för kundkonton.</span><span class="sxs-lookup"><span data-stu-id="b43f1-117">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="b43f1-118">Anpassade tillägg</span><span class="sxs-lookup"><span data-stu-id="b43f1-118">Custom extensions</span></span>

<span data-ttu-id="b43f1-119">Administratörer kan skapa sina egna tillägg för att hantera användarnas avanmälningsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="b43f1-119">Administrators can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="b43f1-120">Mer information finns i [anropa API:er för Butik](e-commerce-extensibility/call-retail-server-apis.md) och [Utbyggbarhet av onlinekanal](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="b43f1-120">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
