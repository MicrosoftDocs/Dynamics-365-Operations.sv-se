---
title: Ställa in en e-handelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server
description: Det här ämnet förklarar hur du ställer in en e-handelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server (VM).
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 38a616c418c3b32490c9adaf69a69af0d47d3478
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019456"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a><span data-ttu-id="dbd29-103">Ställa in en e-handelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server</span><span class="sxs-lookup"><span data-stu-id="dbd29-103">Set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dbd29-104">Det här ämnet förklarar hur du ställer in en e-handelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server (VM).</span><span class="sxs-lookup"><span data-stu-id="dbd29-104">This topic explains how to set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine (VM).</span></span>

## <a name="description"></a><span data-ttu-id="dbd29-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="dbd29-105">Description</span></span>

<span data-ttu-id="dbd29-106">Microsoft Dynamics 365 Commerce nivå 1-miljöer distribueras normalt för Commerce Runtime (CRT) och utökning av kassa (POS).</span><span class="sxs-lookup"><span data-stu-id="dbd29-106">Microsoft Dynamics 365 Commerce Tier 1 environments are typically deployed for Commerce runtime (CRT) and point of sale (POS) extension development.</span></span> <span data-ttu-id="dbd29-107">De är fristående miljöer.</span><span class="sxs-lookup"><span data-stu-id="dbd29-107">They are standalone environments.</span></span> <span data-ttu-id="dbd29-108">På grund av programvaran som en tjänst (SaaS) karaktär av arkitekturen, omfattar de inte komponenter för e-handel.</span><span class="sxs-lookup"><span data-stu-id="dbd29-108">Because of the software as a service (SaaS) nature of the architecture, they don't include e-commerce components.</span></span>

<span data-ttu-id="dbd29-109">I vissa scenarier kanske du vill testa anrop till tillägg i en nivå 1-miljö, så att du kan felsöka tillägg från e-handelskomponenter.</span><span class="sxs-lookup"><span data-stu-id="dbd29-109">In some scenarios, you might want to test calls to extensions in a Tier 1 environment, so that you can debug extensions from e-commerce components.</span></span> <span data-ttu-id="dbd29-110">För allmänna instruktioner, se [Felsöka mot en nivå 1 Commerce utvecklingsmiljö](../e-commerce-extensibility/debug-tier-1.md).</span><span class="sxs-lookup"><span data-stu-id="dbd29-110">For general instructions, see [Debug against a Tier 1 Commerce development environment](../e-commerce-extensibility/debug-tier-1.md).</span></span>

<span data-ttu-id="dbd29-111">När du felsöker mot en nivå 1-miljö, eftersom webbplatsen nu anropar en annan Retail Server, kan det leda till olika fel som hör till säkerhetspolicyn för innehåll.</span><span class="sxs-lookup"><span data-stu-id="dbd29-111">When you debug against a Tier 1 environment, because the site is now calling a different Retail Server, cross-server calls might cause various errors that are related to the content security policy.</span></span>

<span data-ttu-id="dbd29-112">I bilden nedan visas ett exempel på ett fel som kan inträffa när en variant väljs på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="dbd29-112">The following illustration shows an example of an error that might occur when a variant is selected on a product details page.</span></span>

![Fel när en variant väljs på en produktinformationssida](media/unhandled-rejection-error.jpg)

<span data-ttu-id="dbd29-114">I följande bild visas ett exempel på ett liknande fel i en webbläsares felsökningsverktyg (F12 utvecklarverktyg).</span><span class="sxs-lookup"><span data-stu-id="dbd29-114">The following illustration shows an example of a similar error in a browser's debugger tools (F12 Developer Tools).</span></span> <span data-ttu-id="dbd29-115">Felmeddelandet tar upp brott mot säkerhetspolicyn för innehåll.</span><span class="sxs-lookup"><span data-stu-id="dbd29-115">The error message mentions violation of the content security policy directive.</span></span>

![Fel i felsökningsverktyg](media/debugger-tools-error.JPG)

## <a name="resolution"></a><span data-ttu-id="dbd29-117">Upplösning</span><span class="sxs-lookup"><span data-stu-id="dbd29-117">Resolution</span></span>

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a><span data-ttu-id="dbd29-118">Inaktivera säkerhetspolicyn för innehåll för webbplatsen i Commerce-webbplatsbyggaren</span><span class="sxs-lookup"><span data-stu-id="dbd29-118">Disable the content security policy for the site in Commerce site builder</span></span>

1. <span data-ttu-id="dbd29-119">Välj den webbplats som du arbetar på.</span><span class="sxs-lookup"><span data-stu-id="dbd29-119">Select the site that you're working on.</span></span>
1. <span data-ttu-id="dbd29-120">Välj **inställningar** och välj sedan **tillägg**.</span><span class="sxs-lookup"><span data-stu-id="dbd29-120">Select **Settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="dbd29-121">På fliken **Innehållssäkerhetspolicy**, välj **Inaktivera säkerhetspolicy för innehåll**.</span><span class="sxs-lookup"><span data-stu-id="dbd29-121">On the **Content security policy** tab, select **Disable content security policy**.</span></span>
1. <span data-ttu-id="dbd29-122">Välj **Spara och publicera**.</span><span class="sxs-lookup"><span data-stu-id="dbd29-122">Select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="dbd29-123">In inloggning mellan företag till kund (B2C) fungerar inte i en lokal utvecklingsmiljö.</span><span class="sxs-lookup"><span data-stu-id="dbd29-123">Business-to-consumer (B2C) sign-in won't work in a local development environment.</span></span> <span data-ttu-id="dbd29-124">Du kan dock använda gästutcheckningar eller skapa sidutdata för att simulera en användarindata vid behov.</span><span class="sxs-lookup"><span data-stu-id="dbd29-124">However, you can use guest checkouts or build page mocks to simulate a user sign-in as required.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dbd29-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="dbd29-125">Additional resources</span></span>

[<span data-ttu-id="dbd29-126">Kom i gång med utbyggnadsutveckling av näthandel</span><span class="sxs-lookup"><span data-stu-id="dbd29-126">Get started with e-commerce online extensibility development</span></span>](../e-commerce-extensibility/sdk-getting-started.md)

[<span data-ttu-id="dbd29-127">Hantera säkerhetspolicy för innehåll (CSP) på e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="dbd29-127">Manage content security policy (CSP) on e-commerce site</span></span>](../manage-csp.md)
