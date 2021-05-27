---
title: Du kan inte uppdatera den prognostiserade enhetskostnaden när du importerar poster för efterfrågeprognoser
description: När du använder dataenheter för att importera poster för efterfrågeprognoser, uppdateras inte självkostnaden för befintliga poster så att den matchar importerade data.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026919"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a><span data-ttu-id="5d80b-103">Du kan inte uppdatera den prognostiserade enhetskostnaden när du importerar poster för efterfrågeprognoser</span><span class="sxs-lookup"><span data-stu-id="5d80b-103">You can't update the forecasted unit cost when you import demand forecast records</span></span>

<span data-ttu-id="5d80b-104">KB-nummer: 4614109</span><span class="sxs-lookup"><span data-stu-id="5d80b-104">KB number: 4614109</span></span>

## <a name="symptoms"></a><span data-ttu-id="5d80b-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="5d80b-105">Symptoms</span></span>

<span data-ttu-id="5d80b-106">När du använder dataenheter för att importera poster för efterfrågeprognoser, uppdateras inte värdet **Prognostiserad enhetskostnad** för befintliga poster så att den matchar importerade data.</span><span class="sxs-lookup"><span data-stu-id="5d80b-106">When you use data entities to import demand forecast records, the **Forecasted unit cost** value for existing records isn't updated so that it matches the imported data.</span></span>

## <a name="cause"></a><span data-ttu-id="5d80b-107">Orsak</span><span class="sxs-lookup"><span data-stu-id="5d80b-107">Cause</span></span>

<span data-ttu-id="5d80b-108">**Prognostiserad enhetskostnad** är ett skrivskyddat fält.</span><span class="sxs-lookup"><span data-stu-id="5d80b-108">**Forecasted unit cost** is a read-only field.</span></span> <span data-ttu-id="5d80b-109">Värdet baseras på produktenhetskostnaden och kan inte ställas in direkt via import.</span><span class="sxs-lookup"><span data-stu-id="5d80b-109">The value is based on the product unit cost and can't be set directly through import.</span></span>

## <a name="resolution"></a><span data-ttu-id="5d80b-110">Upplösning</span><span class="sxs-lookup"><span data-stu-id="5d80b-110">Resolution</span></span>

<span data-ttu-id="5d80b-111">Eftersom fältet är skrivskyddat kan du inte importera värden för det.</span><span class="sxs-lookup"><span data-stu-id="5d80b-111">Because the field is read only, you can't import values for it.</span></span> <span data-ttu-id="5d80b-112">Värdet beräknas enligt den befintliga affärslogiken.</span><span class="sxs-lookup"><span data-stu-id="5d80b-112">The value will be calculated according to the existing business logic.</span></span>
