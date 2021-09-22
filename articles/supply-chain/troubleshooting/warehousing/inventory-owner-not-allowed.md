---
title: Lagerägare är inte tillåtet när du bearbetar förflyttningar
description: Du kan få felmeddelandet "Lagerägaren är %1 inte tillåten." Lagerhanteringsprocesserna stöder endast lager som ägs av den juridiska personen.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4ee29cfc7bad990cd1ee5deaa98fca217af772ed
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477608"
---
# <a name="inventory-owner-not-allowed-when-processing-movements-in-the-warehouse-app"></a>Lagerägare är inte tillåtet när du bearbetar förflyttningar i distributionslagerappen

## <a name="symptoms"></a>Symtom

När du bearbetar förflyttningar i Warehouse Management-mobilappen kan du få följande felmeddelande:

> Lagerägaren är %1 inte tillåten i den här processen.

## <a name="cause"></a>Orsak

Det inträffar eftersom spårningsdimensionen **Ägare** saknas när Warehouse Management-mobilappen används för att göra förflyttningar. En vanlig lageröverföringsjournal från klienten Supply Chain Management visas som avsett arbete och kan endast bokföras om dimensionen **Ägare** fylls i.

## <a name="resolution"></a>Lösning

Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning. För närvarande stöder lagerhanteringsprocesserna endast lager som ägs av den juridiska personen.
