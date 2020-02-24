---
title: Ta bort en instans
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5c5f875ad9361c31af4fbe863488b881cdd97a6e
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010551"
---
# <a name="remove-an-instance"></a><span data-ttu-id="72899-102">Ta bort en instans</span><span class="sxs-lookup"><span data-stu-id="72899-102">Remove an instance</span></span>

<span data-ttu-id="72899-103">I det här artikel får du veta hur du tar bort en testkörning eller produktionsmiljö för Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72899-103">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="72899-104">Ta bort en testkörningsmiljö</span><span class="sxs-lookup"><span data-stu-id="72899-104">Remove a test drive environment</span></span>

<span data-ttu-id="72899-105">Personal testkörning etableras med en 60 dagars giltighetspolicy.</span><span class="sxs-lookup"><span data-stu-id="72899-105">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="72899-106">Ägare av testkörningsmiljöer kan emellertid välja sina testmiljöer tidigt genom att utföra följande steg.</span><span class="sxs-lookup"><span data-stu-id="72899-106">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="72899-107">Gå till [Power Apps administrationscenter](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="72899-107">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="72899-108">Välj **Miljö**.</span><span class="sxs-lookup"><span data-stu-id="72899-108">Select **Environments**.</span></span>
3. <span data-ttu-id="72899-109">Välj testkörningsmiljö som har ett namnmönster ungefär så här: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="72899-109">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="72899-110">Välj **Ta bort** och bekräfta beslutet.</span><span class="sxs-lookup"><span data-stu-id="72899-110">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="72899-111">Den befintliga testkörningsmiljön tas bort.</span><span class="sxs-lookup"><span data-stu-id="72899-111">The existing test drive environment will be removed.</span></span> <span data-ttu-id="72899-112">Om det tas bort kan du skaffa en ny testkörningmiljö.</span><span class="sxs-lookup"><span data-stu-id="72899-112">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="72899-113">Ta bort en produktionsmiljö</span><span class="sxs-lookup"><span data-stu-id="72899-113">Remove a production environment</span></span>

<span data-ttu-id="72899-114">Den här artikeln förutsätter att du har köpt Personal via en molnbaserad lösningsleverantör (CSP) eller ett arkitekturavtal för företag (EA).</span><span class="sxs-lookup"><span data-stu-id="72899-114">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="72899-115">Eftersom en enda Personal-miljö ”ingår” i en enda Power Apps-miljö, finns det två alternativ att välja mellan.</span><span class="sxs-lookup"><span data-stu-id="72899-115">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="72899-116">Det första alternativet innebär att ta bort hela Power Apps-miljön. Det andra alternativet innebär att endast Personal tas bort.</span><span class="sxs-lookup"><span data-stu-id="72899-116">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="72899-117">Det första alternativet är att föredra när du har skapat en Power Apps-miljö uttryckligen i syfte att etablera Personal och du har precis börjat genomförandet eller du har inte några fastställda integrationer.</span><span class="sxs-lookup"><span data-stu-id="72899-117">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="72899-118">Det andra alternativet är lämpligt om du har en fastställd Power Apps-miljö fylld med rich-data som utnyttjas i Power Apps och Power Automate.</span><span class="sxs-lookup"><span data-stu-id="72899-118">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="72899-119">Innan du tar bort Power Apps-miljön, se till att den inte används för integrering av rich-data utanför Personal omfattning.</span><span class="sxs-lookup"><span data-stu-id="72899-119">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="72899-120">Observera även att de standardinställda Power Apps-miljöerna inte kan tas bort.</span><span class="sxs-lookup"><span data-stu-id="72899-120">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="72899-121">För att ta bort hela Power Apps-miljön, inklusive Personal och tillhörande program och flöden:</span><span class="sxs-lookup"><span data-stu-id="72899-121">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="72899-122">Gå till [Power Apps administrationscenter](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="72899-122">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="72899-123">Välj **Miljö**.</span><span class="sxs-lookup"><span data-stu-id="72899-123">Select **Environments**.</span></span>
3. <span data-ttu-id="72899-124">Välj miljön som ska tas bort.</span><span class="sxs-lookup"><span data-stu-id="72899-124">Select the environment to be removed.</span></span>
4. <span data-ttu-id="72899-125">Välj **Ta bort** och bekräfta beslutet.</span><span class="sxs-lookup"><span data-stu-id="72899-125">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="72899-126">Vänta tills borttagningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="72899-126">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="72899-127">Logga in på [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) med det konto som du använder för din Personal-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="72899-127">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="72899-128">Välj Personal-projektet som innehåller miljön.</span><span class="sxs-lookup"><span data-stu-id="72899-128">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="72899-129">I LCS-projektet väljer du fliken **-hantering for Personal**.</span><span class="sxs-lookup"><span data-stu-id="72899-129">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="72899-130">Markera instansen som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="72899-130">Select the instance to remove.</span></span> 
10. <span data-ttu-id="72899-131">Välj **Ta bort instans** och bekräfta ditt val.</span><span class="sxs-lookup"><span data-stu-id="72899-131">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="72899-132">Gör följande om du vill ta bort en Personal-miljö från en befintlig Power Apps-miljö.</span><span class="sxs-lookup"><span data-stu-id="72899-132">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="72899-133">Observera att behovet av att involvera stöd och kontakta Personal DevOps-teamet är tillfälligt tills funktionen aktiveras direkt i LCS.</span><span class="sxs-lookup"><span data-stu-id="72899-133">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="72899-134">Kontakta supporten för att initiera en begäran om borttagning.</span><span class="sxs-lookup"><span data-stu-id="72899-134">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="72899-135">Supportteamet initierar en begäran om borttagning med Personal DevOps-teamet.</span><span class="sxs-lookup"><span data-stu-id="72899-135">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="72899-136">Fortsätt efter att du fått veta att miljön har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="72899-136">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="72899-137">Logga in på LCS med det konto som du använder för din Personal-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="72899-137">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="72899-138">Välj Personal-projektet som innehåller miljön.</span><span class="sxs-lookup"><span data-stu-id="72899-138">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="72899-139">I LCS-projektet väljer du fliken **-hantering for Personal**.</span><span class="sxs-lookup"><span data-stu-id="72899-139">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="72899-140">Välj instansen som du vill ta bort, som bör markeras med distributionsstatusen **Misslyckad**.</span><span class="sxs-lookup"><span data-stu-id="72899-140">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="72899-141">Välj **Ta bort instans** och bekräfta ditt val.</span><span class="sxs-lookup"><span data-stu-id="72899-141">Select **Remove instance** and confirm your decision.</span></span> 
