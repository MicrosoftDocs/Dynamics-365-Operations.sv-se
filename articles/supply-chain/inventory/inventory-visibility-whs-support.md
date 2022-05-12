---
title: Inventory Visibility-stöd för WHS-artiklar
description: Detta ämne beskriver stöd för Lagersynlighet för artiklar som har aktiverats för avancerade lagerstyrningsprocesser (lagerstyrda artiklar).
author: yufeihuang
ms.date: 03/10/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: cfbff05697f4159cb74d110887b8029f28fbf96b
ms.sourcegitcommit: 1050e58e621d9a0454895ed07c286936f8c03320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2022
ms.locfileid: "8625410"
---
# <a name="inventory-visibility-support-for-whs-items"></a>Inventory Visibility-stöd för WHS-artiklar

[!include [banner](../includes/banner.md)]

Detta ämne beskriver stöd för Lagersynlighet för artiklar som har aktiverats för avancerade lagerstyrningsprocesser (lagerstyrda artiklar). Den funktion som lägger till den här kapaciteten i Lagersynlighet kallas *Avancerad lagerstyrning*.

## <a name="whs-items"></a>Lagerstyrda artiklar

En lagerstyrd artikel är en artikel som är aktiverad för avancerade lagerprocesser (WHS) och bearbetas på ett lager som också är lagerstyrt.

För mer information om lagerstyrning och modulen **Warehouse Management** i Microsoft Dynamics 365 Supply Chain Management, se [Warehouse Management – översikt](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>Definitionsområde för funktionen

Den avancerade lagerstyrningsfunktionen för lagersynlighet fokuserar på beräkningar av lagerbehållningskvantitet som baseras på lagerbehållningsfrågor. Funktionen ska inte användas för att använda lagersynlighet för att hantera bearbetningsaktiviteter för lagerställen i allmänhet. Lagersynlighet innebär inte att lagerställespecifika koncept exponeras för användarna. Här följer några exempel på dessa koncept:

- Reservationshierarki
- Oavsett om en artikel eller ett lager är lagerstyrt 
- Enhetssekvensgrupp-ID
- Lagerställespecifika processer, t.ex. leveranser, lastning, påfyllnader och arbete

Informationen bygger på de data som skickas från Supply Chain Management. Lagerstyrningsspecifika data (d.v.s. data från `WHSInventReserve` registret) är inte synliga för användarna.

När du använder den avancerade lagerstyrningsfunktionen för lagersynlighet blir alla frågeresultat identiska med resultaten från frågor som görs direkt i Supply Chain Management. De kommer dock inte att vara identiska med resultaten från frågor som görs med hjälp av mobilappen Warehouse Management, eftersom mobilappen använder något olika beräkningslogik.

## <a name="when-to-use-the-feature"></a>När ska du använda funktionen

Vi rekommenderar att du använder den avancerade lagerstyrningsfunktionen för lagersynlighet i scenarier där alla följande villkor uppfylls:

- Du synkroniserar data i Supply Chain Management med lagersynlighet.
- Du använder lagerstyrning i Supply Chain Management.
- Användare gör reservationer för lagerstyrningsartiklar på andra nivåer än lagerställenivån (eftersom du till exempel använder lagerarbete).

I andra scenarier är resultaten av behållningsfrågan desamma, oavsett om den avancerade lagerstyrningsfunktionen är aktiverad eller inte. Dessutom blir prestandan bättre om du inte aktiverar funktionen i dessa scenarier eftersom det finns färre beräkningar och mindre omkostnader.

## <a name="enable-the-advanced-whs-feature-for-inventory-visibility"></a>Aktivera den avancerade lagerstyrningsfunktionen för lagersynlighet

Den aktivera den avancerade lagerstyrningsfunktionen för lagersynlighet, följ dessa steg.

1. Logga in i Supply Chain Management som administratör.
1. Öppna till arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera följande funktioner i denna ordning:

    1. *Integrering av lagersynlighet*
    1. *Aktivera lagerartiklar i lagersynlighet*

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för integrering av lagersynlighet**.
1. På fliken **Aktivera lagerstyrningsartiklar** anger du alternativet **Aktivera lagerstyrningsartiklar** till *Ja*.
1. Logga in i Power Apps.
1. Öppna sidan **Konfiguration** och sedan på fliken **Funktionshantering** aktivera funktionen *AdvancedWHS*.
1. I Supply Chain Management, gå till **Lagerhantering \> Periodiska uppgifter \> Integrering av lagersynlighet**.
1. I åtgärdsfönstret väljer du **Inaktivera** om du tillfälligt vill inaktivera Lagersynlighet.
1. I åtgärdsfönstret, välj **Aktivera** för att återaktivera lagersynlighet. Tillägget läses in igen och den nya funktionen aktiveras nu. Dina lager lagerstyrningsrelaterade data börjar synkroniseras med Lagersynlighet.

## <a name="query-on-hand-quantities-of-whs-items"></a>Fråga lagerhållningskvantiteter av WHS-artiklar

För att fråga efter WHS-artiklar använder du samma [API (Application Programming Interface) och meddelandesyntax](inventory-visibility-api.md) som du använder för icke-WHS-artiklar. Du behöver inte ange om en artikel är en WHS-artikel eller en icke-WHS-artikel. Lagersynlighet särskiljer automatiskt artiklar, baserat på lagrade data.

Resultaten från förfrågningar om WHS-artiklar är i huvudsak desamma som resultaten för icke-WHS-artiklar. Den enda skillnaden är att följande fysiska mått från `fno` datakällan beräknas baserat på WHS-logik i Supply Chain Management:

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Alla andra fysiska mått beräknas på samma sätt som när den avancerade lagerstyrningsfunktionen för lagersynlighet inaktiveras.

Detaljerad information om hur lagerhållningsberäkningar för hur WHS-artiklar fungerar finns i dokumentet [Reservationer i Warehouse Management](https://www.microsoft.com/download/details.aspx?id=43284).

De dataenheter som exporteras till Dataverse kan ännu inte uppdatera kvantiteterna för WHS-artiklar. De kvantiteter som visas i dataenheterna är korrekta både för icke-WHS-artiklar och för kvantiteter som inte påverkas av WHS-logik (d.v.s. mått förutom `AvailPhysical`, `AvailOrdered`, `ReservPhysical` och `ReservOrdered` i `fno` datakällan).

Ändringar av WHS-artikelkvantiteter som lagras i datakällan för Supply Chain Management är förbjudna. Vad gäller andra funktioner för lagersynlighet tillämpas den här begränsningen för att förhindra konflikter.

## <a name="soft-reservations-on-whs-items-in-inventory-visibility"></a>Mjuka reservationer på WHS-artiklar i Lagersynlighet

I allmänhet stöds [mjuka reservationer](inventory-visibility-reservations.md) av WHS-artiklar. Du kan inkludera WHS-relaterade fysiska måtten i beräkningar av mjuk reservation. 

I en känd begränsning, stöds beräkningen *tillgängligt för reservation* för närvarande inte för WHS-artiklar. Om det finns reservationer över de aktuella dimensionerna där en mjuk reservation uppstår, blir därför beräkningen *tillgänglig för reservation* fel. Mjuk reservationer kommer inte att påverkas när alternativet **ifCheckAvailForReserv** är inaktiverat i [mjuk reservation API](inventory-visibility-api.md#create-one-reservation-event).

Denna begränsning gäller även för funktioner och anpassningar som baseras på mjuk reservationer (till exempel allokering).

## <a name="calculate-available-to-promise-quantities"></a>Beräkna kvantiteter som är tillgängliga att lova

Lösningen ger stöd för [disponibelt att lova (ATP)](inventory-visibility-available-to-promise.md) frö WHS-artiklar. Du kan definiera ATP-beräkningar utan att behöva oroa dig över WHS-specificerade detaljer.
