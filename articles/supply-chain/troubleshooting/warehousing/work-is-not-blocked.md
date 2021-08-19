---
title: Ej blockerat arbete
description: Ej blockerat arbete
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 6b4361682246397732e8326b98b1b86ff878664e54c8c352296b0d7eaff6bbbd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719561"
---
# <a name="work-isnt-blocked"></a>Ej blockerat arbete

Felkod: WHSUnblockNotBlockedWorkErrorMessage

## <a name="symptoms"></a>Symtom

Systemet visar följande felmeddelande:

> Arbete med ID %1 är inte spärrat.

## <a name="cause"></a>Orsak

Alternativet **Spärrad cykel** på cyklen ställs in som *Nej*. Arbetet kan inte frisättas eftersom det i nuläget inte är spärrat.

## <a name="resolution"></a>Upplösning

 Endast arbete där alternativet **Blockerad cykel** är inställt på *Ja* kan frisättas.
