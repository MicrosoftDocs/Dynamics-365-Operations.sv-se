---
title: Vanliga frågor om arbetsflöde
description: Detta avsnitt besvarar några vanliga frågor om arbetsflödessystemet.
author: ChrisGarty
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0188e8ed3cbbfd7dbccd7d13cf6129e146a919ac
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772707"
---
# <a name="workflow-faq"></a><span data-ttu-id="06302-103">Vanliga frågor om arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="06302-103">Workflow FAQ</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="06302-104">Detta avsnitt besvarar några vanliga frågor om arbetsflödessystemet.</span><span class="sxs-lookup"><span data-stu-id="06302-104">This topic answers frequently asked questions about the workflow system.</span></span>

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="06302-105">Varför tas flera meddelanden emot när en arbetsuppgift avvisas?</span><span class="sxs-lookup"><span data-stu-id="06302-105">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="06302-106">När en arbetsuppgift har avvisats kommer detta arbetsobjekt slutföras som avvisat.</span><span class="sxs-lookup"><span data-stu-id="06302-106">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="06302-107">En annan arbetsuppgift skapas och tilldelas till upphovsmannen.</span><span class="sxs-lookup"><span data-stu-id="06302-107">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="06302-108">Detta innebär att det finns ett meddelande till upphovsmannen för den avvisade arbetsuppgiften och ett separat meddelande till användaren som är tilldelad till den nya ”ändringsbegärda” arbetsuppgiften.</span><span class="sxs-lookup"><span data-stu-id="06302-108">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="06302-109">Varje meddelande är för en olika arbetsuppgift, men likheten kan vara förvirrande.</span><span class="sxs-lookup"><span data-stu-id="06302-109">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="06302-110">Vi undersöker sätt att förbättra detta i framtida versioner.</span><span class="sxs-lookup"><span data-stu-id="06302-110">We are looking at ways to improve this in a future release.</span></span>

## <a name="why-are-my-workflow-exports-failing"></a><span data-ttu-id="06302-111">Varför fungerar inte min arbetsflödesexport?</span><span class="sxs-lookup"><span data-stu-id="06302-111">Why are my workflow exports failing?</span></span>
<span data-ttu-id="06302-112">Det finns en begränsning i funktionen för att exportera arbetsflöden som förhindrar att arbetsflödesnamn innehåller fler än 48 tecken.</span><span class="sxs-lookup"><span data-stu-id="06302-112">There is currently a limitation in the workflow export feature that prevents workflow names from exceeding 48 characters.</span></span> <span data-ttu-id="06302-113">Om du använder ett namn som är längre än 48 tecken kan felmeddelandet "servern kunde inte autentisera begäran" visas och/eller förhindra att en fil exporteras utan filtyp.</span><span class="sxs-lookup"><span data-stu-id="06302-113">Using a name that is longer than 48 characters can result in a "Server failed to authenticate the request" error and/or prevent a file to be exported  without a file type.</span></span> <span data-ttu-id="06302-114">Följande blogginlägg innehåller mer information om [Felsökning av arbetsflödesexport](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="06302-114">The following blog post provides more details [Workflow Export Troubleshooting](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span></span>

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a><span data-ttu-id="06302-115">Kan den som skickar ett arbetsflöde också godkänna arbetsflödet?</span><span class="sxs-lookup"><span data-stu-id="06302-115">Can the submitter of a workflow also approve the workflow?</span></span>
<span data-ttu-id="06302-116">Ja, en avsändare av ett arbetsflöde kan också godkänna arbetsflödet om det är konfigurerat på det sättet.</span><span class="sxs-lookup"><span data-stu-id="06302-116">Yes, a submitter of a workflow can also approve the workflow if it is configured that way.</span></span> <span data-ttu-id="06302-117">Du kan förhindra detta genom att ställa in **Arbetsflödesparametrar > Allmänt > Godkännaren > Tillåt inte godkännande av avsändare** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="06302-117">To prevent this behavior, set **Workflow parameters > General > Approver > Disallow approval by submitter** to **Yes**.</span></span>

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a><span data-ttu-id="06302-118">Kan jag lägga till notifieringar i arbetsflöden för att skicka meddelanden till användarna?</span><span class="sxs-lookup"><span data-stu-id="06302-118">Can I add alerts to workflows to provide notifications to users?</span></span>
<span data-ttu-id="06302-119">Här följer några viktiga områden som du kan använda för att lägga till notifieringar i arbetsflöden för meddelanden:</span><span class="sxs-lookup"><span data-stu-id="06302-119">Here are a few key areas to note about adding alerts to workflows to provide notifications:</span></span>
- <span data-ttu-id="06302-120">Notifieringar jämfört med meddelandefunktioner för arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="06302-120">Alerts versus workflow notification mechanisms</span></span>
    - <span data-ttu-id="06302-121">Notifieringar kan ställas in för poständringar.</span><span class="sxs-lookup"><span data-stu-id="06302-121">Alerts can be set up for record changes.</span></span> <span data-ttu-id="06302-122">Arbetsflöden ändrar poster så det går att ställa in en notifiering som hör till en poständring som orsakas av ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="06302-122">Workflows change records, so it's possible to set up an alert related to a record change caused by a workflow.</span></span> <span data-ttu-id="06302-123">Eftersom arbetsflöden har olika inbyggda meddelandealternativ, är det dock inte idealiskt att använda notifieringar.</span><span class="sxs-lookup"><span data-stu-id="06302-123">However, because workflows have different built-in notification options, using alerts isn’t ideal.</span></span>
- <span data-ttu-id="06302-124">Standardmeddelanden från arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="06302-124">Standard notifications from workflows</span></span> 
    - <span data-ttu-id="06302-125">Arbetsflöden har inbyggda e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="06302-125">Workflows have built in email notifications.</span></span> <span data-ttu-id="06302-126">En kund kan konfigurera meddelandena så att användarna skickar e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="06302-126">A customer can configure the notifications so that the users are sent emails.</span></span> <span data-ttu-id="06302-127">Dessa meddelanden resulterar inte i meddelande från åtgärdscentret för användare.</span><span class="sxs-lookup"><span data-stu-id="06302-127">Those notifications don’t result in Action Center messages for users.</span></span>
    - <span data-ttu-id="06302-128">I en framtida uppdatering kommer vi att lägga till ett meddelande från åtgärdscenter så att en användare tilldelas en arbetsflödesuppgift.</span><span class="sxs-lookup"><span data-stu-id="06302-128">In a future update we will be adding an Action Center message so a user is assigned a workflow work item.</span></span> 
- <span data-ttu-id="06302-129">Lägga till meddelanden till arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="06302-129">Adding notifications to workflows</span></span>
    - <span data-ttu-id="06302-130">Meddelanden i åtgärdscentret kan skapas för specifika användare, t.ex. ett meddelande som skapats från ett arbets flöde i X++.</span><span class="sxs-lookup"><span data-stu-id="06302-130">Action Center messages can be created for specific users, such as a message created from a workflow in X++.</span></span>
    - <span data-ttu-id="06302-131">[Arbetsflöden har affärshändelser](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) som kunden kan använda för att utlösa flöden med de aviseringar som de letar efter.</span><span class="sxs-lookup"><span data-stu-id="06302-131">[Workflows have Business Events](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) that the customer could use to trigger Flows have the notifications that they are looking for.</span></span>   

<span data-ttu-id="06302-132">Sammanfattningsvis, om en användare inte får rätt meddelanden från åtgärdscentret när de tilldelas en arbetsflödesuppgift, och sedan använder [affärshändelser för arbetsflöden](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) med Microsoft Power Automate för att ge ytterligare eller andra meddelanden.</span><span class="sxs-lookup"><span data-stu-id="06302-132">In summary, if a user does not get the proper notification from the Action Center when they are assigned a workflow work item, then leverage [Workflow Business Events](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) with Microsoft Power Automate to provide additional or different notifications.</span></span>
