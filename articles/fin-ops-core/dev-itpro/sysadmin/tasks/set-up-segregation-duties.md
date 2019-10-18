---
title: Ställ in ansvarsfördelning
description: Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare.
author: maertenm
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40b40b77877680e28671b7a15ea8c8b58ce94417
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180885"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="c8bb6-103">Ställ in ansvarsfördelning</span><span class="sxs-lookup"><span data-stu-id="c8bb6-103">Set up segregation of duties</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c8bb6-104">Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="c8bb6-105">Detta koncept kallas ansvarsfördelning.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="c8bb6-106">Du kan till exempel välja att inte samma person både ska bekräfta inleveransen av varor och bearbeta betalningar till leverantören.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="c8bb6-107">Ansvarsfördelning minskar risken för bedrägeri och hjälper även till att identifiera fel eller oriktigheter.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="c8bb6-108">Du kan också använda ansvarsfördelning för att framtvinga interna kontrollpolicyer.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="c8bb6-109">Slutför följande procedur för att skapa en regel.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="c8bb6-110">Du måste vara systemadministratör för att slutföra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="c8bb6-111">Det demonstrationsdataföretag som används för att skapa den här proceduren är DAT.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="c8bb6-112">Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Ansvarsfördelning > Ansvarsfördelningsregler**.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-112">Go to **Navigation pane > Modules > System administration > Security > Segregation of duties > Segregation of duties rules**.</span></span>
2. <span data-ttu-id="c8bb6-113">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-113">Click **New**.</span></span>
3. <span data-ttu-id="c8bb6-114">I fältet **Namn** skriver du ett värde.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-114">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="c8bb6-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Första programbehörighet**.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-115">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="c8bb6-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="c8bb6-117">Välj det första programbehörigheten som kontrolleras av regeln.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-117">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="c8bb6-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Andra programbehörighet**.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-118">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="c8bb6-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-119">In the list, find and select the desired record.</span></span> <span data-ttu-id="c8bb6-120">Välj den andra programbehörigheten som kontrolleras av regeln.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-120">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="c8bb6-121">Markera ett alternativ i fältet **Allvarlighetsgrad**.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-121">In the **Severity** field, select an option.</span></span> <span data-ttu-id="c8bb6-122">Markera allvarlighetsgraden för risken som uppstår när samma användare eller roll utför båda programbehörigheterna.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-122">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="c8bb6-123">Ange ett värde i fältet **Säkerhetsrisk**.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-123">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="c8bb6-124">Ange en beskrivning av säkerhetsrisken.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-124">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="c8bb6-125">Ange ett värde i fältet **Säkerhetshöjning**.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-125">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="c8bb6-126">Ange en beskrivning av de åtgärder som du vidtar för att minska säkerhetrisken.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-126">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="c8bb6-127">Du kan till exempel minska risken genom att utöva mer detaljerad granskning av processen, genom att utöva en månadsvis chefsgranskning eller genom att dela resurser med andra avdelningar.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-127">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="c8bb6-128">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c8bb6-128">Click **Save**.</span></span>

