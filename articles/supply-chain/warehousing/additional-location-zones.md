---
title: Ytterligare platszoner
description: Det här ämnet ger en översikt över de nya platszoner som har lagts till i Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 07/01/2020
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
ms.openlocfilehash: ee6e0b824ff16bf757159da5198a4215f4f5d121
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808952"
---
# <a name="additional-location-zones"></a>Ytterligare platszoner

[!include [banner](../includes/banner.md)]

Tre nya zonfält finns tillgängliga i Microsoft Dynamics 365 Supply Chain Management. Lagerchefer kan använda dem för att definiera ytterligare lagerorganisationer eller layouter. De nya zonfälten kan ställas in antingen manuellt eller med hjälp guiden **platsinställning**. De kan användas i alla frågor eller filter som använder tabellen lagerställen.

Det krävs inga ytterligare inställningar för att använda zonfälten.

## <a name="turn-on-the-additional-location-zone-feature"></a>Aktivera funktionen ytterligare platszoner

Innan du kan använda funktionen *Ytterligare platszon* den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *Ytterligare platszon*

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