---
title: Rensningjobbet för försäljningsuppdateringshistorik misslyckas eller har prestandaproblem
description: Batchjobbet för rensning av försäljningshistorik kan misslyckas eller ta mycket lång tid om det finns stora mängder försäljningsuppdateringsdata.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 371a8c7178cd7c5091d6dd9a91d0ee03b943a269
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103198"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Rensningjobbet för försäljningsuppdateringshistorik misslyckas eller har prestandaproblem

## <a name="symptoms"></a>Symtom

Batchjobbet för **Rensning av försäljningsuppdateringshistorik** misslyckas eller har prestandaproblem.  

## <a name="cause"></a>Orsak

Detta kan inträffa när ditt system omfattar ett stort antal försäljningsuppdateringar, vilket kan leda till en stor mängd försäljningsuppdateringsdata. Rensningsjobbet försöker rensa alla dessa data i en enda transaktion. Detta innebär att jobbet kan ta mycket lång tid att köra eller till och med misslyckas.

## <a name="resolution"></a>Lösning

En ny version av batchjobbet **Rensning av försäljningsuppdateringshistorik** finns för Supply Chain Management version 10.0.19 och högre. Den här funktionen är inte aktiverad som standard. Mer information om hur funktionen fungerar och hur du aktiverar den i funktionshanteringen finns i [Förbättringar i rensningsprestanda för försäljningshistorik](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

