---
title: Ställ in momskvittningsperioder
description: Det här avsnittet innehåller information om hur du ställer in momskvittningsperioder i Dynamics 365 for Finance and Operations.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6fb8488335579ed463d4db235b991e97c39d6f4d
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867425"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="df216-103">Ställ in momskvittningsperioder</span><span class="sxs-lookup"><span data-stu-id="df216-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="df216-104">Det här avsnittet innehåller information om hur du ställer in momskvittningsperioder i Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="df216-104">This topic explains how to set up sales tax settlement periods in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="df216-105">Momskvittningsperioder innehåller information om periodintervall för rapportering och betalning av moms.</span><span class="sxs-lookup"><span data-stu-id="df216-105">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="df216-106">En kvittningprocess kan köras för en kvittningsperiod för ett specifikt datumintervall.</span><span class="sxs-lookup"><span data-stu-id="df216-106">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="df216-107">Alla momskoder som är kopplade till kvittningsperioden kvittas.</span><span class="sxs-lookup"><span data-stu-id="df216-107">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="df216-108">Beroende på inställningen av den relaterade skattemyndigheten bokförs skatteskulden antingen till en leverantör eller ett redovisningskonto.</span><span class="sxs-lookup"><span data-stu-id="df216-108">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>

<span data-ttu-id="df216-109">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="df216-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="df216-110">I navigeringsfönstret går du till **Moduler > Skatt > Indirekta skatter > Moms > Momskvittningsperioder.**</span><span class="sxs-lookup"><span data-stu-id="df216-110">In the navigation pane, go to **Modules > Tax > Indirect taxes > Sales tax > Sales tax settlement periods**.</span></span>
2. <span data-ttu-id="df216-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="df216-111">Select **New**.</span></span>
3. <span data-ttu-id="df216-112">Ange ett värde i fältet **Kvittningsperiod**.</span><span class="sxs-lookup"><span data-stu-id="df216-112">In the **Settlement period** field, type a value.</span></span>
4. <span data-ttu-id="df216-113">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="df216-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="df216-114">I fältet **Myndighet** väljer du skattekontoret som tar emot rapporter och betalningar som skapats för kvittningsperioden.</span><span class="sxs-lookup"><span data-stu-id="df216-114">In the **Authority** field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="df216-115">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="df216-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="df216-116">I fältet **Betalningsvillkor** väljer du önskad post i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="df216-116">In the **Terms of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="df216-117">Den relaterade skattemyndigheten kan ställas in som en leverantör och vid momskvittningen skapas en öppen leverantörsfaktura.</span><span class="sxs-lookup"><span data-stu-id="df216-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="df216-118">Förfallodatumet för den öppna leverantörsfakturan definieras i betalningsvillkoren.</span><span class="sxs-lookup"><span data-stu-id="df216-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
8. <span data-ttu-id="df216-119">Välj en typ av kvittningsperiodintervall.</span><span class="sxs-lookup"><span data-stu-id="df216-119">Select a type for the settlement period intervals.</span></span>
9. <span data-ttu-id="df216-120">Ange antalet periodintervallenheter per period.</span><span class="sxs-lookup"><span data-stu-id="df216-120">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="df216-121">Till exempel har ett kvartal 3 månader.</span><span class="sxs-lookup"><span data-stu-id="df216-121">For example, a quarter has 3 months.</span></span>
10. <span data-ttu-id="df216-122">Markera eller avmarkera kryssrutan **Använd batchbearbetning för momskvittning**.</span><span class="sxs-lookup"><span data-stu-id="df216-122">Select or clear the **Use batch processing for sales tax settlement** check box.</span></span> <span data-ttu-id="df216-123">Kvittningprocessen för kvittningsperioden kan behandlas som batchjobb i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="df216-123">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="df216-124">Detta rekommenderas för ett stort antal momstransaktioner inom ett periodintervall.</span><span class="sxs-lookup"><span data-stu-id="df216-124">This is recommended for a large number of tax transactions within a period interval.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="df216-125">För närvarande stöds detta inte i Österrike, Belgien, Spanien, Italien, Japan och Nederländerna.</span><span class="sxs-lookup"><span data-stu-id="df216-125">Currently this is not supported in Austria, Belgium, Spain, Italy, Japan, and the Netherlands.</span></span>
11. <span data-ttu-id="df216-126">Markera eller avmarkera kryssrutan **Förhindra att motbokade momstransaktioner genereras**.</span><span class="sxs-lookup"><span data-stu-id="df216-126">Select or clear the **Prevent generating offset tax transactions** check box.</span></span> <span data-ttu-id="df216-127">Som standard genereras motbokade momstransaktioner under kvittningsprocessen som kan orsaka prestandaproblem om det finns ett stort antal momstransaktioner inom ett periodintervall.</span><span class="sxs-lookup"><span data-stu-id="df216-127">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="df216-128">Markera denna kryssruta för att förhindra att motbokade momstransaktioner genereras.</span><span class="sxs-lookup"><span data-stu-id="df216-128">Select this check box to prevent generating offset tax transactions.</span></span>
12. <span data-ttu-id="df216-129">Expandera fliken **Periodintervall**.</span><span class="sxs-lookup"><span data-stu-id="df216-129">Expand the **Period intervals** tab.</span></span>
13. <span data-ttu-id="df216-130">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="df216-130">Select **Add**.</span></span>
14. <span data-ttu-id="df216-131">Ange ett datum i fältet **Från-datum** på den nya raden.</span><span class="sxs-lookup"><span data-stu-id="df216-131">In the **From date** field in the new row, enter a date.</span></span>
15. <span data-ttu-id="df216-132">I fältet **Till-datum**, anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="df216-132">In the **To date** field, enter a date.</span></span>
16. <span data-ttu-id="df216-133">Välj **Nytt periodintervall**.</span><span class="sxs-lookup"><span data-stu-id="df216-133">Select **New period interval**.</span></span> <span data-ttu-id="df216-134">När det första periodintervallet har angetts, kan nya perioder skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="df216-134">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="df216-135">Du kan komma tillbaka och lägga till nya periodintervall som krävs.</span><span class="sxs-lookup"><span data-stu-id="df216-135">You can come back and add new period intervals as required.</span></span>  
17. <span data-ttu-id="df216-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="df216-136">Close the page.</span></span>

