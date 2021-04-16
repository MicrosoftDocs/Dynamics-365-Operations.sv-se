---
title: Standardbeskrivningar för redovisningen
description: Standardbeskrivningar kan användas för att uppdatera beskrivningsfältet i verifikationsbokföring i redovisningen.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: d5a38af57d614ae2c93b0af74ec4a1c085519d46
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841916"
---
# <a name="default-descriptions-for-the-general-ledger"></a><span data-ttu-id="465d1-103">Standardbeskrivningar för redovisningen</span><span class="sxs-lookup"><span data-stu-id="465d1-103">Default descriptions for the general ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="465d1-104">Standardbeskrivningar kan användas för att uppdatera fältet **beskrivning** i verifikationsbokföring i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="465d1-104">Default descriptions can be used to update the **Description** field in voucher postings to the general ledger.</span></span> <span data-ttu-id="465d1-105">Den här funktionen har förbättrats så att den fungerar med hemtagningskostnad.</span><span class="sxs-lookup"><span data-stu-id="465d1-105">This functionality has been enhanced to work with Landed cost.</span></span>

<span data-ttu-id="465d1-106">För att ställa in standardbeskrivningar för bokföringsbokningar, gå till **Organisationsadministration \> Inställning \> Standardbeskrivningar**.</span><span class="sxs-lookup"><span data-stu-id="465d1-106">To set up default descriptions for ledger postings, go to **Organizational administration \> Setup \> Default descriptions**.</span></span>

<span data-ttu-id="465d1-107">I följande tabell listas de nya värden som har lagts till för fältet **Beskrivning** på sidan **Standardbeskrivningar** som stöd för hemtagningskostnad.</span><span class="sxs-lookup"><span data-stu-id="465d1-107">The following table lists the new values that have been added for the **Description** field on the **Default descriptions** page to support Landed cost.</span></span>

| <span data-ttu-id="465d1-108">Beskrivningstyp</span><span class="sxs-lookup"><span data-stu-id="465d1-108">Description type</span></span> | <span data-ttu-id="465d1-109">Anteckningar</span><span class="sxs-lookup"><span data-stu-id="465d1-109">Notes</span></span> |
|---|---|
| <span data-ttu-id="465d1-110">Importera kostnadsredovisning – periodisering av kostnader</span><span class="sxs-lookup"><span data-stu-id="465d1-110">Import costing – Cost accrual</span></span> | <span data-ttu-id="465d1-111">När en inköpsorderfaktura bokförs bearbetas en periodisering av kostnader för uppskattade färdkostnader.</span><span class="sxs-lookup"><span data-stu-id="465d1-111">When a purchase order invoice is posted, a cost accrual is processed for estimate voyage costs.</span></span> <span data-ttu-id="465d1-112">Standardbeskrivningar kan anges om du vill lägga till färdnumret i beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="465d1-112">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="465d1-113">Använd *%4* för försändelsenumret.</span><span class="sxs-lookup"><span data-stu-id="465d1-113">Use *%4* for the shipment number.</span></span> |
| <span data-ttu-id="465d1-114">Importkostnadsredovisning – order för varor på väg</span><span class="sxs-lookup"><span data-stu-id="465d1-114">Import costing – Goods in transit order</span></span> | <span data-ttu-id="465d1-115">Om du använder bearbetning av varor på väg bokförs inköpsorderfakturan och varorna bokförs till ett konto för varor på väg.</span><span class="sxs-lookup"><span data-stu-id="465d1-115">If you're using in-transit processing, the purchase order invoice is posted, and the goods are posted to a goods in transit account.</span></span> <span data-ttu-id="465d1-116">Standardbeskrivningar kan anges om du vill lägga till nummer för order för varor på väg i beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="465d1-116">Default descriptions can be specified to add the in-transit order number to the description.</span></span> <span data-ttu-id="465d1-117">Används *%4* för nummer för order för varor på väg.</span><span class="sxs-lookup"><span data-stu-id="465d1-117">Use *%4* for the in-transit order number.</span></span> |
| <span data-ttu-id="465d1-118">Lager - Stängning - Justering</span><span class="sxs-lookup"><span data-stu-id="465d1-118">Inventory – close – adjustment</span></span> | <span data-ttu-id="465d1-119">När leverantörsreskontrafakturan (AP) bearbetas för en färdkostnad bearbetas en lagerjustering för att uppskatta färdkostnader.</span><span class="sxs-lookup"><span data-stu-id="465d1-119">When the accounts payable (AP) invoice is processed for a voyage cost, an inventory adjustment is processed to estimate voyage costs.</span></span> <span data-ttu-id="465d1-120">Standardbeskrivningar kan anges om du vill lägga till färdnumret i beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="465d1-120">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="465d1-121">Använd *%4* för försändelsenumret.</span><span class="sxs-lookup"><span data-stu-id="465d1-121">Use *%4* for the shipment number.</span></span> |

<span data-ttu-id="465d1-122">Mer information om hur du arbetar med sidan **Standardbeskrivningar**, se [Ställ in standardbeskrivningar för automatisk bokföring](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span><span class="sxs-lookup"><span data-stu-id="465d1-122">For more information about how to work with the **Default descriptions** page, see [Set up default descriptions for automatic posting](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span></span>
