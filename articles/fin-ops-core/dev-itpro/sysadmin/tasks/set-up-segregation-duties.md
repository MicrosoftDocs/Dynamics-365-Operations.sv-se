---
title: Ställ in ansvarsfördelning
description: Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare.
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e25fee324ce95cd04b86ee0e4e6a56cfacb61a53
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745751"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="31e2b-103">Ställ in ansvarsfördelning</span><span class="sxs-lookup"><span data-stu-id="31e2b-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="31e2b-104">Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare.</span><span class="sxs-lookup"><span data-stu-id="31e2b-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="31e2b-105">Detta koncept kallas ansvarsfördelning.</span><span class="sxs-lookup"><span data-stu-id="31e2b-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="31e2b-106">Du kan till exempel välja att inte samma person ska bekräfta inleveransen av varor och bearbeta betalningar till leverantören.</span><span class="sxs-lookup"><span data-stu-id="31e2b-106">For example, you might not want the same person to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="31e2b-107">Ansvarsfördelning minskar risken för bedrägeri och hjälper även till att identifiera fel eller oriktigheter.</span><span class="sxs-lookup"><span data-stu-id="31e2b-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="31e2b-108">Du kan också använda ansvarsfördelning för att framtvinga interna kontrollpolicyer.</span><span class="sxs-lookup"><span data-stu-id="31e2b-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="31e2b-109">Slutför följande procedur för att skapa en regel.</span><span class="sxs-lookup"><span data-stu-id="31e2b-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="31e2b-110">Du måste vara systemadministratör för att slutföra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="31e2b-110">You must be a system administrator to complete the procedure.</span></span>

1. <span data-ttu-id="31e2b-111">Gå till **Systemadministration** > **Säkerhet** > **Ansvarsfördelning** > **Ansvarsfördelningsregler**.</span><span class="sxs-lookup"><span data-stu-id="31e2b-111">Go to **System administration** > **Security** > **Segregation of duties** > **Segregation of duties rules**.</span></span>
2. <span data-ttu-id="31e2b-112">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="31e2b-112">Click **New**.</span></span>
3. <span data-ttu-id="31e2b-113">I fältet **Namn** skriver du ett värde.</span><span class="sxs-lookup"><span data-stu-id="31e2b-113">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="31e2b-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Första programbehörighet**.</span><span class="sxs-lookup"><span data-stu-id="31e2b-114">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="31e2b-115">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="31e2b-115">In the list, find and select the desired record.</span></span> <span data-ttu-id="31e2b-116">Välj det första programbehörigheten som kontrolleras av regeln.</span><span class="sxs-lookup"><span data-stu-id="31e2b-116">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="31e2b-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Andra programbehörighet**.</span><span class="sxs-lookup"><span data-stu-id="31e2b-117">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="31e2b-118">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="31e2b-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="31e2b-119">Välj den andra programbehörigheten som kontrolleras av regeln.</span><span class="sxs-lookup"><span data-stu-id="31e2b-119">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="31e2b-120">Markera ett alternativ i fältet **Allvarlighetsgrad**.</span><span class="sxs-lookup"><span data-stu-id="31e2b-120">In the **Severity** field, select an option.</span></span> <span data-ttu-id="31e2b-121">Markera allvarlighetsgraden för risken som uppstår när samma användare eller roll utför båda programbehörigheterna.</span><span class="sxs-lookup"><span data-stu-id="31e2b-121">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="31e2b-122">Ange ett värde i fältet **Säkerhetsrisk**.</span><span class="sxs-lookup"><span data-stu-id="31e2b-122">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="31e2b-123">Ange en beskrivning av säkerhetsrisken.</span><span class="sxs-lookup"><span data-stu-id="31e2b-123">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="31e2b-124">Ange ett värde i fältet **Säkerhetshöjning**.</span><span class="sxs-lookup"><span data-stu-id="31e2b-124">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="31e2b-125">Ange en beskrivning av de åtgärder som du vidtar för att minska säkerhetrisken.</span><span class="sxs-lookup"><span data-stu-id="31e2b-125">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="31e2b-126">Du kan till exempel minska risken genom att utöva mer detaljerad granskning av processen, genom att utöva en månadsvis chefsgranskning eller genom att dela resurser med andra avdelningar.</span><span class="sxs-lookup"><span data-stu-id="31e2b-126">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="31e2b-127">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="31e2b-127">Click **Save**.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="31e2b-128">Efterföljanderegler för uppdelning av uppgifter kontrolleras inte när du skapar en regel.</span><span class="sxs-lookup"><span data-stu-id="31e2b-128">Compliance with the rules for segregation of duties is not verified when you create a rule.</span></span> <span data-ttu-id="31e2b-129">Du kan skapa en regel som skapar en konflikt för befintliga roller.</span><span class="sxs-lookup"><span data-stu-id="31e2b-129">You can create a rule that creates a conflict for existing roles.</span></span> <span data-ttu-id="31e2b-130">Befintliga tilldelningar av användarroller kan också vara i konflikt med den nya regeln.</span><span class="sxs-lookup"><span data-stu-id="31e2b-130">Existing user role assignments can also be in conflict with the new rule.</span></span> <span data-ttu-id="31e2b-131">Du måste validera efterföljande när du har skapat eller ändra en regel.</span><span class="sxs-lookup"><span data-stu-id="31e2b-131">You must validate compliance after you create or modify a rule.</span></span> <span data-ttu-id="31e2b-132">För mer information, se [Identifiera och lösa konflikter vid ansvarsfördelning](identify-resolve-conflicts-segregation-duties.md)</span><span class="sxs-lookup"><span data-stu-id="31e2b-132">For more information, see [Identify and resolve conflicts in segregation of duties](identify-resolve-conflicts-segregation-duties.md)</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]