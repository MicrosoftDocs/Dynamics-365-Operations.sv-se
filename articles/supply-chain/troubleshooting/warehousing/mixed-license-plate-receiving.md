---
title: Inleverans av blandat ID-nummer fungerar för alla dispositionskoder
description: När fältet Åtgärd för en dispositionskod är inställd på Kredit eller Kassation kan du bara använda emnyartikeln Inleverans av blandat ID-nummer för att behandla returnerade artiklar.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b762255bc5ef6a1e15688a9c635940e92e67db3c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477657"
---
# <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-but-credit"></a>Inleverans av blandat ID-nummer fungerar endast för dispositionskoden Kredit

## <a name="symptoms"></a>Symtom

När fältet **Åtgärd** för en dispositionskod är inställd på *Kredit* eller *Kassation* kan du bara använda emnyartikeln [Inleverans av blandat ID-nummer](/dynamics365/supply-chain/warehousing/mixed-license-plate-receiving) för att behandla returnerade artiklar.

## <a name="resolution"></a>Lösning

Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning. För närvarande kan endast [dispositionskoder](/dynamics365/supply-chain/service-management/set-up-disposition-codes) där fältet **Åtgärd** anges till *Kredit* eller *Kassation* stöds för mottagning av blandade registreringsskyltar.
