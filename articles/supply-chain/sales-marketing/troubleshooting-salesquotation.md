---
title: Felsöka försäljningsofferter
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med försäljningsofferter.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 09529ba729170be7281e2ae04008d3ba4a58e060
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824760"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="5c1b0-103">Felsöka försäljningsofferter</span><span class="sxs-lookup"><span data-stu-id="5c1b0-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="5c1b0-104">I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med försäljningsofferter.</span><span class="sxs-lookup"><span data-stu-id="5c1b0-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="5c1b0-105">Jag kan inte ändra försäljningskvantitet för en försäljningsoffert för en serviceartikel.</span><span class="sxs-lookup"><span data-stu-id="5c1b0-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="5c1b0-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="5c1b0-106">Issue description</span></span>

<span data-ttu-id="5c1b0-107">Om du försöker ange en försäljningskvantitet (fältet **SalesQty**) för en artikel av typen *tjänst* på en försäljningsoffertrad visas följande meddelande: "uppdatering är inte tillåten för fältkvantitet".</span><span class="sxs-lookup"><span data-stu-id="5c1b0-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5c1b0-108">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="5c1b0-108">Issue resolution</span></span>

<span data-ttu-id="5c1b0-109">Du kan inte ange en försäljningskvantitet för produkter som är serviceartiklar.</span><span class="sxs-lookup"><span data-stu-id="5c1b0-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="5c1b0-110">Om du till exempel erbjuder en tjänst för att installera en artikel, är det inte klokt att registrera en kvantitet, eftersom det inte finns någon fysisk artikel.</span><span class="sxs-lookup"><span data-stu-id="5c1b0-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="5c1b0-111">Det finns bara en tjänst.</span><span class="sxs-lookup"><span data-stu-id="5c1b0-111">There is only a service.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]