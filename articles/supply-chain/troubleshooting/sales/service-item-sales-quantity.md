---
title: Det går inte att ställa in kvantiteten för en serviceartikel på en försäljningsoffertrad
description: När du arbetar med försäljningsofferter kan du inte ställa in en försäljningskvantitet för produkter som är serviceartiklar, eftersom det inte finns några fysiska artiklar som kan räknas.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea0f8f246e95f90b6ac5e78ee63950c9ca836a0e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477673"
---
# <a name="cant-change-the-sales-quantity-of-a-service-item-on-a-sales-quotation-line"></a>Det går inte att ändra försäljningskvantiteten för en serviceartikel på en försäljningsoffertrad

## <a name="symptoms"></a>Symtom

Om du försöker ange en försäljningskvantitet (fältet **SalesQty**) för en artikel av typen *Service* på en försäljningsoffertrad visas följande meddelande:

> Uppdatering är inte tillåten för fältet Kvantitet.

## <a name="cause"></a>Orsak

Detta är av design. Du kan inte ange en försäljningskvantitet för produkter som är serviceartiklar. Om du till exempel erbjuder en tjänst för att installera en artikel, är det inte klokt att registrera en kvantitet, eftersom det inte finns någon fysisk artikel som kan räknas. Det finns bara en tjänst.
