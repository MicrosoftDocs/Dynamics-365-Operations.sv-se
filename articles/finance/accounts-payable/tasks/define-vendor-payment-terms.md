---
title: Definiera villkor för leverantörsbetalning
description: Det här avsnittet innehåller information om hur du ställer in betalningsvillkor för leverantörsfakturor.
author: abruer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6432d04aa821e76d67e2c430e514f4b9056d8228
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180029"
---
# <a name="define-vendor-payment-terms"></a><span data-ttu-id="b5d62-103">Definiera villkor för leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="b5d62-103">Define vendor payment terms</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b5d62-104">Det här avsnittet innehåller information om hur du ställer in betalningsvillkor för leverantörsfakturor.</span><span class="sxs-lookup"><span data-stu-id="b5d62-104">This topic explains how to set up payment terms for vendor invoices.</span></span> <span data-ttu-id="b5d62-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="b5d62-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="b5d62-106">Go to **Navigeringsfönster > Moduler > Leverantörsreskontra > Betalningsinställning > Betalningsvillkor**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-106">Go to **Navigation pane > Modules > Accounts payable > Payment setup > Terms of payment**.</span></span>
2. <span data-ttu-id="b5d62-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-107">Select **New**.</span></span> <span data-ttu-id="b5d62-108">Betalningsvillkoren används för att definiera hur förfallodatumen ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="b5d62-108">The Terms of payment page is used to define how the due date will be calculated.</span></span> <span data-ttu-id="b5d62-109">Detta används inte för att definiera hur kassarabattdatum beräknas.</span><span class="sxs-lookup"><span data-stu-id="b5d62-109">It is not used to define how the cash discount date will be calculated.</span></span>  
3. <span data-ttu-id="b5d62-110">Skriv ett värde i fältet **Betalningsvillkor**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-110">In the **Terms of payment** field, type a value.</span></span>
4. <span data-ttu-id="b5d62-111">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="b5d62-111">In the **Description field**, type a value.</span></span>
5. <span data-ttu-id="b5d62-112">Välj ett tal i fältet **Dagar**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-112">In the **Days** field, enter a number.</span></span> <span data-ttu-id="b5d62-113">Numret som anges här, ska användas för att lägger till förfallodatumet eller till slutet av perioden som identifieras i betalningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="b5d62-113">The number entered here will be used to add to the due date, or to the end of the period identified in the Payment method.</span></span> <span data-ttu-id="b5d62-114">Om du till exempel väljer **Netto**, kommer antalet läggas till förfallodatumet.</span><span class="sxs-lookup"><span data-stu-id="b5d62-114">For example, if you select **Net**, the number will be added to the due date.</span></span> <span data-ttu-id="b5d62-115">Om du väljer aktuell månad, kommer det att lägga till numret till sista dagen av den **aktuella månaden** för att beräkna förfallodatumet.</span><span class="sxs-lookup"><span data-stu-id="b5d62-115">If you select **Current month**, it will add the number to the last day of the current month to calculate the due date.</span></span>  
6. <span data-ttu-id="b5d62-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-116">Select **Save**.</span></span>
7. <span data-ttu-id="b5d62-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b5d62-117">Close the page.</span></span>
8. <span data-ttu-id="b5d62-118">Gå till **Leverantörsreskontra > Betalningsinställning > Kassarabatter**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-118">Go to **Accounts payable > Payment setup > Cash discounts**.</span></span>
9. <span data-ttu-id="b5d62-119">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-119">Select **New**.</span></span>
10. <span data-ttu-id="b5d62-120">Ange ett ID i fältet **Kassarabatt**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-120">In the **Cash discount** field, enter an ID.</span></span>
11. <span data-ttu-id="b5d62-121">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="b5d62-121">In the **Description** field, type a value.</span></span>
12. <span data-ttu-id="b5d62-122">Om leverantören ger en nivårabatt, välj nästa kassarabatt, efter att den aktuella har upphörts.</span><span class="sxs-lookup"><span data-stu-id="b5d62-122">If the vendor offers a tiered discount, select the next cash discount after the current one is expired.</span></span>
13. <span data-ttu-id="b5d62-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b5d62-123">Close the page.</span></span>
14. <span data-ttu-id="b5d62-124">Välj ett tal i fältet **Dagar**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-124">In the **Days** field, enter a number.</span></span> <span data-ttu-id="b5d62-125">Den kvantitet som anges i fältet **dagar** som ska användas för att beräkna, kassarabattdatumet baserat på vilken väljare valdes i fältet **netto/aktuella**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-125">The quantity entered in the **Days** field will be used to calculate the Cash discount date, based on what option was selected in the **Net/Current** field.</span></span> <span data-ttu-id="b5d62-126">Om **Netto** markeras, ska kvantitet läggas till fakturadatumet för att bestämma kassarabattdatumet.</span><span class="sxs-lookup"><span data-stu-id="b5d62-126">If **Net** was selected, the quantity will be added to the invoice date to determine the cash discount date.</span></span> <span data-ttu-id="b5d62-127">Om **Aktuell månad** markeras, ska kvantitet läggas till i slutet av valutamånaden för att bestämma kassarabattdatumet.</span><span class="sxs-lookup"><span data-stu-id="b5d62-127">If **Current month** was selected, the quantity will be added to the end of the currency month to determine the cash discount date.</span></span>  
15. <span data-ttu-id="b5d62-128">Ange kassarabatten som en procent i fältet **Rabatt**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-128">Enter the percentage of the cash discount in the **Discount** field.</span></span> 
16. <span data-ttu-id="b5d62-129">Ange huvudkontot som kassarabatten ska bokföras på för kundfakturor och ange sedan huvudkontot som kassarabatten ska bokföras på för leverantörsfakturor.</span><span class="sxs-lookup"><span data-stu-id="b5d62-129">Enter the main account to which the cash discount will be posted for customer invoices, then enter the main account to which the cash discount will be posted for vendor invoices.</span></span> <span data-ttu-id="b5d62-130">Om **Rabattmotkonton** anges till **Använd huvudkonto för leverantörsrabatter** ska huvudkontot användas.</span><span class="sxs-lookup"><span data-stu-id="b5d62-130">If **Discount offset accounts** is set to **Use main account for vendor discount**, then the Main account will be used.</span></span> <span data-ttu-id="b5d62-131">Om du väljer **Konton på fakturarader** bokförs kassarabatten till samma tillgångs/utgifthuvudkonton på raderna för fakturan.</span><span class="sxs-lookup"><span data-stu-id="b5d62-131">If the option is set to **Accounts on the invoice lines**, the cash discount will be posted to the asset/expense accounts on the invoice's lines.</span></span>  
17. <span data-ttu-id="b5d62-132">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-132">Select **Save**.</span></span>

