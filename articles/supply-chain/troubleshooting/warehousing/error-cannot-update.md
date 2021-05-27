---
title: Ett fel uppstår när platsen väljs vid plocklisteregistrering
description: Ett fel uppstår när platsen väljs vid plocklisteregistrering.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b7fc579821f9a80d94aea949fcc0301b9d8f6935
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026899"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a><span data-ttu-id="a7b25-103">Ett fel uppstår när platsen väljs vid plocklisteregistrering</span><span class="sxs-lookup"><span data-stu-id="a7b25-103">An error occurs when the location is selected during picking list registration</span></span>

<span data-ttu-id="a7b25-104">KB-nummer: 4613106</span><span class="sxs-lookup"><span data-stu-id="a7b25-104">KB number: 4613106</span></span>

## <a name="symptoms"></a><span data-ttu-id="a7b25-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="a7b25-105">Symptoms</span></span>

<span data-ttu-id="a7b25-106">Det här problemet uppstår när systemet är konfigurerat för att automatiskt reservera försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a7b25-106">This issue occurs when your system is configured to automatically reserve sales orders.</span></span> <span data-ttu-id="a7b25-107">Om du försöker välja plats för en registreringsrad för plocklista visas följande felmeddelande när du använder WMS-reservationsprocesser (Warehouse Management):</span><span class="sxs-lookup"><span data-stu-id="a7b25-107">If you try to select the location for a picking list registration line, you receive the following error message when you use warehouse management (WMS) reservation processes:</span></span>

> <span data-ttu-id="a7b25-108">Det går inte att uppdatera kvantiteten med nya dimensioner</span><span class="sxs-lookup"><span data-stu-id="a7b25-108">Can't update quantity with new dimensions</span></span>

<span data-ttu-id="a7b25-109">Det här problemet kan uppstå eftersom du inte har tillräckligt med lagerbehållning på en angiven plats.</span><span class="sxs-lookup"><span data-stu-id="a7b25-109">This issue can occur because you don't have enough on-hand inventory at a specified location.</span></span>

## <a name="resolution"></a><span data-ttu-id="a7b25-110">Upplösning</span><span class="sxs-lookup"><span data-stu-id="a7b25-110">Resolution</span></span>

<span data-ttu-id="a7b25-111">Systemet beter sig som det är utformat.</span><span class="sxs-lookup"><span data-stu-id="a7b25-111">The system is behaving as designed.</span></span>

<span data-ttu-id="a7b25-112">I scenarier där du använder reservationsprocessen på lagernivå rekommenderar vi att du använder den manuella reservationsprocessen från plockraden om lagerbehållningen inte reserveras på alla lagerdimensionsnivåer och du inte har tillräckligt med lagerbehållning på en angiven plats.</span><span class="sxs-lookup"><span data-stu-id="a7b25-112">In scenarios where you use the warehouse-level reservation process, if the on-hand inventory won't be reserved on all inventory dimension levels, and you don't have enough on-hand inventory at a specified location, we recommend that you use the manual reservation process from the picking line.</span></span> <span data-ttu-id="a7b25-113">Du kan sedan använda funktionen *Reservera parti* för att distribuera de lägre reservationerna, till exempel plats, för alla tillgängliga lagerbevarande kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="a7b25-113">You can then use the *Reserve lot* function to distribute the lower reservations, such as location, for all the available on-hand quantities.</span></span>
