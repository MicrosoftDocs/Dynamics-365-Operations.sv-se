---
title: Text skrivs över när artikel konfigureras på en försäljningsorderrad
description: När en produkt konfigureras på en försäljningsorderrad skrivs ändrad text över med standardtext. Ändra texten när du har konfigurerat raden, inte före.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 20239b9b0eecb355274e909a8b8b39450e468c7e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477586"
---
# <a name="item-text-is-overwritten-when-a-product-is-configured-on-a-sales-order-line"></a>Artikeltext skrivs över när en produkt konfigureras på en försäljningsorderrad

## <a name="symptoms"></a>Symtom

Det här problemet uppstår när du skapar en försäljningsorderrad för en konfigurerbar artikel och sedan ändrar artikelns text. När du konfigurerar artikeln och väljer **OK** skrivs texten över med standardtexten.

## <a name="resolution"></a>Lösning

Detta är ett förväntat beteende. Textfältet innehåller variantnamnet, som endast fylls i när du har konfigurerat raden. Därför måste du ändra texten när du har konfigurerat raden, inte före.
