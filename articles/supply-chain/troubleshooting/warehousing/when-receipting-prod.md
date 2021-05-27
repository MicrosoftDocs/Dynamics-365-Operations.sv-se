---
title: Endast en etikett skrivs ut för flera arbetsrubriker på ett enda kvitto
description: Endast en etikett skrivs ut för flera arbetsrubriker på ett enda kvitto.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026914"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a>Endast en etikett skrivs ut för flera arbetsrubriker på ett enda kvitto

KB-nummer: 4614667

## <a name="symptoms"></a>Symtom

Flera arbetsrubriker skapas för samma mål-ID-nummer som en del av en enda mottagningshändelse för distributionslagerapp. Endast en ID-nummersetikett skrivs dock ut när produkten tas emot.

## <a name="resolution"></a>Upplösning

Systemet beter sig som det är utformat.

I den aktuella designen genereras alltid en enda ID-nummersetikett, oavsett antalet kombinationer av arbetsrubriker och arbetsrader som finns. Den genererade etiketten innehåller informationen för endast en kombination.

För att lösa problemet kontrollerar du att skapandet av arbetsrubriker alltid mappas till bara ett mål-ID-nummer.
