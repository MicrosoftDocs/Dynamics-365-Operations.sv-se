---
title: Artikelsampling för kvalitetshantering
description: I det här avsnittet beskrivs hur du ställer in artikelsampling.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae8bfd329ca0d7c30adcd93a759ee6bea7b76278
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022238"
---
# <a name="quality-management-item-sampling"></a>Artikelsampling för kvalitetshantering

Artikelsampling används som en del av en kvalitetsassociation. Den definierar mängden aktuellt fysiskt lager som måste inspekteras. Samplingen kan baseras på fasta kvantiteter, en procentsats eller komplett registreringsskylt.

## <a name="set-up-item-sampling"></a>Ställ in artikelsampling

Följ dessa steg för att konfigurera artikelsamplingen:

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Artikelsampling**.
1. Välj **Ny**.
1. Ange ett värde i fältet **Artikelsampling**.
1. I fältet **Beskrivning** anger du ett värde.
1. Ange ett nummer i fältet **Värde**. Detta värde är relaterat till det värde för kvantitetsspecifikation som valts i fältet bredvid.
1. I avsnittet **Process** väljer du kryssrutan **Fullständig spärr** om hela partiet eller kvantiteten på orderraden ska spärras om ett test skulle misslyckas. Om denna kryssruta avmarkeras blockeras bara artiklarna i kvalitetsordern om ett test misslyckas.
1. Välj **Spara**.
1. Stäng sidan.

> [!NOTE]
> Funktionen *Kvalitetshantering för lagerprocesser* omfattar ytterligare funktioner för artikelsampling. Det lägger till ett koncept för *artikelsamplingens omfång* och låter dig definiera en fullständig licensskylt som kvantitetspecifikation. Om du har aktiverat denna funktion, se [Kvalitetshantering för lagerprocesser](quality-management-for-warehouses-processes.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
