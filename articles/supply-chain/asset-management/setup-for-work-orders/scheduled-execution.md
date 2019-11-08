---
title: Schemalagt utförande
description: I det här avsnittet beskrivs schemalagt utförande i Tillgångshantering.
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
ms.openlocfilehash: 89e13179e17b7cf075d631bc65d82da5f24da624
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569856"
---
# <a name="scheduled-execution"></a><span data-ttu-id="fab71-103">Schemalagt utförande</span><span class="sxs-lookup"><span data-stu-id="fab71-103">Scheduled execution</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="fab71-104">Du kan använda servicenivåer för arbetsorder när du vill ange schemalagt utförande.</span><span class="sxs-lookup"><span data-stu-id="fab71-104">You can use work order service levels to set up scheduled execution.</span></span> <span data-ttu-id="fab71-105">(Mer information om servicenivåer för arbetsorder finns i [Servicenivå och beskrivning](service-level-and-description.md).) Schemalagt utförande ger flexibilitet vid arbetsplanering av underhållsarbetare, eftersom du kan ange mer detaljerade eller mindre detaljerade krav för intervallet som en arbetsorder ska slutföras under.</span><span class="sxs-lookup"><span data-stu-id="fab71-105">(For more information about work order service levels, see [Service level and description](service-level-and-description.md).) Scheduled execution provides flexibility in work planning for maintenance workers, because you can set up more detailed or less detailed requirements for the interval that a work order should be completed during.</span></span> <span data-ttu-id="fab71-106">En underhållsarbetare som utför jobbet snabbare än väntat i en produktionsanläggning kan till exempel gå vidare till ett annat närliggande jobb som har planerats för den aktuella veckan men inte nödvändigt vis för den aktuella dagen.</span><span class="sxs-lookup"><span data-stu-id="fab71-106">For example, a maintenance worker who completes a job faster than expected in a production facility might be able to move on to another nearby job that was planned for the current week but not necessarily for the current day.</span></span> <span data-ttu-id="fab71-107">På så sätt kan du optimera planeringen av arbetare och jobbslutförande.</span><span class="sxs-lookup"><span data-stu-id="fab71-107">This approach allows for optimization of worker planning and job completion.</span></span>

<span data-ttu-id="fab71-108">Den schemalagda utförandeinställningen, som är relaterad till arbetsorder, kan vara allmän eller specifik.</span><span class="sxs-lookup"><span data-stu-id="fab71-108">Scheduled execution setup, which is related to work orders, can be generic or specific.</span></span> <span data-ttu-id="fab71-109">Du kan ställa in allmänna rader som inte är begränsade till specifika arbetsordertyper, tillgångstyper och så vidare.</span><span class="sxs-lookup"><span data-stu-id="fab71-109">You can set up generic lines that aren't limited to specific work order types, asset types, and so on.</span></span> <span data-ttu-id="fab71-110">Du kan också skapa planerade körningsrader som gäller för en specifik arbetsordertyp, tillgångstyp, underhållsjobbtyp och så vidare.</span><span class="sxs-lookup"><span data-stu-id="fab71-110">Alternatively, you can create scheduled execution lines that apply to a specific work order type, asset type, maintenance job type, and so on.</span></span>

1. <span data-ttu-id="fab71-111">Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Schemalagt utförande**.</span><span class="sxs-lookup"><span data-stu-id="fab71-111">Select **Asset management** \> **Setup** \> **Work orders** \> **Scheduled execution**.</span></span>
2. <span data-ttu-id="fab71-112">Klicka på **Ny** för att skapa en schemalagd utföranderad.</span><span class="sxs-lookup"><span data-stu-id="fab71-112">Select **New** to create a scheduled execution line.</span></span>
3. <span data-ttu-id="fab71-113">I fälten **Funktionsplats**, **Arbetsordertyp**, **Tillgångstyp**, **Tillverkare**, **Modell**, **Kategori av underhållsjobbtyp**, **Underhållsjobbtyp**, **Variant av underhållsjobbtyp** och **Yrkesgren** väljer du värden efter behov.</span><span class="sxs-lookup"><span data-stu-id="fab71-113">In the **Functional location**, **Work order type**, **Asset type**, **Manufacturer**, **Model**, **Maintenance job type category**, **Maintenance job type**, **Maintenance job type variant**, and **Trade** fields, select values as you require.</span></span>
4. <span data-ttu-id="fab71-114">Välj en servicenivå för arbetsorder i fältet **Servicenivå**.</span><span class="sxs-lookup"><span data-stu-id="fab71-114">In the **Service level** field, select a work order service level.</span></span> <span data-ttu-id="fab71-115">Om du lämnar det här fältet tomt skapar du den mest allmänna typen av schemalagd utföranderad.</span><span class="sxs-lookup"><span data-stu-id="fab71-115">If you leave this field blank, you make the most generic type of scheduled execution line.</span></span> <span data-ttu-id="fab71-116">Ett exempel på en allmän rad finns i den första posten i illustrationen nedan.</span><span class="sxs-lookup"><span data-stu-id="fab71-116">For an example of a generic line, see the first record in the illustration that follows.</span></span> <span data-ttu-id="fab71-117">Den raden aktiverar alla arbetsorder som inte har någon servicenivå för arbetsorder som ska schemaläggas för ett visst datum och en viss tid.</span><span class="sxs-lookup"><span data-stu-id="fab71-117">That line enables all work orders that have no work order service level to be scheduled for a specific date and time.</span></span>
5. <span data-ttu-id="fab71-118">Välj tidsintervall i fältet **Schemalagt utförande**.</span><span class="sxs-lookup"><span data-stu-id="fab71-118">In the **Scheduled execution** field, select the time interval.</span></span>
6. <span data-ttu-id="fab71-119">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fab71-119">Select **Save**.</span></span>

![Schemalagt utförande](media/20-setup-for-work-orders.png)
