---
title: Kom igång med kostnadsredovisningstjänsten (privat förhandsvisning)
description: Det här avsnittet innehåller licensieringsinformation och Installationsinstruktioner för kostnadsredovisningstjänst.
author: AndersGirke
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: b6756e3745aa4596bd5d63ad15aaf4385cfc4813
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813205"
---
# <a name="get-started-with-the-cost-accounting-service-private-preview"></a><span data-ttu-id="77efc-103">Kom igång med kostnadsredovisningstjänsten (privat förhandsvisning)</span><span class="sxs-lookup"><span data-stu-id="77efc-103">Get started with the cost accounting service (private preview)</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="77efc-104">Funktionen som beskrivs i det här avsnittet är tillgänglig som en del av en privat förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="77efc-104">The functionality that is described in this topic is available as part of a private preview release.</span></span> <span data-ttu-id="77efc-105">Innehållet i det här avsnittet och den funktionalitet som det beskrivs i kan ändras.</span><span class="sxs-lookup"><span data-stu-id="77efc-105">The content of this topic and the functionality that it describes are subject to change.</span></span> <span data-ttu-id="77efc-106">Mer information om förhandsversioner finns i [Frågor och svar om tjänstuppdateringar för en version](../../fin-ops-core/fin-ops/get-started/one-version.md).</span><span class="sxs-lookup"><span data-stu-id="77efc-106">For more information about preview releases, see [One version service updates FAQ](../../fin-ops-core/fin-ops/get-started/one-version.md).</span></span>

<span data-ttu-id="77efc-107">Med hjälp av kostnadsredovisningstjänsten kan du utföra flera lagerredovisning i de kostnadsredovisning som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="77efc-107">The cost accounting service lets you do multiple inventory accounting in the cost accounting ledgers that you've set up.</span></span> <span data-ttu-id="77efc-108">Du kopplar varje redovisning med en kostnadsredovisning till en *konvention*.</span><span class="sxs-lookup"><span data-stu-id="77efc-108">You associate each cost accounting ledger with a *convention*.</span></span> <span data-ttu-id="77efc-109">En konvention är en samling av följande typer av redovisningsprinciper:</span><span class="sxs-lookup"><span data-stu-id="77efc-109">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="77efc-110">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="77efc-110">Cost object</span></span>
- <span data-ttu-id="77efc-111">Inmatningsmåttbas</span><span class="sxs-lookup"><span data-stu-id="77efc-111">Input measurement basis</span></span>
- <span data-ttu-id="77efc-112">Antagande för kostnadsflöde</span><span class="sxs-lookup"><span data-stu-id="77efc-112">Cost flow assumption</span></span>
- <span data-ttu-id="77efc-113">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="77efc-113">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="77efc-114">Även när du har aktiverat kostnadsredovisningstjänsten kan du fortfarande göra lagerredovisningen i Microsoft Dynamics 365 Supply Chain Management som vanligt.</span><span class="sxs-lookup"><span data-stu-id="77efc-114">Even after you've turned on the cost accounting service, you can still do  inventory accounting in Microsoft Dynamics 365 Supply Chain Management, as usual.</span></span>

<span data-ttu-id="77efc-115">Kostnadsredovisningstjänsten är ett tillägg.</span><span class="sxs-lookup"><span data-stu-id="77efc-115">The cost accounting service is an add-in.</span></span> <span data-ttu-id="77efc-116">För att göra funktionerna tillgängliga måste du installera det från Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="77efc-116">To makes its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="77efc-117">Därför kan du välja att utvärdera den i en testmiljö innan du aktiverar den för produktionsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="77efc-117">Therefore, you can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="77efc-118">Kostnadsredovisningstjänsten stöder för närvarande inte alla kostnads hanteringsfunktioner som är inbyggda i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="77efc-118">The cost accounting service doesn't currently support all the cost management features that are built into Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="77efc-119">Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen ska uppfylla dina krav.</span><span class="sxs-lookup"><span data-stu-id="77efc-119">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-cost-accounting-service-private-preview"></a><a name="sign-up"></a><span data-ttu-id="77efc-120">Så här kommer du igång med kostnadsredovisningstjänsten (privat förhandsvisning)</span><span class="sxs-lookup"><span data-stu-id="77efc-120">How to get the cost accounting service (private preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77efc-121">För att kunna använda kostnadsredovisningstjänsten måste du ha en LCS hög tillgänglighetsmiljö (inte en OneBox-miljö) och du måste köra Dynamics 365 Supply Chain Management version 10.0.11 eller senare.</span><span class="sxs-lookup"><span data-stu-id="77efc-121">To use the cost accounting service, you must have an LCS-enabled high-availability environment (not a OneBox environment), and you must be running Dynamics 365 Supply Chain Management version 10.0.11 or later.</span></span>

<span data-ttu-id="77efc-122">Om du vill registrera dig för privatförhandsvisning för kostnadsredovisningstjänsten skickar du ditt ID för LCS-miljö via e-post till [Kostnadsredovisningstjänst (privat förhandsvisning)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29).</span><span class="sxs-lookup"><span data-stu-id="77efc-122">To sign up for the cost accounting service private preview, please send your LCS environment ID by email to [Cost accounting service (private preview)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29).</span></span> <span data-ttu-id="77efc-123">När vi godkänner dig för programmet kommer vi att skicka ett uppföljningsmail till dig som innehåller en betanyckel för kostnadsredovisningtjänsten.</span><span class="sxs-lookup"><span data-stu-id="77efc-123">On approving you for the program, we will send you a follow up email that contains a cost accounting service beta key.</span></span> <span data-ttu-id="77efc-124">När du tar emot betanyckeln kan du fortsätta genom att [installera tillägget](#install).</span><span class="sxs-lookup"><span data-stu-id="77efc-124">On receiving the beta key, you can proceed by [installing the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="77efc-125">Licensiering</span><span class="sxs-lookup"><span data-stu-id="77efc-125">Licensing</span></span>

<span data-ttu-id="77efc-126">Kostnadsredovisningstjänsten licensieras tillsammans med de standardfunktioner i lagerredovisningen som är tillgängliga för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="77efc-126">The cost accounting service is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="77efc-127">Du behöver inte köpa ytterligare en licens för att kunna använda kostnadsredovisningstjänsten.</span><span class="sxs-lookup"><span data-stu-id="77efc-127">You don't have to purchase an additional license to use the cost accounting service.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="77efc-128">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="77efc-128">Install the add-in</span></span>

<span data-ttu-id="77efc-129">Om du vill använda kostnadsredovisningstjänsten installerar du tillägget kostnadsredovisningstjänst för Supply Chain Management enligt beskrivningen i följande procedur.</span><span class="sxs-lookup"><span data-stu-id="77efc-129">To use the cost accounting service, install the cost accounting service add-in for Supply Chain Management as described in the following procedure.</span></span>

1. <span data-ttu-id="77efc-130">[Registrera dig](#sign-up) för kostnadsredovisningstjänsten (privat förhandsvisning).</span><span class="sxs-lookup"><span data-stu-id="77efc-130">[Sign up](#sign-up) for the cost accounting service (private preview).</span></span>

1. <span data-ttu-id="77efc-131">Logga in på LCS.</span><span class="sxs-lookup"><span data-stu-id="77efc-131">Sign in to LCS.</span></span>

1. <span data-ttu-id="77efc-132">Gå till **Hantering av förhandsgranskningsfunktioner**.</span><span class="sxs-lookup"><span data-stu-id="77efc-132">Go to **Preview feature management**.</span></span>

1. <span data-ttu-id="77efc-133">Välj plustecknet (**+**).</span><span class="sxs-lookup"><span data-stu-id="77efc-133">Select the plus sign (**+**).</span></span>

1. <span data-ttu-id="77efc-134">I fältet **kod** anger du betanyckeln för tillägget för kostnadsredovisningstjänsten.</span><span class="sxs-lookup"><span data-stu-id="77efc-134">In the **Code** field, enter your add-in beta key for the cost accounting service.</span></span> <span data-ttu-id="77efc-135">(Du bör ha tagit emot nyckeln via e-post.)</span><span class="sxs-lookup"><span data-stu-id="77efc-135">(You should have received your key by email.)</span></span>

1. <span data-ttu-id="77efc-136">Välj **Avblockera**.</span><span class="sxs-lookup"><span data-stu-id="77efc-136">Select **Unblock**.</span></span>

1. <span data-ttu-id="77efc-137">Öppna LCS-miljön där du vill lägga till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="77efc-137">Open the LCS environment where you want to add the service.</span></span>

1. <span data-ttu-id="77efc-138">Gå till **Fullständiga detaljer**.</span><span class="sxs-lookup"><span data-stu-id="77efc-138">Go to **Full details**.</span></span>

1. <span data-ttu-id="77efc-139">Bläddra till snabbfliken **miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="77efc-139">Scroll down to the **Environment add-ins** FastTab.</span></span>

1. <span data-ttu-id="77efc-140">Välj **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="77efc-140">Select **Install a new add-in**.</span></span>

1. <span data-ttu-id="77efc-141">Välj **kostnadsredovisningstjänst**.</span><span class="sxs-lookup"><span data-stu-id="77efc-141">Select **Cost accounting service**.</span></span>

1. <span data-ttu-id="77efc-142">Följ installationsguiden och godkänn villkoren.</span><span class="sxs-lookup"><span data-stu-id="77efc-142">Follow the installation guide, and agree to the terms and conditions.</span></span>

1. <span data-ttu-id="77efc-143">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="77efc-143">Select **Install**.</span></span>

1. <span data-ttu-id="77efc-144">På snabbfliken **Miljötillägg** bör du se att kostnadsredovisningstjänsten installeras.</span><span class="sxs-lookup"><span data-stu-id="77efc-144">On the **Environment add-ins** FastTab, you should see that the cost accounting service is being installed.</span></span> <span data-ttu-id="77efc-145">Efter några minuter bör statusen ändras från **installera** till **installerad**.</span><span class="sxs-lookup"><span data-stu-id="77efc-145">After a few minutes, the status should change from **Installing** to **Installed**.</span></span> <span data-ttu-id="77efc-146">(Du kan behöva uppdatera sidan för att se ändringen.) Vid den tidpunkten är kostnadsredovisningstjänsten klar för användning.</span><span class="sxs-lookup"><span data-stu-id="77efc-146">(You might have to refresh the page to see this change.) At that point, the cost accounting service is ready for use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="77efc-147">Inställning och integrering</span><span class="sxs-lookup"><span data-stu-id="77efc-147">Set up the integration</span></span>

<span data-ttu-id="77efc-148">Så här ställer du in integrationen mellan kostnadsredovisningstjänsten och Dynamics 365 Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="77efc-148">To set up the integration between the cost accounting service and Dynamics 365 Supply Chain Management:</span></span>

1. <span data-ttu-id="77efc-149">Gå till **Systemadministration > Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="77efc-149">Go to **System administration > Feature Management**.</span></span>

1. <span data-ttu-id="77efc-150">Välj **Sök efter uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="77efc-150">Select **Check for updates**.</span></span>

1. <span data-ttu-id="77efc-151">Öppna fliken **alla** och sök efter funktionen *kostnadsredovisningstjänst*.</span><span class="sxs-lookup"><span data-stu-id="77efc-151">Open the **All** tab and search for the feature named *Cost accounting service*.</span></span>

1. <span data-ttu-id="77efc-152">Välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="77efc-152">Select **Enable now**.</span></span>

1. <span data-ttu-id="77efc-153">Gå till **Kostnadsredovisning > kostnadsredovisningstjänst > inställningar > parametrar för kostnadsredovisningtjänst > integrationsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="77efc-153">Go to **Cost management > Cost accounting service > Setup > Cost accounting service parameters > Integrations parameters**.</span></span>

1. <span data-ttu-id="77efc-154">I fälten **App-ID** anger du följande kod:</span><span class="sxs-lookup"><span data-stu-id="77efc-154">In the **Application ID** field, enter the following code:</span></span><br> <span data-ttu-id="77efc-155">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span><span class="sxs-lookup"><span data-stu-id="77efc-155">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span></span>

1. <span data-ttu-id="77efc-156">I fältet **Datatjänstslutpunkt** anger du följande URL:</span><span class="sxs-lookup"><span data-stu-id="77efc-156">In the **Data service endpoint** field, enter the following URL:</span></span><br>https://operationsdataservice.operations365.dynamics.com/

1. <span data-ttu-id="77efc-157">I fältet **Slutpunkt för kostnadsredovisningstjänst** anger du följande URL:</span><span class="sxs-lookup"><span data-stu-id="77efc-157">In the **Cost accounting service endpoint** field, enter the following URL:</span></span><br>https://costaccountingservice.operations365.dynamics.com/

1. <span data-ttu-id="77efc-158">Kostnadsredovisningstjänsten är nu klar att användas.</span><span class="sxs-lookup"><span data-stu-id="77efc-158">The cost accounting service is now ready for use.</span></span>

## <a name="related-resources"></a><span data-ttu-id="77efc-159">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="77efc-159">Related resources</span></span>

[<span data-ttu-id="77efc-160">Startsida för kostnadsredovisningstjänst</span><span class="sxs-lookup"><span data-stu-id="77efc-160">Cost accounting service home page</span></span>](cost-accounting-service-home.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]