---
title: Skapa underhållsbudgetar
description: I det här avsnittet beskrivs hur du skapar en underhållsbudget i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d2c748fd230796643f1ed6279743da532e7cb320
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874818"
---
# <a name="create-maintenance-budgets"></a><span data-ttu-id="e2b7e-103">Skapa underhållsbudgetar</span><span class="sxs-lookup"><span data-stu-id="e2b7e-103">Create maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]



<span data-ttu-id="e2b7e-104">Underhållsbudgetar används för att ge en översikt över de förväntade kostnaderna för förebyggande underhåll.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-104">Maintenance budgets are used to provide an overview of expected costs for preventive maintenance.</span></span> <span data-ttu-id="e2b7e-105">Budgetrader beräknas utifrån de rader i underhållsschemat som har ett förväntat startdatum under budgetperioden.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-105">Budget lines are calculated based on maintenance schedule lines that have an expected start date during the budget period.</span></span>

<span data-ttu-id="e2b7e-106">Underhållsbudgetar baseras på kostnadstyperna som används i Tillgångshantering: **förebyggande**, **korrigerande** och **investering**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-106">Maintenance budgets are based on the cost types that are used in Asset Management: **Preventive**, **Corrective**, and **Investment**.</span></span> <span data-ttu-id="e2b7e-107">Budgetkostnader för investeringsunderhåll inkluderas för aktiva tillgångar med ett ersättningsdatum under budgetperioden och ett relaterat ersättningsvärde.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-107">Budget costs for investment maintenance are included for active assets that have a replacement date during the budget period and a related replacement value.</span></span> <span data-ttu-id="e2b7e-108">Budgetkostnader för korrigerande underhåll inkluderas om ett tidigare korrigeringsdatum ingår i budgetberäkningen.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-108">Budget costs for corrective maintenance are included if a past corrective date is included in the budget calculation.</span></span> <span data-ttu-id="e2b7e-109">I det fallet beräknas de eventuella korrigeringskostnader från en tidigare period för samma framtida period som du beräknar underhållsbudgeten för.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-109">In that case, corrective costs from an earlier period are calculated for the same future period that you calculate the maintenance budget for.</span></span>

## <a name="create-a-maintenance-budget"></a><span data-ttu-id="e2b7e-110">Skapa en underhållsbudget</span><span class="sxs-lookup"><span data-stu-id="e2b7e-110">Create a maintenance budget</span></span>

1. <span data-ttu-id="e2b7e-111">Välj **Tillgångshantering** \> **Förfrågningar** \> **Underhållsbudget** \> **Budget**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-111">Select **Asset management** \> **Inquiries** \> **Maintenance budget** \> **Budget**.</span></span>
2. <span data-ttu-id="e2b7e-112">Välj **Skapa budget**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-112">Select **Create budget**.</span></span>
3. <span data-ttu-id="e2b7e-113">I fältet **Underhållsbudget** anger du ett budget-ID.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-113">In the **Maintenance budget** field, enter a budget ID.</span></span>
4. <span data-ttu-id="e2b7e-114">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-114">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="e2b7e-115">Ange start- och slutdatum för budgetperioden på snabbfliken **Period** i fälten **Från datum** och **Till datum**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-115">On the **Period** FastTab, in the **From date** and **To date** fields, enter the start and end dates of the budget period.</span></span>
5. <span data-ttu-id="e2b7e-116">Om du vill inkludera korrigerande budgetkostnader som beräknas på grundval av faktiska kostnader från en tidigare period anger du i fältet **Korrigerande från datum** startdatumet för den period som dessa kostnader ska inkluderas från.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-116">To include corrective budget costs that are calculated on the basis of actual costs from a previous period, in the **Corrective from date** field, enter the start date of the period that those costs should be included from.</span></span>
6. <span data-ttu-id="e2b7e-117">Beroende på vilken detaljnivå som krävs i budgeten ställer du in de relevanta alternativen på de fem snabbflikarna **Gruppera efter**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-117">Depending on the level of detail that is required in the budget, set the relevant options on the five **Group by** FastTabs.</span></span>
7. <span data-ttu-id="e2b7e-118">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-118">Select **OK**.</span></span>
8. <span data-ttu-id="e2b7e-119">Välj **Budgetrader** för att öppna sidan **Budgetrader för underhåll** där du kan visa alla budgetrader som har skapats för perioden.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-119">Select **Budget lines** to open **Maintenance budget lines** page, where you can view all the budget lines that have been created for the period.</span></span>
9. <span data-ttu-id="e2b7e-120">Om du vill godkänna budgeten väljer du den på sidan **Underhållsbudgetar** och väljer sedan **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-120">To approve the budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="e2b7e-121">Välj sedan **OK** i dialogrutan **Godkänn budget**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-121">Then, in the **Approve budget** dialog box, select **OK**.</span></span> <span data-ttu-id="e2b7e-122">Ditt namn anges i fältet **Godkänd av** på sidan **Underhållsbudgetar**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-122">Your name is entered in the **Approved by** field on the **Maintenance budgets** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2b7e-123">När du har godkänt en underhållsbudget kan du inte räkna om eller justera de relaterade raderna på sidan **Budgetrader för underhåll** om du inte först tar bort godkännandet.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-123">After you've approved a maintenance budget, you can't recalculate or adjust the related lines on the **Maintenance budget lines** page unless you first remove the approval.</span></span> <span data-ttu-id="e2b7e-124">Om du vill ta bort godkännandet av en underhållsbudget väljer du den på sidan **Underhållsbudgetar** och väljer sedan **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-124">To remove the approval of a maintenance budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="e2b7e-125">Välj sedan **OK** i dialogrutan **Godkänn budget**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-125">Then, in the **Approve budget** dialog box, select **OK**.</span></span>

![Figur 1](media/01-maintenance-budgets.png)

<span data-ttu-id="e2b7e-127">Du kan också skapa en ny underhållsbudget genom att kopiera en befintlig budget.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-127">You can also create a new maintenance budget by copying an existing budget.</span></span> <span data-ttu-id="e2b7e-128">På sidan **Underhållsbudgetar** väljer du först budgeten som ska kopieras och sedan **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-128">On the **Maintenance budgets** page, select the budget to copy, and then select **Copy**.</span></span> <span data-ttu-id="e2b7e-129">Den här metoden är användbar om du till exempel har skapat en budget för en månad och vill kopiera den till andra månader.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-129">This approach is useful if, for example, you've created a budget for one month and want to copy it to other months.</span></span>

> [!NOTE]
> <span data-ttu-id="e2b7e-130">Underhållsbudgeten beräknar bara budgetkostnader baserat på underhållsschemarader.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-130">The maintenance budget calculates only budget costs based on maintenance schedule lines.</span></span> <span data-ttu-id="e2b7e-131">Om du vill beräkna faktiska kostnader för samma period kan du göra denna beräkning på sidan **Kostnadskontroll för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="e2b7e-131">To calculate actual costs for the same period, you can do that calculation on the **Asset cost control** page.</span></span> 
