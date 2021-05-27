---
title: Konfigurera utökad inloggning för MPOS och molnkassor
description: Detta avsnitt täcker dina alternativ för att ställa in utökad inloggning för molnbaserad kassa och Retail Modern POS (MPOS).
author: rubencdelgado
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f9d8889581e2e11fa5261805c866a6014df57611
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027586"
---
# <a name="set-up-extended-logon-functionality-for-mpos-and-cloud-pos"></a><span data-ttu-id="9712d-103">Ställa in utökad inloggningsfunktion för MPOS och molnbaserad kassa</span><span class="sxs-lookup"><span data-stu-id="9712d-103">Set up extended logon functionality for MPOS and Cloud POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9712d-104">Detta avsnitt täcker dina alternativ för att ställa in utökad inloggning för molnbaserad kassa och Retail Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="9712d-104">This topic covers your options for setting up extended logon for Cloud POS and Retail Modern POS (MPOS).</span></span>

## <a name="setting-up-extended-logon"></a><span data-ttu-id="9712d-105">Ställa in utökade inloggning</span><span class="sxs-lookup"><span data-stu-id="9712d-105">Setting up extended logon</span></span>

<span data-ttu-id="9712d-106">Du hittar inställningarna för streckkod masker på **Butik och handel** &gt; **kanalinställning** &gt; **kassainställning** &gt; **kassaprofiler** &gt; **funktionsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="9712d-106">You can find the setup for bar code masks at **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profiles** &gt; **Functionality profiles**.</span></span> <span data-ttu-id="9712d-107">**Funktionerna** snabbfliken innehåller följande alternativ som är relaterade till utökad inloggning.</span><span class="sxs-lookup"><span data-stu-id="9712d-107">The **Functions** FastTab includes the following options that are related to extended logon.</span></span>

### <a name="staff-bar-code-logon"></a><span data-ttu-id="9712d-108">Streckkodsinloggning för personal</span><span class="sxs-lookup"><span data-stu-id="9712d-108">Staff bar code logon</span></span>

<span data-ttu-id="9712d-109">När **personalen bar kod inloggning** är aktiverad, arbetstagare som har en utökad inloggning tilldelas deras försäljningsställe (POS) inloggningsuppgifter kan logga in med hjälp av en streckkod.</span><span class="sxs-lookup"><span data-stu-id="9712d-109">When the **Staff bar code logon** option is enabled, workers who have an extended logon assigned to their point of sale (POS) credentials can log on by using a bar code.</span></span>

### <a name="staff-bar-code-logon-requires-password"></a><span data-ttu-id="9712d-110">Streckkodsinloggning för personal kräver lösenord</span><span class="sxs-lookup"><span data-stu-id="9712d-110">Staff bar code logon requires password</span></span>

<span data-ttu-id="9712d-111">När **personalen bar kod inloggning kräver lösenord** alternativ är aktiverat personal bar kod inloggning väljer endast de arbetstagare som har tilldelats utökade inloggning att presenteras.</span><span class="sxs-lookup"><span data-stu-id="9712d-111">When the **Staff bar code logon requires password** option is enabled, the staff bar code logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="9712d-112">Arbetstagare måste ange sitt lösenord när det här alternativet är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="9712d-112">Workers must still enter their password when this option is enabled.</span></span>

### <a name="staff-card-logon"></a><span data-ttu-id="9712d-113">Personalkortsinloggning</span><span class="sxs-lookup"><span data-stu-id="9712d-113">Staff card logon</span></span>

<span data-ttu-id="9712d-114">När **personalen kort inloggning** är aktiverad, arbetstagare som har en utökad inloggning tilldelas sina POS inloggningsuppgifter kan logga in med en magnetremsa.</span><span class="sxs-lookup"><span data-stu-id="9712d-114">When the **Staff card logon** option is enabled, workers who have an extended logon assigned to their POS credentials can log on by using a magnetic stripe.</span></span>

### <a name="staff-card-logon-requires-password"></a><span data-ttu-id="9712d-115">Personalkortsinloggning kräver lösenord</span><span class="sxs-lookup"><span data-stu-id="9712d-115">Staff card logon requires password</span></span>

<span data-ttu-id="9712d-116">När **personalen kort inloggning kräver lösenord** alternativ är aktiverat personal kort inloggning väljer endast de arbetstagare som har tilldelats utökade inloggning att presenteras.</span><span class="sxs-lookup"><span data-stu-id="9712d-116">When the **Staff card logon requires password** option is enabled, the staff card logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="9712d-117">Arbetstagare måste ange sitt lösenord när det här alternativet är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="9712d-117">Workers must still enter their password when this option is enabled.</span></span>

## <a name="assigning-an-extended-logon"></a><span data-ttu-id="9712d-118">Tilldela en utökad inloggning</span><span class="sxs-lookup"><span data-stu-id="9712d-118">Assigning an extended logon</span></span>

<span data-ttu-id="9712d-119">Som standard är endast chefer kan tilldela utökade inloggning till arbetstagarna.</span><span class="sxs-lookup"><span data-stu-id="9712d-119">By default, only managers can assign extended logon to workers.</span></span> <span data-ttu-id="9712d-120">Tilldela utökad inloggning genom att navigera till **Utökad inloggning** i POS.</span><span class="sxs-lookup"><span data-stu-id="9712d-120">To assign extended logon, go to **Extended log on** in POS.</span></span> <span data-ttu-id="9712d-121">Sök sedan efter en anställd genom att ange den anställdes operatörs-ID i sökfältet.</span><span class="sxs-lookup"><span data-stu-id="9712d-121">Then search for a worker by entering the worker's operator ID in the search field.</span></span> <span data-ttu-id="9712d-122">Välj anställd och klicka sedan på **Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="9712d-122">Select the worker, and then click **Assign**.</span></span> <span data-ttu-id="9712d-123">På nästa sida, nallar eller skanna utökade inloggning tilldelas arbetaren.</span><span class="sxs-lookup"><span data-stu-id="9712d-123">On the next page, swipe or scan the extended logon to assign to the worker.</span></span> <span data-ttu-id="9712d-124">Om nallar eller skanna finnas framgångsrikt lydde, **OK-** knappen blir tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9712d-124">If the swipe or scan is successfully read, the **OK** button becomes available.</span></span> <span data-ttu-id="9712d-125">Klicka på **OK för** att spara det utökade inloggning för arbetstagaren.</span><span class="sxs-lookup"><span data-stu-id="9712d-125">Click **OK** to save the extended logon for that worker.</span></span>

## <a name="deleting-an-extended-logon"></a><span data-ttu-id="9712d-126">Ta bort en utökad inloggning</span><span class="sxs-lookup"><span data-stu-id="9712d-126">Deleting an extended logon</span></span>

<span data-ttu-id="9712d-127">Ta bort den utökade inloggning som är tilldelad till en arbetstagare, sökningen för arbetstagaren med **utökad logga på** .</span><span class="sxs-lookup"><span data-stu-id="9712d-127">To delete the extended logon that is assigned to a worker, search for the worker by using the **Extended log on** operation.</span></span> <span data-ttu-id="9712d-128">Välj anställd och klicka sedan på **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="9712d-128">Select the worker, and then click **Unassign**.</span></span> <span data-ttu-id="9712d-129">Alla utökade inloggningsbehörighet som associeras med att arbetstagaren är borttagen.</span><span class="sxs-lookup"><span data-stu-id="9712d-129">All extended logon credentials that are associated with that worker are removed.</span></span>

## <a name="extending-extended-logon"></a><span data-ttu-id="9712d-130">Utvidga utökade inloggning</span><span class="sxs-lookup"><span data-stu-id="9712d-130">Extending extended logon</span></span>

<span data-ttu-id="9712d-131">Inloggning tjänsten kan utökas för att stödja ytterligare utökade inloggning enheter, t.ex. palm scannrar.</span><span class="sxs-lookup"><span data-stu-id="9712d-131">The logon service can be extended to support additional extended logon devices, such as palm scanners.</span></span> <span data-ttu-id="9712d-132">För mer information, se POS extensibility dokumentation.</span><span class="sxs-lookup"><span data-stu-id="9712d-132">For more information, see the POS extensibility documentation.</span></span>

## <a name="using-extended-logon"></a><span data-ttu-id="9712d-133">Med hjälp av utökade inloggning</span><span class="sxs-lookup"><span data-stu-id="9712d-133">Using extended logon</span></span>

<span data-ttu-id="9712d-134">När utökad inloggning är konfigurerad, och arbetstagaren har tilldelats en streckkod eller magnetremsa, behöver arbetstagaren bara dra eller skanna sitt kort medan POS-inloggningssidan visas.</span><span class="sxs-lookup"><span data-stu-id="9712d-134">When extended logon is configured, and a worker has been assigned a bar code or magnetic stripe, the worker just has to swipe or scan the worker's card while the POS logon page is displayed.</span></span> <span data-ttu-id="9712d-135">Om ett lösenord krävs före inloggning kan fortsätta, uppmanas arbetstagaren att ange sitt lösenord.</span><span class="sxs-lookup"><span data-stu-id="9712d-135">If a password is also required before logon can proceed, the worker is prompted to enter the worker's password.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]