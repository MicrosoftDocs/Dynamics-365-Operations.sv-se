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
ms.openlocfilehash: 712cc90bef4f3ad56291e99edd9f963ae88add48
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143522"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="abe4b-103">Ställ in ansvarsfördelning</span><span class="sxs-lookup"><span data-stu-id="abe4b-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="abe4b-104">Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare.</span><span class="sxs-lookup"><span data-stu-id="abe4b-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="abe4b-105">Detta koncept kallas ansvarsfördelning.</span><span class="sxs-lookup"><span data-stu-id="abe4b-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="abe4b-106">Du kan till exempel välja att inte samma person både ska bekräfta inleveransen av varor och bearbeta betalningar till leverantören.</span><span class="sxs-lookup"><span data-stu-id="abe4b-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="abe4b-107">Ansvarsfördelning minskar risken för bedrägeri och hjälper även till att identifiera fel eller oriktigheter.</span><span class="sxs-lookup"><span data-stu-id="abe4b-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="abe4b-108">Du kan också använda ansvarsfördelning för att framtvinga interna kontrollpolicyer.</span><span class="sxs-lookup"><span data-stu-id="abe4b-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="abe4b-109">Slutför följande procedur för att skapa en regel.</span><span class="sxs-lookup"><span data-stu-id="abe4b-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="abe4b-110">Du måste vara systemadministratör för att slutföra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="abe4b-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="abe4b-111">Det demonstrationsdataföretag som används för att skapa den här proceduren är DAT.</span><span class="sxs-lookup"><span data-stu-id="abe4b-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="abe4b-112">Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Ansvarsfördelning > Ansvarsfördelningsregler**.</span><span class="sxs-lookup"><span data-stu-id="abe4b-112">Go to **Navigation pane > Modules > System administration > Security > Segregation of duties > Segregation of duties rules**.</span></span>
2. <span data-ttu-id="abe4b-113">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="abe4b-113">Click **New**.</span></span>
3. <span data-ttu-id="abe4b-114">I fältet **Namn** skriver du ett värde.</span><span class="sxs-lookup"><span data-stu-id="abe4b-114">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="abe4b-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Första programbehörighet**.</span><span class="sxs-lookup"><span data-stu-id="abe4b-115">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="abe4b-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="abe4b-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="abe4b-117">Välj det första programbehörigheten som kontrolleras av regeln.</span><span class="sxs-lookup"><span data-stu-id="abe4b-117">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="abe4b-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Andra programbehörighet**.</span><span class="sxs-lookup"><span data-stu-id="abe4b-118">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="abe4b-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="abe4b-119">In the list, find and select the desired record.</span></span> <span data-ttu-id="abe4b-120">Välj den andra programbehörigheten som kontrolleras av regeln.</span><span class="sxs-lookup"><span data-stu-id="abe4b-120">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="abe4b-121">Markera ett alternativ i fältet **Allvarlighetsgrad**.</span><span class="sxs-lookup"><span data-stu-id="abe4b-121">In the **Severity** field, select an option.</span></span> <span data-ttu-id="abe4b-122">Markera allvarlighetsgraden för risken som uppstår när samma användare eller roll utför båda programbehörigheterna.</span><span class="sxs-lookup"><span data-stu-id="abe4b-122">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="abe4b-123">Ange ett värde i fältet **Säkerhetsrisk**.</span><span class="sxs-lookup"><span data-stu-id="abe4b-123">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="abe4b-124">Ange en beskrivning av säkerhetsrisken.</span><span class="sxs-lookup"><span data-stu-id="abe4b-124">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="abe4b-125">Ange ett värde i fältet **Säkerhetshöjning**.</span><span class="sxs-lookup"><span data-stu-id="abe4b-125">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="abe4b-126">Ange en beskrivning av de åtgärder som du vidtar för att minska säkerhetrisken.</span><span class="sxs-lookup"><span data-stu-id="abe4b-126">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="abe4b-127">Du kan till exempel minska risken genom att utöva mer detaljerad granskning av processen, genom att utöva en månadsvis chefsgranskning eller genom att dela resurser med andra avdelningar.</span><span class="sxs-lookup"><span data-stu-id="abe4b-127">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="abe4b-128">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="abe4b-128">Click **Save**.</span></span>

