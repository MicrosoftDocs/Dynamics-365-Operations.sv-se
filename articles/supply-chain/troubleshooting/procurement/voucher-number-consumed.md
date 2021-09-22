---
title: Ett verifikationsnummer för produktinleverans används även om ingen verifikation skapas
description: Ett verifikationsnummer för produktinleverans används även om ingen ekonomisk verifikation genereras vid produktinleverans
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
ms.openlocfilehash: 0556969950c45e80d177a0e96096c4157d690ae3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477626"
---
# <a name="a-product-receipt-voucher-number-is-consumed-even-when-not-generating-a-voucher"></a>Ett verifikationsnummer för produktinleverans används även om ingen verifikation skapas

## <a name="symptoms"></a>Symtom

Ett verifikationsnummer för produktinleverans förbrukas även om ingen ekonomisk verifikation genereras vid produktinleverans.

## <a name="resolution"></a>Lösning

Om alternativet **Periodisera skulder vid produktinleverans** anges till *Nej* för artikelmodellgruppen görs inga bokföringar i redovisningen. En fysisk händelse registreras emellertid i syfte att bokföras i redovisningen och den händelsen kräver ett verifikationsnummer. Detta verifikationsnummer är det verifikationsnummer som refereras i lagertransaktionerna.

Vi rekommenderar att du ställer in alternativet **Periodisera skulder vid produktinleverans** till *Ja*, vilket beskrivs i följande blogginlägg: [Bokför tillägg vid inleverans av produkten](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
