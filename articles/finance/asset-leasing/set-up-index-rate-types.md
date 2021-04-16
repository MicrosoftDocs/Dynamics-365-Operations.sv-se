---
title: Konfigurera indexräntor
description: Det här ämnet innehåller information om hur du konfigurerar indexräntor. Det krävs indexräntor om din organisation kopplar leasingbetalningsbelopp till en uppsättning indexräntor.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 6424248e8d01d04720ad65e80aaa543b42abccc6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823033"
---
# <a name="set-up-index-rates"></a><span data-ttu-id="c6a10-104">Konfigurera indexräntor</span><span class="sxs-lookup"><span data-stu-id="c6a10-104">Set up index rates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6a10-105">Om leasingbetalningar är beroende av ett index, kan indexräntetyper läggas till och upprätthållas i systemet.</span><span class="sxs-lookup"><span data-stu-id="c6a10-105">If lease payments depend on an index, the index rate types can be added and maintained in the system.</span></span> <span data-ttu-id="c6a10-106">Om du vill omvärdera leasingbetalningarna från sidan **Indexräntetyp**, använder ombedömningsprocessen för indexränta den senaste indexräntan från datumet för omvärderingen.</span><span class="sxs-lookup"><span data-stu-id="c6a10-106">To revalue the lease payments from the **Index rate type** page, the index rate revaluation process uses the most recent index rate from the date of revaluation.</span></span>

<span data-ttu-id="c6a10-107">Följ stegen nedan om du vill lägga till indexräntetyper och indexräntor.</span><span class="sxs-lookup"><span data-stu-id="c6a10-107">To add index rate types and index rates, follow these steps.</span></span>

1. <span data-ttu-id="c6a10-108">Gå till **Leasing av tillgångar \> Konfigurera \> Indexräntetyper**.</span><span class="sxs-lookup"><span data-stu-id="c6a10-108">Go to **Asset leasing \> Setup \> Index rate type**.</span></span>
2. <span data-ttu-id="c6a10-109">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c6a10-109">Select **New**.</span></span>
3. <span data-ttu-id="c6a10-110">I tillämpliga fält anger du räntetyp och namn på indexräntan.</span><span class="sxs-lookup"><span data-stu-id="c6a10-110">In the appropriate fields, enter the rate type and the name of the index rate.</span></span>
4. <span data-ttu-id="c6a10-111">Om du vill lägga till ett nytt värde för indexränta väljer du indexräntetyp och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="c6a10-111">To add a new index rate value, select the index rate type, and then select **Add**.</span></span>
5. <span data-ttu-id="c6a10-112">Välj effektivt startdatum för räntan och välj räntevärdet.</span><span class="sxs-lookup"><span data-stu-id="c6a10-112">Select the effective start date of the rate, and select the rate value.</span></span>

<span data-ttu-id="c6a10-113">Du måste välja antingen **Värdedifferens för indexränta** eller **Indexräntevärde** som indexräntemetod.</span><span class="sxs-lookup"><span data-stu-id="c6a10-113">You must select either **Index rate value difference** or **Index rate value** as the index rate method.</span></span>

- <span data-ttu-id="c6a10-114">Välj metoden **Värdedifferens för indexränta** för att beräkna en ny leasingbetalning, baserat på differensen mellan indexräntan på startdatumet och den senaste indexräntan.</span><span class="sxs-lookup"><span data-stu-id="c6a10-114">Select the **Index rate value difference** method to calculate a new lease payment, based on the difference between the index rate on the start date and the most recent index rate.</span></span> <span data-ttu-id="c6a10-115">Indexräntan definieras i fältet **Indexränta (%)**.</span><span class="sxs-lookup"><span data-stu-id="c6a10-115">The index rate is defined in the **Index rate (%)** field.</span></span>
- <span data-ttu-id="c6a10-116">Välj metoden **Indexräntevärde** om du vill beräkna leasingbetalningen med hjälp av procentsatsen som anges i fältet **Indexränta (%)**.</span><span class="sxs-lookup"><span data-stu-id="c6a10-116">Select the **Index rate value** method to calculate the lease payment by using the percentage that is specified in the **Index rate (%)** field.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]