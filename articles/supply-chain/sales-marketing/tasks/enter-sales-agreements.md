---
title: Ange försäljningsavtal
description: I det här avsnittet visas hur du skapar en försäljningsavtal där en av dina kunder åtar sig att köpa en produkt för ett avtalat belopp över tid i utbyte mot speciella rabatter.
author: omulvad
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 723621f61a237d4b390271e65bce204c44ee4fc2
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204342"
---
# <a name="enter-sales-agreements"></a><span data-ttu-id="3540c-103">Ange försäljningsavtal</span><span class="sxs-lookup"><span data-stu-id="3540c-103">Enter sales agreements</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3540c-104">I det här avsnittet visas hur du skapar en försäljningsavtal där en av dina kunder åtar sig att köpa en produkt för ett avtalat belopp över tid i utbyte mot speciella rabatter.</span><span class="sxs-lookup"><span data-stu-id="3540c-104">This topic explains how to create a sales agreement that commits one of your customers to buy a product for an agreed amount over time in exchange for special discounts.</span></span> <span data-ttu-id="3540c-105">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="3540c-105">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-sales-agreement-header"></a><span data-ttu-id="3540c-106">Ställ in försäljningsavtalshuvudet</span><span class="sxs-lookup"><span data-stu-id="3540c-106">Set up sales agreement header</span></span>
1. <span data-ttu-id="3540c-107">I navigeringsfönstret, gå till **Moduler > Försäljning och marknadsföring > Försäljningsavtal > Försäljningsavtal**.</span><span class="sxs-lookup"><span data-stu-id="3540c-107">In the navigation pane, go to **Modules > Sales and marketing > Sales agreements > Sales agreements**.</span></span>
2. <span data-ttu-id="3540c-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="3540c-108">Select **New**.</span></span>
3. <span data-ttu-id="3540c-109">I fältet **Kundkonto** välj önskad post i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="3540c-109">In the **Customer account** field, select the desired record from the drop-down menu.</span></span>
4. <span data-ttu-id="3540c-110">I fältet **Klassificering av försäljningsavtal** välj önskad post i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="3540c-110">In the **Sales agreement classification** field, select the desired record from the drop-down menu.</span></span>
5. <span data-ttu-id="3540c-111">Expandera den **allmänna** delen.</span><span class="sxs-lookup"><span data-stu-id="3540c-111">Expand the **General** section.</span></span>
6. <span data-ttu-id="3540c-112">I fältet **Standardutfästelse**, välj **Utfästelse för produktvärde**.</span><span class="sxs-lookup"><span data-stu-id="3540c-112">In the **Default commitment** field, select **Product value commitment**.</span></span> <span data-ttu-id="3540c-113">En utfästelsetyp är ett obligatoriskt kriterium som du måste tilldela till avtalet för att definiera hur avtalskontraktet uppfylls.</span><span class="sxs-lookup"><span data-stu-id="3540c-113">A commitment type is a mandatory criterion that you must assign to the agreement to define how the agreement contract will be fulfilled.</span></span> <span data-ttu-id="3540c-114">De fyra fördefinierade typer kan du ställa in kundens åtagande mål, uttryckt som en kvantitet eller ett värde.</span><span class="sxs-lookup"><span data-stu-id="3540c-114">The four predefined types let you set up the customer's commitment target, expressed as a quantity or a value.</span></span> <span data-ttu-id="3540c-115">Kvantitetutfästelsetypen kan endast tillämpas på en specifik produkt, men de hierarkibaserade typerna kan användas för både försäljning och icke-specifika produkter.</span><span class="sxs-lookup"><span data-stu-id="3540c-115">The quantity commitment type can only be applied to a specific product, but the value-based types are applicable to sales of both specific and non-specific products.</span></span>  
7. <span data-ttu-id="3540c-116">I fältet **Utgångsdatum**, ange datumet till ett framtida datum när du vill att avtalet ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="3540c-116">In the **Expiration date** field, set the date to a future date when you want the agreement to expire.</span></span>
8. <span data-ttu-id="3540c-117">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3540c-117">Select **OK**.</span></span>

## <a name="set-up-product-value-commitment-lines"></a><span data-ttu-id="3540c-118">Ställ in utfästelserader för produktvärde</span><span class="sxs-lookup"><span data-stu-id="3540c-118">Set up product value commitment lines</span></span>
1. <span data-ttu-id="3540c-119">Välj **Markera rad**.</span><span class="sxs-lookup"><span data-stu-id="3540c-119">Select **Add line**.</span></span>
2. <span data-ttu-id="3540c-120">I fältet **Artikelnummer** välj önskad post i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="3540c-120">In the **Item number** field, select the desired record from the drop-down menu.</span></span> <span data-ttu-id="3540c-121">Typen av åtagande som du har valt för avtalet påverkar den typ av information som du kan ange för avtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="3540c-121">The type of commitment that you have chosen for the agreement affects the kind of information you can enter for the agreement lines.</span></span> <span data-ttu-id="3540c-122">För exempelvis en värde-baserade avtal måste du ange det totala nettobeloppet (i den överenskomna valuta) för vilken kunden förbinder sig att köpa varor från dig.</span><span class="sxs-lookup"><span data-stu-id="3540c-122">For example, for a value-based agreement you must specify the total net amount (in the agreed currency) for which the customer commits to buys goods from you.</span></span> <span data-ttu-id="3540c-123">I det här exemplet är fälten **Kvantitet** och **Enhet** på raden inte tillgängliga eftersom du skapar ett avtal för att kunden om att köpa för ett visst värde av en produkt.</span><span class="sxs-lookup"><span data-stu-id="3540c-123">In this example the **Quantity** and **Unit** fields on the line are unavailable because you're creating an agreement for the customer to buy a specific value of a product.</span></span>   
3. <span data-ttu-id="3540c-124">I fältet **Nettobelopp**, ange penningbeloppet som kunden har åtagit sig att köpa för.</span><span class="sxs-lookup"><span data-stu-id="3540c-124">In the **Net amount** field, enter the monetary amount that the customer has committed to buying.</span></span>
4. <span data-ttu-id="3540c-125">I fältet **Rabatt i procent**, ange en procentsats som ska användas för kundens försäljningsorderrader, som är kopplade till detta avtal.</span><span class="sxs-lookup"><span data-stu-id="3540c-125">In the **Discount percent** field, enter a percentage value that will apply to the customer's sales order lines that are linked to this agreement.</span></span>
5. <span data-ttu-id="3540c-126">Visa avsnittet **Raddetaljer**.</span><span class="sxs-lookup"><span data-stu-id="3540c-126">Expand the **Line details** section.</span></span>
6. <span data-ttu-id="3540c-127">Välj **Ja** i fältet **Max framtvingas**.</span><span class="sxs-lookup"><span data-stu-id="3540c-127">Select **Yes** in the **Max is enforced** field.</span></span>
    - <span data-ttu-id="3540c-128">Om du väljer **Max framtvingas** innebär att det totala beloppet för alla försäljningsorderrader som använder utfästelsens särskilda priser, rabatter och/eller betalningsvillkor inte får överstiga beloppet som anges på utfästelsen.</span><span class="sxs-lookup"><span data-stu-id="3540c-128">Selecting **Max is enforced** means that the total amount of all the sales order lines that use the commitment's special prices, discounts and/or payment terms must not exceed the amount specified on the commitment.</span></span>  
    - <span data-ttu-id="3540c-129">Minsta och högsta frisläppningsbeloppen anger ett värdeintervall som måste säljas på varje försäljningsorder som använder det valda avtalet.</span><span class="sxs-lookup"><span data-stu-id="3540c-129">The minimum and maximum release amounts specify a range of values that must be sold on each sales order that uses the selected agreement.</span></span>   
7. <span data-ttu-id="3540c-130">Expandera avsnittet **Försäljningsavtalshuvud**.</span><span class="sxs-lookup"><span data-stu-id="3540c-130">Expand the **Sales agreement header** section.</span></span> <span data-ttu-id="3540c-131">Om inte status för avtalet är **Giltig**, beställningar kan inte associeras med avtalet och kan därför inte bidra till uppfyllandet av avtalet.</span><span class="sxs-lookup"><span data-stu-id="3540c-131">Unless the status of the agreement is set to **Effective**, sales orders cannot be associated with the agreement and can therefore not contribute to the fulfilment of that agreement.</span></span> <span data-ttu-id="3540c-132">Du kan ändra status manuellt i detta skede.</span><span class="sxs-lookup"><span data-stu-id="3540c-132">You can change the status manually at this stage.</span></span> <span data-ttu-id="3540c-133">Emellertid ändras statusen normalt när du bekräftar avtalet för kunden.</span><span class="sxs-lookup"><span data-stu-id="3540c-133">However, the status would normally be changed when you confirm the agreement for the customer.</span></span>  
8. <span data-ttu-id="3540c-134">Välj **Försäljningsavtal** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3540c-134">On the Action Pane, select **Sales agreement**.</span></span>
9. <span data-ttu-id="3540c-135">VäljSelect **Bekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="3540c-135">Select **Confirmation**.</span></span> <span data-ttu-id="3540c-136">Se till att alternativet **Markera avtal som giltigt** har inställningen **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3540c-136">Make sure that the **Mark agreement as effective** option is set to **Yes**.</span></span>  
10. <span data-ttu-id="3540c-137">Välj **Ja** i fältet **Skriv ut rapport**.</span><span class="sxs-lookup"><span data-stu-id="3540c-137">Select **Yes** in the **Print report** field.</span></span>
11. <span data-ttu-id="3540c-138">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3540c-138">Select **OK**.</span></span>
12. <span data-ttu-id="3540c-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3540c-139">Close the page.</span></span> <span data-ttu-id="3540c-140">Avtalet är nu giltigt.</span><span class="sxs-lookup"><span data-stu-id="3540c-140">The agreement is now effective.</span></span> <span data-ttu-id="3540c-141">Du kan börja att länka kundens order till avtalet för att motboka mot det utfästa målet.</span><span class="sxs-lookup"><span data-stu-id="3540c-141">You can start linking the customer's orders to the agreement to offset against the committed target.</span></span>  

