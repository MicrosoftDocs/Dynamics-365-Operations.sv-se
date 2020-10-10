---
title: Felsöka försäljningsofferter
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med försäljningsofferter.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 67610a833be132399b2d47ae8c6b27119be9ce95
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834427"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="bfcdb-103">Felsöka försäljningsofferter</span><span class="sxs-lookup"><span data-stu-id="bfcdb-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="bfcdb-104">I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med försäljningsofferter.</span><span class="sxs-lookup"><span data-stu-id="bfcdb-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="bfcdb-105">Jag kan inte ändra försäljningskvantitet för en försäljningsoffert för en serviceartikel.</span><span class="sxs-lookup"><span data-stu-id="bfcdb-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="bfcdb-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="bfcdb-106">Issue description</span></span>

<span data-ttu-id="bfcdb-107">Om du försöker ange en försäljningskvantitet (fältet **SalesQty**) för en artikel av typen *tjänst* på en försäljningsoffertrad visas följande meddelande: "uppdatering är inte tillåten för fältkvantitet".</span><span class="sxs-lookup"><span data-stu-id="bfcdb-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bfcdb-108">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="bfcdb-108">Issue resolution</span></span>

<span data-ttu-id="bfcdb-109">Du kan inte ange en försäljningskvantitet för produkter som är serviceartiklar.</span><span class="sxs-lookup"><span data-stu-id="bfcdb-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="bfcdb-110">Om du till exempel erbjuder en tjänst för att installera en artikel, är det inte klokt att registrera en kvantitet, eftersom det inte finns någon fysisk artikel.</span><span class="sxs-lookup"><span data-stu-id="bfcdb-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="bfcdb-111">Det finns bara en tjänst.</span><span class="sxs-lookup"><span data-stu-id="bfcdb-111">There is only a service.</span></span>

