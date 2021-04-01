---
title: Konfigurera utgiftstyper
description: Det här avsnittet beskriver hur du konfigurerar utgiftstyper i Leasing av tillgångar.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1538826f140393eec59be9ff4df5242d5ced9d8f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249759"
---
# <a name="set-up-expense-types"></a><span data-ttu-id="24182-103">Konfigurera utgiftstyper</span><span class="sxs-lookup"><span data-stu-id="24182-103">Set up expense types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24182-104">Det här avsnittet beskriver hur du konfigurerar utgiftstyper i Leasing av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="24182-104">This topic explains how to set up expense types in Asset leasing.</span></span> <span data-ttu-id="24182-105">Kostnader som inte representeras av betalningsplanen kallas för *utgiftskostnader*.</span><span class="sxs-lookup"><span data-stu-id="24182-105">Costs that aren't represented by the payment schedule are known as *expense costs*.</span></span> <span data-ttu-id="24182-106">Exempel på dessa kostnader är fastighetsskatter, allmänna underhållskostnader och försäkringskostnader.</span><span class="sxs-lookup"><span data-stu-id="24182-106">Examples of these costs include property taxes, common area maintenance costs, and insurance expenses.</span></span>

## <a name="add-an-administrative-expense-type"></a><span data-ttu-id="24182-107">Lägga till en administrativ utgiftstyp</span><span class="sxs-lookup"><span data-stu-id="24182-107">Add an administrative expense type</span></span>

1. <span data-ttu-id="24182-108">Gå till **Leasing av tillgångar \> Konfigurera \> Utgiftstyper**.</span><span class="sxs-lookup"><span data-stu-id="24182-108">Go to **Asset leasing \> Setup \> Expense types**.</span></span>
2. <span data-ttu-id="24182-109">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="24182-109">Select **New**.</span></span>
3. <span data-ttu-id="24182-110">Ange den nya utgiftstypen och en beskrivning i lämpliga fält.</span><span class="sxs-lookup"><span data-stu-id="24182-110">In the appropriate fields, enter the new expense type and a description.</span></span>

## <a name="assign-accounts-to-administrative-costs"></a><span data-ttu-id="24182-111">Tilldela konton till administrationskostnader</span><span class="sxs-lookup"><span data-stu-id="24182-111">Assign accounts to administrative costs</span></span>

<span data-ttu-id="24182-112">Därefter ska du koppla konton till utgiftstyperna.</span><span class="sxs-lookup"><span data-stu-id="24182-112">Next, you should associate accounts with the expense types.</span></span> <span data-ttu-id="24182-113">De här kontona kommer att debiteras när poster för utgiftsplaner bokförs.</span><span class="sxs-lookup"><span data-stu-id="24182-113">These accounts will be debited when expense schedule entries are posted.</span></span> <span data-ttu-id="24182-114">Motkontot anges på raderna för **betalningsplanen för verkställighetskostnad** för varje leasing.</span><span class="sxs-lookup"><span data-stu-id="24182-114">The offset account is specified on the **Executory costs payment schedule** lines on each lease.</span></span>

1. <span data-ttu-id="24182-115">Gå till **Leasing av tillgångar \> Konfigurera \> Parametrar för tillgångsleasing**.</span><span class="sxs-lookup"><span data-stu-id="24182-115">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="24182-116">Välj utgiftstypen på fliken **Konton**, på snabbfliken **Verkställighetskostnader**, i fältet **Utgiftstyp** .</span><span class="sxs-lookup"><span data-stu-id="24182-116">On the **Accounts** tab, on the **Executory costs** FastTab, in the **Expense type** field, select the expense type.</span></span>
3. <span data-ttu-id="24182-117">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="24182-117">Select **Add**.</span></span>
4. <span data-ttu-id="24182-118">I **Boktyp** väljer du den boktyp som ska länkas till administrationskostnaderna.</span><span class="sxs-lookup"><span data-stu-id="24182-118">In the **Book type** field, select the book type to link to the administrative costs.</span></span>

    > [!NOTE]
    > <span data-ttu-id="24182-119">Flera boktyper kan kopplas till samma utgiftskonto.</span><span class="sxs-lookup"><span data-stu-id="24182-119">Multiple book types can be linked to the same expense account.</span></span>

5. <span data-ttu-id="24182-120">I fältet **Kontokod** anger du vilka leasingar som boken ska gälla för:</span><span class="sxs-lookup"><span data-stu-id="24182-120">In the **Account code** field, specify which leases the book should be applied to:</span></span>

    - <span data-ttu-id="24182-121">**Alla** – Boken gäller för alla leasingar.</span><span class="sxs-lookup"><span data-stu-id="24182-121">**All** – Apply the book to all leases.</span></span>
    - <span data-ttu-id="24182-122">**Grupp** – Boken gäller för en specifik grupp med leasingar.</span><span class="sxs-lookup"><span data-stu-id="24182-122">**Group** – Apply the book to a specific group of leases.</span></span>
    - <span data-ttu-id="24182-123">**Tabell** – Boken gäller för specifika leasingar.</span><span class="sxs-lookup"><span data-stu-id="24182-123">**Table** – Apply the book to specific leases.</span></span>

6. <span data-ttu-id="24182-124">Om du har valt **Grupp** eller **Tabell** i fältet **Kontokod** väljer du ett kontonummer eller gruppnummer i fältet **Konto/gruppnummer**.</span><span class="sxs-lookup"><span data-stu-id="24182-124">If you selected **Group** or **Table** in the **Account code** field, select an account number or group number in the **Account/Group number** field.</span></span>
7. <span data-ttu-id="24182-125">Välj huvudkonto för finansiell leasing och huvudkonto för operationell leasing i lämpliga fält.</span><span class="sxs-lookup"><span data-stu-id="24182-125">In the appropriate fields, select the finance lease main account and the operating lease main account.</span></span>

<span data-ttu-id="24182-126">När du har utfört de här stegen kan du lägga till utgifter via raderna för **betalningsplanen för verkställighetskostnad** på sidan **Leasingdetaljer** för en vald leasing.</span><span class="sxs-lookup"><span data-stu-id="24182-126">When you've completed these steps, you can add expenses through the **Executory costs payment schedule** lines on the **Lease details** page of a selected lease.</span></span> <span data-ttu-id="24182-127">Du kan också lägga till utgifter när du skapar en ny leasing.</span><span class="sxs-lookup"><span data-stu-id="24182-127">Alternatively, you can add expenses when you create a new lease.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]