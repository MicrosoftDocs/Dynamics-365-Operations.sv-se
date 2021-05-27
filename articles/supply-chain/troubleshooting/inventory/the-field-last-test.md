---
title: Fältet Senaste testdatum uppdateras inte när flera kvalitetsorder skapas
description: Fältet Senaste testdatum uppdateras inte när flera kvalitetsorder skapas.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026926"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a><span data-ttu-id="f4c58-103">Fältet Senaste testdatum uppdateras inte när flera kvalitetsorder skapas</span><span class="sxs-lookup"><span data-stu-id="f4c58-103">The Last tested date field isn't updated when multiple quality orders are created</span></span>

<span data-ttu-id="f4c58-104">KB-nummer: 4612803</span><span class="sxs-lookup"><span data-stu-id="f4c58-104">KB number: 4612803</span></span>

## <a name="symptoms"></a><span data-ttu-id="f4c58-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="f4c58-105">Symptoms</span></span>

<span data-ttu-id="f4c58-106">Fältet **Senaste testdatum** uppdateras inte när flera kvalitetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="f4c58-106">The **Last tested date** field isn't updated when multiple quality orders are created.</span></span>

## <a name="resolution"></a><span data-ttu-id="f4c58-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="f4c58-107">Resolution</span></span>

<span data-ttu-id="f4c58-108">Systemet beter sig som det är utformat.</span><span class="sxs-lookup"><span data-stu-id="f4c58-108">The system is behaving as designed.</span></span> <span data-ttu-id="f4c58-109">Det senaste testdatumet är inte relaterat till kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="f4c58-109">The last tested date isn't related to quality orders.</span></span> <span data-ttu-id="f4c58-110">Här lagras det datum då de färdiga varorna först köpts in eller tillverkats.</span><span class="sxs-lookup"><span data-stu-id="f4c58-110">It stores the date when the finished goods were first purchased or manufactured.</span></span> <span data-ttu-id="f4c58-111">Detta datum används för att beräkna hållbarhetstid.</span><span class="sxs-lookup"><span data-stu-id="f4c58-111">This date is used to calculate the shelf life advice date.</span></span>
