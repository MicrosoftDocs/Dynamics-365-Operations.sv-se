---
title: Det finns inget värde för Från-datum på fliken Aktiva priser på sidan Artikelpris
description: Det finns inget värde för Från-datum på fliken Aktiva priser på sidan Artikelpris.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026930"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a>Det finns inget värde för Från-datum på fliken Aktiva priser på sidan Artikelpris

KB-nummer: 4613548

## <a name="symptoms"></a>Symtom

Det finns inget värde för **Från-datum** på fliken **Aktiva priser** på sidan **Artikelpris**.

## <a name="resolution"></a>Upplösning

Värdet **Från-datum** (effektivt datum) som har angetts i det väntande priset överförs inte till det aktiva priset.

När en artikelkostnadspost först registreras har den status *Väntande* och ett avsett giltighetsdatum. När artikelkostnadsposten aktiveras uppdateras statusvärdet till *Aktiv* och giltighetsdatumet uppdateras till aktiveringsdatumet. Därför är det aktiva prisets aktiveringsdatum alltid det faktiska datumet för aktiveringen.

Mer information finns i [Översikt över versioner av kostnadsredovisning](../../cost-management/costing-versions.md).
