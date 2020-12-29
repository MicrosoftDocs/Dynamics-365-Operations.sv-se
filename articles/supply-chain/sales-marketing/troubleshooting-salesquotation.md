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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437623"
---
# <a name="troubleshoot-sales-quotations"></a>Felsöka försäljningsofferter

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med försäljningsofferter.

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a>Jag kan inte ändra försäljningskvantitet för en försäljningsoffert för en serviceartikel.

### <a name="issue-description"></a>Problembeskrivning

Om du försöker ange en försäljningskvantitet (fältet **SalesQty**) för en artikel av typen *tjänst* på en försäljningsoffertrad visas följande meddelande: "uppdatering är inte tillåten för fältkvantitet".

### <a name="issue-resolution"></a>Problemlösning

Du kan inte ange en försäljningskvantitet för produkter som är serviceartiklar. Om du till exempel erbjuder en tjänst för att installera en artikel, är det inte klokt att registrera en kvantitet, eftersom det inte finns någon fysisk artikel. Det finns bara en tjänst.

