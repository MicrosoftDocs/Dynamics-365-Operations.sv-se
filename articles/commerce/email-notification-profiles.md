---
title: Ange en meddelandeprofil för e-post
description: I det här avsnittet beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.openlocfilehash: 9e5d90eaf1815bbe54b0bea40d92a0a993a23b75
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113815"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="3d166-103">Ange en meddelandeprofil för e-post</span><span class="sxs-lookup"><span data-stu-id="3d166-103">Set up an email notification profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3d166-104">I det här avsnittet beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3d166-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3d166-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="3d166-105">Overview</span></span>

<span data-ttu-id="3d166-106">Innan du skapar kanaler ska du ställa in en profil så att e-postmeddelanden kan skickas ut för olika händelser, t.ex. skapa order, orderleveransstatus och betalningsfel.</span><span class="sxs-lookup"><span data-stu-id="3d166-106">Before creating channels, you'll want to set up a profile to ensure that email notifications can be sent out for various events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="3d166-107">För ytterligare information om e-postkonfiguration, se [konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="3d166-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="3d166-108">Skapa en meddelandeprofil för e-post</span><span class="sxs-lookup"><span data-stu-id="3d166-108">Create an email notification profile</span></span>

<span data-ttu-id="3d166-109">Skapa en meddelandeprofil för e-post enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="3d166-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="3d166-110">I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.</span><span class="sxs-lookup"><span data-stu-id="3d166-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="3d166-111">Klicka på **Nytt** i Åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3d166-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="3d166-112">I fältet **Meddelandeprofil för e-post** ange ett namn för att identifiera profilen.</span><span class="sxs-lookup"><span data-stu-id="3d166-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="3d166-113">Ange relevant beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="3d166-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="3d166-114">Ställ in **aktiva** växeln på **ja**.</span><span class="sxs-lookup"><span data-stu-id="3d166-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="3d166-115">Skapa en e-postmall</span><span class="sxs-lookup"><span data-stu-id="3d166-115">Create an email template</span></span>

<span data-ttu-id="3d166-116">Innan du kan skapa ett e-postmeddelande måste du skapa en organisations e-postmall som innehåller avsändarens e-postinformation och e-postmall.</span><span class="sxs-lookup"><span data-stu-id="3d166-116">Before an email notification can be created, you must create an organization email template which contains the senders email information and the email template.</span></span>

<span data-ttu-id="3d166-117">Gör så här om du vill skapa en e-postmall.</span><span class="sxs-lookup"><span data-stu-id="3d166-117">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="3d166-118">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar**.</span><span class="sxs-lookup"><span data-stu-id="3d166-118">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="3d166-119">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3d166-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="3d166-120">I fältet **E-post-ID** ange ett ID för att hjälpa till att identifiera den här mallen.</span><span class="sxs-lookup"><span data-stu-id="3d166-120">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="3d166-121">I fältet **Avsändarens namn** anger du avsändarens namn.</span><span class="sxs-lookup"><span data-stu-id="3d166-121">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="3d166-122">I **E-postbeskrivning**, ange relevant beskrivning.</span><span class="sxs-lookup"><span data-stu-id="3d166-122">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="3d166-123">I fälten **avsändarens e-postadress**, ange avsändarnas e-postadress.</span><span class="sxs-lookup"><span data-stu-id="3d166-123">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="3d166-124">I avsnittet **allmänt** fyller du i valfri information som behövs (t.ex. e-postprioriteten).</span><span class="sxs-lookup"><span data-stu-id="3d166-124">In the **General** section, fill out any optional information needed (such as the email priority).</span></span>
1. <span data-ttu-id="3d166-125">Expandera avsnittet **innehåll** i e-postmeddelanden och välj **Ny** om du vill skapa mallinnehåll.</span><span class="sxs-lookup"><span data-stu-id="3d166-125">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="3d166-126">För varje innehållsobjekt väljer du språket och tillhandahåller e-postmeddelandets ämnesrad.</span><span class="sxs-lookup"><span data-stu-id="3d166-126">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="3d166-127">Om e-postmeddelandet ska ha en brödtext kontrollerar du att kryssrutan **Har brödtext** ärt markerad.</span><span class="sxs-lookup"><span data-stu-id="3d166-127">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="3d166-128">Välj **e-postmeddelande** i åtgärdsfönstret för att ange en e-postmall.</span><span class="sxs-lookup"><span data-stu-id="3d166-128">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="3d166-129">I bilden nedan visas några exempel på Inställningar för e-postmallar.</span><span class="sxs-lookup"><span data-stu-id="3d166-129">The following image shows some example email template settings.</span></span>

![Inställningar för e-postmall](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="3d166-131">Skapa en e-posthändelse</span><span class="sxs-lookup"><span data-stu-id="3d166-131">Create an email event</span></span>

<span data-ttu-id="3d166-132">Gör så här om du vill skapa en e-posthändelse.</span><span class="sxs-lookup"><span data-stu-id="3d166-132">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="3d166-133">I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.</span><span class="sxs-lookup"><span data-stu-id="3d166-133">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="3d166-134">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="3d166-134">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="3d166-135">Välj e-postmallen i listrutan **E-post-ID**.</span><span class="sxs-lookup"><span data-stu-id="3d166-135">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="3d166-136">Välj rätt **Typ av e-postmeddelande** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="3d166-136">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="3d166-137">Markera kryssrutan **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="3d166-137">Select the **Active** check box.</span></span>
1. <span data-ttu-id="3d166-138">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3d166-138">On the action pane, select **Save**.</span></span>

<span data-ttu-id="3d166-139">I bilden nedan visas några exempel på Inställningar för meddelande för händelse.</span><span class="sxs-lookup"><span data-stu-id="3d166-139">The following image shows some example event notification settings.</span></span>

![Meddelandeinställningar för händelse](media/email-notification-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="3d166-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3d166-141">Additional resources</span></span>

[<span data-ttu-id="3d166-142">Konfigurera och skicka e-post</span><span class="sxs-lookup"><span data-stu-id="3d166-142">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="3d166-143">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="3d166-143">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="3d166-144">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="3d166-144">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="3d166-145">Organisationer och organisationshierarkier – översikt</span><span class="sxs-lookup"><span data-stu-id="3d166-145">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
