---
title: Det går inte att ändra giltighetsdatum för en godkänd leverantör
description: Den lista över godkända leverantörer per produktenhet tillåter inte att giltighetsdatumet ändras
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: cb6dbd134d63daa163261cabdbd7eceb978877ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477588"
---
# <a name="cant-change-the-effective-date-for-an-approved-vendor"></a>Det går inte att ändra giltighetsdatum för en godkänd leverantör


## <a name="symptoms"></a>Symtom

En produkt har en godkänd leverantör som t.ex. är ett giltighetsdatum på 11 januari 2018 (*01/11/2018*) och ett utgångsdatum för *aldrig*. Om du försöker ändra giltighetsdatum till 10 januari 2018 (*01/10/2018*) eller 12 januari 2018 (*01/12/2018*) visas följande felmeddelande:

> Det går inte att skapa en post i listan över godkända leverantörer (PdsApproveVendorList). Värdet för utgångsdatum måste vara större än eller lika med värdet effektiv.

## <a name="resolution"></a>Lösning

Du kan bara utöka den period som leverantören är godkänd för. Följande regler gäller:

- Om du vill ändra giltighetsdatumet så att det är tidigare än någon av de befintliga posterna (perioderna) för artikelleverantören, måste utgångsdatumet för den nya perioden vara före alla utgångsdatum i de befintliga posterna.
- Om du vill ändra utgångsdatum så att det blir senare än någon av de befintliga perioderna måste giltighetsdatumet vara efter det senaste utgångsdatumet i någon befintlig post.
- Om du vill minska den totala perioden som leverantören har godkänts för måste du ta bort eller ändra befintliga poster. Alternativt kan du använda växeln **trunkera** under importen. Den här växeln tar bort alla befintliga poster i registret för godkända leverantörer per artikel.

I det här scenariot som beskrivs i ärendebeskrivningen, där en post har giltighetsdatumet *01/11/2018* och ett utgångsdatum för *aldrig*, kan du importera en ny post som har ett giltighetsdatum på *01/10/2018* och ett utgångsdatum för *aldrig*. Du kan dock inte förkorta perioden så att giltighetsdatumet uppdateras till *01/12/2018* via datahantering. Du måste göra ändringen genom användargränssnittet.
