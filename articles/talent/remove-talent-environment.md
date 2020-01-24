---
title: Ta bort Talent-miljöer
description: I det här avsnittet får du veta hur du tar bort en testkörning eller produktionsmiljö för Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: e752d658388fc6cb6f4b84ac83cb12a71522199b
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898120"
---
# <a name="remove-talent-environments"></a><span data-ttu-id="2d949-103">Ta bort Talent-miljöer</span><span class="sxs-lookup"><span data-stu-id="2d949-103">Remove Talent environments</span></span>

<span data-ttu-id="2d949-104">I det här avsnittet får du veta hur du tar bort en testkörning eller produktionsmiljö för Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="2d949-104">This topic walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Talent.</span></span>

## <a name="removing-a-test-drive-environment"></a><span data-ttu-id="2d949-105">Ta bort en testkörningsmiljö</span><span class="sxs-lookup"><span data-stu-id="2d949-105">Removing a test drive environment</span></span>

<span data-ttu-id="2d949-106">Talent testkörning etableras med en 60 dagars giltighetspolicy.</span><span class="sxs-lookup"><span data-stu-id="2d949-106">Talent test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="2d949-107">Ägare av testkörningsmiljöer kan emellertid välja sina testmiljöer tidigt genom att utföra följande steg.</span><span class="sxs-lookup"><span data-stu-id="2d949-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="2d949-108">Gå till [Power Apps administrationscenter](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="2d949-108">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="2d949-109">Välj **Miljö**.</span><span class="sxs-lookup"><span data-stu-id="2d949-109">Select **Environments**.</span></span>
3. <span data-ttu-id="2d949-110">Välj testkörningsmiljö som har ett namnmönster ungefär så här: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="2d949-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="2d949-111">Välj **Ta bort** och bekräfta beslutet.</span><span class="sxs-lookup"><span data-stu-id="2d949-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="2d949-112">Den befintliga testkörningsmiljön tas bort.</span><span class="sxs-lookup"><span data-stu-id="2d949-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="2d949-113">Om det tas bort kan du skaffa en ny testkörningmiljö.</span><span class="sxs-lookup"><span data-stu-id="2d949-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="removing-a-production-environment"></a><span data-ttu-id="2d949-114">Ta bort en produktionsmiljö</span><span class="sxs-lookup"><span data-stu-id="2d949-114">Removing a production environment</span></span>

<span data-ttu-id="2d949-115">Det här avsnittet förutsätter att du har köpt Talent via en molnbaserad lösningsleverantör (CSP) eller ett arkitekturavtal för företag (EA).</span><span class="sxs-lookup"><span data-stu-id="2d949-115">This topic assumes that you've purchased Talent through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="2d949-116">Eftersom en enda Talent-miljö ”ingår” i en enda Power Apps-miljö, finns det två alternativ att välja mellan.</span><span class="sxs-lookup"><span data-stu-id="2d949-116">Since a single Talent environment is “contained” within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="2d949-117">Det första alternativet innebär att ta bort hela Power Apps-miljön. Det andra alternativet innebär att endast Talent tas bort.</span><span class="sxs-lookup"><span data-stu-id="2d949-117">The first option involves removing the entire Power Apps environment; the second option involves removing only Talent.</span></span> <span data-ttu-id="2d949-118">Det första alternativet är att föredra när du har skapat en Power Apps-miljö uttryckligen i syfte att etablera Talent och du har precis börjat genomförandet eller du har inte några fastställda integrationer.</span><span class="sxs-lookup"><span data-stu-id="2d949-118">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Talent, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="2d949-119">Det andra alternativet är lämpligt om du har en fastställd Power Apps-miljö fylld med rich-data som utnyttjas i Power Apps och Power Automate.</span><span class="sxs-lookup"><span data-stu-id="2d949-119">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="2d949-120">Innan du tar bort Power Apps-miljön, se till att den inte används för integrering av rich-data utanför Talents omfattning.</span><span class="sxs-lookup"><span data-stu-id="2d949-120">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Talent.</span></span> <span data-ttu-id="2d949-121">Observera även att de standardinställda Power Apps-miljöerna inte kan tas bort.</span><span class="sxs-lookup"><span data-stu-id="2d949-121">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="2d949-122">För att ta bort hela Power Apps-miljön, inklusive Talent och tillhörande program och flöden:</span><span class="sxs-lookup"><span data-stu-id="2d949-122">To remove the entire Power Apps environment, including Talent and the associated apps and flows:</span></span>

1. <span data-ttu-id="2d949-123">Gå till [Power Apps administrationscenter](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="2d949-123">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="2d949-124">Välj **Miljö**.</span><span class="sxs-lookup"><span data-stu-id="2d949-124">Select **Environments**.</span></span>
3. <span data-ttu-id="2d949-125">Välj miljön som ska tas bort.</span><span class="sxs-lookup"><span data-stu-id="2d949-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="2d949-126">Välj **Ta bort** och bekräfta beslutet.</span><span class="sxs-lookup"><span data-stu-id="2d949-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="2d949-127">Vänta tills borttagningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="2d949-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="2d949-128">Logga in på [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) med det konto som du använder för din Talent-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="2d949-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Talent.</span></span> 
7. <span data-ttu-id="2d949-129">Välj Talent-projektet som innehåller miljön.</span><span class="sxs-lookup"><span data-stu-id="2d949-129">Select the Talent Project that contains the environment.</span></span> 
8. <span data-ttu-id="2d949-130">I LCS-projektet väljer du fliken **App-hantering for Talent**.</span><span class="sxs-lookup"><span data-stu-id="2d949-130">In your LCS project, select the **Talent App Management** tile.</span></span> 
9. <span data-ttu-id="2d949-131">Markera instansen som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="2d949-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="2d949-132">Välj **Ta bort instans** och bekräfta ditt val.</span><span class="sxs-lookup"><span data-stu-id="2d949-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="2d949-133">Gör följande om du vill ta bort en Talent-miljö från en befintlig Power Apps-miljö.</span><span class="sxs-lookup"><span data-stu-id="2d949-133">To remove a Talent environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="2d949-134">Observera att behovet av att involvera stöd och kontakta Talent DevOps-teamet är tillfälligt tills funktionen aktiveras direkt i LCS.</span><span class="sxs-lookup"><span data-stu-id="2d949-134">Note that the need to involve support and contact the Talent DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="2d949-135">Kontakta supporten för att initiera en begäran om borttagning.</span><span class="sxs-lookup"><span data-stu-id="2d949-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="2d949-136">Supportteamet initierar en begäran om borttagning med Talent DevOps-teamet.</span><span class="sxs-lookup"><span data-stu-id="2d949-136">The Support team will initiate a removal request with the Talent DevOps team.</span></span> 
3. <span data-ttu-id="2d949-137">Fortsätt efter att du fått veta att miljön har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="2d949-137">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="2d949-138">Logga in på LCS med det konto som du använder för din Talent-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="2d949-138">Sign in to LCS using the account that you used to subscribe to Talent.</span></span> 
5. <span data-ttu-id="2d949-139">Välj Talent-projektet som innehåller miljön.</span><span class="sxs-lookup"><span data-stu-id="2d949-139">Select the Talent project that contains the environment.</span></span> 
6. <span data-ttu-id="2d949-140">I LCS-projektet väljer du fliken **App-hantering for Talent**.</span><span class="sxs-lookup"><span data-stu-id="2d949-140">In your LCS project, select the **Talent App Management** tile.</span></span> 
7. <span data-ttu-id="2d949-141">Välj instansen som du vill ta bort, som bör markeras med distributionsstatusen **Misslyckad**.</span><span class="sxs-lookup"><span data-stu-id="2d949-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="2d949-142">Välj **Ta bort instans** och bekräfta ditt val.</span><span class="sxs-lookup"><span data-stu-id="2d949-142">Select **Remove instance** and confirm your decision.</span></span> 

