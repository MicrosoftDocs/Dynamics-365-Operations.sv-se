---
title: Aktivera och konfigurera automatiska avgifter efter kanal
description: I det här avsnittet beskrivs hur du aktiverar och konfigurerar automatiska debiteringar utifrån kanal i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: d37b2b785dd29850dcd02d0905e5872445384990
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993738"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a><span data-ttu-id="f5d73-103">Aktivera och konfigurera automatiska avgifter efter kanal</span><span class="sxs-lookup"><span data-stu-id="f5d73-103">Enable and configure auto charges by channel</span></span>

<span data-ttu-id="f5d73-104">I det här avsnittet beskrivs hur du aktiverar och konfigurerar automatiska avgifter utifrån kanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f5d73-104">This topic explains how to enable and configure automatic charges (auto charges) by channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f5d73-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="f5d73-105">Overview</span></span>

<span data-ttu-id="f5d73-106">Du kanske har scenarier där återvinningsavgifter eller andra avgifter måste användas för en grupp produkter som säljs i alla eller vissa butiker i en viss delstat (t.ex. Kalifornien).</span><span class="sxs-lookup"><span data-stu-id="f5d73-106">You might have scenarios where recycling fees or other fees must be applied to a group of products that are sold in all or some stores in a specific state (for example, California).</span></span> <span data-ttu-id="f5d73-107">Med funktionen **Aktivera filter för automatiska avgifter per kanal** i Commerce kan du ange automatiska debiteringar utifrån kanal (t.ex. en viss fysisk butikskanal).</span><span class="sxs-lookup"><span data-stu-id="f5d73-107">The **Enable filter auto charges by channel** feature in Commerce lets you specify auto charges by channel (for example, a specific brick-and-mortar channel).</span></span> <span data-ttu-id="f5d73-108">Den här funktionen finns i Dynamics 365 Commerce version 10.0.10 och senare.</span><span class="sxs-lookup"><span data-stu-id="f5d73-108">This feature is available in Dynamics 365 Commerce version 10.0.10 and later.</span></span>

<span data-ttu-id="f5d73-109">Om du vill aktivera och konfigurera automatiska tillägg per kanal, måste du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="f5d73-109">To enable and configure auto charges by channel, you must complete the following tasks:</span></span>

- <span data-ttu-id="f5d73-110">Aktivera funktionen **aktivera filter för automatiska avgifter per kanal**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-110">Turn on the **Enable filter auto charges by channel** feature.</span></span>
- <span data-ttu-id="f5d73-111">Konfigurera syftet med organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="f5d73-111">Configure the organization hierarchy purpose.</span></span>
- <span data-ttu-id="f5d73-112">Definiera automatiska tillägg per kanal.</span><span class="sxs-lookup"><span data-stu-id="f5d73-112">Define auto charges by channel.</span></span>

> [!NOTE]
> <span data-ttu-id="f5d73-113">Funktionen **aktivera filter för automatiska avgifter per kanal** fungerar bara om funktionen avancerade automatiska tillägg också är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="f5d73-113">The **Enable filter auto charges by channel** feature works only if the advanced auto charges feature is also turned on.</span></span> <span data-ttu-id="f5d73-114">Information om hur du aktiverar funktionen avancerade automatiska tillägg finns i [Avancerade automatiska avgifter för flera kanaler](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="f5d73-114">For information about how to turn on the advanced auto charges feature, see [Omni-channel advanced auto charges](omni-auto-charges.md).</span></span>

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a><span data-ttu-id="f5d73-115">Aktivera funktionen aktivera filter för automatiska avgifter per kanal</span><span class="sxs-lookup"><span data-stu-id="f5d73-115">Turn on the Enable filter auto charges by channel feature</span></span>

<span data-ttu-id="f5d73-116">Om du vill aktivera automatiska debiteringar utifrån kanal i Commerce följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="f5d73-116">To enable auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f5d73-117">Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-117">Go to **System administrator \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="f5d73-118">På fliken **Inte aktiverad** i listan **Funktionsnamn** hitta och välj **aktivera filter för automatiska avgifter per kanal**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-118">On the **Not enabled** tab, in the **Feature name** list, find and select **Enable filter auto charges by channel**.</span></span>
1. <span data-ttu-id="f5d73-119">Klicka på **Aktivera nu** i det nedre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="f5d73-119">In the lower-right corner, select **Enable now**.</span></span> <span data-ttu-id="f5d73-120">När funktionen har aktiverats visas den i listan på fliken **alla**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-120">After the feature has been turned on, it will appear in the list on the **All** tab.</span></span>
1. <span data-ttu-id="f5d73-121">Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-121">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="f5d73-122">Hitta och välj i den vänstra rutan jobbet **1110** (**Global konfiguration**).</span><span class="sxs-lookup"><span data-stu-id="f5d73-122">In the left pane, find and select the **1110** (**Global configuration**) job.</span></span>
1. <span data-ttu-id="f5d73-123">I åtgärdsfönstret väljer du **kör nu** om du vill sprida konfigurationsändringarna.</span><span class="sxs-lookup"><span data-stu-id="f5d73-123">On the Action Pane, select **Run now** to propagate the configuration changes.</span></span>

> [!WARNING]
> <span data-ttu-id="f5d73-124">Om du inaktiverar funktionen **aktivera filter för automatiska avgifter per kanal** när du redan har använt den visas inte längre fältet **Butikskanalrelation** under **Automatiska avgifter** och du kommer då att förlora alla befintliga konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="f5d73-124">If you turn off the **Enable filter auto charges by channel** feature after you've already used it, the **Retail channel relation** field under **Auto charges** will no longer appear, and you will lose all existing configurations.</span></span> <span data-ttu-id="f5d73-125">Om du tar bort konfigurationerna för **Butikskanalrelation** kommer regler för automatiska avgifter att dubbleras och ett försök att inaktivera funktionen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="f5d73-125">If removal of the **Retail channel relation** configurations will cause auto charges rules to be duplicated, an attempt to turn off the feature will fail.</span></span> <span data-ttu-id="f5d73-126">Innan du inaktiverar funktionen måste du granska alla automatiska tilläggsregler och göra nödvändiga ändringar.</span><span class="sxs-lookup"><span data-stu-id="f5d73-126">Before you turn off the feature, be sure to review all auto charges rules and make any required changes.</span></span>

## <a name="configure-the-organization-hierarchy-purpose"></a><span data-ttu-id="f5d73-127">Konfigurera syftet med organisationshierarkin</span><span class="sxs-lookup"><span data-stu-id="f5d73-127">Configure the organization hierarchy purpose</span></span>

<span data-ttu-id="f5d73-128">Ett nytt syfte för organisationshierarki med namnet **automatisk avgift för butik** har skapats för att hantera hierarkin för automatiska avgifter efter kanal.</span><span class="sxs-lookup"><span data-stu-id="f5d73-128">A new organization hierarchy purpose that is named **Retail auto charge** has been created to manage the hierarchy for auto charges by channel.</span></span>

<span data-ttu-id="f5d73-129">Om du vill tilldela en standardhierarki till ett syfte för organisationshierarki i Commerce följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="f5d73-129">To assign a default hierarchy to an organization hierarchy purpose in Commerce, follow these steps.</span></span>
        
1. <span data-ttu-id="f5d73-130">Gå till **Organisationsadministration \> Organisationer \> Syften med organisationshierarkier**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-130">Go to **Organization administration \> Organizations \> Organization hierarchy purposes**.</span></span>
1. <span data-ttu-id="f5d73-131">I vänstra fönstret, välj **automatisk avgift för butik**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-131">In the left pane, select **Retail auto charge**.</span></span>
1. <span data-ttu-id="f5d73-132">Under **tilldelade hierarkier**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-132">Under **Assigned hierarchies**, select **Add**.</span></span>
1. <span data-ttu-id="f5d73-133">I dialogrutan **organisationshierarkier** välj en organisationshierarki (till exempel **butiker efter region**) och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-133">In the **Organization hierarchies** dialog box, select an organization hierarchy (for example, **Retail Stores by Region**), and then select **OK**.</span></span>
1. <span data-ttu-id="f5d73-134">Under **tilldelade hierarkier**, välj **Ange som standard**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-134">Under **Assigned hierarchies**, select **Set as default**.</span></span>
1. <span data-ttu-id="f5d73-135">Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="f5d73-136">Hitta och välj i den vänstra rutan jobbet **1040** (**produkter**).</span><span class="sxs-lookup"><span data-stu-id="f5d73-136">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="f5d73-137">I åtgärdsfönstret, klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-137">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="f5d73-138">Upprepa de föregående två stegen för att köra jobben **1070** (**Kanalkonfiguration**) och **1110** (**Global konfiguration**).</span><span class="sxs-lookup"><span data-stu-id="f5d73-138">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>

![Konfiguration av syfte med organisationshierarkier för automatisk avgift för butik](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a><span data-ttu-id="f5d73-140">Definiera automatiska tillägg per kanal</span><span class="sxs-lookup"><span data-stu-id="f5d73-140">Define auto charges by channel</span></span>

<span data-ttu-id="f5d73-141">När du har aktiverat funktionen **Aktivera filter för automatiska tillägg efter kanal** och konfigurerat syftet för organisationshierarkin **automatisk avgift för butik** kan du definiera automatiska avgifter per kanal på orderhuvudnivån eller orderradnivån.</span><span class="sxs-lookup"><span data-stu-id="f5d73-141">After you've turned on the **Enable filter auto charges by channel** feature and configured the **Retail auto charge** organization hierarchy purpose, auto charges by channel can be defined at either the order header level or the order line level.</span></span>

<span data-ttu-id="f5d73-142">Om du vill definiera automatiska debiteringar utifrån kanal i Commerce följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="f5d73-142">To define auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f5d73-143">Gå till **Kundreskontra \> Ställa in avgifter \> Automatiska avgifter**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-143">Go to **Accounts receivable \> Charges setup \> Auto charges**.</span></span>
1. <span data-ttu-id="f5d73-144">I vänstra fönstret i fältet **Nivå** välj antingen **Huvud** eller **Rad**, hitta och välj i den vänstra rutan.</span><span class="sxs-lookup"><span data-stu-id="f5d73-144">In the left pane, in the **Level** field, select either **Header** or **Line**, depending on your business requirements.</span></span>
1. <span data-ttu-id="f5d73-145">I fältet **Butik kanalkod** välj lämplig kanalkod (t.ex. **Tabell** eller **Grupp**).</span><span class="sxs-lookup"><span data-stu-id="f5d73-145">In the **Retail channel code** field, select the appropriate channel code (for example, **Table** or **Group**).</span></span> <span data-ttu-id="f5d73-146">Om standardinställningen **alla**, används tilläggsregler för alla kanaler.</span><span class="sxs-lookup"><span data-stu-id="f5d73-146">If the default setting, **All**, is used, charge rules are applied to all channels.</span></span>

    - <span data-ttu-id="f5d73-147">Om du väljer **Grupp**, ska du se till att en avgiftsgrupp för butikskanaler **Retail och Commerce \> Kanalinställningen \> Avgifter \> Avgiftsgrupper för butikskanal**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-147">If you select **Group**, make sure that a retail channel charges group is created at **Retail and Commerce \> Channel setup \> Charges \> Retail channel charge groups**.</span></span>
    - <span data-ttu-id="f5d73-148">Om du väljer **Register** kan du välja en specifik kanal (t.ex. **San Francisco**) i fältet **Butikskanalrelation**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-148">If you select **Table**, you can select a specific channel (for example, **San Francisco**) in the **Retail channel relation** field.</span></span>

1. <span data-ttu-id="f5d73-149">Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-149">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="f5d73-150">Hitta och välj i den vänstra rutan jobbet **1040** (**produkter**).</span><span class="sxs-lookup"><span data-stu-id="f5d73-150">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="f5d73-151">I åtgärdsfönstret, klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-151">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="f5d73-152">Upprepa de föregående två stegen för att köra jobben **1070** (**Kanalkonfiguration**) och **1110** (**Global konfiguration**).</span><span class="sxs-lookup"><span data-stu-id="f5d73-152">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>
    
![Automatiska tillägg definieras per kanal](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a><span data-ttu-id="f5d73-154">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="f5d73-154">Example scenario</span></span>

<span data-ttu-id="f5d73-155">I följande exempel beskrivs de steg som krävs för att konfigurera en produkt så att återvinningsavgifter debiteras när produkten säljs via en San Francisco-kanal i en fysisk butik.</span><span class="sxs-lookup"><span data-stu-id="f5d73-155">The following example outlines the steps that are required to configure a product so that recycling fees are charged when the product is sold through a San Francisco brick-and-mortar channel.</span></span> <span data-ttu-id="f5d73-156">Exemplet visar också hur de automatiska avgifterna visas i programmet Commerce-kassa (POS).</span><span class="sxs-lookup"><span data-stu-id="f5d73-156">The example also shows how the auto charges appear in the Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="f5d73-157">Organisationen definierar en avgiftskod som kallas **ÅTERVINNING**, som visas på bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="f5d73-157">The organization defines a charges code that is named **RECYCLE**, as shown in the following illustration.</span></span>

![Avgiftskod för ÅTERVINNING](media/Auto-charges-charge-code.png)

<span data-ttu-id="f5d73-159">En automatisk avgift skapas på radnivå.</span><span class="sxs-lookup"><span data-stu-id="f5d73-159">An auto charge is created at the line level.</span></span> <span data-ttu-id="f5d73-160">Det har följande konfigurationer:</span><span class="sxs-lookup"><span data-stu-id="f5d73-160">It has the following configuration:</span></span>

- <span data-ttu-id="f5d73-161">Fältet **Kontokod** ställs in på **Alla**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-161">The **Account code** field is set to **All**.</span></span>
- <span data-ttu-id="f5d73-162">Fältet **Artikelkod** ställs in på **Register**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-162">The **Item code** field is set to **Table**.</span></span>
- <span data-ttu-id="f5d73-163">Fältet **Artikelrelation** ställs in på produkt-ID **91001**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-163">The **Item relation** field is set to product ID **91001**.</span></span>
- <span data-ttu-id="f5d73-164">Fältet **Kod för leveranssätt** ställs in på **Alla**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-164">The **Mode of delivery code** field is set to **All**.</span></span>
- <span data-ttu-id="f5d73-165">Fältet **Butikskanal** ställs in på **Register**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-165">The **Retail channel code** field is set to **Table**.</span></span>
- <span data-ttu-id="f5d73-166">Fältet **butikskanalrelation** ställs in på **San Francisco**-butiken.</span><span class="sxs-lookup"><span data-stu-id="f5d73-166">The **Retail channel relation** field is set to the **San Francisco** store.</span></span>

<span data-ttu-id="f5d73-167">En rad för automatiska avgifter skapas.</span><span class="sxs-lookup"><span data-stu-id="f5d73-167">An auto charges line is created.</span></span> <span data-ttu-id="f5d73-168">Det har följande konfigurationer:</span><span class="sxs-lookup"><span data-stu-id="f5d73-168">It has the following configuration:</span></span>

- <span data-ttu-id="f5d73-169">Fältet **Valuta** anges till **USD**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-169">The **Currency** field is set to **USD**.</span></span>
- <span data-ttu-id="f5d73-170">Fältet **Kod för avgifter** ställs in på **ÅTERVINNING**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-170">The **Charges code** field is set to **RECYCLE**.</span></span>
- <span data-ttu-id="f5d73-171">Fältet **Kategori** ställs in på **fast**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-171">The **Category** field is set to **Fixed**.</span></span>
- <span data-ttu-id="f5d73-172">Fältet **avgifter** anges till **$6,25**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-172">The **Charges** field is set to **$6.25**.</span></span>

![Konfiguration av automatiska avgiften på radnivå och automatiska avgiftsraden](media/Auto-charges-recyclingfee-line-fee.png)

<span data-ttu-id="f5d73-174">I kassaprogrammet skapas en försäljningsorder i **San Francisco** butikskanal.</span><span class="sxs-lookup"><span data-stu-id="f5d73-174">In the POS application, a sales order is created in the **San Francisco** store channel.</span></span> <span data-ttu-id="f5d73-175">Raden **Avgifter** visar återvinningsavgiften på **$6,25**.</span><span class="sxs-lookup"><span data-stu-id="f5d73-175">The **Charges** line shows the recycling fee of **$6.25**.</span></span>

<span data-ttu-id="f5d73-176">Genom att välja avgifter **Transaktionsalternativ \> Avgifter \> Hantera avgifter** i kassaprogrammet kan du se avgiftskoden och beskrivning för återvinningsavgiften.</span><span class="sxs-lookup"><span data-stu-id="f5d73-176">By selecting **Transaction options \> Charges \> Manage charges** in the POS application, you can view the charges code and description for the recycling fee.</span></span>

![Återvinningsavgift i kassaprogrammet](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a><span data-ttu-id="f5d73-178">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f5d73-178">Additional resources</span></span>

[<span data-ttu-id="f5d73-179">Avancerade automatiska avgifter för flera kanaler</span><span class="sxs-lookup"><span data-stu-id="f5d73-179">Omni-channel advanced auto charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="f5d73-180">Allokera huvudavgifter för att matcha försäljningsrader</span><span class="sxs-lookup"><span data-stu-id="f5d73-180">Prorate header charges to matching sales lines</span></span>](pro-rate-charges-matching-lines.md)
