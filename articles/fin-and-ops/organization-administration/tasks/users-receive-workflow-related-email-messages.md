---
title: Låt användare ta emot arbetsflödesrelaterade e-postmeddelanden
description: Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser.
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6800d02878123388611d35760123d0215e9d539f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "344603"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="219c6-103">Låt användare ta emot arbetsflödesrelaterade e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="219c6-103">Enable users to receive workflow-related email messages</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="219c6-104">Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser.</span><span class="sxs-lookup"><span data-stu-id="219c6-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="219c6-105">E-postmeddelanden kan till exempel skickas till användare när dokument tilldelas till dem för godkännande.</span><span class="sxs-lookup"><span data-stu-id="219c6-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="219c6-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="219c6-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="219c6-107">Gå till Systemadministration > Användare > Användare.</span><span class="sxs-lookup"><span data-stu-id="219c6-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="219c6-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="219c6-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="219c6-109">Klicka på Användaralternativ.</span><span class="sxs-lookup"><span data-stu-id="219c6-109">Click User options.</span></span>
4. <span data-ttu-id="219c6-110">Klicka på fliken Arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="219c6-110">Click the Workflow tab.</span></span>
    * <span data-ttu-id="219c6-111">Kontrollera att avsnittet för meddelanden expanderas.</span><span class="sxs-lookup"><span data-stu-id="219c6-111">Make sure that the Notifications section is expanded.</span></span>     <span data-ttu-id="219c6-112">I avsnittet för meddelanden kan du ange hur du vill att användaren ska meddelas om arbetsflödesrelaterade händelser.</span><span class="sxs-lookup"><span data-stu-id="219c6-112">In the Notifications section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="219c6-113">Välj ett alternativ i fältet Meddelandetyp för arbetsflöde för radartikel.</span><span class="sxs-lookup"><span data-stu-id="219c6-113">In the Line-item workflow notification type field, select an option.</span></span>
    * <span data-ttu-id="219c6-114">Gruppering – Meddelanden för radartiklar grupperas i ett enda e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="219c6-114">Grouped – Notifications for line items are grouped into a single email message.</span></span>    <span data-ttu-id="219c6-115">Enskilt – Ett e-postmeddelande skickas för varje radartikel.</span><span class="sxs-lookup"><span data-stu-id="219c6-115">Individual – An email message is sent for each line item.</span></span>  
    * <span data-ttu-id="219c6-116">Om du vill att användaren ska ta emot meddelanden i klienten ska du välja kryssrutan Skicka meddelanden i e-post.</span><span class="sxs-lookup"><span data-stu-id="219c6-116">If you want the user to receive notifications in the client, select the Send notifications in email check box.</span></span>  
6. <span data-ttu-id="219c6-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="219c6-117">Click Save.</span></span>
7. <span data-ttu-id="219c6-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="219c6-118">Close the page.</span></span>

