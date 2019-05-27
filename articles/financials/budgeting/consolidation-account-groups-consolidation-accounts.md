---
title: Skapa konsolideringskontogrupper och ytterligare konsolideringskonton
description: Det här avsnittet innehåller information om konsolideringskontogrupper och ytterligare konsolideringskonton, och förklarar hur de används i Microsoft Dynamics 365 for Finance and Operations.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f1c463ee54512b07f5e45c4df995aefed6110cb0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570959"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a><span data-ttu-id="fe9bb-103">Skapa konsolideringskontogrupper och ytterligare konsolideringskonton</span><span class="sxs-lookup"><span data-stu-id="fe9bb-103">Consolidation account groups and additional consolidation accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fe9bb-104">Det här avsnittet innehåller information om konsolideringskontogrupper och ytterligare konsolideringskonton, och förklarar hur de används i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-104">This topic provides information about consolidation account groups and additional consolidation accounts, and explains how they are used in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<a name="consolidation-account-groups"></a><span data-ttu-id="fe9bb-105">Konsolideringskontogrupper</span><span class="sxs-lookup"><span data-stu-id="fe9bb-105">Consolidation account groups</span></span>
----------------------------

<span data-ttu-id="fe9bb-106">Med konsolideringskontogrupper kan du skapa grupper av konton som du vill använda för att konsolidera data.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-106">Consolidation account groups let you create groups of the accounts that you want to use to consolidate data.</span></span> <span data-ttu-id="fe9bb-107">Oftast representerar konsolideringskontogrupp en myndighetsbeviljad kontoplan eller mappar konton till en grupp som definieras av företagets huvudkontor.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-107">Most often, a consolidation account group represents a government-mandated chart of accounts or maps accounts to a group that is defined by the company's headquarters.</span></span> <span data-ttu-id="fe9bb-108">Du hittar konsolideringskontogrupper i avsnittet **Inställningar** i modulen **Konsolideringar**.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-108">You can find consolidation account groups in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="fe9bb-109">När du lägger till en ny grupp kan du ange en unik identifierare för kontogruppen och ett namn.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-109">When you add a new group, you enter a unique identifier for the account group and a name.</span></span>

## <a name="additional-consolidation-accounts"></a><span data-ttu-id="fe9bb-110">Ytterligare konsolideringskonton</span><span class="sxs-lookup"><span data-stu-id="fe9bb-110">Additional consolidation accounts</span></span>
<span data-ttu-id="fe9bb-111">Med ytterligare konsolideringskonton kan du tilldela en konsolideringskontogrupp ett konto från en befintlig kontoplan.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-111">Additional consolidation accounts let you assign an account from an existing chart of accounts to a consolidation account group.</span></span> <span data-ttu-id="fe9bb-112">Du kan sedan ange ett värde för konsolideringskonto och ett namn.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-112">You can then specify a consolidation account value and name.</span></span> 

<span data-ttu-id="fe9bb-113">Du hittar ytterligare konsolideringskonton i avsnittet **Inställningar** i modulen **Konsolideringar**.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-113">You can find additional consolidation accounts in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="fe9bb-114">När du skapar ett nytt konsolideringskonto måste du ange följande information:</span><span class="sxs-lookup"><span data-stu-id="fe9bb-114">When you create a new consolidation account, you must specify the following information:</span></span>

-   <span data-ttu-id="fe9bb-115">**Huvudkontot** – Detta fält är en sökning som visar alla huvudkonton som baseras på den kontoplan som du valde på sidan</span><span class="sxs-lookup"><span data-stu-id="fe9bb-115">**Main account** – This field is a lookup that shows all the main accounts that are based on the chart of accounts that you selected on the page.</span></span> <span data-ttu-id="fe9bb-116">När du väljer ett konto anges namnet automatiskt i fältet **Huvudkontonamn**.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-116">When you select an account, the name is automatically entered in the **Main account name** field.</span></span>
-   <span data-ttu-id="fe9bb-117">**Konsolideringskontogrupp** – Använd detta fält för att ange den grupp som kontot ska tilldelas till.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-117">**Consolidation account group** – Use this field to specify the group to assign the account to.</span></span> <span data-ttu-id="fe9bb-118">Om du konsoliderar på två olika sätt måste du lägga till samma konto i alla fyra konsolideringskontogrupper.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-118">If you consolidate in two different ways, you must add the same account to all four consolidation account groups.</span></span>
-   <span data-ttu-id="fe9bb-119">**Konsolideringskonto** – Ange värdet för konsolideringskontot.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-119">**Consolidation account** – Enter the value of the consolidation account.</span></span> <span data-ttu-id="fe9bb-120">Det här värdet måste inte vara ett konto från en kontoplan.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-120">This value doesn't have to be an account from a chart of accounts.</span></span> <span data-ttu-id="fe9bb-121">Det kan vara ett valfritt värde som du behöver.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-121">It can be any value that you require.</span></span>
-   <span data-ttu-id="fe9bb-122">**Namn på konsolideringskonto** – Ange namnet på det konto som du vill ska visas på förfrågningar och rapporter.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-122">**Consolidation account name** – Enter the name of account as you want it to appear on inquiries and reports.</span></span>
-   <span data-ttu-id="fe9bb-123">**SAT-nivå** – Detta fält används för att rapportera kontoutdrag till de mexikanska skattemyndigheterna.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-123">**SAT level** – This field is used to report account statements to the Mexican tax authorities.</span></span> 

<span data-ttu-id="fe9bb-124">När du har skapat dina konsolideringskontogrupper och ytterligare konsolideringskonton kan du välja gruppen i processen för onlinekonsolidering.</span><span class="sxs-lookup"><span data-stu-id="fe9bb-124">When you've finished creating your consolidation account groups and additional consolidation accounts, you can select the group in the Consolidate online process.</span></span>


<span data-ttu-id="fe9bb-125">För mer information, se [Skapa konsolideringsgrupper och ytterligare konsolideringskonton](../general-ledger/tasks/create-consolidation-groups.md)</span><span class="sxs-lookup"><span data-stu-id="fe9bb-125">For more information, see [Create consolidation groups and additional consolidation accounts](../general-ledger/tasks/create-consolidation-groups.md).</span></span> 



