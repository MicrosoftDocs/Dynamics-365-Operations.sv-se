---
title: Anpassa transaktionsmeddelanden via e-post efter leveranssätt
description: I det här avsnittet beskrivs hur du ställer in anpassade e-postmallar för specifika meddelandetyper och leveranssätt i Microsoft Dynamics 365 Commerce.
author: stuharg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: faf5fba70bf9297727464e6046806696ab725001
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594999"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a><span data-ttu-id="388c8-103">Anpassa transaktionsmeddelanden via e-post efter leveranssätt</span><span class="sxs-lookup"><span data-stu-id="388c8-103">Customize transactional emails by mode of delivery</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="388c8-104">I det här avsnittet beskrivs hur du ställer in anpassade e-postmallar för specifika meddelandetyper och leveranssätt i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="388c8-104">This topic describes how to set up custom email templates for specific notification types and modes of delivery in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="388c8-105">Transaktionsmeddelanden via e-post kan nu anpassas för en kombination av en meddelandetyp (t. ex. **Order skapad**, **Order förpackad** eller **Order fakturerad**) och ett leveranssätt (t. ex. nästa dag, upphämtning i butik eller drive in-upphämtning).</span><span class="sxs-lookup"><span data-stu-id="388c8-105">Transactional emails can now be customized for a combination of a notification type (for example, **Order created**, **Order packed**, or **Order invoiced**) and a mode of delivery (for example, overnight, in-store pickup, or curbside pickup).</span></span> <span data-ttu-id="388c8-106">Anpassade transaktionsmeddelanden via e-post gör att återförsäljare tillhandahåller kundorder med uppfyllelseupplevelser som är skräddarsydda efter orderns leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="388c8-106">Custom transactional emails let retailers provide their customers order with fulfillment experiences that are tailored to the order's mode of delivery.</span></span> <span data-ttu-id="388c8-107">Händelsen "order packad" kan till exempel anpassas så att den tillhandahåller instruktioner rörande drive in-upphämtning till för kunder som väljer detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="388c8-107">For example, the "order packed" event can be customized so that it provides curbside pickup instructions for customers who choose curbside pickup.</span></span> <span data-ttu-id="388c8-108">Det kan också tillhandahålla information om speditör och leverans för kunder som väljer att låta ordern levereras.</span><span class="sxs-lookup"><span data-stu-id="388c8-108">Alternatively, it can provide shipping carrier and delivery information for customers who choose to have their order shipped.</span></span>

> [!NOTE]
> <span data-ttu-id="388c8-109">Om du vill använda funktionen för anpassade transaktionsmeddelanden via e-post måste du först aktivera funktionen **Anpassa transaktionsmeddelanden via e-post efter leveranssätt** genom att gå till **Arbetsytor \> Funktionshantering** i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="388c8-109">To use the functionality for customized transactional emails, you first must turn on the **Customize transactional email templates by mode of delivery** feature by going to **Workspaces \> Feature management** in Commerce headquarters.</span></span>

<span data-ttu-id="388c8-110">E-postmeddelanden kan anpassas efter leveranssätt för följande meddelandetyper:</span><span class="sxs-lookup"><span data-stu-id="388c8-110">Emails can be customized by mode of delivery for the following notification types:</span></span>

- <span data-ttu-id="388c8-111">**Annullering av order** – Denna meddelandetyp via e-post är ny.</span><span class="sxs-lookup"><span data-stu-id="388c8-111">**Order cancellation** – This email notification type is new.</span></span>
- <span data-ttu-id="388c8-112">**Order skapad**</span><span class="sxs-lookup"><span data-stu-id="388c8-112">**Order created**</span></span>
- <span data-ttu-id="388c8-113">**Ordern är bekräftad**</span><span class="sxs-lookup"><span data-stu-id="388c8-113">**Order confirmed**</span></span>
- <span data-ttu-id="388c8-114">**Order fakturerad** – Denna meddelandetyp via e-post är ny.</span><span class="sxs-lookup"><span data-stu-id="388c8-114">**Order invoiced** – This email notification type is new.</span></span> <span data-ttu-id="388c8-115">Den kan användas istället för meddelandetypen **Order skickad** som skickar ett meddelande för alla fakturahändelser med som har ett leveranssätt som innefattar avsändande (ej upphämtning, utkörning eller elektroniskt leveranssätt).</span><span class="sxs-lookup"><span data-stu-id="388c8-115">It can be used instead of the **Order shipped** notification type that will send a notification for any invoice event that has a shipped mode of delivery (not a pickup, carry out, or electronic mode of delivery).</span></span>
- <span data-ttu-id="388c8-116">**Order plockad**</span><span class="sxs-lookup"><span data-stu-id="388c8-116">**Order picked**</span></span>
- <span data-ttu-id="388c8-117">**Order packad**</span><span class="sxs-lookup"><span data-stu-id="388c8-117">**Order packed**</span></span>
- <span data-ttu-id="388c8-118">**Order klar för upphämtning** – Denna meddelandetyp kan bara anpassas efter leveranssätt om funktionen **Stöd för flera leveranssätt genom upphämtning** har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="388c8-118">**Order ready for pickup** – This notification type can be customized by mode of delivery only if the **Support for multiple pickup delivery modes** feature is turned on.</span></span> <span data-ttu-id="388c8-119">I så fall är denna meddelandetyp funktionellt likvärdig med meddelandetypen **Order packad**.</span><span class="sxs-lookup"><span data-stu-id="388c8-119">In that case, this notification type is functionally equivalent to the **Order packed** notification type.</span></span>
- <span data-ttu-id="388c8-120">**Betalning lyckades inte**</span><span class="sxs-lookup"><span data-stu-id="388c8-120">**Payment failed**</span></span>
- <span data-ttu-id="388c8-121">**Ersättningsorder skapad**</span><span class="sxs-lookup"><span data-stu-id="388c8-121">**Replacement order created**</span></span>

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a><span data-ttu-id="388c8-122">Konfigurera e-postmallar för specifika leveranssätt</span><span class="sxs-lookup"><span data-stu-id="388c8-122">Configure email templates for specific modes of delivery</span></span>

<span data-ttu-id="388c8-123">För denna procedur görs antagandet att du redan har skapat dina nya, anpassade e-postmallar och lagt till dessa på sidan **E-postmallar för organisation**.</span><span class="sxs-lookup"><span data-stu-id="388c8-123">For this procedure, the assumption is that you've already created your new, custom email templates and added them to the **Organization email templates** page.</span></span> <span data-ttu-id="388c8-124">Information om hur du skapar och överför e-postmallar finns i [Skapa e-postmallar för transaktionshändelser](email-templates-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="388c8-124">For information about how to create and upload email templates, see [Create email templates for transactional events](email-templates-transactions.md).</span></span>

<span data-ttu-id="388c8-125">Följ dessa steg om du vill konfigurera e-postmallar för specifika leveranssätt i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="388c8-125">To configure email templates for specific modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="388c8-126">Gå till **Meddelandeprofil via e-post i Commerce**.</span><span class="sxs-lookup"><span data-stu-id="388c8-126">Go to **Commerce email notification profile**.</span></span>
1. <span data-ttu-id="388c8-127">Under **Meddelandeinställningar för butikshändelse** väljer du en befintlig meddelandetyp.</span><span class="sxs-lookup"><span data-stu-id="388c8-127">Under **Retail event notification settings**, select an existing notification type.</span></span>
1. <span data-ttu-id="388c8-128">När meddelandetypen fortfarande är markerad väljer du **Konfigurera leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="388c8-128">While the notification type is still selected, select **Configure modes of delivery**.</span></span>
1. <span data-ttu-id="388c8-129">I dialogrutan **Leveranssätt** väljer du **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="388c8-129">In the **Modes of delivery** dialog box, select **New**.</span></span>
1. <span data-ttu-id="388c8-130">I den nya raden i fältet **Leveranssätt** väljer du ett leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="388c8-130">In the new row, in the **Mode of delivery** field, select a mode of delivery.</span></span>
1. <span data-ttu-id="388c8-131">I fältet **ID- för e-post** väljer du den e-postmall du vill mappa till leveranssättet.</span><span class="sxs-lookup"><span data-stu-id="388c8-131">In the **Email ID** field, select the email template to map to the mode of delivery.</span></span>
1. <span data-ttu-id="388c8-132">Markera kryssrutan **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="388c8-132">Select the **Active** check box.</span></span>
1. <span data-ttu-id="388c8-133">Upprepa steg 4 till 7 om du vill lägga till fler leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="388c8-133">Repeat steps 4 through 7 to add more modes of delivery.</span></span>
1. <span data-ttu-id="388c8-134">Välj **OK** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="388c8-134">When you've finished, select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="388c8-135">När det finns fler än ett leveranssätt över flera rader i en försäljningsorder används standardmallen.</span><span class="sxs-lookup"><span data-stu-id="388c8-135">When more than one mode of delivery is present across lines in a sales order, the default template will be used.</span></span> <span data-ttu-id="388c8-136">Standardmallen är den mall som mappas till meddelande typen på sidan **Meddelandeprofil via e-post för Commerce**.</span><span class="sxs-lookup"><span data-stu-id="388c8-136">The default template is the template that is mapped to the notification type on the **Commerce email notification profile** page.</span></span>
> - <span data-ttu-id="388c8-137">Om en försäljningsorder har ett leveranssätt som inte har konfigurerats för en anpassad e-postmall, kommer standard-e-postmallen att användas.</span><span class="sxs-lookup"><span data-stu-id="388c8-137">If a sales order has a mode of delivery that hasn't been configured for a custom email template, the default email template will be used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="388c8-138">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="388c8-138">Additional resources</span></span>

[<span data-ttu-id="388c8-139">Skapa kundtjänstorder</span><span class="sxs-lookup"><span data-stu-id="388c8-139">Create call center orders</span></span>](tasks/create-call-center-orders.md)

[<span data-ttu-id="388c8-140">Ändra leveranssätt i kassan</span><span class="sxs-lookup"><span data-stu-id="388c8-140">Change mode of delivery in POS</span></span>](pos-change-delivery-mode.md)
