---
title: Typer av arbetsorder
description: Det här avsnittet innehåller förklaringar av arbetsordertyper i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b8e43908e3f13c9e4fd6fab6f1e17a171866b803
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/25/2020
ms.locfileid: "3888795"
---
# <a name="work-order-types"></a><span data-ttu-id="0e597-103">Typer av arbetsorder</span><span class="sxs-lookup"><span data-stu-id="0e597-103">Work order types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0e597-104">Arbetsordertyper används för att kategorisera arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="0e597-104">Work order types are used to categorize work orders.</span></span> <span data-ttu-id="0e597-105">Du kan till exempel ha arbetsorder som är relaterade till förebyggande underhåll eller korrigerande underhåll.</span><span class="sxs-lookup"><span data-stu-id="0e597-105">For example, you might have work orders that are related to preventive maintenance or corrective maintenance.</span></span>

<span data-ttu-id="0e597-106">En arbetsordertyp definierar en anknytning till en livscykelmodell för arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="0e597-106">A work order type defines an affiliation with a work order lifecycle model.</span></span> <span data-ttu-id="0e597-107">En livscykelmodell för arbetsorder anger livscykeltillstånd som kan anges för en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="0e597-107">A work order lifecycle model defines the work order lifecycle states that can be set on a work order.</span></span> <span data-ttu-id="0e597-108">(Exempel på livscykeltillstånd för arbetsorder är bland annat **Skapat**, **Pågår** och **Slutfört**.)</span><span class="sxs-lookup"><span data-stu-id="0e597-108">(Examples of work order lifecycle states include **Created**, **In Process**, and **Finished**.)</span></span>

<span data-ttu-id="0e597-109">Mer information om livscykeltillstånd för arbetsorder och projektfaser finns [Livscykeltillstånd för arbetsorder](work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="0e597-109">For more information about work order lifecycle states and project stages, see [Work order lifecycle states](work-order-lifecycle-states.md).</span></span>

1. <span data-ttu-id="0e597-110">Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Arbetsordertyper**.</span><span class="sxs-lookup"><span data-stu-id="0e597-110">Select **Asset management** \> **Setup** \> **Work orders** \> **Work order types**.</span></span>
2. <span data-ttu-id="0e597-111">Skapa en ny arbetsordertyp genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="0e597-111">Select **New** to create a work order type.</span></span>
3. <span data-ttu-id="0e597-112">I fältet **Arbetsordertyp** anger du ett ID för arbetsordertypen.</span><span class="sxs-lookup"><span data-stu-id="0e597-112">In the **Work order type** field, enter an ID for the work order type.</span></span>
4. <span data-ttu-id="0e597-113">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="0e597-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="0e597-114">Välj en livscykelmodell i fältet **Livscykelmodell för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="0e597-114">In the **Work order lifecycle model** field, select a lifecycle model.</span></span>
5. <span data-ttu-id="0e597-115">Ställ in alternativet **En underhållsarbetare** på **Ja** om alla arbetsorderjobb som är relaterade till en arbetsorder av den här typen ska planeras till samma underhållsarbetare.</span><span class="sxs-lookup"><span data-stu-id="0e597-115">Set the **One maintenance worker** option to **Yes** if all work order jobs that are related to a work order of this type should be scheduled to the same maintenance worker.</span></span>
6. <span data-ttu-id="0e597-116">I fältet **Kostnadstyp** väljer du **Korrigerande**, **Förebyggande** eller **Investering**, beroende på vad som är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="0e597-116">In the **Cost type** field, select **Corrective**, **Preventive**, or **Investment**, as appropriate.</span></span> <span data-ttu-id="0e597-117">Alla arbetsorderjob på en arbetsorder måste ha samma kostnadstyp.</span><span class="sxs-lookup"><span data-stu-id="0e597-117">All work order jobs on a work order must have the same cost type.</span></span>
7. <span data-ttu-id="0e597-118">I avsnittet **Obligatoriskt** anger du de relevanta alternativen till **Ja** för att ange vilka felrelaterade eller underhållsstopptid-relaterade uppgifter som ska läggas till i en arbetsorder av den här typen.</span><span class="sxs-lookup"><span data-stu-id="0e597-118">In the **Mandatory** section, set the relevant options to **Yes** to specify which fault-related or maintenance downtime–related information is added to a work order of this type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0e597-119">Alternativetn i avsnittet **Obligatorisk** är relaterade till alternativen på snabbfliken **Validera** på sidan **Livscykeltillstånd för arbetsorder** (**Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Livscykeltillstånd**).</span><span class="sxs-lookup"><span data-stu-id="0e597-119">The options in the **Mandatory** section are related to the options on the **Validate** FastTab of the **Work order lifecycle states** page (**Asset management** \> **Setup** \> **Work orders** \> **Lifecycle states**).</span></span>

8. <span data-ttu-id="0e597-120">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0e597-120">Select **Save**.</span></span>

![Typer av arbetsorder](media/16-setup-for-work-orders.png)
