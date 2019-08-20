---
title: Ställ in ansvarsfördelning
description: Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: e3682dbcb72588633fb6b3fe4cbda99f422163a3
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851273"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="9295b-103">Ställ in ansvarsfördelning</span><span class="sxs-lookup"><span data-stu-id="9295b-103">Set up segregation of duties</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9295b-104">Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare.</span><span class="sxs-lookup"><span data-stu-id="9295b-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="9295b-105">Detta koncept kallas ansvarsfördelning.</span><span class="sxs-lookup"><span data-stu-id="9295b-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="9295b-106">Du kan till exempel välja att inte samma person både ska bekräfta inleveransen av varor och bearbeta betalningar till leverantören.</span><span class="sxs-lookup"><span data-stu-id="9295b-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="9295b-107">Ansvarsfördelning minskar risken för bedrägeri och hjälper även till att identifiera fel eller oriktigheter.</span><span class="sxs-lookup"><span data-stu-id="9295b-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="9295b-108">Du kan också använda ansvarsfördelning för att framtvinga interna kontrollpolicyer.</span><span class="sxs-lookup"><span data-stu-id="9295b-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="9295b-109">Slutför följande procedur för att skapa en regel.</span><span class="sxs-lookup"><span data-stu-id="9295b-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="9295b-110">Du måste vara systemadministratör för att slutföra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="9295b-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="9295b-111">Det demonstrationsdataföretag som används för att skapa den här proceduren är DAT.</span><span class="sxs-lookup"><span data-stu-id="9295b-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="9295b-112">Gå till Systemadministration > Säkerhet > Ansvarsfördelning > Ansvarsfördelningsregler.</span><span class="sxs-lookup"><span data-stu-id="9295b-112">Go to System administration > Security > Segregation of duties > Segregation of duties rules.</span></span>
2. <span data-ttu-id="9295b-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9295b-113">Click New.</span></span>
3. <span data-ttu-id="9295b-114">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="9295b-114">In the Name field, type a value.</span></span>
    * <span data-ttu-id="9295b-115">Ange ett namn på regeln.</span><span class="sxs-lookup"><span data-stu-id="9295b-115">Enter a name for the rule.</span></span>  
4. <span data-ttu-id="9295b-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Första programbehörighet.</span><span class="sxs-lookup"><span data-stu-id="9295b-116">In the First duty field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="9295b-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9295b-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9295b-118">Välj det första programbehörigheten som kontrolleras av regeln.</span><span class="sxs-lookup"><span data-stu-id="9295b-118">Select the first duty that is controlled by the rule.</span></span>  
6. <span data-ttu-id="9295b-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9295b-119">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="9295b-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Andra programbehörighet.</span><span class="sxs-lookup"><span data-stu-id="9295b-120">In the Second duty field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="9295b-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9295b-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9295b-122">Välj den andra programbehörigheten som kontrolleras av regeln.</span><span class="sxs-lookup"><span data-stu-id="9295b-122">Select the second duty that is controlled by the rule.</span></span>  
9. <span data-ttu-id="9295b-123">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9295b-123">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="9295b-124">Markera ett alternativ i fältet Allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="9295b-124">In the Severity field, select an option.</span></span>
    * <span data-ttu-id="9295b-125">Markera allvarlighetsgraden för risken som uppstår när samma användare eller roll utför båda programbehörigheterna.</span><span class="sxs-lookup"><span data-stu-id="9295b-125">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="9295b-126">Ange ett värde i fältet Säkerhet.</span><span class="sxs-lookup"><span data-stu-id="9295b-126">In the Security risk field, type a value.</span></span>
    * <span data-ttu-id="9295b-127">Ange en beskrivning av säkerhetsrisken.</span><span class="sxs-lookup"><span data-stu-id="9295b-127">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="9295b-128">Ange ett värde i fältet Säkerhetshöjning.</span><span class="sxs-lookup"><span data-stu-id="9295b-128">In the Security mitigation field, type a value.</span></span>
    * <span data-ttu-id="9295b-129">Ange en beskrivning av de åtgärder som du vidtar för att minska säkerhetrisken.</span><span class="sxs-lookup"><span data-stu-id="9295b-129">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="9295b-130">Du kan till exempel minska risken genom att utöva mer detaljerad granskning av processen, genom att utöva en månadsvis chefsgranskning eller genom att dela resurser med andra avdelningar.</span><span class="sxs-lookup"><span data-stu-id="9295b-130">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>  
13. <span data-ttu-id="9295b-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9295b-131">Click Save.</span></span>

