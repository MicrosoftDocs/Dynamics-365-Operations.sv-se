---
title: Strukturlistenedbrytning fungerar på olika sätt för bekräftade och uppskattade produktionsorder
description: Nedbrytning av strukturlistor fungerar annorlunda för fasta produktionsorder och för uppskattade produktionsorder för manuellt skapat arbete
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 94d4b00ea30396923a61b2748cf1aaeedc0af8af
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477629"
---
# <a name="bom-explosion-behaves-differently-for-firmed-and-estimated-production-orders"></a>Strukturlistenedbrytning fungerar på olika sätt för bekräftade och uppskattade produktionsorder

## <a name="symptoms"></a>Symtom

När en tillverkningsorder bekräftas bryts artiklarna inte ned när du bryter ned strukturlistan. Men när du skapar en arbetsorder manuellt och sedan uppskattar tillverkningsordern, bryts artiklarna ned.

### <a name="resolution"></a>Lösning

Nedbrytningen som inträffar när tillverkningsordern bekräftas pekar på den planerade ordern, men den visas inte om den planerade ordern för närvarande är bekräftad i detta fall. Om tillverkningsordern har uppskattats utlöses nedbrytningen från den släppta produktionsordern där det inte finns någon planerad order.
