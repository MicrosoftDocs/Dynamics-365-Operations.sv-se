--- 
title: "Konfigurera systemet för att skicka arbetsflödesrelaterad e-post till användare"
description: "Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 04d90c9ded1ba7fb1ceac4ff1d54f54f6c43f9e9
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="configure-the-system-to-send-workflow-related-email-to-users"></a><span data-ttu-id="a0b5b-103">Konfigurera systemet för att skicka arbetsflödesrelaterad e-post till användare</span><span class="sxs-lookup"><span data-stu-id="a0b5b-103">Configure the system to send workflow-related email to users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a0b5b-104">Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="a0b5b-105">E-postmeddelanden kan till exempel skickas till användare när dokument tilldelas till dem för godkännande.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="a0b5b-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="a0b5b-107">Gå till Systemadministration > Användare > Användare.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="a0b5b-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a0b5b-109">Klicka på Användaralternativ.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-109">Click User options.</span></span>
4. <span data-ttu-id="a0b5b-110">Klicka på fliken Arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-110">Click the Workflow tab.</span></span>
    * <span data-ttu-id="a0b5b-111">Kontrollera att avsnittet för meddelanden expanderas.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-111">Make sure that the Notifications section is expanded.</span></span>     <span data-ttu-id="a0b5b-112">I avsnittet för meddelanden kan du ange hur du vill att användaren ska meddelas om arbetsflödesrelaterade händelser.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-112">In the Notifications section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="a0b5b-113">Välj ett alternativ i fältet Meddelandetyp för arbetsflöde för radartikel.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-113">In the Line-item workflow notification type field, select an option.</span></span>
    * <span data-ttu-id="a0b5b-114">Gruppering – Meddelanden för radartiklar grupperas i ett enda e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-114">Grouped – Notifications for line items are grouped into a single email message.</span></span>    <span data-ttu-id="a0b5b-115">Enskilt – Ett e-postmeddelande skickas för varje radartikel.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-115">Individual – An email message is sent for each line item.</span></span>  
    * <span data-ttu-id="a0b5b-116">Om du vill att användaren ska ta emot meddelanden i klienten ska du välja kryssrutan Skicka meddelanden i e-post.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-116">If you want the user to receive notifications in the client, select the Send notifications in email check box.</span></span>  
6. <span data-ttu-id="a0b5b-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-117">Click Save.</span></span>
7. <span data-ttu-id="a0b5b-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a0b5b-118">Close the page.</span></span>


