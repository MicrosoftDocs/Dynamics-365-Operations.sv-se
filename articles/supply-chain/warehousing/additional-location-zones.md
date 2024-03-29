---
title: Ytterligare platszoner
description: Denna artikel ger en översikt över de nya platszoner som har lagts till i Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 819330e0f6e6cd419da441f919d68ff996b6475c
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336528"
---
# <a name="additional-location-zones"></a>Ytterligare platszoner

[!include [banner](../includes/banner.md)]

Tre nya zonfält finns tillgängliga i Microsoft Dynamics 365 Supply Chain Management. Lagerchefer kan använda dem för att definiera ytterligare lagerorganisationer eller layouter. De nya zonfälten kan ställas in antingen manuellt eller med hjälp guiden **platsinställning**. De kan användas i alla frågor eller filter som använder tabellen lagerställen.

Det krävs inga ytterligare inställningar för att använda zonfälten.

## <a name="turn-the-additional-location-zone-feature-on-or-off"></a>Aktivera eller inaktivera funktionen ytterligare platszoner

Innan du kan använda funktionen måste den aktiveras i ditt system. Från och med version 10.0.25 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.29 version av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.29 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Ytterligare platszoner* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="use-location-zones"></a>Använda platszoner

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Guide för platsinställning**.
2. Ange följande värden.

    - I fältet **Lagerställe**, välj _62_.
    - I fältet **Zon-ID** välj _FLOOR_.
    - I fältet **Ytterligare Zon 1** välj _PICKZONE1_.
    - I fältet **Ytterligare Zon 2** välj _WEBSHOP1_.
    - I fältet **Platsprofil-ID**, välj _FLOOR_.

3. Välj rad **Våning**.
4. I fältet **Från nummer**, ange _1_. I fältet **Till nummer**, ange _3_.
5. Välj rad **Gång**.
6. I fältet **Från nummer**, ange _1_. I fältet **Till nummer**, ange _5_.
7. Markera **Skapa**.
8. Du får meddelanden om att nya platser har lagts till. Välj knappen **Visa meddelanden** om du vill visa meddelandena.
9. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**. De nya platserna visas i listan och alla zonfält är tillgängliga (det vill säga det befintliga zonfältet och de nya ytterligare zonfälten).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]