---
title: Etablera en Dynamics 365 Commerce förhandsversionsmiljö
description: Det här avsnittet förklarar hur du etablerar en förhandsversionsmiljö för Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: cbd4c118de2e91c8849461b20a01403049a07e66
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024646"
---
# <a name="provision-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="4e136-103">Etablera en Dynamics 365 Commerce förhandsversionsmiljö</span><span class="sxs-lookup"><span data-stu-id="4e136-103">Provision a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="4e136-104">Det här avsnittet förklarar hur du etablerar en förhandsversionsmiljö för Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4e136-104">This topic explains how to provision a Dynamics 365 Commerce preview environment.</span></span>

<span data-ttu-id="4e136-105">Innan du börjar rekommenderar vi att du tar en snabbgenomgång genom det här avsnittet för att få en uppfattning om vad processen kräver.</span><span class="sxs-lookup"><span data-stu-id="4e136-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="4e136-106">Om du inte har beviljats åtkomst till förhandsgranskning för Dynamics 365 Commerce kan du begära förhandsgranskningsåtkomst från [Dynamics 365 Commerce webbplats](https://aka.ms/Dynamics365CommerceWebsite).</span><span class="sxs-lookup"><span data-stu-id="4e136-106">If you haven't yet been granted access to the Dynamics 365 Commerce preview, you can request preview access from the [Dynamics 365 Commerce website](https://aka.ms/Dynamics365CommerceWebsite).</span></span>

## <a name="overview"></a><span data-ttu-id="4e136-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="4e136-107">Overview</span></span>

<span data-ttu-id="4e136-108">För att kunna etablera din förhandsversionsmiljö för Commerce måste du skapa ett projekt som har ett specifikt produktnamn och en viss typ.</span><span class="sxs-lookup"><span data-stu-id="4e136-108">To successfully provision your Commerce preview environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="4e136-109">Miljön och skalningsenhet för handel (CSU) har även del specifika parametrar som du måste använda för att kunna etablera e-handel senare.</span><span class="sxs-lookup"><span data-stu-id="4e136-109">The environment and commerce scale unit (CSU) also have some specific parameters that you must use when you provision e-Commerce later.</span></span> <span data-ttu-id="4e136-110">Instruktionerna i det här avsnittet beskriver alla nödvändiga steg för att slutföra etablering och de parametrar som du måste använda.</span><span class="sxs-lookup"><span data-stu-id="4e136-110">The instructions in this topic describe all the steps required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="4e136-111">När du har tillhandahållit din förhandsversionsmiljö för Commerce måste du slutföra några steg efter etablering för att förbereda den.</span><span class="sxs-lookup"><span data-stu-id="4e136-111">After you successfully provision your Commerce preview environment, you must complete a few post-provisioning steps to prepare it.</span></span> <span data-ttu-id="4e136-112">Vissa steg är valfria, beroende på vilka delar av systemet du vill utvärdera.</span><span class="sxs-lookup"><span data-stu-id="4e136-112">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="4e136-113">Du kan alltid slutföra de valfria stegen senare.</span><span class="sxs-lookup"><span data-stu-id="4e136-113">You can always complete the optional steps later.</span></span>

<span data-ttu-id="4e136-114">Information om hur du konfigurerar förhandsversionsmiljö för Commerce efter att du har konfigurerat den finns i [Konfigurera en förhandsversionsmiljö för Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="4e136-114">For information about how to configure your Commerce preview environment after you provision it, see [Configure a Commerce preview environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="4e136-115">Information om hur du konfigurerar valfria funktioner för Commerce efter att du har konfigurerat den finns i [Konfigurera valfria funktioner för förhandsversionsmiljö för Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="4e136-115">For information about how to configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

<span data-ttu-id="4e136-116">Om du har frågor om etableringsstegen eller om du stöter på problem ska du tala om för Microsoft i [Microsoft Dynamics 365 Commerce förhandsgranskning Yammer-grupp](https://aka.ms/Dynamics365CommercePreviewYammer).</span><span class="sxs-lookup"><span data-stu-id="4e136-116">If you have any questions about the provisioning steps, or if you encounter any issues, let Microsoft know in the [Microsoft Dynamics 365 Commerce Preview Yammer group](https://aka.ms/Dynamics365CommercePreviewYammer).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4e136-117">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4e136-117">Prerequisites</span></span>

<span data-ttu-id="4e136-118">Följande förutsättningar måste vara på plats innan du kan etablera din förhandsversionsmiljö för Commerce:</span><span class="sxs-lookup"><span data-stu-id="4e136-118">The following prerequisites must be in place before you can provision your Commerce preview environment:</span></span>

- <span data-ttu-id="4e136-119">Du har åtkomst till Microsoft Dynamics Lifecycle Services-portal (LCS).</span><span class="sxs-lookup"><span data-stu-id="4e136-119">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="4e136-120">Du är en befintlig Microsoft Dynamics 365-partner eller kund och kan skapa ett Dynamics 365 Commerce-projekt.</span><span class="sxs-lookup"><span data-stu-id="4e136-120">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="4e136-121">Du har accepterats i Dynamics 365 Commerce förhandsgranskningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="4e136-121">You've been accepted into the Dynamics 365 Commerce Preview program.</span></span>
- <span data-ttu-id="4e136-122">Du har de behörigheter som krävs för att skapa ett projekt för **Migrera, skapa lösningar och lär dig**.</span><span class="sxs-lookup"><span data-stu-id="4e136-122">You have the required permissions to create a project for **Migrate, create solutions, and learn**.</span></span>
- <span data-ttu-id="4e136-123">Du är rollen **Miljöhanterare** eller **Projektägare** i projektet där du ska etablera miljön</span><span class="sxs-lookup"><span data-stu-id="4e136-123">You're a member of the **Environment manager** or **Project owner** role in the project where you will provision the environment.</span></span>
- <span data-ttu-id="4e136-124">Du har administratörsåtkomst till din Microsoft Azure-prenumeration eller kontakta en prenumerationsadministratör som kan slutföra de två steg som kräver administratörsbehörighet för din räkning</span><span class="sxs-lookup"><span data-stu-id="4e136-124">You have admin access to your Microsoft Azure subscription, or you're in contact with a subscription admin who can complete the two steps that require admin permissions on your behalf.</span></span>
- <span data-ttu-id="4e136-125">Du har ditt Azure Active Directory (Azure AD) innehavar-ID tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="4e136-125">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="4e136-126">Du har skapat en Azure AD-säkerhetsgrupp som kan användas som en systemadministratörsgrupp för e-handel och du har dess ID tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="4e136-126">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="4e136-127">Du har skapat en Azure AD-säkerhetsgrupp som kan användas som gruppen moderator för omdömen och recensioner och du har dess ID tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="4e136-127">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="4e136-128">(Den här säkerhetsgruppen kan vara samma som administratörsgruppen för e-handelssystem.)</span><span class="sxs-lookup"><span data-stu-id="4e136-128">(This security group can be the same as the e-Commerce system admin group.)</span></span>

## <a name="provision-your-commerce-preview-environment"></a><span data-ttu-id="4e136-129">Etablera en förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="4e136-129">Provision your Commerce preview environment</span></span>

<span data-ttu-id="4e136-130">Dessa procedurer förklarar hur du etablerar en förhandsversionsmiljö för Commerce.</span><span class="sxs-lookup"><span data-stu-id="4e136-130">These procedures explain how to provision a Commerce preview environment.</span></span> <span data-ttu-id="4e136-131">När du har slutfört dem kommer förhandsversionsmiljö för Commerce att vara redo för konfigurering.</span><span class="sxs-lookup"><span data-stu-id="4e136-131">After you successfully complete them, the Commerce preview environment will be ready for configuration.</span></span> <span data-ttu-id="4e136-132">Alla aktiviteter som beskrivs här utförs i LCS-portalen.</span><span class="sxs-lookup"><span data-stu-id="4e136-132">All the activities that are described here occur in the LCS portal.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e136-133">Förhandsgranskningsåtkomsten är knuten till LCS-kontot och organisationen som du angav i förhandsgranskningsprogrammet för Handel.</span><span class="sxs-lookup"><span data-stu-id="4e136-133">Preview access is tied to the LCS account and organization that you specified in your Commerce preview application.</span></span> <span data-ttu-id="4e136-134">Du måste använda samma konto för att etablera förhandsversionsmiljö för Commerce.</span><span class="sxs-lookup"><span data-stu-id="4e136-134">You must use the same account to provision the Commerce preview environment.</span></span> <span data-ttu-id="4e136-135">Om du måste använda ett annat LCS-konto eller en innehavare för förhandsversionsmiljö för Commerce måste du ange dessa uppgifter för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e136-135">If you need to use a different LCS account or tenant for the Commerce preview environment, you must provide those details to Microsoft.</span></span> <span data-ttu-id="4e136-136">Kontaktinformation finns i avsnittet [Förhandsversionsmiljö för Commerce](#commerce-preview-environment-support) senare i det här ämnet.</span><span class="sxs-lookup"><span data-stu-id="4e136-136">For contact information, see the [Commerce preview environment support](#commerce-preview-environment-support) section later in this topic.</span></span>

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a><span data-ttu-id="4e136-137">Bekräfta att förhandsgranskningsfunktioner är tillgängliga och aktiverade i LCS</span><span class="sxs-lookup"><span data-stu-id="4e136-137">Confirm that preview features are available and turned on in LCS</span></span>

<span data-ttu-id="4e136-138">För att bekräfta att förhandsgranskningsfunktioner är tillgängliga och aktiverade i LCS.</span><span class="sxs-lookup"><span data-stu-id="4e136-138">To confirm that preview features are available and turned on in LCS, follow these steps.</span></span>

1. <span data-ttu-id="4e136-139">Logga in på [LCS-portalen](https://lcs.dynamics.com) med hjälp av samma LCS-konto som du använde för att begära åtkomst till förhandsgranskningen.</span><span class="sxs-lookup"><span data-stu-id="4e136-139">Sign in to the [LCS portal](https://lcs.dynamics.com) by using the same LCS account that you used to request access to the preview.</span></span>
1. <span data-ttu-id="4e136-140">Rulla hela vägen till höger på LCS-startsida och klicka på panelen för **Hantering av förhandsgranskningsfunktioner**.</span><span class="sxs-lookup"><span data-stu-id="4e136-140">On the LCS home page, scroll all the way to the right, and select the **Preview feature management** tile.</span></span>

    ![Panel för förhandsgranskningsfunktion](./media/preview1.png)

1. <span data-ttu-id="4e136-142">Rulla ned till **Privata förhandsgranskningsfunktioner** och se till att följande funktioner är tillgängliga och aktiverade:</span><span class="sxs-lookup"><span data-stu-id="4e136-142">Scroll down to **Private preview features**, and confirm that the following features are available and turned on:</span></span>

    - <span data-ttu-id="4e136-143">Utvärdering av e-handel</span><span class="sxs-lookup"><span data-stu-id="4e136-143">e-Commerce Evaluation</span></span>
    - <span data-ttu-id="4e136-144">Miljöer för förhandsgranskningsprogram</span><span class="sxs-lookup"><span data-stu-id="4e136-144">Commerce Preview Program Environments</span></span>

    ![Privata förhandsgranskningsfunktioner](./media/preview2.png)

1. <span data-ttu-id="4e136-146">Om dessa funktioner inte visas i listan kan du kontakta Microsoft och ange din e-postadress för arbete, LCS-konto och klientinformation.</span><span class="sxs-lookup"><span data-stu-id="4e136-146">If those features don't appear in the list, contact Microsoft, and provide your work email address, LCS account, and tenant details.</span></span> <span data-ttu-id="4e136-147">Kontaktinformation finns i avsnittet [Förhandsversionsmiljö för Commerce](#commerce-preview-environment-support) senare.</span><span class="sxs-lookup"><span data-stu-id="4e136-147">For contact information, see the [Commerce preview environment support](#commerce-preview-environment-support) section.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="4e136-148">Skapa ett nytt projekt</span><span class="sxs-lookup"><span data-stu-id="4e136-148">Create a new project</span></span>

<span data-ttu-id="4e136-149">Om du vill skapa ett nytt projekt i LCS, följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="4e136-149">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="4e136-150">På LCS-startsidan väljer du plustecknet (**+**) för att skapa ett projekt.</span><span class="sxs-lookup"><span data-stu-id="4e136-150">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="4e136-151">I den högra rutan följer du något av följande steg:</span><span class="sxs-lookup"><span data-stu-id="4e136-151">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="4e136-152">Om du är partner väljer du **Migrera, skapa lösningar och lär dig**.</span><span class="sxs-lookup"><span data-stu-id="4e136-152">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="4e136-153">Om du är kund väljer du **Potentiella försäljningar**.</span><span class="sxs-lookup"><span data-stu-id="4e136-153">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="4e136-154">Ange ett namn, beskrivning och bransch.</span><span class="sxs-lookup"><span data-stu-id="4e136-154">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="4e136-155">I fältet **Produktnamn** välj **Dynamics 365 Retail**.</span><span class="sxs-lookup"><span data-stu-id="4e136-155">In the **Product name** field, select **Dynamics 365 Retail**.</span></span>
1. <span data-ttu-id="4e136-156">I fältet **Produktversion** välj **Dynamics 365 Retail**.</span><span class="sxs-lookup"><span data-stu-id="4e136-156">In the **Product version** field, select **Dynamics 365 Retail**.</span></span>
1. <span data-ttu-id="4e136-157">Fältet **Metod**, välj **Dynamics Retail implementeringsmetod**.</span><span class="sxs-lookup"><span data-stu-id="4e136-157">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="4e136-158">Valfritt: Du kan importera roller och användare från ett befintligt projekt.</span><span class="sxs-lookup"><span data-stu-id="4e136-158">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="4e136-159">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="4e136-159">Select **Create**.</span></span> <span data-ttu-id="4e136-160">Projektvyn visas.</span><span class="sxs-lookup"><span data-stu-id="4e136-160">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="4e136-161">Lägg till Azure-koppling</span><span class="sxs-lookup"><span data-stu-id="4e136-161">Add the Azure Connector</span></span>

<span data-ttu-id="4e136-162">Så här lägger du till Azure Connector i ditt LCS-projekt.</span><span class="sxs-lookup"><span data-stu-id="4e136-162">To add the Azure Connector to your LCS project, follow these steps.</span></span>

1. <span data-ttu-id="4e136-163">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="4e136-163">Follow one of these steps:</span></span>

    - <span data-ttu-id="4e136-164">Om du är en partner väljer du panelen **Projektinställningar** längst till höger.</span><span class="sxs-lookup"><span data-stu-id="4e136-164">If you're a partner, select the **Project settings** tile on the far right.</span></span>
    - <span data-ttu-id="4e136-165">Om du är kund väljer du **projektinställningar** på huvudmenyn.</span><span class="sxs-lookup"><span data-stu-id="4e136-165">If you're a customer, select **Project settings** on the top menu.</span></span>

1. <span data-ttu-id="4e136-166">Välj **Azure-kopplingar**.</span><span class="sxs-lookup"><span data-stu-id="4e136-166">Select **Azure connectors**.</span></span>
1. <span data-ttu-id="4e136-167">Klicka på **+ Lägg till** om du vill lägga till Azure-koppling.</span><span class="sxs-lookup"><span data-stu-id="4e136-167">Select **Add** to add the Azure Connector.</span></span>
1. <span data-ttu-id="4e136-168">Ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="4e136-168">Enter a name.</span></span>
1. <span data-ttu-id="4e136-169">Ange ditt Azure prenumerations-ID.</span><span class="sxs-lookup"><span data-stu-id="4e136-169">Enter your Azure subscription ID.</span></span>
1. <span data-ttu-id="4e136-170">Aktivera alternativet **Konfigurera för att använda Azure Resource Manager (ARM)**.</span><span class="sxs-lookup"><span data-stu-id="4e136-170">Turn on the **Configure to use Azure Resource Manager (ARM)** option.</span></span>
1. <span data-ttu-id="4e136-171">Kontrollera att värdet **Azure-abonnemangets AAD-innehavardomän (eller ID)** är korrekt.</span><span class="sxs-lookup"><span data-stu-id="4e136-171">Verify that the **Azure subscription AAD Tenant Domain (or ID)** value is correct.</span></span> <span data-ttu-id="4e136-172">Kontakta din Azure abonnemangsadministratör om det behövs.</span><span class="sxs-lookup"><span data-stu-id="4e136-172">Consult your Azure subscription admin as required.</span></span>
1. <span data-ttu-id="4e136-173">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4e136-173">Select **Next**.</span></span>
1. <span data-ttu-id="4e136-174">Följ instruktionerna på sidan och ge de program som krävs åtkomst till din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="4e136-174">Follow the instructions on the page to grant the required applications access to your subscription.</span></span> <span data-ttu-id="4e136-175">Kontakta din Azure abonnemangsadministratör om det behövs.</span><span class="sxs-lookup"><span data-stu-id="4e136-175">Consult your Azure subscription admin as required.</span></span>

    1. <span data-ttu-id="4e136-176">Logga in på [Azure-portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="4e136-176">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
    1. <span data-ttu-id="4e136-177">Kontrollera att rätt katalog är markerad och välj sedan **prenumerationer** på menyn till vänster.</span><span class="sxs-lookup"><span data-stu-id="4e136-177">Make sure that the correct directory is selected, and then, on the menu on the left, select **Subscriptions**.</span></span>
    1. <span data-ttu-id="4e136-178">Leta rätt på den korrekta prenumerationen i listan och markera den.</span><span class="sxs-lookup"><span data-stu-id="4e136-178">Find the correct subscription in the list, and select it.</span></span> <span data-ttu-id="4e136-179">Använd sökfunktionen efter behov.</span><span class="sxs-lookup"><span data-stu-id="4e136-179">Use the search functionality as required.</span></span>
    1. <span data-ttu-id="4e136-180">Välj **åtkomstkontroll (IAM)** på menyn.</span><span class="sxs-lookup"><span data-stu-id="4e136-180">On the menu, select **Access control (IAM)**.</span></span>
    1. <span data-ttu-id="4e136-181">Till höger under **Lägg till** välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="4e136-181">On the right, under **Add a role assignment**, select **Add**.</span></span> <span data-ttu-id="4e136-182">Fönstret **Lägg till rolltilldelning** visas.</span><span class="sxs-lookup"><span data-stu-id="4e136-182">The **Add role assignment** pane appears.</span></span>
    1. <span data-ttu-id="4e136-183">I fältet **Roll**, välj **Deltagare**.</span><span class="sxs-lookup"><span data-stu-id="4e136-183">In the **Role** field, select **Contributor**.</span></span>
    1. <span data-ttu-id="4e136-184">I fältet **Tilldela åtkomst till**, lämna standardvärdet **Azure AD användare, grupp eller Service Principals**.</span><span class="sxs-lookup"><span data-stu-id="4e136-184">In the **Assign access to** field, leave the default value, **Azure AD user, group, or service principal**.</span></span>
    1. <span data-ttu-id="4e136-185">Under **Välj**, anger du **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.</span><span class="sxs-lookup"><span data-stu-id="4e136-185">Under **Select**, enter **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.</span></span>
    1. <span data-ttu-id="4e136-186">Välj **Dynamics distributionstjänst \[wsfed-enabled\]** i listan.</span><span class="sxs-lookup"><span data-stu-id="4e136-186">Select **Dynamics Deployment Services \[wsfed-enabled\]** in the list.</span></span>
    1. <span data-ttu-id="4e136-187">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4e136-187">Select **Save**.</span></span>

1. <span data-ttu-id="4e136-188">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4e136-188">Select **Next**.</span></span>
1. <span data-ttu-id="4e136-189">Följ instruktionerna på sidan och ge de program som krävs åtkomst till din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="4e136-189">Follow the instructions on the page to grant the required applications access to your subscription.</span></span> <span data-ttu-id="4e136-190">Kontakta din Azure abonnemangsadministratör om det behövs.</span><span class="sxs-lookup"><span data-stu-id="4e136-190">Consult your Azure subscription admin as required.</span></span>
1. <span data-ttu-id="4e136-191">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4e136-191">Select **Next**.</span></span>
1. <span data-ttu-id="4e136-192">I fältet **Azure-region**, väljer du antingen **östra US**, **östra US 2**, **västra US** eller **västra US 2**.</span><span class="sxs-lookup"><span data-stu-id="4e136-192">In the **Azure region** field, select **East US**, **East US 2**, **West US**, or **West US 2**.</span></span>
1. <span data-ttu-id="4e136-193">Välj **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="4e136-193">Select **Connect**.</span></span> <span data-ttu-id="4e136-194">Din Azure-koppling ska visas i listan.</span><span class="sxs-lookup"><span data-stu-id="4e136-194">Your Azure Connector should appear in the list.</span></span>

### <a name="import-the-commerce-preview-demo-base-extension"></a><span data-ttu-id="4e136-195">Importera Commerce-förhandsgranskning demo bastillägg</span><span class="sxs-lookup"><span data-stu-id="4e136-195">Import the Commerce Preview Demo Base Extension</span></span>

<span data-ttu-id="4e136-196">Så här importerar du Commerce-förhandsgranskning demo bastillägg till ditt projekt.</span><span class="sxs-lookup"><span data-stu-id="4e136-196">To import the Commerce Preview Demo Base Extension into your project, follow these steps.</span></span>

1. <span data-ttu-id="4e136-197">Öppna projektets startsida genom att välja projektnamnet överst.</span><span class="sxs-lookup"><span data-stu-id="4e136-197">Open the home page for your project by selecting the project name at the top.</span></span>
1. <span data-ttu-id="4e136-198">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="4e136-198">Follow one of these steps:</span></span>

    - <span data-ttu-id="4e136-199">Om du är en partner väljer du panelen **Tillgångsbibliotek** längst till höger.</span><span class="sxs-lookup"><span data-stu-id="4e136-199">If you're a partner, select the **Asset library** tile on the far right.</span></span>
    - <span data-ttu-id="4e136-200">Om du är kund väljer du **Tillgångsbibliotek** på huvudmenyn.</span><span class="sxs-lookup"><span data-stu-id="4e136-200">If you're a customer, select **Asset library** on the top menu.</span></span>

1. <span data-ttu-id="4e136-201">I listan till vänster, välj **Distribuerbart programpaket**.</span><span class="sxs-lookup"><span data-stu-id="4e136-201">In the list on the left, select **Software deployable package**.</span></span>
1. <span data-ttu-id="4e136-202">Välj **Importera**.</span><span class="sxs-lookup"><span data-stu-id="4e136-202">Select **Import**.</span></span>
1. <span data-ttu-id="4e136-203">Under **Delat tillgångsbibliotek**, välj **Commerce-förhandsgranskning demo bastillägg** från listan med tillgångar.</span><span class="sxs-lookup"><span data-stu-id="4e136-203">Under **Shared asset library**, select **Commerce Preview Demo Base Extension** in the list of assets.</span></span>
1. <span data-ttu-id="4e136-204">Välj **Plocka**.</span><span class="sxs-lookup"><span data-stu-id="4e136-204">Select **Pick**.</span></span> <span data-ttu-id="4e136-205">Du kommer att returneras till tillgångsbiblioteket och du bör se filnamnstillägget i listan.</span><span class="sxs-lookup"><span data-stu-id="4e136-205">You're returned to the Asset library, and you should see the extension in the list.</span></span>

<span data-ttu-id="4e136-206">Följande illustration visar de åtgärder som måste vidtas på sidan LCS **tillgångsbibliotek**.</span><span class="sxs-lookup"><span data-stu-id="4e136-206">The following illustration shows the actions that must be taken on the LCS **Asset library** page.</span></span>

![Importera Commerce-förhandsgranskning demo bastillägg](./media/import.png)

### <a name="deploy-the-environment"></a><span data-ttu-id="4e136-208">Distribuera miljö</span><span class="sxs-lookup"><span data-stu-id="4e136-208">Deploy the environment</span></span>

<span data-ttu-id="4e136-209">Följ dessa steg för att distribuera miljön.</span><span class="sxs-lookup"><span data-stu-id="4e136-209">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="4e136-210">Du kanske inte behöver slutföra steg 6, 7 och/eller 8, eftersom sidor som har ett enda alternativ hoppas över.</span><span class="sxs-lookup"><span data-stu-id="4e136-210">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="4e136-211">När du är i vyn **Miljöparametrar** bekräfta att texten **Dynamics 365 Commerce - Demo (10.0.* x* med plattformsuppdatering *xx*)\*\* visas direkt ovan fältet **Miljönamn**.</span><span class="sxs-lookup"><span data-stu-id="4e136-211">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="4e136-212">För mer information, se illustrationen som visas efter steg 8.</span><span class="sxs-lookup"><span data-stu-id="4e136-212">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="4e136-213">På huvudmenyn väljer du miljön **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="4e136-213">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="4e136-214">Klicka på **Lägg till** om du vill lägga till en miljö.</span><span class="sxs-lookup"><span data-stu-id="4e136-214">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="4e136-215">I fältet **Programversion** väljer du den mest aktuella versionen.</span><span class="sxs-lookup"><span data-stu-id="4e136-215">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="4e136-216">Om du har ett specifikt behov av att välja en annan programversion än den senaste versionen ska du inte välja en version före **10.0.8**.</span><span class="sxs-lookup"><span data-stu-id="4e136-216">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.8**.</span></span>
1. <span data-ttu-id="4e136-217">I fältet **plattformsversion** använder du den plattformsversion som väljs automatiskt för den valda programversionen.</span><span class="sxs-lookup"><span data-stu-id="4e136-217">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Välj program- och plattformsversioner](./media/project1.png)

1. <span data-ttu-id="4e136-219">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4e136-219">Select **Next**.</span></span>
1. <span data-ttu-id="4e136-220">Välj **Demo** som miljötopologi.</span><span class="sxs-lookup"><span data-stu-id="4e136-220">Select **Demo** as the environment topology.</span></span>

    ![Välja miljötopologi 1](./media/project2.png)

1. <span data-ttu-id="4e136-222">Välj **Dynamics 365 Commerce - Demo** som miljötopologi.</span><span class="sxs-lookup"><span data-stu-id="4e136-222">Select **Dynamics 365 Commerce - Demo** as the environment topology.</span></span> <span data-ttu-id="4e136-223">Om du konfigurerade en enda Azure-koppling tidigare kommer den att användas i den här miljön.</span><span class="sxs-lookup"><span data-stu-id="4e136-223">If you configured a single Azure Connector earlier, it will be used for this environment.</span></span> <span data-ttu-id="4e136-224">Om du har konfigurerat flera Azure-kopplingar kan du välja vilken koppling som: **Östra USA**, **Östra USA 2**, **Västra USA** eller **Västra USA 2**.</span><span class="sxs-lookup"><span data-stu-id="4e136-224">If you configured multiple Azure Connectors, you can select which connector to use: **East US**, **East US 2**, **West US**, or **West US 2**.</span></span> <span data-ttu-id="4e136-225">(För bästa slutpunkt till slutpunkt-prestanda rekommenderar vi att du väljer **Västra USA 2**.)</span><span class="sxs-lookup"><span data-stu-id="4e136-225">(For the best end-to-end performance, we recommend that you select **West US 2**.)</span></span>

    ![Välja miljötopologi 2](./media/project3.png)

1. <span data-ttu-id="4e136-227">Ange ett **miljönamn** på sidan distribuera miljö.</span><span class="sxs-lookup"><span data-stu-id="4e136-227">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="4e136-228">Lämna Avancerade inställningar som de är.</span><span class="sxs-lookup"><span data-stu-id="4e136-228">Leave the advanced settings as they are.</span></span>

    ![Sidan Distribuera miljö](./media/project4.png)

1. <span data-ttu-id="4e136-230">Justera VM-storlek som krävs.</span><span class="sxs-lookup"><span data-stu-id="4e136-230">Adjust the VM size as required.</span></span> <span data-ttu-id="4e136-231">(Vi rekommenderar VM lagerhållningsenhet \[SKU\]**D13 v2**.)</span><span class="sxs-lookup"><span data-stu-id="4e136-231">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="4e136-232">Granska prissättnings- och licensvillkoren och markera sedan kryssrutan för att ange att du godkänner dem.</span><span class="sxs-lookup"><span data-stu-id="4e136-232">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="4e136-233">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4e136-233">Select **Next**.</span></span>
1. <span data-ttu-id="4e136-234">På sidan för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **distribuera**.</span><span class="sxs-lookup"><span data-stu-id="4e136-234">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="4e136-235">Du kommer tillbaka till vyn **Molnstyrda miljöer** och din miljö bör visas i listan.</span><span class="sxs-lookup"><span data-stu-id="4e136-235">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="4e136-236">Den begärda miljön visas som en kö och distribueras sedan.</span><span class="sxs-lookup"><span data-stu-id="4e136-236">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="4e136-237">Miljöarbetsflödena kommer att ta lite tid att slutföras.</span><span class="sxs-lookup"><span data-stu-id="4e136-237">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="4e136-238">Kontrollera därför tillbaka efter ungefär sex till nio timmar.</span><span class="sxs-lookup"><span data-stu-id="4e136-238">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="4e136-239">Innan du fortsätter bör du kontrollera att miljöstatus är **distribuerad**.</span><span class="sxs-lookup"><span data-stu-id="4e136-239">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-csu"></a><span data-ttu-id="4e136-240">Initiera skalningsenhet för handel (CSU)</span><span class="sxs-lookup"><span data-stu-id="4e136-240">Initialize the commerce scale unit (CSU)</span></span>

<span data-ttu-id="4e136-241">Gör så här om du vill initiera en CSU.</span><span class="sxs-lookup"><span data-stu-id="4e136-241">To initialize CSU, follow these steps.</span></span>

1. <span data-ttu-id="4e136-242">Välj din miljö i listan **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="4e136-242">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="4e136-243">Välj i miljövyn till höger **Fullständig information**.</span><span class="sxs-lookup"><span data-stu-id="4e136-243">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="4e136-244">Vyn miljöinformation visas.</span><span class="sxs-lookup"><span data-stu-id="4e136-244">The environment details view appears.</span></span>
1. <span data-ttu-id="4e136-245">Under **Miljöfunktioner**, välj **hantera**.</span><span class="sxs-lookup"><span data-stu-id="4e136-245">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="4e136-246">På fliken **Handel**, välj **Initiera**.</span><span class="sxs-lookup"><span data-stu-id="4e136-246">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="4e136-247">Parametervyn CSU-initiering visas.</span><span class="sxs-lookup"><span data-stu-id="4e136-247">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="4e136-248">I fältet **Region**, väljer du antingen **östra US**, **östra US 2**, **västra US** eller **västra US 2**.</span><span class="sxs-lookup"><span data-stu-id="4e136-248">In the **Region** field, select **East US**, **East US 2**, **West US**, or **West US 2**.</span></span>
1. <span data-ttu-id="4e136-249">I fältet **version** väljer du **ange en version** i listan och anger sedan **9.18.20014.4** i fältet som visas.</span><span class="sxs-lookup"><span data-stu-id="4e136-249">In the **Version** field, select **Specify a version** in the list, and then specify **9.18.20014.4** in the field that appears.</span></span> <span data-ttu-id="4e136-250">Var noga med att ange den exakta versionen som anges här.</span><span class="sxs-lookup"><span data-stu-id="4e136-250">Be sure to specify the exact version that is indicated here.</span></span> <span data-ttu-id="4e136-251">I annat fall måste du uppdatera RCSU till rätt version senare.</span><span class="sxs-lookup"><span data-stu-id="4e136-251">Otherwise, you will have to update RCSU to the correct version later.</span></span>
1. <span data-ttu-id="4e136-252">Aktivera alternativet **Använd tillägg**.</span><span class="sxs-lookup"><span data-stu-id="4e136-252">Turn on the **Apply extension** option.</span></span>
1. <span data-ttu-id="4e136-253">Från listan över tillägg, välj **Handelsförhandsgranskning demobastillägg**.</span><span class="sxs-lookup"><span data-stu-id="4e136-253">In the list of extensions, select **Commerce Preview Demo Base Extension**.</span></span>
1. <span data-ttu-id="4e136-254">Välj **initiera**.</span><span class="sxs-lookup"><span data-stu-id="4e136-254">Select **Initialize**.</span></span>
1. <span data-ttu-id="4e136-255">På sidan för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4e136-255">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="4e136-256">Vyn **Hantering av handel** visas igen, där fliken **Handel** väljs.</span><span class="sxs-lookup"><span data-stu-id="4e136-256">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="4e136-257">Din CSU har ställts i kö för etablering.</span><span class="sxs-lookup"><span data-stu-id="4e136-257">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="4e136-258">Innan du fortsätter bör du kontrollera att status för din CSU är **Lyckades**.</span><span class="sxs-lookup"><span data-stu-id="4e136-258">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="4e136-259">Initieringen tar ungefär två till fem timmar.</span><span class="sxs-lookup"><span data-stu-id="4e136-259">Initialization takes approximately two to five hours.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="4e136-260">Initiera e-handelsplattform</span><span class="sxs-lookup"><span data-stu-id="4e136-260">Initialize e-Commerce</span></span>

<span data-ttu-id="4e136-261">Gör så här om du vill initiera e-handel.</span><span class="sxs-lookup"><span data-stu-id="4e136-261">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="4e136-262">Granska medgivande för förhandsversion på fliken **e-handel** och välj sedan **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="4e136-262">On the **e-Commerce** tab, review the preview consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="4e136-263">I fältet **E-handelsinnehavarens namn**, ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="4e136-263">In the **e-Commerce tenant name** field, enter a name.</span></span> <span data-ttu-id="4e136-264">Tänk dock på att det här namnet kommer att visas i några av webbadresserna som pekar på din e-handelsinstans.</span><span class="sxs-lookup"><span data-stu-id="4e136-264">However, be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="4e136-265">I fältet **Namn på skalningsenhet för handel** välj din CSU i listan.</span><span class="sxs-lookup"><span data-stu-id="4e136-265">In the **Commerce scale unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="4e136-266">(Listan bör bara ha ett alternativ.)</span><span class="sxs-lookup"><span data-stu-id="4e136-266">(The list should have only one option.)</span></span>

    <span data-ttu-id="4e136-267">Fältet **e-handelsgeografi** ställs in automatiskt och värdet kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="4e136-267">The **e-Commerce geography** field is set automatically, and the value can't be changed.</span></span>

1. <span data-ttu-id="4e136-268">Klicka på **Nästa** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="4e136-268">Select **Next** to continue.</span></span>
1. <span data-ttu-id="4e136-269">I fältet **Värdnamn som stöds** ange en giltig domän, t.ex. `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="4e136-269">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1.  <span data-ttu-id="4e136-270">I fältet **AAD säkerhetsgrupp för systemadministration**, ange de första bokstäverna i namnet på säkerhetsgruppen du vill använda.</span><span class="sxs-lookup"><span data-stu-id="4e136-270">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use.</span></span> <span data-ttu-id="4e136-271">Välj ikonen förstoringsglas för att visa sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="4e136-271">Select the magnifying class icon to display the search results.</span></span> <span data-ttu-id="4e136-272">Välj korrekt säkerhetsgrupp i listan.</span><span class="sxs-lookup"><span data-stu-id="4e136-272">Select the correct security group from the list.</span></span>
2.  <span data-ttu-id="4e136-273">I fältet **AAD-säkerhetsgruppen för moderator för omdömen och recensioner**, ange de första bokstäverna i namnet på säkerhetsgruppen du vill använda.</span><span class="sxs-lookup"><span data-stu-id="4e136-273">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use.</span></span> <span data-ttu-id="4e136-274">Välj ikonen förstoringsglas för att visa sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="4e136-274">Select the magnifying class icon to display the search results.</span></span> <span data-ttu-id="4e136-275">Välj korrekt säkerhetsgrupp i listan.</span><span class="sxs-lookup"><span data-stu-id="4e136-275">Select the correct security group from the list.</span></span>
1. <span data-ttu-id="4e136-276">Lämna alternativet **tjänsten aktivera klassificering** aktiverat.</span><span class="sxs-lookup"><span data-stu-id="4e136-276">Leave the **Enable ratings and review service** option turned on.</span></span>
1. <span data-ttu-id="4e136-277">Välj **initiera**.</span><span class="sxs-lookup"><span data-stu-id="4e136-277">Select **Initialize**.</span></span> <span data-ttu-id="4e136-278">Vyn **Hantering av handel** visas igen, där fliken **e-handel** väljs.</span><span class="sxs-lookup"><span data-stu-id="4e136-278">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="4e136-279">Initieringen av e-handel har påbörjats.</span><span class="sxs-lookup"><span data-stu-id="4e136-279">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="4e136-280">Innan du fortsätter väntar du tills initieringsstatus för e-handel är **initialisering har slutförts**.</span><span class="sxs-lookup"><span data-stu-id="4e136-280">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="4e136-281">Under **länkar** längst ned till höger, anteckna webbadresserna för följande länkar:</span><span class="sxs-lookup"><span data-stu-id="4e136-281">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="4e136-282">**e-handelsplats** – länken till roten på din e-handelsplats.</span><span class="sxs-lookup"><span data-stu-id="4e136-282">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="4e136-283">**e-handelsplats hanteringsverktyg** – länken till webbplatshanteringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="4e136-283">**e-Commerce site management tool** – The link to the site management tool.</span></span>

## <a name="commerce-preview-environment-support"></a><span data-ttu-id="4e136-284">Support för förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="4e136-284">Commerce preview environment support</span></span>

<span data-ttu-id="4e136-285">Om du får problem när du slutför etableringsstegen kan du gå till [Microsoft Dynamics 365 Commerce förhandsversion Yammer-gruppen](https://aka.ms/Dynamics365CommercePreviewYammer) och be om hjälp.</span><span class="sxs-lookup"><span data-stu-id="4e136-285">If you experience issues while you're completing the provisioning steps, visit the [Microsoft Dynamics 365 Commerce Preview Yammer group](https://aka.ms/Dynamics365CommercePreviewYammer) for help.</span></span>

<span data-ttu-id="4e136-286">Om du får problem när du försöker komma åt Yammer-gruppen kan du kontakta Microsoft via e-post på <Dynamics365Commerce@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="4e136-286">If you experience issues when you try to access the Yammer group, you can contact Microsoft by email at <Dynamics365Commerce@microsoft.com>.</span></span> <span data-ttu-id="4e136-287">Den här e-postadressen övervakas inte aktivt.</span><span class="sxs-lookup"><span data-stu-id="4e136-287">This email address isn't actively monitored.</span></span> <span data-ttu-id="4e136-288">Förvänta dig därför en fördröjning i svaret.</span><span class="sxs-lookup"><span data-stu-id="4e136-288">Therefore, expect a delay in the response.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4e136-289">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4e136-289">Next steps</span></span>

<span data-ttu-id="4e136-290">För att fortsätta processen med att tillhandahålla och konfigurera din förhandsgranskningsmiljö för Commerce, se [Konfigurera en förhandsversionsmiljö för Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="4e136-290">To continue the process of provisioning and configuring your Commerce preview environment, see [Configure a Commerce preview environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4e136-291">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4e136-291">Additional resources</span></span>

[<span data-ttu-id="4e136-292">Dynamics 365 Commerce förhandsversionsmiljö – översikt</span><span class="sxs-lookup"><span data-stu-id="4e136-292">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="4e136-293">Konfigurera en förhandsversionsmiljö för Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="4e136-293">Configure a Dynamics 365 Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="4e136-294">Konfigurera valfria funktioner för en förhandsversionsmiljö för Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="4e136-294">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="4e136-295">Vanliga frågor om Dynamics 365 Commerce förhandsversionsmiljö</span><span class="sxs-lookup"><span data-stu-id="4e136-295">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="4e136-296">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="4e136-296">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="4e136-297">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="4e136-297">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="4e136-298">Microsoft Azure-portal</span><span class="sxs-lookup"><span data-stu-id="4e136-298">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="4e136-299">Dynamics 365 Commerce webbplatsen</span><span class="sxs-lookup"><span data-stu-id="4e136-299">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

