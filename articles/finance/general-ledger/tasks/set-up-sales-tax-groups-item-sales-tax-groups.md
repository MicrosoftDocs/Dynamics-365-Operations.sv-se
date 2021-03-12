---
title: Ställ in momsgrupper och artikelmomsgrupper
description: Registreringen av den här uppgiften omfattar inställningarna för moms och artikelmomsgrupper.
author: twheeloc
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e35f98de715af95b0bec2b2ca5d7e7570aa8fdba
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994500"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="31ff2-103">Ställ in momsgrupper och artikelmomsgrupper</span><span class="sxs-lookup"><span data-stu-id="31ff2-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="31ff2-104">Registreringen av den här uppgiften omfattar inställningarna för moms och artikelmomsgrupper.</span><span class="sxs-lookup"><span data-stu-id="31ff2-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="31ff2-105">Momsgrupper är grupper av momskoder som är kopplade till kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="31ff2-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="31ff2-106">De kopplas även till redovisningskonton för transaktioner som inte har bokförts för en viss leverantör eller kund.</span><span class="sxs-lookup"><span data-stu-id="31ff2-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="31ff2-107">Artikelmomsgrupper är grupper av momskoder som är kopplade till resurser som produkter.</span><span class="sxs-lookup"><span data-stu-id="31ff2-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="31ff2-108">De momsgrupper som gäller för en viss transaktion fastställs av momskoderna som är inkluderade i både momsgruppen och artikelmomsgruppen för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="31ff2-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="31ff2-109">Moms kan bara beräknas om en momsgrupp och en artikelmomsgrupp väljs för samtliga transaktioner där moms måste beräknas eller registreras.</span><span class="sxs-lookup"><span data-stu-id="31ff2-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="31ff2-110">Gå till **Navigeringsfönster > Moduler > Moms > Indirekta skatter > Moms > Momsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="31ff2-110">Go to **Navigation pane > Modules > Tax > Indirect taxes > Sales tax > Sales tax groups**.</span></span>
2. <span data-ttu-id="31ff2-111">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="31ff2-111">Click **New**.</span></span>
3. <span data-ttu-id="31ff2-112">I fältet **Momsgrupp**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="31ff2-112">In the **Sales tax group** field, type a value.</span></span>
4. <span data-ttu-id="31ff2-113">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="31ff2-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="31ff2-114">Växla utökningen av avsnittet **Inställning**.</span><span class="sxs-lookup"><span data-stu-id="31ff2-114">Toggle the expansion of the **Setup** section.</span></span>
6. <span data-ttu-id="31ff2-115">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="31ff2-115">Click **Add**.</span></span>
7. <span data-ttu-id="31ff2-116">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="31ff2-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="31ff2-117">I fältet **Momskod**, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="31ff2-117">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="31ff2-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="31ff2-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="31ff2-119">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="31ff2-119">Click **Save**.</span></span>
11. <span data-ttu-id="31ff2-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="31ff2-120">Close the page.</span></span>
12. <span data-ttu-id="31ff2-121">Gå till **Skatt > Indirekta skatter > Moms > Artikelmomsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="31ff2-121">Go to **Tax > Indirect taxes > Sales tax > Item sales tax groups**.</span></span>
13. <span data-ttu-id="31ff2-122">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="31ff2-122">Click **New**.</span></span>
14. <span data-ttu-id="31ff2-123">I fältet **Artikelmomsgrupp**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="31ff2-123">In the **Item sales tax group** field, type a value.</span></span>
15. <span data-ttu-id="31ff2-124">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="31ff2-124">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="31ff2-125">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="31ff2-125">Click **Add**.</span></span>
17. <span data-ttu-id="31ff2-126">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="31ff2-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="31ff2-127">I fältet **Momskod**, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="31ff2-127">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="31ff2-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="31ff2-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="31ff2-129">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="31ff2-129">Click **Save**.</span></span>

