---
title: Dimensionsplatsen kan inte vara tom om serienummer har ställts in
description: Om du får det här felmeddelandet när du bekräftar en leverans efter att en överföringsorder har skapas för en seriell artikel, är fältet Standardinleveransplats tomt.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6f58c72438d5d1d93e59e46525debd65d44d9a76
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477668"
---
# <a name="error-when-confirming-shipment-after-creating-a-transfer-order-for-a-serial-item"></a>Fel vid bekräftelse av leverans efter att en överföringsorder för en serieartikel har skapas

## <a name="symptoms"></a>Symtom

Det här felmeddelandet visas om du skapar en överföringsorder för varor med serienummer med hjälp av ett lagerställe som har aktiverats för WMS (avancerad lagerstyrning) och du sedan försöker bekräfta leveransen när arbetet har slutförts.

> Dimensionsplatsen kan inte vara tom om dimensionsserienummer har ställts in.

## <a name="cause"></a>Orsak

Det inträffar eftersom fältet **Standardinleveransplats** är tomt för ett transitlager för "från"-lagerstället.

## <a name="resolution"></a>Lösning

Du åtgärdar det här problemet genom att ange en standard inleveransplats i transitlagret. Kontrollera att den här platsen är ID-nummerstyrd
