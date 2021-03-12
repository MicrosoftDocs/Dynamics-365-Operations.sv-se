---
title: Skapa månadsvisa poster i redovisningsjournal i en batch
description: I det här ämnet beskrivs hur du skapar journalposter i ett batchjobb för att öka effektiviteten när månadsutgifter för leasing registreras.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7f46f289c58c32c535dd20fb510cf2812625c49c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971338"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a><span data-ttu-id="b765f-103">Skapa månadsvisa poster i redovisningsjournal i en batch</span><span class="sxs-lookup"><span data-stu-id="b765f-103">Create monthly journal entries in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b765f-104">I det här ämnet beskrivs hur du skapar journalposter i ett batchjobb för att öka effektiviteten när månadsutgifter för leasing registreras.</span><span class="sxs-lookup"><span data-stu-id="b765f-104">This topic explains how to create journal entries in a batch to help increase efficiency when monthly lease expenses are recorded.</span></span> <span data-ttu-id="b765f-105">Batchbearbetning kan användas för att skapa journalposter från flera planer.</span><span class="sxs-lookup"><span data-stu-id="b765f-105">Batch processing can be used to create journal entries from multiple schedules.</span></span> <span data-ttu-id="b765f-106">Dessa journalposter kan vara leasingbetalningar, skuldamorteringar, amortering av ROU-tillgångar samt utgifter för verkställighetskostnader.</span><span class="sxs-lookup"><span data-stu-id="b765f-106">These journal entries can include lease payments, liability amortization, right-of-use (ROU) asset amortization, and executory cost expenses.</span></span> <span data-ttu-id="b765f-107">Du kan också använda batchbearbetning för att utföra den första redovisningen av flera leasingar samtidigt, eller för att skapa övergångsjusteringar för flera leasingar samtidigt.</span><span class="sxs-lookup"><span data-stu-id="b765f-107">You can also use batch processing to do the initial recognition of multiple leases at the same time, or to create transition adjustments for multiple leases at the same time.</span></span>

<span data-ttu-id="b765f-108">Om du vill konfigurera ett batchjobb eller bearbeta betalningsfakturor, avskrivningar eller räntor för flera leasingar går du till **Leasing av tillgångar \> Periodisk \> Batchgenerering av journal**.</span><span class="sxs-lookup"><span data-stu-id="b765f-108">To set up a batch job, or to process payment invoices, depreciation, or interest for multiple leases, go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span> <span data-ttu-id="b765f-109">I dialogrutan som visas kan du välja den plan som journalposterna ska skapas från.</span><span class="sxs-lookup"><span data-stu-id="b765f-109">In the dialog box that appears, you can select the schedule that the journal entries should be created from.</span></span> <span data-ttu-id="b765f-110">Du kan även ange om batchprocessen ska köras för specifika entiteter, leasinggrupper eller leasingböcker.</span><span class="sxs-lookup"><span data-stu-id="b765f-110">You can also specify whether the batch process should be run for specific entities, lease groups, or lease books.</span></span>

> [!NOTE]
> <span data-ttu-id="b765f-111">Efterföljande transaktioner, till exempel skuldamorteringsplaner, betalningar, avskrivningar och utgifter bokförs först efter det att första redovisningstillfället för motsvarande leasingar har bokförts.</span><span class="sxs-lookup"><span data-stu-id="b765f-111">Subsequent transactions, such as liability amortization schedules, payments, depreciation, and expenses, will be posted only after the initial recognition for corresponding leases is posted.</span></span>
>
> <span data-ttu-id="b765f-112">Journalposterna skapas men bokförs inte förrän du väljer kommandot **Kör**.</span><span class="sxs-lookup"><span data-stu-id="b765f-112">The journal entries are created, but they won't be posted until you select the **Run** command.</span></span>
