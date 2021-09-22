---
title: ID-nummer måste anges för den här platsen
description: Om du får det här felmeddelandet när du skapar en överföringsorder för ett WMS-aktiverat lagerställe är fältet Standardinleveransplats tomt för ett transitlager.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2e562ad2b41dd149f215adc83bd2d54e55dccc05
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477599"
---
# <a name="license-plate-specification-error-when-confirming-shipment-for-a-transfer-order"></a>Fel ID-nummerspecifikation när du bekräftar leverans för en överföringsorder

## <a name="symptoms"></a>Symtom

Om du skapar en överföringsorder med hjälp av ett lagerställe som har aktiverats WMS (avancerad lagerstyrning) och du sedan försöker bekräfta leveransen när arbetet har slutförts kan du få följande felmeddelande.

> Registreringsskylten måste anges för den här platsen.

## <a name="cause"></a>Orsak

Det inträffar eftersom fältet **Standardinleveransplats** är tomt för ett transitlager för "från"-lagerstället.

## <a name="resolution"></a>Lösning

Du åtgärdar det här problemet genom att ange en standard inleveransplats i transitlagret. Kontrollera att den här platsen är ID-nummerstyrd
