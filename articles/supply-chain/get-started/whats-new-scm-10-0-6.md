---
title: Nyheter och ändringar i Dynamics 365 Supply Chain Management (10.0.6 november 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Supply Chain Management 10.0.6.
author: josaw1
manager: tfehr
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac1
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 319ba09184c087a194b664ca87076d57c6ba0c66
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201558"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a><span data-ttu-id="2fd87-103">Nyheter och ändringar i Dynamics 365 Supply Chain Management (10.0.6 november 2019)</span><span class="sxs-lookup"><span data-stu-id="2fd87-103">What's new or changed in Dynamics 365 Supply Chain Management 10.0.6 (November 2019)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2fd87-104">Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span><span class="sxs-lookup"><span data-stu-id="2fd87-104">This topic describes features that are either new or changed in Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span></span> <span data-ttu-id="2fd87-105">Den här versionen har ett versionsnummer på 10.0.234.</span><span class="sxs-lookup"><span data-stu-id="2fd87-105">This version has a build number of 10.0.234.</span></span> <span data-ttu-id="2fd87-106">Även om det allmänna tillgänglighetsdatumet är i november, är de nya funktionerna tillgängliga för tidig lansering i oktober.</span><span class="sxs-lookup"><span data-stu-id="2fd87-106">While the general availability date is in November, the new features are available for early release in October.</span></span> <span data-ttu-id="2fd87-107">Mer information om version 10.0.6, se [Ytterligare resurser](whats-new-scm-10-0-6.md#additional-resources).</span><span class="sxs-lookup"><span data-stu-id="2fd87-107">For more information about version 10.0.6, see [Additional resources](whats-new-scm-10-0-6.md#additional-resources).</span></span>

## <a name="product-configuration-models-v2-data-entity"></a><span data-ttu-id="2fd87-108">Produktkonfigurationsmodeller V2 datatabell</span><span class="sxs-lookup"><span data-stu-id="2fd87-108">Product configuration models V2 data entity</span></span>

<span data-ttu-id="2fd87-109">En andra version för datatabellen "produktkonfigurationsmodeller" har frisläppts (kallas "produkterkonfigurationsmodeller V2").</span><span class="sxs-lookup"><span data-stu-id="2fd87-109">A second version for the "product configuration models" data entity is released (called "products configuration models V2").</span></span> <span data-ttu-id="2fd87-110">Standard mallen "418-produktkonfigurationsmodeller" måste också vara så att den nya enheten "produktkonfigurationsmodeller V2" används i mallarna importera/exportera.</span><span class="sxs-lookup"><span data-stu-id="2fd87-110">The default template "418-product configuration models" is also needs to be so that it uses the new "product configuration models V2" data entity in the import/export framework templates.</span></span> <span data-ttu-id="2fd87-111">Mallen uppdateras inte automatiskt så att du måste läsa in mallen från standardvärdet manuellt.</span><span class="sxs-lookup"><span data-stu-id="2fd87-111">The template will not be auto-updated so that you will have to load the template from the default manually.</span></span> <span data-ttu-id="2fd87-112">V2-enheten exporterar en rad som separat fil i en bifogad fil i stället för på infogad och löser storleksbegränsningarna för V1-enheten.</span><span class="sxs-lookup"><span data-stu-id="2fd87-112">The V2 entity exports one row as separate file in an attachment instead of inline, solving the size limitations of the V1 entity.</span></span> 
 
<span data-ttu-id="2fd87-113">Vad behöver du göra för att göra ändringen?</span><span class="sxs-lookup"><span data-stu-id="2fd87-113">What do you need to do to take this change?</span></span>
-    <span data-ttu-id="2fd87-114">Eftersom V1-enheten är föråldrad ska du börja migrera från V1 till V2.</span><span class="sxs-lookup"><span data-stu-id="2fd87-114">As the V1 entity has been deprecated, you should start migrating from V1 to V2.</span></span> <span data-ttu-id="2fd87-115">Om du använder mallen "418-produktkonfigurationsmodeller" kan du klicka på knappen "Läs in standardmallar" och läsa in mallen på nytt "418 – produktkonfigurationsmodeller"</span><span class="sxs-lookup"><span data-stu-id="2fd87-115">If you are using the  "418-product configuration models" template, you can click on "load default templates" button and reload the template "418 – product configuration models"</span></span>
-    <span data-ttu-id="2fd87-116">Om du behöver behålla kompatibiliteten med befintliga system kan du nu fortsätta att använda den befintliga mallen och den (inaktuella) V1-enheten tills du flyttar integrationerna till den nya mallen.</span><span class="sxs-lookup"><span data-stu-id="2fd87-116">If you need to keep compatibility with existing systems, you can for now continue using the existing template and the (deprecated) V1 entity until you move your integrations to the new template.</span></span> 

## <a name="feature-management-enhancements"></a><span data-ttu-id="2fd87-117">Förbättringar över funktionshantering</span><span class="sxs-lookup"><span data-stu-id="2fd87-117">Feature management enhancements</span></span>
<span data-ttu-id="2fd87-118">Med funktionshantering kan du nu aktivera alla nya funktioner som standard, kräva bekräftelse för att aktivera en funktion och aktivera alla funktioner som inte redan har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="2fd87-118">Feature management now allows you to enable all new features by default, require confirmation to enable a feature, and enable all features that have not already been enabled.</span></span> 


## <a name="purchase-agreement-responsible-party"></a><span data-ttu-id="2fd87-119">Ansvarig part för inköpsavtal</span><span class="sxs-lookup"><span data-stu-id="2fd87-119">Purchase agreement responsible party</span></span>
<span data-ttu-id="2fd87-120">Nu kan du definiera primära och sekundära ansvariga parter i formuläret klassificering av inköpsavtal och resulterande inköpsavtal.</span><span class="sxs-lookup"><span data-stu-id="2fd87-120">You now have the ability to define primary and secondary responsible parties on the Purchase agreement classification form and resulting Purchase agreements.</span></span>  <span data-ttu-id="2fd87-121">Detta ger användaren åtkomst till vem som ser över avtalen.</span><span class="sxs-lookup"><span data-stu-id="2fd87-121">This provides the user access to who oversees the agreements.</span></span>

## <a name="rfq-link-on-the-purchase-order-line"></a><span data-ttu-id="2fd87-122">Länk för anbudsförfrågan för inköpsorderrad</span><span class="sxs-lookup"><span data-stu-id="2fd87-122">RFQ link on the Purchase order line</span></span>
<span data-ttu-id="2fd87-123">Du kan lägga tillbaka en referens länk från inköpsorderraderna till motsvarande rader för anbudsförfrågningar som de kom från, vilket gör att användaren enkelt kan tillhandahålla det stödjande anbudsförfrågningsdokumentet.</span><span class="sxs-lookup"><span data-stu-id="2fd87-123">You can add a reference link from the Purchase order lines back to the corresponding RFQ lines they originated from, allowing the user to easily be provided with the supporting request for quotation document.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2fd87-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2fd87-124">Additional resources</span></span>

### <a name="bug-fixes"></a><span data-ttu-id="2fd87-125">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="2fd87-125">Bug fixes</span></span>
<span data-ttu-id="2fd87-126">Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.6 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span><span class="sxs-lookup"><span data-stu-id="2fd87-126">For information about the bug fixes included in each of the updates that are part of 10.0.6, sign in to Lifecycle Services (LCS) and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span></span>

### <a name="platform-update-30"></a><span data-ttu-id="2fd87-127">Plattform update 30</span><span class="sxs-lookup"><span data-stu-id="2fd87-127">Platform update 30</span></span>
<span data-ttu-id="2fd87-128">Microsoft Dynamics 365 Supply Chain Management 10.0.6 ingår plattformsuppdatering 30.</span><span class="sxs-lookup"><span data-stu-id="2fd87-128">Microsoft Dynamics 365 Supply Chain Management 10.0.6 includes Platform update 30.</span></span> <span data-ttu-id="2fd87-129">Mer information om plattformsuppdatering 30 finns i [Nyheter och ändringar i plattformsuppdatering 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span><span class="sxs-lookup"><span data-stu-id="2fd87-129">To learn more about Platform update 30, see [What's new or changed in Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span></span>

### <a name="dynamics-365-2019-release-wave-2-plan"></a><span data-ttu-id="2fd87-130">Dynamics 365: 2019 utgivningsvåg 2 plan</span><span class="sxs-lookup"><span data-stu-id="2fd87-130">Dynamics 365: 2019 release wave 2 plan</span></span>
<span data-ttu-id="2fd87-131">Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?</span><span class="sxs-lookup"><span data-stu-id="2fd87-131">Wondering about upcoming and recently released capabilities in any of our business apps or platform?</span></span>

<span data-ttu-id="2fd87-132">Se [Dynamics 365: 2019 utgivningsvåg 2 plan](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span><span class="sxs-lookup"><span data-stu-id="2fd87-132">Check out the [Dynamics 365: 2019 release wave 2 plan](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span></span> <span data-ttu-id="2fd87-133">Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.</span><span class="sxs-lookup"><span data-stu-id="2fd87-133">We've captured all the details, end to end, top to bottom, in a single document that you can use for planning.</span></span>

### <a name="removed-and-deprecated-supply-chain-management-features"></a><span data-ttu-id="2fd87-134">Borttagna och inaktuella funktioner för Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2fd87-134">Removed and deprecated Supply Chain Management features</span></span>

<span data-ttu-id="2fd87-135">De [borttagna eller föråldrade funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) i ämnet beskriver funktioner som har schemalagts eller är planerade att tas bort eller inaktuellt för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fd87-135">The [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic describes features that have been or are scheduled to be removed or deprecated for Supply Chain Management.</span></span>

- <span data-ttu-id="2fd87-136">En *borttagen* funktion är inte längre tillgänglig i produkten.</span><span class="sxs-lookup"><span data-stu-id="2fd87-136">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="2fd87-137">En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.</span><span class="sxs-lookup"><span data-stu-id="2fd87-137">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="2fd87-138">Innan någon funktion tas bort från produkten visas understrykningsmeddelandet i ämnet [borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före avhämtningen.</span><span class="sxs-lookup"><span data-stu-id="2fd87-138">Before any feature is removed from the product, the deprecation notice will be announced in the [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic 12 months prior to the removal.</span></span>

<span data-ttu-id="2fd87-139">För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader.</span><span class="sxs-lookup"><span data-stu-id="2fd87-139">For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time will be less than 12 months.</span></span> <span data-ttu-id="2fd87-140">Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.</span><span class="sxs-lookup"><span data-stu-id="2fd87-140">Typically, these are functional updates that need to be made to the compiler.</span></span>
