---
title: Skapa och tillämpa villkor för innehållen leverantörsbetalning
description: I det här avsnittet finns information om hur du ställer in och underhåller villkor för kvarhållande för leverantörsbetalningar.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410269"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a><span data-ttu-id="b393e-103">Skapa och tillämpa villkor för innehållen leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="b393e-103">Create and apply vendor payment retention terms</span></span>

[!include [banner](../includes/banner.md)] 

<span data-ttu-id="b393e-104">Att ställa in kvarhållande av leverantörsbetalningsvillkor för ett projekt är användbart när organisationen vill behålla en del av betalningarna som har gjorts till en leverantör.</span><span class="sxs-lookup"><span data-stu-id="b393e-104">Setting up vendor payment retention terms for a project is useful when your organization wants to retain part of the payments made to a vendor.</span></span> <span data-ttu-id="b393e-105">Till exempel när du vill spärra betalning till en leverantör tills de produkter som levererats uppfyller dina förväntningar.</span><span class="sxs-lookup"><span data-stu-id="b393e-105">For example, when you want to hold payment to a vendor until the products delivered meet your expectations.</span></span> <span data-ttu-id="b393e-106">Villkor för leverantörsbetalning kan anges när du förhandlar om ett leverantörskontrakt.</span><span class="sxs-lookup"><span data-stu-id="b393e-106">Vendor payment retention terms can be specified when you negotiate a vendor contract.</span></span>

## <a name="create-vendor-payment-retention-terms"></a><span data-ttu-id="b393e-107">Skapa kvarhållandevillkor för leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="b393e-107">Create vendor payment retention terms</span></span>

<span data-ttu-id="b393e-108">Du kan ange procentandelen av en leverantörsbetalning för kvarhållande som du vill hålla inne och procentandelen av tidigare innehållna belopp som ska frisläppas.</span><span class="sxs-lookup"><span data-stu-id="b393e-108">You can enter the percentage of vendor payment for retention and the percentage of the previously retained amounts to be released.</span></span> <span data-ttu-id="b393e-109">Belopp hålls automatiskt inne på leverantörsfakturor tills avtalet når den angivna slutförandefasen.</span><span class="sxs-lookup"><span data-stu-id="b393e-109">Amounts are automatically retained on vendor invoices until the contract reaches the specified state of completion.</span></span> <span data-ttu-id="b393e-110">När du har ställt in kvarhållandevillkoren kan du tillämpa dem på alla projekt för den leverantören.</span><span class="sxs-lookup"><span data-stu-id="b393e-110">After you set up the retention terms, you can apply them to any project for that vendor.</span></span>

<span data-ttu-id="b393e-111">Använd följande steg om du vill ställa in och underhålla villkor för innehållet belopp i leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="b393e-111">Use the following steps to set up and maintain retention terms for vendor payments.</span></span> 

1. <span data-ttu-id="b393e-112">Gå till **Projekthantering och redovisning** > **Kvarhållande** > **Villkor för innehållen leverantörsbetalning**.</span><span class="sxs-lookup"><span data-stu-id="b393e-112">Go to **Project management and accounting** > **Retention** > **Vendor payment retention terms**.</span></span>
2. <span data-ttu-id="b393e-113">Välj **Nytt** om du vill lägga till ett nytt villkor för innehållet belopp.</span><span class="sxs-lookup"><span data-stu-id="b393e-113">Select **New** to add a new vendor retention term.</span></span> <span data-ttu-id="b393e-114">Värdet i **Regel-ID** för det nya villkoret anges i automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b393e-114">The **Rule ID** value for the new term is automatically entered.</span></span> 
3. <span data-ttu-id="b393e-115">Ange en kort beskrivning i fältet **Beskrivning** och snabbfliken **Villkor**, välj **Lägg till rad** om du vill ange villkorsvärden för följande:</span><span class="sxs-lookup"><span data-stu-id="b393e-115">Enter a brief description in the **Description** field, and on the **Terms** FastTab, select **Add line** to enter term values for the following:</span></span>

   - <span data-ttu-id="b393e-116">**Levererade enheter i procent**: Ange en slutförandeprocent för villkoret.</span><span class="sxs-lookup"><span data-stu-id="b393e-116">**Percentage of units delivered**: Enter a percentage of completion for the term.</span></span> <span data-ttu-id="b393e-117">Belopp hålls inne automatiskt på leverantörsfakturor tills projektslutförandefasen är lika med procentsatsen som du anger.</span><span class="sxs-lookup"><span data-stu-id="b393e-117">Amounts are automatically retained on vendor invoices until the project stage of completion is equal to the specified percentage.</span></span> <span data-ttu-id="b393e-118">Om du till exempel anger 50,00 hålls beloppen inne tills projektet är 50 procent slutfört.</span><span class="sxs-lookup"><span data-stu-id="b393e-118">For example, if you enter 50.00, amounts are retained until the project is 50 percent completed.</span></span>
   - <span data-ttu-id="b393e-119">**Procent att hålla inne**: Ange en procentandel av leverantörsfakturor som ska hållas inne.</span><span class="sxs-lookup"><span data-stu-id="b393e-119">**Percentage to retain**: Enter a percentage of the vendor invoice amount to be retained.</span></span> <span data-ttu-id="b393e-120">Om du till exempel anger 10,00 hålls 10 procent av beloppet på leverantörsfakturorna inne tills projektet når slutförandeprocenten som du väljer i formuläret **Levererade enheter i procent**.</span><span class="sxs-lookup"><span data-stu-id="b393e-120">For example, if you enter 10.00, then 10 percent of the amount on a vendor invoice is retained until the project reaches the percentage of completion as set in the **Percentage of units delivered field**.</span></span>
   - <span data-ttu-id="b393e-121">**Procent att frisläppa**: Välj **Lägg till rad** för att ange en procentandel av tidigare behållna belopp som ska frisläppas för den valda nivån för projektets slutförande.</span><span class="sxs-lookup"><span data-stu-id="b393e-121">**Percentage to release**: Select **Add line** to enter a percentage of any previously retained amounts to be released for the selected level of project completion.</span></span>

> [!NOTE]
> <span data-ttu-id="b393e-122">Om du har mer än en milstolpe för olika nivåer för projektslutförande anger du en separat rad för villkor för innehållet belopp för varje regel.</span><span class="sxs-lookup"><span data-stu-id="b393e-122">If you have more than one milestone for different levels of project completion, enter a separate vendor retention term line for each retention rule.</span></span> <span data-ttu-id="b393e-123">Varje rad kan ange en annan kvarhållandeprocentsats och en annan procentsats för frisläppning på varje nivå av projektslutförande.</span><span class="sxs-lookup"><span data-stu-id="b393e-123">Each line can specify a different retention percentage and a different release percentage for each designated level of project completion.</span></span>

<span data-ttu-id="b393e-124">När du har skapat villkor för återförsäljare för en leverantör kan du tillämpa villkoren på ett projekt.</span><span class="sxs-lookup"><span data-stu-id="b393e-124">After you create vendor retention terms for a vendor, you can apply the terms to a project.</span></span>

## <a name="apply-vendor-retention-terms-to-a-project"></a><span data-ttu-id="b393e-125">Tillämpa innehållet belopp till leverantören på ett projekt</span><span class="sxs-lookup"><span data-stu-id="b393e-125">Apply vendor retention terms to a project</span></span>

1. <span data-ttu-id="b393e-126">Gå till **Projekthantering och redovisning** > **Projekt** > **Alla projekt** och öppna ett projekt från sidan projektlista.</span><span class="sxs-lookup"><span data-stu-id="b393e-126">Go to **Project management and accounting** > **Projects** > **All projects** and open a project from the project list page.</span></span>
2. <span data-ttu-id="b393e-127">Klicka på **Lägg till rad** på snabbfliken, välj **Leverantörsavtal**.</span><span class="sxs-lookup"><span data-stu-id="b393e-127">On the **Vendor agreements** FastTab, select **Add line**.</span></span>
3. <span data-ttu-id="b393e-128">Välj ett av följande alternativ i fältet **Kontokod**:</span><span class="sxs-lookup"><span data-stu-id="b393e-128">In the **Account code field**, select one of the following options:</span></span> 

   - <span data-ttu-id="b393e-129">**Tabell**: Villkoren för innehållet belopp till leverantören gäller för en enskild leverantör.</span><span class="sxs-lookup"><span data-stu-id="b393e-129">**Table**: The vendor retention terms apply to a single vendor.</span></span>
   - <span data-ttu-id="b393e-130">**Grupp**: Villkor för innehållet belopp till leverantören gäller för alla leverantörer inom en leverantörsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b393e-130">**Group**: The vendor retention terms apply to all vendors in a vendor group.</span></span>
   - <span data-ttu-id="b393e-131">**Alla**: Villkor för innehållet belopp till leverantören gäller för alla leverantörer.</span><span class="sxs-lookup"><span data-stu-id="b393e-131">**All**: The vendor retention terms apply to all vendors.</span></span>

4. <span data-ttu-id="b393e-132">Välj den leverantör eller leverantörsgrupp som villkoren för innehållet belopp gäller för i fältet **Leverantör/leverantörsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="b393e-132">In the **Vendor/Vendor group field**, select the vendor or vendor group to which the vendor retention terms apply.</span></span> <span data-ttu-id="b393e-133">Om du har valt **Alla** i det föregående steget är det här fältet inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="b393e-133">If you selected **All** in the previous step, this field is unavailable.</span></span>
5. <span data-ttu-id="b393e-134">I fältet **Villkor för kvarhållande** väljer du de kvarhållandevillkor som du skapade i föregående procedur.</span><span class="sxs-lookup"><span data-stu-id="b393e-134">In the **Vendor retention terms** field, select the retention terms that you created in the previous procedure.</span></span>
6. <span data-ttu-id="b393e-135">Om projektet även har bet. vid bet.-villkor inställda för leverantören använder du fältet **Bet. vid bet.-tröskelprocent** och anger ingångsprocentsatsen för projektet.</span><span class="sxs-lookup"><span data-stu-id="b393e-135">If the project also has pay-when-paid (PWP) terms set up for the vendor, enter the threshold percentage for the project in the **PWP threshold percentage** field.</span></span>

<span data-ttu-id="b393e-136">Villkoren för innehållet belopp till leverantören visas också på inköpsorder som du skapar för leverantören.</span><span class="sxs-lookup"><span data-stu-id="b393e-136">The vendor retention terms are also displayed on purchase orders that you create for the vendor.</span></span>
