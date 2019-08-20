---
title: Ställ in momsgrupper och artikelmomsgrupper
description: Registreringen av den här uppgiften omfattar inställningarna för moms och artikelmomsgrupper.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c58755be2c927de1d308576a2bff2ed3340db34
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846281"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="e4959-103">Ställ in momsgrupper och artikelmomsgrupper</span><span class="sxs-lookup"><span data-stu-id="e4959-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e4959-104">Registreringen av den här uppgiften omfattar inställningarna för moms och artikelmomsgrupper.</span><span class="sxs-lookup"><span data-stu-id="e4959-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="e4959-105">Momsgrupper är grupper av momskoder som är kopplade till kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="e4959-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="e4959-106">De kopplas även till redovisningskonton för transaktioner som inte har bokförts för en viss leverantör eller kund.</span><span class="sxs-lookup"><span data-stu-id="e4959-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="e4959-107">Artikelmomsgrupper är grupper av momskoder som är kopplade till resurser som produkter.</span><span class="sxs-lookup"><span data-stu-id="e4959-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="e4959-108">De momsgrupper som gäller för en viss transaktion fastställs av momskoderna som är inkluderade i både momsgruppen och artikelmomsgruppen för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e4959-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="e4959-109">Moms kan bara beräknas om en momsgrupp och en artikelmomsgrupp väljs för samtliga transaktioner där moms måste beräknas eller registreras.</span><span class="sxs-lookup"><span data-stu-id="e4959-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="e4959-110">Gå till Skatt > Indirekta skatter > Moms > Momsgrupper.</span><span class="sxs-lookup"><span data-stu-id="e4959-110">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="e4959-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e4959-111">Click New.</span></span>
3. <span data-ttu-id="e4959-112">I fältet Momsgrupp, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="e4959-112">In the Sales tax group field, type a value.</span></span>
4. <span data-ttu-id="e4959-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="e4959-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e4959-114">Växla utökningen av avsnittet Inställning.</span><span class="sxs-lookup"><span data-stu-id="e4959-114">Toggle the expansion of the Setup section.</span></span>
6. <span data-ttu-id="e4959-115">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e4959-115">Click Add.</span></span>
7. <span data-ttu-id="e4959-116">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e4959-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="e4959-117">I fältet Momskod, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="e4959-117">In the Sales tax code field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="e4959-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="e4959-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="e4959-119">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e4959-119">Click Save.</span></span>
11. <span data-ttu-id="e4959-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e4959-120">Close the page.</span></span>
12. <span data-ttu-id="e4959-121">Gå till Skatt > Indirekta skatter > Moms > Artikelmomsgrupper.</span><span class="sxs-lookup"><span data-stu-id="e4959-121">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
13. <span data-ttu-id="e4959-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e4959-122">Click New.</span></span>
14. <span data-ttu-id="e4959-123">I fältet Artikelmomsgrupp, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="e4959-123">In the Item sales tax group field, type a value.</span></span>
15. <span data-ttu-id="e4959-124">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="e4959-124">In the Description field, type a value.</span></span>
16. <span data-ttu-id="e4959-125">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e4959-125">Click Add.</span></span>
17. <span data-ttu-id="e4959-126">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e4959-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="e4959-127">I fältet Momskod, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="e4959-127">In the Sales tax code field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="e4959-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="e4959-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="e4959-129">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e4959-129">Click Save.</span></span>

