---
title: Annullerade produktinleveranser uppdaterar inte transaktionsstatus till registrerad
description: När du har annullerat produktinleveranser för en inkommande beläggning, uppdaterar systemet automatiskt lagertransaktionens status från Inleverans till Beställd.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c86457d50a7a9ac2a699a0e0a9c7bdf4cd7c67b
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294180"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a><span data-ttu-id="bcc8a-103">Annullerade produktinleveranser uppdaterar inte transaktionsstatus till registrerad</span><span class="sxs-lookup"><span data-stu-id="bcc8a-103">Canceled product receipts don't update transaction status to Registered</span></span>

## <a name="symptoms"></a><span data-ttu-id="bcc8a-104">Symtom</span><span class="sxs-lookup"><span data-stu-id="bcc8a-104">Symptoms</span></span>

<span data-ttu-id="bcc8a-105">När du har kört åtgärden **annullera produktinleveranser** för en inkommande beläggning, uppdaterar systemet automatiskt lagertransaktionens status från *Inleverans* till *Beställd*.</span><span class="sxs-lookup"><span data-stu-id="bcc8a-105">After you run the **Cancel product receipts** action on an inbound load, the system automatically updates the status of inventory transactions from *Received* to *Ordered*.</span></span>

## <a name="resolution"></a><span data-ttu-id="bcc8a-106">Lösning</span><span class="sxs-lookup"><span data-stu-id="bcc8a-106">Resolution</span></span>

<span data-ttu-id="bcc8a-107">När följesedlar annulleras för utgående lastning förblir statusen för lagertransaktionerna *Plockad*.</span><span class="sxs-lookup"><span data-stu-id="bcc8a-107">When packing slips are canceled for outbound loads, the status of inventory transactions remains *Picked*.</span></span> <span data-ttu-id="bcc8a-108">När produktinleveranser från en inkommande belastning annulleras, återställs dock statusen för lagertransaktionerna till *Registrerad*.</span><span class="sxs-lookup"><span data-stu-id="bcc8a-108">However, when product receipts from an inbound load are canceled, the status of inventory transactions isn't restored to *Registered*.</span></span> <span data-ttu-id="bcc8a-109">När en produktinleverans från en inkommande belastning har annullerats måste lagerarbetaren därför registrera artikelkvantiteterna på nytt för inläsningen.</span><span class="sxs-lookup"><span data-stu-id="bcc8a-109">Therefore, after a product receipt from an inbound load is canceled, the warehouse worker must re-register item quantities for the loads.</span></span>

<span data-ttu-id="bcc8a-110">Mer information finns i [Registrera artikelkvantiteter som inkommer till en inkommande last](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span><span class="sxs-lookup"><span data-stu-id="bcc8a-110">For more information, see [Register item quantities that arrive on an inbound load](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span></span>
