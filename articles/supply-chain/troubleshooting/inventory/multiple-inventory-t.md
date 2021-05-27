---
title: Flera lagertransaktioner för batchnummer när Vid fysisk uppdatering avaktiveras
description: Flera lagertransaktioner skapas efter att du har justerat en inköpsorderrad för artiklar där alternativet Vid fysisk uppdatering för batchnummergruppen är inställt på Nej.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026929"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a><span data-ttu-id="cfece-103">Flera lagertransaktioner för batchnummer när Vid fysisk uppdatering avaktiveras</span><span class="sxs-lookup"><span data-stu-id="cfece-103">Multiple inventory transactions for batch numbers when On physical update is disabled</span></span>

<span data-ttu-id="cfece-104">KB-nummer: 4613390</span><span class="sxs-lookup"><span data-stu-id="cfece-104">KB number: 4613390</span></span>

## <a name="symptoms"></a><span data-ttu-id="cfece-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="cfece-105">Symptoms</span></span>

<span data-ttu-id="cfece-106">Flera lagertransaktioner skapas efter att du har justerat en inköpsorderrad för artiklar där alternativet **Vid fysisk uppdatering** för batchnummergruppen är inställt på *Nej*.</span><span class="sxs-lookup"><span data-stu-id="cfece-106">Multiple inventory transactions are created after you adjust a purchase order line for items where the **On physical update** option of the batch number group is set to *No*.</span></span>

<span data-ttu-id="cfece-107">När du skapar en artikel där alternativet **Vid fysisk uppdatering** för batchnummergruppen är insätllt på *Nej* skapar systemet automatiskt ett nytt batchnummer om du ändrar kvantitet på en inköpsrad och sparar inköpsordersidan.</span><span class="sxs-lookup"><span data-stu-id="cfece-107">When you create an item where the **On physical update** option of the batch number group is set to *No*, the system automatically creates a new batch number if you modify a purchase line quantity and save the purchase order page.</span></span>

## <a name="resolution"></a><span data-ttu-id="cfece-108">Upplösning</span><span class="sxs-lookup"><span data-stu-id="cfece-108">Resolution</span></span>

<span data-ttu-id="cfece-109">Inställningen **Vid fysisk uppdatering** för batchnummergrupper fungerar på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="cfece-109">The **On physical update** setting for batch number groups works in the following way:</span></span>

- <span data-ttu-id="cfece-110">När alternativet är inställt på *Ja* skapas nya batchnummer endast efter en fysisk uppdatering (till exempel när artiklar skickas eller tas emot).</span><span class="sxs-lookup"><span data-stu-id="cfece-110">When the option is set to *Yes*, new batch numbers are created only after a physical update (for example, when items are shipped or received).</span></span>
- <span data-ttu-id="cfece-111">När alternativet är inställt på *Nej* skapas ett nytt batchnummer varje gång en tillämplig uppdatering sker (till exempel när en ny kvantitet läggs till i en inköpsorder).</span><span class="sxs-lookup"><span data-stu-id="cfece-111">When the option is set to *No*, a new batch number is created every time that an applicable update occurs (for example, when a new quantity is added to a purchase order).</span></span>
