---
title: Planerade order skapas för i lager med produktionsorder
description: Planerade order skapas trots att det redan finns artiklar i lager- och produktionsorder för dem
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
ms.openlocfilehash: aa803bcd7d43aa36675596050ccbe06831f1724d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477681"
---
# <a name="planned-orders-are-generated-for-in-stock-with-production-orders"></a>Planerade order skapas för i lager med produktionsorder

## <a name="symptoms"></a>Symtom

Planerade order skapas trots att det redan finns artiklar i lager- och produktionsorder för dem.

## <a name="resolution"></a>Lösning

Du kanske kan åtgärda det här problemet genom att öka värdet för **Positiva dagar** för relevanta grupper på sidan **Disponeringsgrupp**. Den här ändringen gör att systemet avgör om lagerbehållning kan användas för efterfrågan. Sedan genereras en ny planerad order för de artiklar som finns i lager.
