---
title: Standardbeskrivningar för redovisningen
description: Standardbeskrivningar kan användas för att uppdatera beskrivningsfältet i verifikationsbokföring i redovisningen.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f95dff3a77a552d5788d813b3d13dc30579be715
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695719"
---
# <a name="default-descriptions-for-the-general-ledger"></a>Standardbeskrivningar för redovisningen

[!include [banner](../../includes/banner.md)]

Standardbeskrivningar kan användas för att uppdatera fältet **beskrivning** i verifikationsbokföring i redovisningen. Den här funktionen har förbättrats så att den fungerar med hemtagningskostnad.

För att ställa in standardbeskrivningar för bokföringsbokningar, gå till **Organisationsadministration \> Inställning \> Standardbeskrivningar**.

I följande tabell listas de nya värden som har lagts till för fältet **Beskrivning** på sidan **Standardbeskrivningar** som stöd för hemtagningskostnad.

| Beskrivningstyp | Anteckningar |
|---|---|
| Importera kostnadsredovisning – periodisering av kostnader | När en inköpsorderfaktura bokförs bearbetas en periodisering av kostnader för uppskattade färdkostnader. Standardbeskrivningar kan anges om du vill lägga till färdnumret i beskrivningen. Använd *%4* för försändelsenumret. |
| Importkostnadsredovisning – order för varor på väg | Om du använder bearbetning av varor på väg bokförs inköpsorderfakturan och varorna bokförs till ett konto för varor på väg. Standardbeskrivningar kan anges om du vill lägga till nummer för order för varor på väg i beskrivningen. Används *%4* för nummer för order för varor på väg. |
| Lager - Stängning - Justering | När leverantörsreskontrafakturan (AP) bearbetas för en färdkostnad bearbetas en lagerjustering för att uppskatta färdkostnader. Standardbeskrivningar kan anges om du vill lägga till färdnumret i beskrivningen. Använd *%4* för försändelsenumret. |

Mer information om hur du arbetar med sidan **Standardbeskrivningar**, se [Ställ in standardbeskrivningar för automatisk bokföring](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).
