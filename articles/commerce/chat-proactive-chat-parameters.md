---
title: Commerce-chattmodulens proaktiva chattparametrar
description: Den här artikeln beskriver de förebyggande chattparametrarna för Commerce-chattmoduler i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: f3cff89a25ff84414e7fdd32cbb26404c2080187
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691103"
---
# <a name="commerce-chat-module-proactive-chat-parameters"></a>Commerce-chattmodulens proaktiva chattparametrar

[!include [banner](includes/banner.md)]

I den här artikeln beskrivs parametrarna för förebyggande chatt i Commerce-chatten med Flerkanal för Customer Service och Chatta i Commerce med Power Virtual Agents-moduler i Microsoft Dynamics 365 Commerce.

## <a name="proactive-chat-properties"></a>Egenskaper för proaktiva chatt

De proaktiva chattegenskaperna finns i egenskapsrutan i Chatta i Commerce med Flerkanal för Customer Service och Chatta i Commerce med Power Virtual Agents moduler i Commerce-webbplatsbyggaren.

> [!NOTE]
> Som standard är alla egenskaper för förebyggande chatt som anges här tomma. Vi rekommenderar att du lära dig mer om de här egenskaperna och bara ställer in dem efter behov. Det här minimerar felaktiga förebyggande chattar från utlösta.

### <a name="proactive-chat"></a>Proaktiv chatt

| Eget namn | Beskrivning | Standardvärde |
|---------------|-------------|---------------|
| Aktiverad | Arbeta i förebyggande syfte med kunder baserat på olika utlösare. | Inaktiverade |
| Chatthälsning | Det hälsningsmeddelande som används när en förebyggande chatt har utlösts. | Tom |

### <a name="wait-time-proactive-chat"></a>Väntetid (Proaktiv chatt)

| Eget namn | Beskrivning |
|---------------|-------------|
| Väntetid (sek) | Den tid (i sekunder) som webbplatsanvändare ägnar åt på en webbplatssida innan en förebyggande chatt utlöses. |
| Chatthälsning | Det hälsningsmeddelande som används när en förebyggande chatt har utlösts. |

### <a name="number-of-page-visits-proactive-chat"></a>Antal sidbesök (förebyggande chatt)

| Eget namn | Beskrivning |
|---------------|-------------|
| Antal sidbesök | Antalet sidbesök innan en förebyggande chatt initieras. Webbplatsanvändare måste först acceptera prompten i bannern för godkännande. |
| Chatthälsning | Det hälsningsmeddelande som används när en förebyggande chatt har utlösts. |

### <a name="specific-pages-proactive-chat"></a>Specifika sidor (Förebyggande chatt)

| Eget namn | Beskrivning |
|---------------|-------------|
| Sida | En lista med sidor som utlöser en förebyggande chatt när de besöks. |
| Chatthälsning | Det hälsningsmeddelande som används när en förebyggande chatt har utlösts. |

### <a name="from-specific-pages-proactive-chat"></a>Från specifika sidor (Förebyggande chatt)

| Eget namn | Beskrivning |
|---------------|-------------|
| Sida | En lista med sidor som utlöser en förebyggande chatt när användare navigerar bort från dem. |
| Chatthälsning | Det hälsningsmeddelande som används när en förebyggande chatt har utlösts. |

### <a name="specific-countryregion-proactive-chat"></a>Specifikt land/område (förebyggande chatt)

| Eget namn | Beskrivning |
|---------------|-------------|
| Landskod | Användare som besöker från angivna länder eller regioner utlöser en förebyggande chatt. Lands-/regionkoder ska vara två versaler (till exempel **USA**). |
| Chatthälsning | Det hälsningsmeddelande som används när en förebyggande chatt har utlösts. |

### <a name="date-range-proactive-chat"></a>Datumintervall (förebyggande chatt)

| Eget namn | Beskrivning |
|---------------|-------------|
| Startdatum (dd/mm/yyy) | Datumet då en förebyggande chatt utlöses. |
| Slutdatum (dd/mm/yyy) | Datumet då eller före en förebyggande chatt utlöses. |
| Chatthälsning | Det hälsningsmeddelande som används när en förebyggande chatt har utlösts. |

### <a name="total-amount-in-cart-proactive-chat"></a>Totalt belopp i kundvagnen (förebyggande chatt)

| Eget namn | Beskrivning |
|---------------|-------------|
| Minimum | Det minsta monetära beloppet (inklusive) i shoppingvagnen som utlöser en förebyggande chatt när användarna besöker vagnsidan. |
| Maximum | Det högsta monetära beloppet (inklusive) i shoppingvagnen som utlöser en förebyggande chatt när användarna besöker vagnsidan. |
|Chatthälsning | Det hälsningsmeddelande som används när en förebyggande chatt har utlösts. |

### <a name="total-number-of-items-in-cart-proactive-chat"></a>Totalt antal artiklar i vagnen (förebyggande chatt)

| Eget namn | Beskrivning |
|---------------|-------------|
| Minimum | Det minsta antalet artiklar (inklusive) i shoppingvagnen som utlöser en förebyggande chatt när användarna besöker vagnsidan. |
| Maximum | Det högsta antalet artiklar (inklusive) i shoppingvagnen som utlöser en förebyggande chatt när användarna besöker vagnsidan. |
| Chatthälsning | Det hälsningsmeddelande som används när en förebyggande chatt har utlösts. |

### <a name="specific-products-in-cart-proactive-chat"></a>Specifika produkter i kundvagnen (Förebyggande chatt)

| Eget namn | Beskrivning |
|---------------|-------------|
| Produkter ID/SKU | En lista med produkt-/lagerhållningsenhetsnummer (SKU) som utlöser en förebyggande chatt när användarna besöker vagnsidan. |
| Chatthälsning | Det hälsningsmeddelande som används när en förebyggande chatt har utlösts. |

## <a name="additional-resources"></a>Ytterligare resurser

[Funktioner för Commerce-chatt](commerce-chat-overview.md)

[Chatta i Commerce med modulen Flerkanal för Customer Service](commerce-chat-module.md)

[Commerce-chatt med Power Virtual Agents modul](chat-module-pva.md)
