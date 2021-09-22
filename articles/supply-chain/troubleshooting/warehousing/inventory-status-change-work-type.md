---
title: Det går inte att välja Lagerstatusändring som Arbetstyp
description: Det går inte att skapa en arbetsmallrad för ändring av lagerstatus eftersom arbetstypen bara används i systemprocesser. Välj en annan arbetstyp.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ad7f26f3235d15779583f9cdadeb4e6dca16242a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477666"
---
# <a name="cant-select-inventory-status-change-in-the-work-type-column"></a>Det går inte att välja Lagerstatusändring i kolumnen Arbetstyp

## <a name="symptoms"></a>Symtom

När du konfigurerar Microsoft Dynamics 365 Supply Chain Management kan följande felmeddelande visas:

> Det går inte att skapa en arbetsmallrad för ändring av lagerstatus eftersom arbetstypen är ogiltig. Välj en annan arbetstyp.

## <a name="resolution"></a>Lösning

Detta beteende är av design. Arbetstypen *Ändring av lagerstatus* används endast av systemprocesser. Det kan inte konfigureras. Eftersom listan med arbetstyper är fast som en uppräkning kan inte de extra posterna filtreras från den nedrullningsbara menyn **Arbetstyp**.
