---
title: Distributionslagret i plocklistejournalen uppdateras inte på en strukturlisterad.
description: Distributionslagret i plocklistejournalen uppdateras inte på en strukturlisterad.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 970930bbdd30b57a8374de7810bb3ece8cb19a7010b5ef19d90bfc39d09f172b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740561"
---
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a>Distributionslagret i plocklistejournalen uppdateras inte på en strukturlisterad

KB-nummer: 4614848

## <a name="symptoms"></a>Symtom

Distributionslagret i plocklistejournalen uppdateras inte på en strukturlisterad.

## <a name="resolution"></a>Upplösning

Systemet beter sig som det är utformat. Om en plocklistejournalrad skapas som har en referens (via parti-ID) till en produktionsstrukturrad uppdateras inte distributionslagret på produktionsstrukturraden om lagerdimensionen på produktionsplocklistejournalraden ändras senare.
