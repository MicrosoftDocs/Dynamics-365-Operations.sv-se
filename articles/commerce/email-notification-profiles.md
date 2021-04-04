---
title: Ange en meddelandeprofil för e-post
description: I det här avsnittet beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: d82a1abe68ff6e162acb75c6fdc1e207af11c279
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555317"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="da7e1-103">Ställa in en meddelandeprofil för e-post</span><span class="sxs-lookup"><span data-stu-id="da7e1-103">Set up an email notification profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="da7e1-104">I det här avsnittet beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="da7e1-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="da7e1-105">När du skapar kanaler kan du ställa in en e-postmeddelandeprofil.</span><span class="sxs-lookup"><span data-stu-id="da7e1-105">When you create channels, you can set up an email notification profile.</span></span> <span data-ttu-id="da7e1-106">På så sätt kan e-postmeddelanden skickas till kunderna för olika transaktionshändelser, till exempel skapa order, leveransstatus för order och betalningsfel.</span><span class="sxs-lookup"><span data-stu-id="da7e1-106">In that way, emails can be sent to customers for various transactional events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="da7e1-107">För ytterligare information om e-postkonfiguration, se [konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="da7e1-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="da7e1-108">Skapa en meddelandeprofil för e-post</span><span class="sxs-lookup"><span data-stu-id="da7e1-108">Create an email notification profile</span></span>

<span data-ttu-id="da7e1-109">Skapa en meddelandeprofil för e-post enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="da7e1-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="da7e1-110">I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.</span><span class="sxs-lookup"><span data-stu-id="da7e1-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="da7e1-111">Klicka på **Nytt** i Åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da7e1-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="da7e1-112">I fältet **Meddelandeprofil för e-post** ange ett namn för att identifiera profilen.</span><span class="sxs-lookup"><span data-stu-id="da7e1-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="da7e1-113">Ange relevant beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="da7e1-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="da7e1-114">Ställ in **aktiva** växeln på **ja**.</span><span class="sxs-lookup"><span data-stu-id="da7e1-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="da7e1-115">Skapa en e-postmall</span><span class="sxs-lookup"><span data-stu-id="da7e1-115">Create an email template</span></span>

<span data-ttu-id="da7e1-116">Innan en e-postmeddelandetyp kan aktiveras måste du skapa en e-postmall för organisationen i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="da7e1-116">Before an email notification type can be enabled, you must create an organization email template in Commerce headquarters.</span></span> <span data-ttu-id="da7e1-117">I den här mallen definieras ämnes-, avsändar-, standardspråk och e-posttext för alla språk som du vill stödja.</span><span class="sxs-lookup"><span data-stu-id="da7e1-117">This template defines the email subject, sender, default language, and email body for each language that you want to support.</span></span>

<span data-ttu-id="da7e1-118">Gör så här om du vill skapa en e-postmall.</span><span class="sxs-lookup"><span data-stu-id="da7e1-118">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="da7e1-119">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar**.</span><span class="sxs-lookup"><span data-stu-id="da7e1-119">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="da7e1-120">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da7e1-120">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="da7e1-121">I fältet **E-post-ID** ange ett ID för att hjälpa till att identifiera den här mallen.</span><span class="sxs-lookup"><span data-stu-id="da7e1-121">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="da7e1-122">I fältet **Avsändarens namn** anger du avsändarens namn.</span><span class="sxs-lookup"><span data-stu-id="da7e1-122">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="da7e1-123">I **E-postbeskrivning**, ange relevant beskrivning.</span><span class="sxs-lookup"><span data-stu-id="da7e1-123">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="da7e1-124">I fälten **avsändarens e-postadress**, ange avsändarnas e-postadress.</span><span class="sxs-lookup"><span data-stu-id="da7e1-124">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="da7e1-125">I avsnittet **Vanlig**, välj ett standardspråk för e-postmallen.</span><span class="sxs-lookup"><span data-stu-id="da7e1-125">In the **General** section, select a default language for the email template.</span></span> <span data-ttu-id="da7e1-126">Standardspråket används när det inte finns någon lokaliserad mall för det angivna språket.</span><span class="sxs-lookup"><span data-stu-id="da7e1-126">The default language will be used when no localized template exists for the specified language.</span></span>
1. <span data-ttu-id="da7e1-127">Expandera avsnittet **innehåll** i e-postmeddelanden och välj **Ny** om du vill skapa mallinnehåll.</span><span class="sxs-lookup"><span data-stu-id="da7e1-127">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="da7e1-128">För varje innehållsobjekt väljer du språket och tillhandahåller e-postmeddelandets ämnesrad.</span><span class="sxs-lookup"><span data-stu-id="da7e1-128">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="da7e1-129">Om e-postmeddelandet ska ha en brödtext kontrollerar du att kryssrutan **Har brödtext** ärt markerad.</span><span class="sxs-lookup"><span data-stu-id="da7e1-129">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="da7e1-130">Välj **e-postmeddelande** i åtgärdsfönstret för att ange en e-postmall.</span><span class="sxs-lookup"><span data-stu-id="da7e1-130">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="da7e1-131">I bilden nedan visas några exempel på Inställningar för e-postmallar.</span><span class="sxs-lookup"><span data-stu-id="da7e1-131">The following image shows some example email template settings.</span></span>

![Inställningar för e-postmall](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="da7e1-133">Skapa en e-posthändelse</span><span class="sxs-lookup"><span data-stu-id="da7e1-133">Create an email event</span></span>

<span data-ttu-id="da7e1-134">Gör så här om du vill skapa en e-posthändelse.</span><span class="sxs-lookup"><span data-stu-id="da7e1-134">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="da7e1-135">I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.</span><span class="sxs-lookup"><span data-stu-id="da7e1-135">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="da7e1-136">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="da7e1-136">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="da7e1-137">Välj e-postmallen i listrutan **E-post-ID**.</span><span class="sxs-lookup"><span data-stu-id="da7e1-137">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="da7e1-138">Välj rätt **Typ av e-postmeddelande** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="da7e1-138">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="da7e1-139">Markera kryssrutan **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="da7e1-139">Select the **Active** check box.</span></span>
1. <span data-ttu-id="da7e1-140">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da7e1-140">On the action pane, select **Save**.</span></span>

<span data-ttu-id="da7e1-141">I bilden nedan visas några exempel på Inställningar för meddelande för händelse.</span><span class="sxs-lookup"><span data-stu-id="da7e1-141">The following image shows some example event notification settings.</span></span>

![Meddelandeinställningar för händelse](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="da7e1-143">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="da7e1-143">Next steps</span></span>

<span data-ttu-id="da7e1-144">Innan du kan skicka e-post måste du konfigurera den utgående e-posttjänsten och ställa in ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="da7e1-144">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="da7e1-145">Om du vill ha mer information, se [Konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="da7e1-145">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="da7e1-146">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="da7e1-146">Additional resources</span></span>

[<span data-ttu-id="da7e1-147">Konfigurera och skicka e-post</span><span class="sxs-lookup"><span data-stu-id="da7e1-147">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="da7e1-148">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="da7e1-148">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="da7e1-149">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="da7e1-149">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="da7e1-150">Organisationer och organisationshierarkier – översikt</span><span class="sxs-lookup"><span data-stu-id="da7e1-150">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
