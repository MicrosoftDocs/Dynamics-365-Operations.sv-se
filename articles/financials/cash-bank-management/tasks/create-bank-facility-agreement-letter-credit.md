---
title: Skapa ett kreditlimitavtal för en remburs
description: Denna uppgift är en genomgång av hur du skapar ett bankkreditlimitavtal om du vill bearbeta en remburs.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankDocumentFacilityAgreement, BankAccountTableLookUp, BankDocumentFacilityAgreementExtension, DefaultDashboard
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 18395f300965df7e024f0eec2b53fa4e8ad2cc3e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566212"
---
# <a name="create-a-bank-facility-agreement-for-a-letter-of-credit"></a><span data-ttu-id="4ceee-103">Skapa ett kreditlimitavtal för en remburs</span><span class="sxs-lookup"><span data-stu-id="4ceee-103">Create a bank facility agreement for a letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4ceee-104">Denna uppgift är en genomgång av hur du skapar ett bankkreditlimitavtal om du vill bearbeta en remburs.</span><span class="sxs-lookup"><span data-stu-id="4ceee-104">This task walks through the creating a Bank facility agreement to process a Letter of credit.</span></span> <span data-ttu-id="4ceee-105">Du kanske vill ställa in bankkreditlimiter och bokföringsprofiler före detta.</span><span class="sxs-lookup"><span data-stu-id="4ceee-105">You will want to set up bank facilities and posting profiles before this task.</span></span>  <span data-ttu-id="4ceee-106">I den här uppgiften används demonstrationsföretaget "USMF".</span><span class="sxs-lookup"><span data-stu-id="4ceee-106">This task uses the demo company 'USMF'.</span></span>  


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="4ceee-107">Skapa bankkreditlimitavtalet</span><span class="sxs-lookup"><span data-stu-id="4ceee-107">Create Bank facility agreement</span></span>
1. <span data-ttu-id="4ceee-108">Gå till Kassa- och bankhantering > Remburser > Kreditlimitavtal för bank.</span><span class="sxs-lookup"><span data-stu-id="4ceee-108">Go to Cash and bank management > Letters of credit > Bank facility agreements.</span></span>
2. <span data-ttu-id="4ceee-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4ceee-109">Click New.</span></span>
3. <span data-ttu-id="4ceee-110">Ange avtalsnumret enligt avtalet med banken i fältet Avtalsnummer.</span><span class="sxs-lookup"><span data-stu-id="4ceee-110">In the Agreement number field, enter the agreement number according to the agreement with the bank.</span></span>
4. <span data-ttu-id="4ceee-111">Ange bankkontonumret i den utfärdande banken i fältet Bankkonto.</span><span class="sxs-lookup"><span data-stu-id="4ceee-111">In the Bank account field, enter the account number at the issuing bank.</span></span>
5. <span data-ttu-id="4ceee-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4ceee-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="4ceee-113">Ange datum och tid i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="4ceee-113">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="4ceee-114">I fältet Slutdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="4ceee-114">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="4ceee-115">Utöka eller komprimera avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="4ceee-115">Expand or collapse the General section.</span></span>
9. <span data-ttu-id="4ceee-116">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="4ceee-116">Click Add line.</span></span>
10. <span data-ttu-id="4ceee-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i Kreditlimittyp.</span><span class="sxs-lookup"><span data-stu-id="4ceee-117">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="4ceee-118">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="4ceee-118">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="4ceee-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4ceee-119">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="4ceee-120">I fältet Gräns, ange kreditlimitbeloppet som har förhandlats med banken.</span><span class="sxs-lookup"><span data-stu-id="4ceee-120">In the Limit field, enter the facility amount that was negotiated with the bank.</span></span>
14. <span data-ttu-id="4ceee-121">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="4ceee-121">Click Save.</span></span>
15. <span data-ttu-id="4ceee-122">Klicka på Utöka om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="4ceee-122">Click Extend to open the drop dialog.</span></span>
16. <span data-ttu-id="4ceee-123">Skriv ett värde i fältet Nytt avtal.</span><span class="sxs-lookup"><span data-stu-id="4ceee-123">In the New agreement number field, type a value.</span></span>
17. <span data-ttu-id="4ceee-124">I fältet Slutdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="4ceee-124">In the End date field, enter a date and time.</span></span>
18. <span data-ttu-id="4ceee-125">Klicka på Utöka.</span><span class="sxs-lookup"><span data-stu-id="4ceee-125">Click Extend.</span></span>
19. <span data-ttu-id="4ceee-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4ceee-126">Close the page.</span></span>

