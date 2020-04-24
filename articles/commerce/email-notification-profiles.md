---
title: Ange en meddelandeprofil för e-post
description: I det här avsnittet beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/31/2020
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
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c0ab56c15a37313d0a88b1174d5bcf51d391dcec
ms.sourcegitcommit: 17ffdcbf4b1801bd6ee9c9ddc18622d5d04b8a98
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2020
ms.locfileid: "3180205"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="6bcb7-103">Ange en meddelandeprofil för e-post</span><span class="sxs-lookup"><span data-stu-id="6bcb7-103">Set up an email notification profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6bcb7-104">I det här avsnittet beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6bcb7-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="6bcb7-105">Overview</span></span>

<span data-ttu-id="6bcb7-106">Innan du skapar kanaler ska du ställa in en profil så att e-postmeddelanden kan skickas ut för olika händelser, t.ex. skapa order, orderleveransstatus och betalningsfel.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-106">Before creating channels, you'll want to set up a profile to ensure that email notifications can be sent out for various events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="6bcb7-107">För ytterligare information om e-postkonfiguration, se [konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="6bcb7-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="6bcb7-108">Skapa en meddelandeprofil för e-post</span><span class="sxs-lookup"><span data-stu-id="6bcb7-108">Create an email notification profile</span></span>

<span data-ttu-id="6bcb7-109">Skapa en meddelandeprofil för e-post enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="6bcb7-110">I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="6bcb7-111">Klicka på **Nytt** i Åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="6bcb7-112">I fältet **Meddelandeprofil för e-post** ange ett namn för att identifiera profilen.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="6bcb7-113">Ange relevant beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="6bcb7-114">Ställ in **aktiva** växeln på **ja**.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="6bcb7-115">Skapa en e-postmall</span><span class="sxs-lookup"><span data-stu-id="6bcb7-115">Create an email template</span></span>

<span data-ttu-id="6bcb7-116">Innan du kan skapa ett e-postmeddelande måste du skapa en organisations e-postmall som innehåller avsändarens e-postinformation och e-postmall.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-116">Before an email notification can be created, you must create an organization email template which contains the senders email information and the email template.</span></span>

<span data-ttu-id="6bcb7-117">Gör så här om du vill skapa en e-postmall.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-117">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="6bcb7-118">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar**.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-118">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="6bcb7-119">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="6bcb7-120">I fältet **E-post-ID** ange ett ID för att hjälpa till att identifiera den här mallen.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-120">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="6bcb7-121">I fältet **Avsändarens namn** anger du avsändarens namn.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-121">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="6bcb7-122">I **E-postbeskrivning**, ange relevant beskrivning.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-122">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="6bcb7-123">I fälten **avsändarens e-postadress**, ange avsändarnas e-postadress.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-123">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="6bcb7-124">I avsnittet **allmänt** fyller du i valfri information som behövs (t.ex. e-postprioriteten).</span><span class="sxs-lookup"><span data-stu-id="6bcb7-124">In the **General** section, fill out any optional information needed (such as the email priority).</span></span>
1. <span data-ttu-id="6bcb7-125">Expandera avsnittet **innehåll** i e-postmeddelanden och välj **Ny** om du vill skapa mallinnehåll.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-125">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="6bcb7-126">För varje innehållsobjekt väljer du språket och tillhandahåller e-postmeddelandets ämnesrad.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-126">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="6bcb7-127">Om e-postmeddelandet ska ha en brödtext kontrollerar du att kryssrutan **Har brödtext** ärt markerad.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-127">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="6bcb7-128">Välj **e-postmeddelande** i åtgärdsfönstret för att ange en e-postmall.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-128">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="6bcb7-129">I bilden nedan visas några exempel på Inställningar för e-postmallar.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-129">The following image shows some example email template settings.</span></span>

![Inställningar för e-postmall](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="6bcb7-131">Skapa en e-posthändelse</span><span class="sxs-lookup"><span data-stu-id="6bcb7-131">Create an email event</span></span>

<span data-ttu-id="6bcb7-132">Gör så här om du vill skapa en e-posthändelse.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-132">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="6bcb7-133">I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-133">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="6bcb7-134">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-134">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="6bcb7-135">Välj e-postmallen i listrutan **E-post-ID**.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-135">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="6bcb7-136">Välj rätt **Typ av e-postmeddelande** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-136">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="6bcb7-137">Markera kryssrutan **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-137">Select the **Active** check box.</span></span>
1. <span data-ttu-id="6bcb7-138">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-138">On the action pane, select **Save**.</span></span>

<span data-ttu-id="6bcb7-139">I bilden nedan visas några exempel på Inställningar för meddelande för händelse.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-139">The following image shows some example event notification settings.</span></span>

![Meddelandeinställningar för händelse](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="6bcb7-141">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6bcb7-141">Next steps</span></span>

<span data-ttu-id="6bcb7-142">Innan du kan skicka e-post måste du konfigurera den utgående e-posttjänsten och ställa in ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="6bcb7-142">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="6bcb7-143">Om du vill ha mer information, se [Konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="6bcb7-143">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="6bcb7-144">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6bcb7-144">Additional resources</span></span>

[<span data-ttu-id="6bcb7-145">Konfigurera och skicka e-post</span><span class="sxs-lookup"><span data-stu-id="6bcb7-145">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="6bcb7-146">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="6bcb7-146">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="6bcb7-147">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="6bcb7-147">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="6bcb7-148">Organisationer och organisationshierarkier – översikt</span><span class="sxs-lookup"><span data-stu-id="6bcb7-148">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
