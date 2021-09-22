---
title: Lastvikt kan endast innehålla positiva tal
description: När du bearbetar arbetet mellan platser kan det visas ett felmeddelande om att lastvikten och uppdateringen annulleras. Följ stegen nedan för att åtgärda problemet.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8ea1f6679a521e3e8683b8e5f18f509e98044414
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477620"
---
# <a name="load-weight-error-and-update-canceled-when-processing-work-between-locations"></a>Lastviktsfel och uppdatering avbruten vid bearbetning av arbete mellan platser

## <a name="symptoms"></a>Symtom

Om det finns öppet arbete när du bearbetar arbete från packningsplatser till mellanlagringsplatser, eller från mellanlagring till lastkajsplatser, kan du få följande felmeddelande:

> Fältet Lastvikt(=-%1) kan endast innehålla positiva tal. Uppdateringen har avbrutits.

## <a name="resolution"></a>Lösning

Du löser det här problemet genom att gå till **Systemadministration \> Periodiska uppgifter \> Databas \> Konsekvenskontroll** och köra processen för **Konsekvenskontroll för lagerplatsstatus**.
