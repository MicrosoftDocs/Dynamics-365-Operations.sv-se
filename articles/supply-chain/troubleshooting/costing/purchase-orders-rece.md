---
title: Fysiskt mottagna inköpsorder visas inte i lagerstängningsrapporten
description: Fysiskt mottagna inköpsorder visas inte i lagerstängningsrapporten Kontrollera öppna kvantiteter.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9508d6d75d8ebee7ca10140ed4c4215d7ad1dda7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026915"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a><span data-ttu-id="81f65-103">Fysiskt mottagna inköpsorder visas inte i lagerstängningsrapporten</span><span class="sxs-lookup"><span data-stu-id="81f65-103">Physically received purchase orders don't appear on the inventory closing report</span></span>

<span data-ttu-id="81f65-104">KB-nummer: 4612595</span><span class="sxs-lookup"><span data-stu-id="81f65-104">KB number: 4612595</span></span>

## <a name="symptoms"></a><span data-ttu-id="81f65-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="81f65-105">Symptoms</span></span>

<span data-ttu-id="81f65-106">Fysiskt mottagna inköpsorder visas inte i lagerstängningsrapporten **Kontrollera öppna kvantiteter**.</span><span class="sxs-lookup"><span data-stu-id="81f65-106">Physically received purchase orders don't appear on the **Check open quantities** inventory closing report.</span></span>

## <a name="resolution"></a><span data-ttu-id="81f65-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="81f65-107">Resolution</span></span>

<span data-ttu-id="81f65-108">Rapporten **Kontrollera öppna kvantiteter** visar utleveranstransaktioner som inte kan kvittas mot ekonomiskt uppdaterade lagerinleveranser per det valda slutdatumet.</span><span class="sxs-lookup"><span data-stu-id="81f65-108">The **Check open quantities** report shows issue transactions that can't be settled against financially updated inventory receipts as of the selected closing date.</span></span> <span data-ttu-id="81f65-109">Du kan välja att inkludera fysiska inleveranser i rapporten.</span><span class="sxs-lookup"><span data-stu-id="81f65-109">You can choose to include physical receipts on the report.</span></span> <span data-ttu-id="81f65-110">I så fall visas fysiska inleveranser om de kan täcka utleveranstransaktionerna som inte kan kvittas.</span><span class="sxs-lookup"><span data-stu-id="81f65-110">In that case, physical receipts will be shown if they can cover the issue transactions that can't be settled.</span></span> <span data-ttu-id="81f65-111">Mer information finns i [Förbered körning av stängning av lager](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).</span><span class="sxs-lookup"><span data-stu-id="81f65-111">For more information, see [Preparing to run inventory close](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).</span></span>
