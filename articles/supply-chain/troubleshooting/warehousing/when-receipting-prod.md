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
ms.openlocfilehash: cf307964a07c2b69eb5e4ef2cf9dc094482736d0970e333e84f674c9be6331c7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740537"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a>Endast en etikett skrivs ut för flera arbetsrubriker på ett enda kvitto

KB-nummer: 4614667

## <a name="symptoms"></a>Symtom

Flera arbetsrubriker skapas för samma mål-ID-nummer som en del av en enda mottagningshändelse för distributionslagerapp. Endast en ID-nummersetikett skrivs dock ut när produkten tas emot.

## <a name="resolution"></a>Upplösning

Systemet beter sig som det är utformat.

I den aktuella designen genereras alltid en enda ID-nummersetikett, oavsett antalet kombinationer av arbetsrubriker och arbetsrader som finns. Den genererade etiketten innehåller informationen för endast en kombination.

För att lösa problemet kontrollerar du att skapandet av arbetsrubriker alltid mappas till bara ett mål-ID-nummer.
