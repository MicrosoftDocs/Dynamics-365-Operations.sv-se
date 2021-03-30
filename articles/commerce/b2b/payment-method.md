---
title: Konfigurera betalsätt för kundkonto på B2B-näthandelssajter
description: I det här avsnittet beskrivs hur du konfigurerar betalsättet för kundkonto för B2B-näthandelssajter.
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 82dfd6ac7e97d838ef442fd6ded4a4f165fc795b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211211"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a><span data-ttu-id="5fe08-103">Konfigurera betalsätt för kundkonto på B2B-näthandelssajter</span><span class="sxs-lookup"><span data-stu-id="5fe08-103">Configure the customer account payment method for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5fe08-104">I det här avsnittet beskrivs hur du konfigurerar betalsättet för kundkonto för B2B-näthandelssajter.</span><span class="sxs-lookup"><span data-stu-id="5fe08-104">This topic describes how to configure the customer account payment method for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="5fe08-105">Återförsäljare kan acceptera olika typer av betalning i utbytet mot de produkter och tjänster man säljer i en näthandelskanal.</span><span class="sxs-lookup"><span data-stu-id="5fe08-105">Retailers can accept various types of payment in exchange for the products and services that they sell in an e-commerce channel.</span></span> <span data-ttu-id="5fe08-106">Varje betalningstyp som en återförsäljare godtar, måste konfigureras i Microsoft Dynamics 365 Commerce när systemet installeras.</span><span class="sxs-lookup"><span data-stu-id="5fe08-106">Each payment type that a retailer accepts must be configured in Microsoft Dynamics 365 Commerce when the system is set up.</span></span> <span data-ttu-id="5fe08-107">Kundkontots betalsätt (eller "on account") måste stödjas på B2B-näthandelssajter.</span><span class="sxs-lookup"><span data-stu-id="5fe08-107">The customer account (or "on account") payment method must be supported on B2B e-commerce sites.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5fe08-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="5fe08-108">Prerequisites</span></span>

1. <span data-ttu-id="5fe08-109">Lägg till betalsättet för kundkonto i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="5fe08-109">Add the customer account payment method in Commerce headquarters.</span></span>
2. <span data-ttu-id="5fe08-110">Koppla betalsättet för kundkontot till näthandelskanalen.</span><span class="sxs-lookup"><span data-stu-id="5fe08-110">Associate the customer account payment method with the e-commerce channel.</span></span>
3. <span data-ttu-id="5fe08-111">Kontrollera att **Tillåt a conto** har aktiverats för kunden på **Butik och Handel \> Kunder \> Alla kunder \> Betalningsstandarder** i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="5fe08-111">Make sure that **Allow on account** is enabled for the customer at **Retail and Commerce \> Customers \> All customers \> Payment defaults** in Commerce headquarters.</span></span> <span data-ttu-id="5fe08-112">Kontrollera också att parametrarna för **Kreditgräns** har angetts korrekt för kunden på **Butik och Handel \> Kunder \> Alla kunder \> Kredit och inkasso** i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="5fe08-112">Also make sure that **Credit limit** parameters are set appropriately for the customer at **Retail and Commerce \> Customers \> All customers \> Credit and Collections** in Commerce headquarters.</span></span> 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a><span data-ttu-id="5fe08-113">Aktivera betalsättet för kund i Commerce-webbplatsbyggaren</span><span class="sxs-lookup"><span data-stu-id="5fe08-113">Enable the customer account payment method in Commerce site builder</span></span> 

<span data-ttu-id="5fe08-114">För att aktivera betalsättet för kund i Commerce-webbplatsbyggaren följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="5fe08-114">To enable the customer account payment method in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5fe08-115">Gå till **Webbplatsinställningar \> Tillägg**.</span><span class="sxs-lookup"><span data-stu-id="5fe08-115">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="5fe08-116">Ställ in egenskapen **Aktivera kundkontobetalningar** som **Aktiverad för B2B-kunder**.</span><span class="sxs-lookup"><span data-stu-id="5fe08-116">Set the **Enable customer account payments** property to **Enabled for B2B customers**.</span></span> 
1. <span data-ttu-id="5fe08-117">Välj **Spara och publicera**.</span><span class="sxs-lookup"><span data-stu-id="5fe08-117">Select **Save and Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="5fe08-118">De nya webbplatsinställningarna träder i kraft först när filen app.settings.json har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="5fe08-118">The new site settings take effect only after the app.settings.json file is updated.</span></span> <span data-ttu-id="5fe08-119">Mer information finns i [SDK- och modulbiblioteksuppdateringar](../e-commerce-extensibility/sdk-updates.md).</span><span class="sxs-lookup"><span data-stu-id="5fe08-119">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md).</span></span>

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a><span data-ttu-id="5fe08-120">Aktivera betalsättet för kundkonto på kassasidan för B2B-näthandelssajten</span><span class="sxs-lookup"><span data-stu-id="5fe08-120">Enable the customer account payment method on the checkout page for the B2B e-commerce site</span></span>

<span data-ttu-id="5fe08-121">Följ dessa steg om du vill aktivera betalsättet för kundkonto på kassasidan för B2B-näthandelssajten.</span><span class="sxs-lookup"><span data-stu-id="5fe08-121">To enable the customer account payment method on the checkout page for the B2B e-commerce site, follow these steps.</span></span>

1. <span data-ttu-id="5fe08-122">Sök efter och redigera kassasidan eller det fragment som innehåller kassamodulen för B2B-näthandelssajten i Commerce-webbplatsbyggaren.</span><span class="sxs-lookup"><span data-stu-id="5fe08-122">In Commerce site builder, find and edit the checkout page or fragment that contains the checkout module for the B2B e-commerce site.</span></span>
1. <span data-ttu-id="5fe08-123">I fältet **Behållare för kassaavsnitt** väljer du **Lägg till modul** innan du lägger till en **Kundkontobetalning**-modul.</span><span class="sxs-lookup"><span data-stu-id="5fe08-123">In the **Checkout section container** slot, select **Add Module**, and then add a **Customer account payment** module.</span></span>
1. <span data-ttu-id="5fe08-124">Placera **Kundkontobetalning**-modulen genom att välja ellipsen (**...**) och sedan **Flytta upp** eller **Flytta ner** efter behov.</span><span class="sxs-lookup"><span data-stu-id="5fe08-124">Position the **Customer account payment** module by selecting the ellipsis (**...**), and then selecting **Move Up** or **Move Down** as required.</span></span>
1. <span data-ttu-id="5fe08-125">Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="5fe08-125">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a><span data-ttu-id="5fe08-126">Bekräfta att betalsättet för kundkontot har aktiverats och publicerats</span><span class="sxs-lookup"><span data-stu-id="5fe08-126">Confirm that the customer account payment method has been enabled and published</span></span>

<span data-ttu-id="5fe08-127">För att bekräfta att betalsättet för kundkontot har aktiverats följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="5fe08-127">To confirm that the customer account payment method has been enabled, follow these steps.</span></span>

1. <span data-ttu-id="5fe08-128">Logga in på näthandelssajten.</span><span class="sxs-lookup"><span data-stu-id="5fe08-128">Sign in to the e-commerce site.</span></span>
1. <span data-ttu-id="5fe08-129">Lägg till en produkt i kundvagnen.</span><span class="sxs-lookup"><span data-stu-id="5fe08-129">Add a product to the cart.</span></span>
1. <span data-ttu-id="5fe08-130">Gå till kassasidan.</span><span class="sxs-lookup"><span data-stu-id="5fe08-130">Go to the checkout page.</span></span> <span data-ttu-id="5fe08-131">Du bör se det nya betalsättet **Kundkonto**.</span><span class="sxs-lookup"><span data-stu-id="5fe08-131">You should see the new **Customer Account** payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5fe08-132">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5fe08-132">Additional resources</span></span>

[<span data-ttu-id="5fe08-133">Konfigurera en B2B-näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="5fe08-133">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="5fe08-134">Skapa org-modellhierarkier för B2B-organisationer</span><span class="sxs-lookup"><span data-stu-id="5fe08-134">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="5fe08-135">Hantera affärspartneranvändare på B2B-näthandelssajter</span><span class="sxs-lookup"><span data-stu-id="5fe08-135">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="5fe08-136">Ange produktkvantitetsgränser för B2B-näthandelssajter</span><span class="sxs-lookup"><span data-stu-id="5fe08-136">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)

[<span data-ttu-id="5fe08-137">Uppdateringar av SDK och modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="5fe08-137">SDK and Module library updates</span></span>](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]