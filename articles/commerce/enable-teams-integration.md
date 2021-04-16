---
title: Aktivera Dynamics 365 Commerce och Microsoft Teams-integration
description: I det här avsnittet beskrivs hur du aktiverar Microsoft Dynamics 365 Commerce och Microsoft Teams-integrerar.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c0dbf7a3c7fa3532e35cac240c1abb8adbdbe489
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842745"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a><span data-ttu-id="be3d6-103">Aktivera Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="be3d6-103">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="be3d6-104">I det här avsnittet beskrivs hur du aktiverar Microsoft Dynamics 365 Commerce och Microsoft Teams-integrerar.</span><span class="sxs-lookup"><span data-stu-id="be3d6-104">This topic describes how to enable Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="be3d6-105">Att förse Teams med information från Dynamics 365 Commerce och synkronisera uppgiftshanteringsfunktionerna mellan Teams och kassaappen, måste du aktivera integrationsfunktionerna i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="be3d6-105">To provision Teams with information from Dynamics 365 Commerce and synchronize the task management features between Teams and the point of sale (POS) application, you must enable the integration features in Commerce headquarters.</span></span>

> [!NOTE]
> <span data-ttu-id="be3d6-106">När du aktiverar Teams-integration godkänner du att du delar dina data med Team.</span><span class="sxs-lookup"><span data-stu-id="be3d6-106">When you enable Teams integration, you consent to share your data with Teams.</span></span> <span data-ttu-id="be3d6-107">Data som delas med Teams kanske finns i ett annat land än dina Commerce-data, och kan tillämpas på andra efterföljande standarder.</span><span class="sxs-lookup"><span data-stu-id="be3d6-107">Data that is shared with Teams might reside in a different country than your Commerce data, and it might be subject to different compliance standards.</span></span> <span data-ttu-id="be3d6-108">För mer information, se [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="be3d6-108">For more information, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="be3d6-109">Mer information om sekretesspolicy för Microsoft finns i [Microsoft sekretesspolicyn](https://aka.ms/privacy).</span><span class="sxs-lookup"><span data-stu-id="be3d6-109">For information about Microsoft privacy policies, see the [Microsoft Privacy Statement](https://aka.ms/privacy).</span></span>

## <a name="enable-teams-integration"></a><span data-ttu-id="be3d6-110">Aktivera Teams-integration</span><span class="sxs-lookup"><span data-stu-id="be3d6-110">Enable Teams integration</span></span>

<span data-ttu-id="be3d6-111">Innan du kan aktivera Microsoft Teams-integreringen med Commerce måste du registrera programmet Teams med din innehavare i Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="be3d6-111">Before you can enable Microsoft Teams integration with Commerce, you must register the Teams application with your tenant in the Azure portal.</span></span>

<span data-ttu-id="be3d6-112">Registrera Teams-programmet hos din innehavare i Azure-portal genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="be3d6-112">To register the Teams application with your tenant in the Azure portal, follow these steps.</span></span>

1. <span data-ttu-id="be3d6-113">Följ stegen i [Snabbstart: Registrera en app i Microsoft identitetsplattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) för att registrera Teams-applikationen med din klient i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="be3d6-113">Follow the steps in [Quickstart: Register an app in the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) to register the Teams application with your tenant in the Azure portal.</span></span>
1. <span data-ttu-id="be3d6-114">Kopiera värdet **App (klient) ID** från **Översikt** för den registrerade appen.</span><span class="sxs-lookup"><span data-stu-id="be3d6-114">Copy the **Application (client) ID** value from the **Overview** page for the registered app.</span></span> <span data-ttu-id="be3d6-115">Det här värdet använder du när du aktiverar Teams-integration i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="be3d6-115">You will use this value to enable Teams integration in Commerce headquarters.</span></span>
1. <span data-ttu-id="be3d6-116">Kopiera intygsvärdet som angavs när du [lade till ett intyg](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) i steg 1.</span><span class="sxs-lookup"><span data-stu-id="be3d6-116">Copy the certificate value that was entered when you [added a certificate](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) in step 1.</span></span> <span data-ttu-id="be3d6-117">Certifikatet kallas också för offentlig nyckel eller programnyckel.</span><span class="sxs-lookup"><span data-stu-id="be3d6-117">The certificate is also known as the public key or application key.</span></span> <span data-ttu-id="be3d6-118">Det här värdet använder du när du aktiverar Teams-integration i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="be3d6-118">You will use this value to enable Teams integration in Commerce headquarters.</span></span>

<span data-ttu-id="be3d6-119">För att möjliggöra Teams-integrering i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="be3d6-119">To enable Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="be3d6-120">Öppna **Retail och Commerce \> Kanalinställningar \> Microsoft Teams integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="be3d6-120">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams integration configuration**.</span></span>
1. <span data-ttu-id="be3d6-121">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="be3d6-121">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="be3d6-122">Ange alternativet **Aktivera Microsoft Teams-integration** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="be3d6-122">Set the **Enable Microsoft Teams integration** option to **Yes**.</span></span>
1. <span data-ttu-id="be3d6-123">I fälten **Program-ID** och **Programnyckel**, ange de värden du fick när du registrerade Teams-appen i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="be3d6-123">In the **Application ID** and **Application key** fields, enter the values you obtained when you registered the Teams application in the Azure portal.</span></span>
1. <span data-ttu-id="be3d6-124">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="be3d6-124">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="be3d6-125">I följande bild visas ett exempel på konfigurationen av Teams-integration i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="be3d6-125">The following illustration shows an example of the configuration of Teams integration in Commerce headquarters.</span></span>

![Konfiguration av Teams-integration i Commerce-administration](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a><span data-ttu-id="be3d6-127">Inaktivera Teams-integration</span><span class="sxs-lookup"><span data-stu-id="be3d6-127">Disable Teams integration</span></span>

<span data-ttu-id="be3d6-128">För att inaktivera Microsoft Teams-integrering i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="be3d6-128">To disable Microsoft Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="be3d6-129">Öppna **Retail och Commerce \> Kanalinställningar \> Microsoft Teams integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="be3d6-129">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="be3d6-130">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="be3d6-130">On the Action Pane, select **Edit**.</span></span>
3. <span data-ttu-id="be3d6-131">Ange alternativet **Aktivera Microsoft Teams-integration** till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="be3d6-131">Set the **Enable Microsoft Teams integration** option to **No**.</span></span>
4. <span data-ttu-id="be3d6-132">Rensa värdena från fälten för **program-ID** och **programnyckel**.</span><span class="sxs-lookup"><span data-stu-id="be3d6-132">Clear the values from the **Application ID** and **Application Key** fields.</span></span>
1. <span data-ttu-id="be3d6-133">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="be3d6-133">On the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="be3d6-134">När du inaktiverar Teams-integration med Commerce visar kassaterminaler inte längre uppgifter som har publiceras från Teams-programmet.</span><span class="sxs-lookup"><span data-stu-id="be3d6-134">After you disable Teams integration with Commerce, POS terminals will no longer show tasks that are published from the Teams application.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be3d6-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="be3d6-135">Additional resources</span></span>

[<span data-ttu-id="be3d6-136">Dynamics 365 Commerce och Microsoft Teams-integrering, översikt</span><span class="sxs-lookup"><span data-stu-id="be3d6-136">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="be3d6-137">Provision Microsoft Teams från Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="be3d6-137">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="be3d6-138">Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="be3d6-138">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="be3d6-139">Hantera användarroller i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be3d6-139">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="be3d6-140">Mappa butiker och team om det finns befintliga team i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be3d6-140">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="be3d6-141">Vanliga frågor och svar om Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="be3d6-141">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
