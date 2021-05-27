---
title: Ett fel uppstår när platsen väljs vid plocklisteregistrering
description: Ett fel uppstår när platsen väljs vid plocklisteregistrering.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b7fc579821f9a80d94aea949fcc0301b9d8f6935
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026899"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a>Ett fel uppstår när platsen väljs vid plocklisteregistrering

KB-nummer: 4613106

## <a name="symptoms"></a>Symtom

Det här problemet uppstår när systemet är konfigurerat för att automatiskt reservera försäljningsorder. Om du försöker välja plats för en registreringsrad för plocklista visas följande felmeddelande när du använder WMS-reservationsprocesser (Warehouse Management):

> Det går inte att uppdatera kvantiteten med nya dimensioner

Det här problemet kan uppstå eftersom du inte har tillräckligt med lagerbehållning på en angiven plats.

## <a name="resolution"></a>Upplösning

Systemet beter sig som det är utformat.

I scenarier där du använder reservationsprocessen på lagernivå rekommenderar vi att du använder den manuella reservationsprocessen från plockraden om lagerbehållningen inte reserveras på alla lagerdimensionsnivåer och du inte har tillräckligt med lagerbehållning på en angiven plats. Du kan sedan använda funktionen *Reservera parti* för att distribuera de lägre reservationerna, till exempel plats, för alla tillgängliga lagerbevarande kvantiteter.
