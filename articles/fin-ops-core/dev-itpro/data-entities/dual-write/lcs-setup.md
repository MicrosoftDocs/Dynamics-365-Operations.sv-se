---
title: Inställning av dubbelriktad skrivning från Lifecycle Services
description: I det här avsnittet beskrivs hur du ställer in en dubbelriktad anslutning från Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: e51b4ef1e309e5f89dc82a3776b88c505dc6593d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748551"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="4ef19-103">Inställning av dubbelriktad skrivning från Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="4ef19-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="4ef19-104">I det här avsnittet beskrivs hur du ställer in en dubbelriktad anslutning i en ny Finance and Operations-miljö och en ny Dataverse-miljö från Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4ef19-104">This topic explains how to set up a dual-write connection between a new Finance and Operations environment and a new Dataverse environment from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4ef19-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4ef19-105">Prerequisites</span></span>

<span data-ttu-id="4ef19-106">Du måste vara administratör för att kunna konfigurera en anslutning med dubbelriktad anslutning.</span><span class="sxs-lookup"><span data-stu-id="4ef19-106">You must be an admin to set up a dual-write connection.</span></span>

+ <span data-ttu-id="4ef19-107">Du måste ha åtkomst till innehavare.</span><span class="sxs-lookup"><span data-stu-id="4ef19-107">You must have access to the tenant.</span></span>
+ <span data-ttu-id="4ef19-108">Du måste vara administratör i både Finance and Operations-miljöer och Dataverse-miljöer.</span><span class="sxs-lookup"><span data-stu-id="4ef19-108">You must be an admin in both Finance and Operations environments and Dataverse environments.</span></span>

## <a name="set-up-a-dual-write-connection"></a><span data-ttu-id="4ef19-109">Konfigurera en dubbelriktad anslutning</span><span class="sxs-lookup"><span data-stu-id="4ef19-109">Set up a dual-write connection</span></span>

<span data-ttu-id="4ef19-110">Följ dessa steg för att konfigurera dubbelriktad anslutning.</span><span class="sxs-lookup"><span data-stu-id="4ef19-110">Follow these steps to set up the dual-write connection.</span></span>

1. <span data-ttu-id="4ef19-111">I LCS till ditt projekt.</span><span class="sxs-lookup"><span data-stu-id="4ef19-111">In LCS, go to your project.</span></span>
2. <span data-ttu-id="4ef19-112">Välj **konfigurera** om du vill distribuera en ny miljö.</span><span class="sxs-lookup"><span data-stu-id="4ef19-112">Select **Configure** to deploy a new environment.</span></span>
3. <span data-ttu-id="4ef19-113">Välj version.</span><span class="sxs-lookup"><span data-stu-id="4ef19-113">Select the version.</span></span> 
4. <span data-ttu-id="4ef19-114">Välj topologi.</span><span class="sxs-lookup"><span data-stu-id="4ef19-114">Select the topology.</span></span> <span data-ttu-id="4ef19-115">Om det bara finns en tillgänglig topologi väljs den automatiskt.</span><span class="sxs-lookup"><span data-stu-id="4ef19-115">If only one topology is available, it's automatically selected.</span></span>
5. <span data-ttu-id="4ef19-116">Slutför de första stegen i guiden **distributionsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="4ef19-116">Complete the first steps in the **Deployment settings** wizard.</span></span>
6. <span data-ttu-id="4ef19-117">På fliken **Dataverse** följ stegen:</span><span class="sxs-lookup"><span data-stu-id="4ef19-117">On the **Dataverse** tab, follow one of these steps:</span></span>

    - <span data-ttu-id="4ef19-118">Om en Dataverse-miljö redan har etablerats för din klientorganisation kan du välja den.</span><span class="sxs-lookup"><span data-stu-id="4ef19-118">If a Dataverse environment is already provisioned for your tenant, you can select it.</span></span>

        1. <span data-ttu-id="4ef19-119">Ange alternativet **Konfigurera Dataverse** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4ef19-119">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="4ef19-120">I kolumnen **Tillgängliga miljöer** välj miljön som ska integreras med dina Finance and Operations data.</span><span class="sxs-lookup"><span data-stu-id="4ef19-120">In the **Available environments** column, select the environment to integrate with your Finance and Operations data.</span></span> <span data-ttu-id="4ef19-121">Listan innehåller alla miljöer där du har administratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="4ef19-121">The list includes all environments where you have admin privileges.</span></span>
        3. <span data-ttu-id="4ef19-122">Markera kryssrutan **acceptera** för att ange att du godkänner villkoren.</span><span class="sxs-lookup"><span data-stu-id="4ef19-122">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Fliken Dataverse när en Dataverse-miljö redan har etablerats för din klientorganisation](../dual-write/media/lcs_setup_1.png)

    - <span data-ttu-id="4ef19-124">Om din klientorganisation inte redan har en Dataverse-miljö, kommer en ny miljö att etableras.</span><span class="sxs-lookup"><span data-stu-id="4ef19-124">If your tenant doesn't already have a Dataverse environment, a new environment will be provisioned.</span></span>

        1. <span data-ttu-id="4ef19-125">Ange alternativet **Konfigurera Dataverse** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4ef19-125">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="4ef19-126">Ange ett namn på Dataverse-miljön.</span><span class="sxs-lookup"><span data-stu-id="4ef19-126">Enter a name for the Dataverse environment.</span></span>
        3. <span data-ttu-id="4ef19-127">Välj regionen som miljön ska distribueras till.</span><span class="sxs-lookup"><span data-stu-id="4ef19-127">Select the region to deploy the environment in.</span></span>
        4. <span data-ttu-id="4ef19-128">Välj standardspråk och valuta för miljön.</span><span class="sxs-lookup"><span data-stu-id="4ef19-128">Select the default language and currency for the environment.</span></span>

            > [!NOTE]
            > <span data-ttu-id="4ef19-129">Du kan inte ändra språk och valuta senare.</span><span class="sxs-lookup"><span data-stu-id="4ef19-129">You can't change the language and currency later.</span></span>

        5. <span data-ttu-id="4ef19-130">Markera kryssrutan **acceptera** för att ange att du godkänner villkoren.</span><span class="sxs-lookup"><span data-stu-id="4ef19-130">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Dataverse fliken när din klientorganisation inte redan har Dataverse-miljö](../dual-write/media/lcs_setup_2.png)

7. <span data-ttu-id="4ef19-132">Slutför de kvarstående stegen i guiden **distributionsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="4ef19-132">Complete the remaining steps in the **Deployment settings** wizard.</span></span>
8. <span data-ttu-id="4ef19-133">När miljön har statusen **distribuerad** ska du öppna sidan miljöinformation.</span><span class="sxs-lookup"><span data-stu-id="4ef19-133">After the environment has a status of **Deployed**, open the environment details page.</span></span> <span data-ttu-id="4ef19-134">I avsnittet **Power Platform-integration** visas namnen på Finance and Operations-miljön och Dataverse-miljön som är länkade.</span><span class="sxs-lookup"><span data-stu-id="4ef19-134">The **Power Platform Integration** section shows the names of the Finance and Operations environment and the Dataverse environment that are linked.</span></span>

    ![Power Platform-integrationsavsnitt](../dual-write/media/lcs_setup_3.png)

9. <span data-ttu-id="4ef19-136">En administratör för Finance and Operations-miljön måste logga in på LCS och välja **länka till CDS-skivor för appar** för att slutföra länken.</span><span class="sxs-lookup"><span data-stu-id="4ef19-136">An admin of the Finance and Operations environment must sign in to LCS and select **Link to CDS for Apps** to complete the link.</span></span> <span data-ttu-id="4ef19-137">På sidan miljöinformation visas kontaktinformationen för administratören.</span><span class="sxs-lookup"><span data-stu-id="4ef19-137">The environment details page shows the admin's contact information.</span></span>

    <span data-ttu-id="4ef19-138">När länken är slutförd uppdateras status till **Miljölänkning har slutförts**.</span><span class="sxs-lookup"><span data-stu-id="4ef19-138">After the link is completed, the status is updated to **Environment linking successfully completed**.</span></span>

10. <span data-ttu-id="4ef19-139">Öppna arbetsytan **Dataintegration** i Finance and Operations-miljön och kontrollera vilka mallar som är tillgängliga, välj **Länk till CDS för appar**.</span><span class="sxs-lookup"><span data-stu-id="4ef19-139">To open the **Data integration** workspace in the Finance and Operations environment and control the templates that are available, select **Link to CDS for Apps**.</span></span>

    ![Knappen länk till CDS för appar i avsnittet Power Platform-integration](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> <span data-ttu-id="4ef19-141">Du kan inte avlänka miljöer med hjälp av LCS.</span><span class="sxs-lookup"><span data-stu-id="4ef19-141">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="4ef19-142">Om du vill ta bort länken för en miljö, öppna arbetsytan **Dataintegration** i Finance and Operations-miljön och välj sen **Ta bort länk**.</span><span class="sxs-lookup"><span data-stu-id="4ef19-142">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]