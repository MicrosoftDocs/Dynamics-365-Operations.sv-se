---
title: Systemet kan inte hitta en planerad order under operationer på flera order
description: Felet "Planerad order finns inte" uppstår när du utför operationer på flera planerade order och minst två order tillhör samma artikel-ID.
author: t-benebo
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo_ReqTransPoMarkChangeType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 0ece4a331b63b86e896c5b337a58185ed3ea1049
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920817"
---
# <a name="the-system-cant-find-a-planned-order-during-operations-on-multiple-orders"></a>Systemet kan inte hitta en planerad order under operationer på flera order

Felkod: SYS24774

## <a name="symptoms"></a>Symtom

Följande felmeddelande visas när du försöker utföra en operation på flera planerade order samtidigt, och minst två av orderna tillhör samma artikel-ID. Felet kan till exempel inträffa när orderna bekräftas eller ordertypen ändras.

> Den planerade ordern %1 finns inte.

## <a name="cause"></a>Orsak

När systemet påverkar eller ändrar typ av order måste systemet föra över befintliga planerade order för artikeln för att se till att den planerade tillgången matchar efterfrågan och den befintliga tillförseln. Som en del av den här processen skapas planerade order för artikeln på nytt i systemet. Därför finns inte den andra planerade ordern som systemet förväntar sig att bearbeta längre.

## <a name="workaround"></a>Lösning

Godkänn orderna innan du bearbetar dem. På det här sättet tas orderna inte bort när systemet bearbetar den första ordern för artikeln.
