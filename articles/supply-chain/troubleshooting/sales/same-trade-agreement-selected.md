---
title: Samma handelsavtal valdes när försäljningsorderrader skapas
description: Om det finns fler än ett handelsavtal definierat för ett angivet datum väljs alltid det som har lägsta priset när försäljningsorderrader skapas.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a586a399fb349965b972191bec1271651bec5fcb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477637"
---
# <a name="if-two-trade-agreements-exist-for-overlapping-dates-the-same-one-is-always-selected"></a>Om två handelsavtal finns för överlappande datum väljs alltid samma

## <a name="symptoms"></a>Symtom

Om två handelsavtal har definierats för samma period eller överlappande perioder verkar samma handelsavtal väljas varje gång du skapar försäljningsorderrader som innehåller dessa artiklar.

## <a name="resolution"></a>Lösning

Om det finns fler än ett handelsavtal för ett givet datum väljs alltid handelsavtalet med det lägsta priset. Om du vill ha mer information hämtar du följande faktablad: [handelsavtal i Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).
