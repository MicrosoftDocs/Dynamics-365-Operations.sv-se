---
title: Journalföra bokförda poster i redovisningsjournal
description: Den här proceduren visar dig hur du journalför bokförda journalposter.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b50809cf9eb59475856f91d9f1ddfe28ecfd8de6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547920"
---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="e1248-103">Journalföra bokförda poster i redovisningsjournal</span><span class="sxs-lookup"><span data-stu-id="e1248-103">Journalize posted journal entries</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e1248-104">Den här proceduren visar dig hur du journalför bokförda journalposter.</span><span class="sxs-lookup"><span data-stu-id="e1248-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="e1248-105">I proceduren används demonstrationsföretag USMF.</span><span class="sxs-lookup"><span data-stu-id="e1248-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="e1248-106">Validera inställningarna för journalföring under General ledger > Ledger setup > General ledger parameters.</span><span class="sxs-lookup"><span data-stu-id="e1248-106">Validate the settings for journalizing under General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="e1248-107">Fältet Extended ledger journal kan anges som Yes eller No.</span><span class="sxs-lookup"><span data-stu-id="e1248-107">The Extended ledger journal field can be set to Yes or No.</span></span> <span data-ttu-id="e1248-108">Om "Yes" kommer rapportutdatan att skilja sig åt.</span><span class="sxs-lookup"><span data-stu-id="e1248-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="e1248-109">Välj om perioden kan stängas även om journalföringsprocessen inte har körts.</span><span class="sxs-lookup"><span data-stu-id="e1248-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span>
    * <span data-ttu-id="e1248-110">Om detta alternativ är inställt på "Yes" kan inte perioden stängas förrän journalföringsprocessen har slutförts för den perioden.</span><span class="sxs-lookup"><span data-stu-id="e1248-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="e1248-111">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e1248-111">Close the page.</span></span>
5. <span data-ttu-id="e1248-112">Gå till Redovisning > Periodiska uppgifter > Journalföring.</span><span class="sxs-lookup"><span data-stu-id="e1248-112">Go to General ledger > Periodic tasks > Journalizing.</span></span>
6. <span data-ttu-id="e1248-113">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="e1248-113">Click Filter.</span></span>
7. <span data-ttu-id="e1248-114">Markera raden med filtervillkoret som du vill definiera.</span><span class="sxs-lookup"><span data-stu-id="e1248-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="e1248-115">Ange eller välj filterkriterier i fältet Criteria.</span><span class="sxs-lookup"><span data-stu-id="e1248-115">In the Criteria field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="e1248-116">Klicka på OK för att stänga filtersidan.</span><span class="sxs-lookup"><span data-stu-id="e1248-116">Click OK to close the filter page.</span></span>
10. <span data-ttu-id="e1248-117">Starta journalföringsprocessen genom att klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e1248-117">Click OK to start the journalizing process.</span></span>
    * <span data-ttu-id="e1248-118">En rapport skapas när processen är slutförd.</span><span class="sxs-lookup"><span data-stu-id="e1248-118">A report will be generated after the process is complete.</span></span>  

