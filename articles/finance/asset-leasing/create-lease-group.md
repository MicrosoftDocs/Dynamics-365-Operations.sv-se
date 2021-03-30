---
title: Skapa en leasinggrupp
description: Det här ämnet innehåller information om hur du konfigurerar leasinggrupper. Leasinggrupper krävs för att skapa nya leasingar.
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
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e8ad226e87776615d9c19a239e0fb90b648d9c49
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210467"
---
# <a name="create-a-lease-group"></a><span data-ttu-id="efa52-104">Skapa en leasinggrupp</span><span class="sxs-lookup"><span data-stu-id="efa52-104">Create a lease group</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efa52-105">Det här ämnet innehåller information om hur du konfigurerar leasinggrupper.</span><span class="sxs-lookup"><span data-stu-id="efa52-105">This topic explains how to set up lease groups.</span></span> <span data-ttu-id="efa52-106">Leasinggrupper krävs för att skapa nya leasingar.</span><span class="sxs-lookup"><span data-stu-id="efa52-106">Lease groups are required to create new leases.</span></span> <span data-ttu-id="efa52-107">Leasingböcker associeras med varje leasinggrupp.</span><span class="sxs-lookup"><span data-stu-id="efa52-107">Lease books are associated with each lease group.</span></span> <span data-ttu-id="efa52-108">Leasingböcker avgör vilka standardböcker som måste skapas för varje leasing.</span><span class="sxs-lookup"><span data-stu-id="efa52-108">Lease books determine the default books that must be created for each lease.</span></span> <span data-ttu-id="efa52-109">Du kan tilldela specifika konton till en leasinggrupp på sidan **Parametrar för bokföring av leasing**.</span><span class="sxs-lookup"><span data-stu-id="efa52-109">You can assign specific accounts to a lease group on the **Lease posting parameters** page.</span></span>

## <a name="create-a-lease-book-and-add-a-lease-group"></a><span data-ttu-id="efa52-110">Skapa en leasingbok och lägga till en leasinggrupp</span><span class="sxs-lookup"><span data-stu-id="efa52-110">Create a lease book and add a lease group</span></span>

1. <span data-ttu-id="efa52-111">Gå till **Leasing av tillgångar \> Konfigurera \> Leasinggrupper**.</span><span class="sxs-lookup"><span data-stu-id="efa52-111">Go to **Asset leasing \> Setup \> Lease groups**.</span></span>
2. <span data-ttu-id="efa52-112">I åtgärdsfönstret, välj **Ny** för att lägga till en ny leasinggrupp.</span><span class="sxs-lookup"><span data-stu-id="efa52-112">On the Action Pane, select **New** to add a lease group.</span></span> <span data-ttu-id="efa52-113">En rad läggs till i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="efa52-113">A line is added to the grid.</span></span>
3. <span data-ttu-id="efa52-114">Ange ett värde i fältet **Leasingrupp** på den nya raden.</span><span class="sxs-lookup"><span data-stu-id="efa52-114">On the new line, in the **Lease group** field, enter a value.</span></span>
4. <span data-ttu-id="efa52-115">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="efa52-115">In the **Description** field, enter a value.</span></span>

<span data-ttu-id="efa52-116">Den information som du just har lagt till läggs till i fältet **Leasinggrupp** på sidan **Lägg till leasing**.</span><span class="sxs-lookup"><span data-stu-id="efa52-116">The information that you just entered is added to the **Lease group** field on the **Add lease** page.</span></span>

## <a name="associate-a-book-with-a-lease-group"></a><span data-ttu-id="efa52-117">Associera en bok med en leasinggrupp</span><span class="sxs-lookup"><span data-stu-id="efa52-117">Associate a book with a lease group</span></span>

<span data-ttu-id="efa52-118">När du har skapat leasinggrupper kan du tilldela böcker till varje grupp.</span><span class="sxs-lookup"><span data-stu-id="efa52-118">After you create lease groups, you can assign books to each group.</span></span> <span data-ttu-id="efa52-119">När du skapar en leasing och tilldelar den till en leasinggrupp, skapar systemet en uppsättning planer för varje bok som associeras med denna leasinggrupp.</span><span class="sxs-lookup"><span data-stu-id="efa52-119">When you create a lease and assign it to a lease group, the system creates a set of schedules for each book that is associated with that lease group.</span></span>

> [!NOTE]
> <span data-ttu-id="efa52-120">Du måste konfigurera böcker innan de kan tilldelas till en leasinggrupp.</span><span class="sxs-lookup"><span data-stu-id="efa52-120">Books must be set up before they can be assigned to a lease group.</span></span>

1. <span data-ttu-id="efa52-121">Gå till **Leasing av tillgångar \> Konfigurera \> Leasinggrupp**.</span><span class="sxs-lookup"><span data-stu-id="efa52-121">Go to **Asset leasing \> Setup \> Lease group**.</span></span>
2. <span data-ttu-id="efa52-122">Välj en leasinggrupp och välj sedan **Böcker**.</span><span class="sxs-lookup"><span data-stu-id="efa52-122">Select a lease group, and then select **Books**.</span></span>
3. <span data-ttu-id="efa52-123">Välj **Ny** och i fältet **Boktyp** väljer du sedan den bok som ska tilldelas leasinggruppen.</span><span class="sxs-lookup"><span data-stu-id="efa52-123">Select **New**, and then, in the **Book type** field, select the book to assign to the lease group.</span></span> <span data-ttu-id="efa52-124">Du kan tilldela flera böcker till en leasinggrupp om en leasing måste redovisas på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="efa52-124">You can assign multiple books to a lease group if a lease must be accounted for in different ways.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]