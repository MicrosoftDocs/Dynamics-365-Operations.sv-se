---
title: Inte tillräckligt med arbete hittades för kluster efter konfigurering av profil
description: Om du konfigurerar en klusterprofil kan du få ett felmeddelande om att det inte går att hitta tillräckligt med arbete. Redigera profilen och ställ in Aktivera positioner till Nej.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 139fd72e571c8ef83af2fd0e497cf334b6ef0ea4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477598"
---
# <a name="not-enough-work-found-for-cluster-when-using-system-directed-cluster-picking"></a>Inte tillräckligt med arbete hittades för kluster när Systemdirigerad klusterplockning används

## <a name="symptoms"></a>Symtom

När du använder processen *Systemdirigerad klusterplockning* om du konfigurerar en klusterprofil där till exempel 10 positioner kan väljas, fungerar processen som planerat när det finns tillräckligt med arbete för att välja till 10 positioner. Om det bara finns åtta positioner att plocka visas följande felmeddelande:

> Det finns inte tillräckligt med arbete för kluster.

## <a name="resolution"></a>Lösning

Åtgärda problemet genom att redigera klusterprofilen och ställa in alternativet **Aktivera positioner** på *Nej*.
