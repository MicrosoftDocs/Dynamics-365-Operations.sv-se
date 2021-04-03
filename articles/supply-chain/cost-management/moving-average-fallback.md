---
title: Rörligt genomsnitt, reservkostnadssekvens
description: Det här avsnittet innehåller information om reservkostnadssekvenser för beräkningar av rörligt genomsnitt i Microsoft Dynamics 365 Supply Chain Management.
author: AndersGirke
manager: tfehr
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 1f5b1307f039bb9e921d50aed411b3dc603ada65
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263624"
---
# <a name="moving-average-fallback-cost-sequence"></a><span data-ttu-id="beb6d-103">Rörligt genomsnitt, reservkostnadssekvens</span><span class="sxs-lookup"><span data-stu-id="beb6d-103">Moving average fallback cost sequence</span></span>

<span data-ttu-id="beb6d-104">Ett sätt att beräkna kostnaden för ditt lager är att använda ett _Rörligt genomsnitt_.</span><span class="sxs-lookup"><span data-stu-id="beb6d-104">One way that you can calculate the cost of your inventory is by using a _moving average_.</span></span> <span data-ttu-id="beb6d-105">Upp till tre kostnadsvärden kan kopplas till varje lagerartikel:</span><span class="sxs-lookup"><span data-stu-id="beb6d-105">Up to three cost values can be associated with each inventory item:</span></span>

- <span data-ttu-id="beb6d-106">**Senaste utleverans** – den senaste utleveranskostnaden som tilldelades innan lagret blev negativt</span><span class="sxs-lookup"><span data-stu-id="beb6d-106">**Last issue** – The last issue cost that was assigned before inventory went negative</span></span>
- <span data-ttu-id="beb6d-107">**Aktiv kostnad** – den senaste kostnad som aktiverades i en kostnadsversion</span><span class="sxs-lookup"><span data-stu-id="beb6d-107">**Active cost** – The latest cost that was activated in a costing version</span></span>
- <span data-ttu-id="beb6d-108">**Artikelpris** – den kostnad som angetts för den frisläppta produkten</span><span class="sxs-lookup"><span data-stu-id="beb6d-108">**Item price** – The cost that is specified for the released product</span></span>

<span data-ttu-id="beb6d-109">För att avgöra vilka av dessa kostnadsvärden som ska användas vid beräkningar av rörligt genomsnitt använder systemet en _reservkostnadssekvens_ för att fastställa prioritetsordningen för värdena.</span><span class="sxs-lookup"><span data-stu-id="beb6d-109">To determine which of these cost values should be used in moving average calculations, the system uses a _fallback cost sequence_ to establish the order of preference for the values.</span></span> <span data-ttu-id="beb6d-110">Om det prioriterade kostnadsvärdet inte är tillgängligt använder systemet nästa önskade värde, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="beb6d-110">If the preferred cost value isn't available, the system uses the next-preferred value, and so on.</span></span>

<span data-ttu-id="beb6d-111">I tidigare versioner av Microsoft Dynamics 365 Supply Chain Management använde systemet en fast reservkostnadssekvens (_senaste utleverans – aktiv kostnad – artikelpris_).</span><span class="sxs-lookup"><span data-stu-id="beb6d-111">In previous versions of Microsoft Dynamics 365 Supply Chain Management, the system used a fixed fallback cost sequence (_Last issue – Active cost – Item price_).</span></span> <span data-ttu-id="beb6d-112">I version 10.0.11 är den här sekvensen fortfarande standardsekvensen.</span><span class="sxs-lookup"><span data-stu-id="beb6d-112">In version 10.0.11, this sequence is still the default sequence.</span></span> <span data-ttu-id="beb6d-113">Du kan emellertid också aktivera en funktion som gör att du kan välja bland tre tillgängliga reservkostnadssekvenser.</span><span class="sxs-lookup"><span data-stu-id="beb6d-113">However, you can also turn on a feature that lets you select among three available fallback cost sequences.</span></span> <span data-ttu-id="beb6d-114">Den här funktionen kan vara särskilt användbar för organisationer som regelbundet använder negativa lagervärden.</span><span class="sxs-lookup"><span data-stu-id="beb6d-114">This feature can be especially useful for organizations that regularly use negative inventory values.</span></span>

<span data-ttu-id="beb6d-115">Om du vill göra väljaren för den tillgängliga reservkostnadssekvenser måste du (eller en administratör) använda [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera funktionen med namnet _rörligt genomsnitt för reservkostnadssekvenser_.</span><span class="sxs-lookup"><span data-stu-id="beb6d-115">To make the selector for the fallback cost sequence available, you (or an admin) must use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named _Moving average fallback cost sequence_.</span></span>

<span data-ttu-id="beb6d-116">Följ de här stegen om du vill välja en reservkostnadssekvenser för beräkning av rörligt genomsnitt.</span><span class="sxs-lookup"><span data-stu-id="beb6d-116">To select the fallback cost sequence for moving average calculations, follow these steps.</span></span>

1. <span data-ttu-id="beb6d-117">Öppna sidan **Parametrar**.</span><span class="sxs-lookup"><span data-stu-id="beb6d-117">Open the **Parameters** page.</span></span>
2. <span data-ttu-id="beb6d-118">På fliken **Lagerredovisning** i avsnittet **Rörligt genomsnitt** ange fältet **Reservkostnadssekvens** till ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="beb6d-118">On the **Inventory accounting** tab, in the **Moving average** section, set the **Fallback cost sequence** field to one of the following values:</span></span>

    - <span data-ttu-id="beb6d-119">**Senaste utleverans – aktiv kostnad – artikelpris** – den här sekvensen är standardsekvens.</span><span class="sxs-lookup"><span data-stu-id="beb6d-119">**Last issue – Active cost – Item price** – This sequence is the default sequence.</span></span> <span data-ttu-id="beb6d-120">Det är samma sekvens som används om funktionen för _Rörligt genomsnitt, reservkostnadssekvens_ inte är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="beb6d-120">It's the same sequence that is used if the _Moving average fallback cost sequence_ feature isn't turned on.</span></span>
    - <span data-ttu-id="beb6d-121">**Aktiv kostnad – senaste utleverans**</span><span class="sxs-lookup"><span data-stu-id="beb6d-121">**Active cost – Last issue**</span></span>
    - <span data-ttu-id="beb6d-122">**Aktiv kostnad – ett artikelpris** – organisationer kan uppleva prestandaproblem om de använder affärsprocesser där lagret regelbundet blir negativt och samtidigt är transaktionsvolymen hög.</span><span class="sxs-lookup"><span data-stu-id="beb6d-122">**Active cost – Item price** – Organizations might experience performance issues if they use business processes where inventory regularly goes negative and, at the same time, the transaction volume is high.</span></span> <span data-ttu-id="beb6d-123">Den här inställningen kan hjälpa till att minska prestandaproblemen.</span><span class="sxs-lookup"><span data-stu-id="beb6d-123">This setting can help mitigate those performance issues.</span></span>

<span data-ttu-id="beb6d-124">![Parametrarna lagerredovisning](media/inventory-accounting-parameters.png "Parametrarna lagerredovisning")</span><span class="sxs-lookup"><span data-stu-id="beb6d-124">![Inventory accounting parameters](media/inventory-accounting-parameters.png "Inventory accounting parameters")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]