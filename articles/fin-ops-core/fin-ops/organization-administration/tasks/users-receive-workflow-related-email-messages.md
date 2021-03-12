---
title: Låt användare ta emot arbetsflödesrelaterade e-postmeddelanden
description: Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser.
author: jasongre
manager: AnnBe
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 221e38cbe31e2ad24a56cb2e71206a1ebcdd619e
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "4799014"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="88033-103">Låt användare ta emot arbetsflödesrelaterade e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="88033-103">Enable users to receive workflow-related email messages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="88033-104">Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser.</span><span class="sxs-lookup"><span data-stu-id="88033-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="88033-105">E-postmeddelanden kan till exempel skickas till användare när dokument tilldelas till dem för godkännande.</span><span class="sxs-lookup"><span data-stu-id="88033-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="88033-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="88033-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="88033-107">Gå till **Navigeringsfönster > Moduler > Systemadministration > Användare > Användare**.</span><span class="sxs-lookup"><span data-stu-id="88033-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="88033-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="88033-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="88033-109">Klicka på **Användaralternativ** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="88033-109">On the **Action pane**, click **User options**.</span></span>
4. <span data-ttu-id="88033-110">Klicka på fliken **Arbetsflöde**. Kontrollera att avsnittet **Meddelanden** är expanderat.</span><span class="sxs-lookup"><span data-stu-id="88033-110">Click the **Workflow** tab. Make sure that the **Notifications** section is expanded.</span></span> <span data-ttu-id="88033-111">I avsnittet **Meddelanden** kan du ange hur du vill att användaren ska meddelas om arbetsflödesrelaterade händelser.</span><span class="sxs-lookup"><span data-stu-id="88033-111">In the **Notifications** section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="88033-112">Välj ett alternativ i fältet **Meddelandetyp för arbetsflöde för radartikel**.</span><span class="sxs-lookup"><span data-stu-id="88033-112">In the **Line-item workflow notification type** field, select an option.</span></span>
    - <span data-ttu-id="88033-113">Gruppering – Meddelanden för radartiklar grupperas i ett enda e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="88033-113">Grouped – Notifications for line items are grouped into a single email message.</span></span>
    - <span data-ttu-id="88033-114">Enskilt – Ett e-postmeddelande skickas för varje radartikel.</span><span class="sxs-lookup"><span data-stu-id="88033-114">Individual – An email message is sent for each line item.</span></span>  
    - <span data-ttu-id="88033-115">Om du vill att användaren ska ta emot meddelanden i klienten ska du välja kryssrutan **Skicka meddelanden i e-post**.</span><span class="sxs-lookup"><span data-stu-id="88033-115">If you want the user to receive notifications in the client, select the **Send notifications in email** check box.</span></span>  
6. <span data-ttu-id="88033-116">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="88033-116">Click **Save**.</span></span>
7. <span data-ttu-id="88033-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="88033-117">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="88033-118">E-postmallarna för arbetsflödet kommer att hämtas från antingen systemets e-postmallar eller organisationens e-postmallar beroende på om arbetsflödet är på systemnivå (inte företagsspecifik) eller arbetsflödet på organisationsnivå (företagsspecifik).</span><span class="sxs-lookup"><span data-stu-id="88033-118">The workflow email templates will be sourced from either system email templates or organization email templates depending on whether the workflow is a system-level (not company specific) or organization-level (company specific) workflow.</span></span>
