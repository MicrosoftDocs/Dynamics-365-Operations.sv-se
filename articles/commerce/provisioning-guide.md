---
title: Tillhandahåll en Dynamics 365 Commerce utvärderingsmiljö
description: Det här avsnittet förklarar hur du etablerar en bedömningsmiljö för Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a57cc02c6d62f288f14b65191c2f4927a019963c
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478174"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="3ab5c-103">Tillhandahåll en Dynamics 365 Commerce utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="3ab5c-103">Provision a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3ab5c-104">Det här avsnittet förklarar hur du etablerar en bedömningsmiljö för Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="3ab5c-105">Innan du börjar rekommenderar vi att du tar en snabbgenomgång genom det här avsnittet för att få en uppfattning om vad processen kräver.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="3ab5c-106">Commerce bedömningsmiljöer är i allmänhet inte tillgängliga och ges till partners och kunder för varje enskild begäran.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-106">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="3ab5c-107">För mer information, kontakta din Microsoft-partnerkontakt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-107">For more information, reach out to your Microsoft partner contact.</span></span>

<span data-ttu-id="3ab5c-108">För att kunna etablera din bedömningsmiljö för Commerce måste du skapa ett projekt som har ett specifikt produktnamn och en viss typ.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-108">To successfully provision a Commerce evaluation environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="3ab5c-109">Miljön och Commerce Scale Unit (CSU) har även del specifika parametrar som du måste använda för att kunna förvänta dig att etablera näthandel senare.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-109">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you expect to provision e-Commerce later.</span></span> <span data-ttu-id="3ab5c-110">Instruktionerna i det här avsnittet beskriver alla nödvändiga steg för att slutföra etablering och de parametrar som du måste använda.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-110">The instructions in this topic describe all the steps that are required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="3ab5c-111">När du har tillhandahållit din bedömningsmiljö för Commerce måste du slutföra några steg efter etablering för att förbereda den.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-111">After you successfully provision your Commerce evaluation environment, you must complete a few post-provisioning steps to prepare it for use.</span></span> <span data-ttu-id="3ab5c-112">Vissa steg är valfria, beroende på vilka delar av systemet du vill utvärdera.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-112">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="3ab5c-113">Du kan alltid slutföra de valfria stegen senare.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-113">You can always complete the optional steps later.</span></span>

<span data-ttu-id="3ab5c-114">Information om hur du konfigurerar bedömningsmiljö för Commerce efter att du har konfigurerat den finns i [Konfigurera en bedömningsmiljö för Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="3ab5c-114">For information about how to configure your Commerce evaluation environment after you provision it, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="3ab5c-115">Information om hur du konfigurerar valfria funktioner för din Commerce bedömningsmiljö finns i [Konfigurera valfria funktioner för bedömningsmiljö för Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="3ab5c-115">For information about how to configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ab5c-116">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="3ab5c-116">Prerequisites</span></span>

<span data-ttu-id="3ab5c-117">Följande förutsättningar måste vara på plats innan du kan etablera din bedömningsmiljö för Commerce:</span><span class="sxs-lookup"><span data-stu-id="3ab5c-117">The following prerequisites must be in place before you can provision your Commerce evaluation environment:</span></span>

- <span data-ttu-id="3ab5c-118">Du har tagit med i bedömningsprogrammet och beviljats kapacitet för en bedömningsmiljö.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-118">You have been onboarded into the evaluation program and granted capacity for an evaluation environment.</span></span>
- <span data-ttu-id="3ab5c-119">Du har åtkomst till Microsoft Dynamics Lifecycle Services-portal (LCS).</span><span class="sxs-lookup"><span data-stu-id="3ab5c-119">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="3ab5c-120">Du är en befintlig Microsoft Dynamics 365-partner eller kund och kan skapa ett Dynamics 365 Commerce-projekt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-120">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="3ab5c-121">Du har administratörsåtkomst till din Microsoft Azure prenumeration, eller så har du kontakt med en prenumerationsadministratör som kan hjälpa dig om det behövs.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-121">You have administrator access to your Microsoft Azure subscription, or you're in contact with a subscription administrator who can assist you if required.</span></span>
- <span data-ttu-id="3ab5c-122">Du har ditt Azure Active Directory (Azure AD) innehavar-ID tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-122">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="3ab5c-123">Du har skapat en Azure AD-säkerhetsgrupp som kan användas som en systemadministratörsgrupp för näthandel och du har dess ID tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-123">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="3ab5c-124">Du har skapat en Azure AD-säkerhetsgrupp som kan användas som gruppen moderator för omdömen och recensioner och du har dess ID tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-124">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="3ab5c-125">(Den här säkerhetsgruppen kan vara samma som administratörsgruppen för näthandelssystem.)</span><span class="sxs-lookup"><span data-stu-id="3ab5c-125">(This security group can be the same as the e-Commerce system admin group.)</span></span>

<span data-ttu-id="3ab5c-126">Observera att listan inte är uttömmande.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-126">Note that this list isn't exhaustive.</span></span> <span data-ttu-id="3ab5c-127">Om du har problem kontakta din Microsoft-partnerkontakt för hjälp.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-127">If you experience any issues, reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="provision-your-commerce-evaluation-environment"></a><span data-ttu-id="3ab5c-128">Etablera en bedömningsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="3ab5c-128">Provision your Commerce evaluation environment</span></span>

<span data-ttu-id="3ab5c-129">Dessa procedurer förklarar hur du etablerar en bedömningsmiljö för Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-129">These procedures explain how to provision a Commerce evaluation environment.</span></span> <span data-ttu-id="3ab5c-130">När du har slutfört dem kommer bedömningsmiljö för Commerce att vara redo för konfigurering.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-130">After you successfully complete them, the Commerce evaluation environment will be ready for configuration.</span></span> <span data-ttu-id="3ab5c-131">Alla aktiviteter som beskrivs här utförs i LCS-portalen.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-131">All the activities that are described here occur in the LCS portal.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="3ab5c-132">Skapa ett nytt projekt</span><span class="sxs-lookup"><span data-stu-id="3ab5c-132">Create a new project</span></span>

<span data-ttu-id="3ab5c-133">Om du vill skapa ett nytt projekt i LCS, följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="3ab5c-133">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="3ab5c-134">På LCS-startsidan väljer du plustecknet (**+**) för att skapa ett projekt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-134">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="3ab5c-135">I den högra rutan följer du något av följande steg:</span><span class="sxs-lookup"><span data-stu-id="3ab5c-135">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="3ab5c-136">Om du är partner väljer du **Migrera, skapa lösningar och lär dig**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-136">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="3ab5c-137">Om du är kund väljer du **Potentiella försäljningar**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-137">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="3ab5c-138">Ange ett namn, beskrivning och bransch.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-138">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="3ab5c-139">I fältet **Produktnamn** välj **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-139">In the **Product name** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="3ab5c-140">I fältet **Produktversion** välj **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-140">In the **Product version** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="3ab5c-141">Fältet **Metod**, välj **Dynamics Retail implementeringsmetod**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-141">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="3ab5c-142">Valfritt: Du kan importera roller och användare från ett befintligt projekt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-142">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="3ab5c-143">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-143">Select **Create**.</span></span> <span data-ttu-id="3ab5c-144">Projektvyn visas.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-144">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="3ab5c-145">Lägg till Azure-koppling</span><span class="sxs-lookup"><span data-stu-id="3ab5c-145">Add the Azure Connector</span></span>

<span data-ttu-id="3ab5c-146">Om du vill lägga till Azure-anslutaren i LCS-projektet följer du stegen i [slutföra registreringsprocessen för Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span><span class="sxs-lookup"><span data-stu-id="3ab5c-146">To add the Azure Connector to your LCS project, follow the steps in [Complete the Azure Resource Manager (ARM) onboarding process](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span></span>

### <a name="deploy-the-environment"></a><span data-ttu-id="3ab5c-147">Distribuera miljö</span><span class="sxs-lookup"><span data-stu-id="3ab5c-147">Deploy the environment</span></span>

<span data-ttu-id="3ab5c-148">Följ dessa steg för att distribuera miljön.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-148">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="3ab5c-149">Du kanske inte behöver slutföra steg 6, 7 och/eller 8, eftersom sidor som har ett enda alternativ hoppas över.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-149">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="3ab5c-150">När du är i vyn **Miljöparametrar** bekräfta att texten **Dynamics 365 Commerce – Demo (10.0.* x* med plattformsuppdatering *xx*)\*\* visas direkt ovan fältet **Miljönamn**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-150">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="3ab5c-151">För mer information, se illustrationen som visas efter steg 8.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-151">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="3ab5c-152">På huvudmenyn väljer du miljön **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-152">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="3ab5c-153">Klicka på **Lägg till** om du vill lägga till en miljö.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-153">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="3ab5c-154">I fältet **Programversion** väljer du den mest aktuella versionen.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-154">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="3ab5c-155">Om du har ett specifikt behov av att välja en annan programversion än den senaste versionen ska du inte välja en version före **10.0.14**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-155">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.14**.</span></span>
1. <span data-ttu-id="3ab5c-156">I fältet **plattformsversion** använder du den plattformsversion som väljs automatiskt för den valda programversionen.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-156">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Välj program- och plattformsversioner](./media/project1.png)

1. <span data-ttu-id="3ab5c-158">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-158">Select **Next**.</span></span>
1. <span data-ttu-id="3ab5c-159">Välj **Demo** som miljötopologi.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-159">Select **Demo** as the environment topology.</span></span>

    ![Välja miljötopologi 1](./media/project2.png)

1. <span data-ttu-id="3ab5c-161">Ange ett **miljönamn** på sidan distribuera miljö.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-161">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="3ab5c-162">Lämna Avancerade inställningar som de är.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-162">Leave the advanced settings as they are.</span></span>

    ![Sidan Distribuera miljö](./media/project4.png)

1. <span data-ttu-id="3ab5c-164">Justera VM-storlek som krävs.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-164">Adjust the VM size as required.</span></span> <span data-ttu-id="3ab5c-165">(Vi rekommenderar VM lagerhållningsenhet \[SKU\]**D13 v2**.)</span><span class="sxs-lookup"><span data-stu-id="3ab5c-165">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="3ab5c-166">Granska prissättnings- och licensvillkoren och markera sedan kryssrutan för att ange att du godkänner dem.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-166">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="3ab5c-167">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-167">Select **Next**.</span></span>
1. <span data-ttu-id="3ab5c-168">På sidan för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **distribuera**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-168">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="3ab5c-169">Du kommer tillbaka till vyn **Molnstyrda miljöer** och din miljö bör visas i listan.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-169">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="3ab5c-170">Den begärda miljön visas som en kö och distribueras sedan.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-170">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="3ab5c-171">Miljöarbetsflödena kommer att ta lite tid att slutföras.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-171">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="3ab5c-172">Kontrollera därför tillbaka efter ungefär sex till nio timmar.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-172">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="3ab5c-173">Innan du fortsätter bör du kontrollera att miljöstatus är **distribuerad**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-173">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="3ab5c-174">Initiera Commerce Scale Unit (moln)</span><span class="sxs-lookup"><span data-stu-id="3ab5c-174">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="3ab5c-175">Gör så här om du vill initiera CSU:n.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-175">To initialize the CSU, follow these steps.</span></span>

1. <span data-ttu-id="3ab5c-176">Välj din miljö i listan **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-176">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="3ab5c-177">Välj i miljövyn till höger **Fullständig information**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-177">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="3ab5c-178">Vyn miljöinformation visas.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-178">The environment details view appears.</span></span>
1. <span data-ttu-id="3ab5c-179">Under **Miljöfunktioner**, välj **hantera**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-179">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="3ab5c-180">På fliken **Commerce**, välj **Initiera**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-180">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="3ab5c-181">Parametervyn CSU-initiering visas.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-181">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="3ab5c-182">I fältet **Region** väljer du den region som är densamma eller nära den region som du har distribuerat miljön till.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-182">In the **Region** field, select the region that is the same or close to the region that you deployed the environment to.</span></span>
1. <span data-ttu-id="3ab5c-183">Lämna fältet **Version** tomt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-183">Leave the **Version** field as it is.</span></span>
1. <span data-ttu-id="3ab5c-184">Välj **initiera**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-184">Select **Initialize**.</span></span>
1. <span data-ttu-id="3ab5c-185">På sidan för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-185">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="3ab5c-186">Vyn **Hantering av handel** visas igen, där fliken **Commerce** väljs.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-186">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="3ab5c-187">Din CSU har ställts i kö för etablering.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-187">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="3ab5c-188">Innan du fortsätter bör du kontrollera att status för din CSU är **Lyckades**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-188">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="3ab5c-189">Initieringen tar ungefär två till fem timmar.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-189">Initialization takes approximately two to five hours.</span></span>

<span data-ttu-id="3ab5c-190">Om du inte hittar länken **hantera** i vyn miljödetaljer kontaktar du din Microsoft-kontakt för att få hjälp.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-190">If you can't find the **Manage** link in the environment details view, reach out to your Microsoft contact for assistance.</span></span>

<span data-ttu-id="3ab5c-191">Följande felmeddelande kan visas under distributionsprocessen:</span><span class="sxs-lookup"><span data-stu-id="3ab5c-191">During the deployment process, you might receive the following error message:</span></span>

> <span data-ttu-id="3ab5c-192">Bedömnings(demo-/test)miljöer måste registrera anslutningsprogrammet för skalningsenhet \<application ID\> i administrationen.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-192">Evaluation (demo/test) environments need to register the scale unit connector application \<application ID\> in headquarters.</span></span>

<span data-ttu-id="3ab5c-193">Om CSU-initialiseringen misslyckas och du får det här felmeddelandet, noterar du program-ID:t (som är en global unik identifierare, GUID) och följer sedan stegen i nästa avsnitt om du vill registrera CSU-distribueringsprogrammet i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-193">If the CSU initialization fails and you receive this error message, make a note of the application ID, which is a globally unique identifier (GUID), and then follow the steps in the next section to register the CSU deployment application in Commerce headquarters.</span></span>

### <a name="register-the-csu-deployment-application-in-commerce-headquarters-if-required"></a><span data-ttu-id="3ab5c-194">Registrera CSU-distribueringsprogrammet i Commerce-administrationen (vid behov)</span><span class="sxs-lookup"><span data-stu-id="3ab5c-194">Register the CSU deployment application in Commerce headquarters (if required)</span></span>

<span data-ttu-id="3ab5c-195">Följ dessa steg om du vill registrera CSU-distribueringsprogrammet i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-195">To register the CSU deployment application in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="3ab5c-196">I Commerce-administrationen går du till **Systemadministration \> Inställningar \> Azure Active Directory-program**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-196">In Commerce headquarters, go to **System administration \> Setup \> Azure Active Directory applications**.</span></span>
1. <span data-ttu-id="3ab5c-197">I kolumnen **Klient-ID** anger du program-ID:t från det CSU-initieringsfelmeddelande som du har fått.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-197">In the **Client Id** column, enter the application ID from the CSU initialization error message that you received.</span></span>
1. <span data-ttu-id="3ab5c-198">Ange eventuell beskrivande text i kolumnen **Namn** (t. ex. **CSU Eval**).</span><span class="sxs-lookup"><span data-stu-id="3ab5c-198">In the **Name** column, enter any descriptive text (for example, **CSU Eval**).</span></span>
1. <span data-ttu-id="3ab5c-199">I kolumnen **Användar-ID** anger du **RetailServiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-199">In the **User ID** column, enter **RetailServiceAccount**.</span></span>
1. <span data-ttu-id="3ab5c-200">Försök att initiera CSU igen och distribuera från LCS.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-200">Retry the CSU initialization and deployment from LCS.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="3ab5c-201">Initiera näthandelsplattform</span><span class="sxs-lookup"><span data-stu-id="3ab5c-201">Initialize e-Commerce</span></span>

<span data-ttu-id="3ab5c-202">Gör så här om du vill initiera näthandel.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-202">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="3ab5c-203">Granska medgivande för utvärdering på fliken **näthandel** och välj sedan **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-203">On the **e-Commerce** tab, review the evaluation consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="3ab5c-204">I fältet **miljönamn för näthandel**, ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-204">In the **e-Commerce environment name** field, enter a name.</span></span> <span data-ttu-id="3ab5c-205">Tänk på att det här namnet kommer att visas i några av webbadresserna som pekar mot din näthandelsinstans.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-205">Be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="3ab5c-206">I fältet **Namn på Commerce Scale Unit** välj din CSU i listan.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-206">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="3ab5c-207">(Listan bör bara ha ett alternativ.)</span><span class="sxs-lookup"><span data-stu-id="3ab5c-207">(The list should have only one option.)</span></span>

    <span data-ttu-id="3ab5c-208">Fältet **geografi för näthandel** ställs in automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-208">The **e-Commerce geography** field is set automatically.</span></span>

1. <span data-ttu-id="3ab5c-209">Klicka på **Nästa** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-209">Select **Next** to continue.</span></span>
1. <span data-ttu-id="3ab5c-210">I fältet **Värdnamn som stöds** ange en giltig domän, t.ex. `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-210">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1. <span data-ttu-id="3ab5c-211">I fältet **AAD-säkerhetsgruppen för systemadministratör**, ange de första bokstäverna i namnet på den säkerhetsgrupp som du vill använda och välj sedan förstoringsglassymbol för att se sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-211">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="3ab5c-212">Välj korrekt säkerhetsgrupp i listan.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-212">Select the correct security group in the list.</span></span>
1.  <span data-ttu-id="3ab5c-213">I fältet **AAD-säkerhetsgruppen för moderator för omdömen och recensioner**, ange de första bokstäverna i namnet på den säkerhetsgrupp som du vill använda och välj sedan förstoringsglassymbol för att se sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-213">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="3ab5c-214">Välj korrekt säkerhetsgrupp i listan.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-214">Select the correct security group in the list.</span></span>
1. <span data-ttu-id="3ab5c-215">Lämna alternativet **tjänsten aktivera klassificering och granska** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-215">Leave the **Enable ratings and review service** option set to **Yes**.</span></span>
1. <span data-ttu-id="3ab5c-216">Välj **initiera**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-216">Select **Initialize**.</span></span> <span data-ttu-id="3ab5c-217">Vyn **Hantering av handel** visas igen, där fliken **näthandel** väljs.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-217">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="3ab5c-218">Initieringen av näthandel har påbörjats.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-218">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="3ab5c-219">Innan du fortsätter väntar du tills initieringsstatus för näthandel är **initialisering har slutförts**.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-219">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="3ab5c-220">Under **länkar** längst ned till höger, anteckna webbadresserna för följande länkar:</span><span class="sxs-lookup"><span data-stu-id="3ab5c-220">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="3ab5c-221">**näthandelssajt** – länken till roten på din näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-221">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="3ab5c-222">**Commerce webbplatsskaparen** – länken till webbplatshanteringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-222">**Commerce site builder** – The link to the site management tool.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ab5c-223">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="3ab5c-223">Next steps</span></span>

<span data-ttu-id="3ab5c-224">För att fortsätta processen med att tillhandahålla och konfigurera din bedömningsmiljö för Commerce, se [Konfigurera en bedömningsmiljö för Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="3ab5c-224">To continue the process of provisioning and configuring your Commerce evaluation environment, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3ab5c-225">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3ab5c-225">Additional resources</span></span>

[<span data-ttu-id="3ab5c-226">Dynamics 365 Commerce bedömningsmiljö – översikt</span><span class="sxs-lookup"><span data-stu-id="3ab5c-226">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="3ab5c-227">Konfigurera en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="3ab5c-227">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="3ab5c-228">Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="3ab5c-228">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="3ab5c-229">Konfigurera valfria funktioner för en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="3ab5c-229">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="3ab5c-230">Dynamics 365 Commerce bedömningsmiljö – vanliga frågor</span><span class="sxs-lookup"><span data-stu-id="3ab5c-230">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="3ab5c-231">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="3ab5c-231">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="3ab5c-232">Commerce Scale Unit (moln)</span><span class="sxs-lookup"><span data-stu-id="3ab5c-232">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="3ab5c-233">Microsoft Azure-portal</span><span class="sxs-lookup"><span data-stu-id="3ab5c-233">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="3ab5c-234">Dynamics 365 Commerce webbplatsen</span><span class="sxs-lookup"><span data-stu-id="3ab5c-234">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
