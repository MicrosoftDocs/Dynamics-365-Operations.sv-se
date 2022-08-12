---
title: Inventory Visibility-stöd för WMS-artiklar
description: Denna artikel beskriver stöd för Lagersynlighet för artiklar som har aktiverats för lagerstyrningsprocesser (WMS-artiklar).
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
ms.openlocfilehash: 54ce637d2d7b590988f7590eae5248276bcc4b96
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066623"
---
# <a name="inventory-visibility-support-for-wms-items"></a>Inventory Visibility-stöd för WMS-artiklar

[!include [banner](../includes/banner.md)]

Denna artikel beskriver stöd för Lagersynlighet för artiklar som har aktiverats för lagerstyrningsprocesser (WMS). Den funktion som lägger till denna kapacitet i Lagersynlighet kallas *Avancerat WMS*.

## <a name="wms-items"></a>WMS-artiklar

En WMS artikel är en artikel som aktiverats för WMS och bearbetas på ett lagerställe som också aktiverats för WMS.

För mer information om WMS och modulen **Warehouse Management** i Microsoft Dynamics 365 Supply Chain Management, se [Warehouse Management – översikt](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>Definitionsområde för funktionen

Den avancerade WMS-funktionen för lagersynlighet fokuserar på beräkningar av lagerbehållningskvantitet som baseras på lagerbehållningsfrågor. Funktionen ska inte användas för att använda lagersynlighet för att hantera bearbetningsaktiviteter för lagerställen i allmänhet. Lagersynlighet innebär inte att lagerställespecifika koncept exponeras för användarna. Här följer några exempel på dessa koncept:

- Reservationshierarki
- Huruvida en artikel eller ett lager är WMS-aktiverat
- Enhetssekvensgrupp-ID
- Lagerställespecifika processer, t.ex. leveranser, lastning, påfyllnader och arbete

Informationen bygger på de data som skickas från Supply Chain Management. WMS-specifika data (d.v.s. data från `WHSInventReserve`-tabellen) är inte synliga för användarna.

När du använder den avancerade WMS-funktionen för lagersynlighet blir alla frågeresultat identiska med resultaten från frågor som görs direkt i Supply Chain Management. De kommer dock inte att vara identiska med resultaten från frågor som görs med hjälp av mobilappen Warehouse Management, eftersom mobilappen använder något olika beräkningslogik.

## <a name="when-to-use-the-feature"></a>När ska du använda funktionen

Vi rekommenderar att du använder den avancerade WMS-funktionen för Lagersynlighet i scenarier där alla följande villkor uppfylls:

- Du synkroniserar data i Supply Chain Management med lagersynlighet.
- Du använder WMS i Supply Chain Management.
- Användare gör reservationer för WMS-artiklar på andra nivåer än lagerställenivån (eftersom du till exempel använder lagerarbete).

I andra scenarier är resultaten av behållningsfrågan desamma, oavsett om den avancerade WMS-funktionen för lagersynlighet är aktiverad eller inte. Dessutom blir prestandan bättre om du inte aktiverar funktionen i dessa scenarier eftersom det finns färre beräkningar och mindre omkostnader.

## <a name="enable-the-advanced-wms-feature-for-inventory-visibility"></a>Aktivera den avancerade WMS-funktionen för lagersynlighet

Följ dessa steg för att aktivera den avancerade WMS-funktionen för lagersynlighet.

1. Logga in i Supply Chain Management som administratör.
1. Öppna till arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera följande funktioner i denna ordning:

    1. *Integrering av lagersynlighet*
    1. *Aktivera lagerartiklar i lagersynlighet*

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för integrering av lagersynlighet**.
1. På fliken **Aktivera WMS-artiklar** anger du alternativet **Aktivera WMS-artiklar** som *Ja*.
1. Logga in i Power Apps.
1. Öppna sidan **Konfiguration** och sedan på fliken **Funktionshantering** aktivera funktionen *AdvancedWHS*.
1. I Supply Chain Management, gå till **Lagerhantering \> Periodiska uppgifter \> Integrering av lagersynlighet**.
1. I åtgärdsfönstret väljer du **Inaktivera** om du tillfälligt vill inaktivera Lagersynlighet.
1. I åtgärdsfönstret, välj **Aktivera** för att återaktivera lagersynlighet. Tillägget läses in igen och den nya funktionen aktiveras nu. Dina WMS-relaterade data börjar synkroniseras med Lagersynlighet.

## <a name="query-on-hand-quantities-of-wms-items"></a>Fråga lagerhållningskvantiteter av WMS-artiklar

För att fråga efter WMS-artiklar använder du samma [API (Application Programming Interface) och meddelandesyntax](inventory-visibility-api.md) som du använder för icke-WMS-artiklar. Du behöver inte ange om en artikel är en WMS-artikel eller en icke-WMS-artikel. Lagersynlighet särskiljer automatiskt artiklar, baserat på lagrade data.

Resultaten från förfrågningar om WMS-artiklar är i huvudsak desamma som resultaten för icke-WMS-artiklar. Den enda skillnaden är att följande fysiska mått från `fno` datakällan beräknas baserat på WMS-logik i Supply Chain Management:

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Alla andra fysiska mätvärden beräknas på samma sätt som när den avancerade WMS-funktionen för Lagersynlighet inaktiveras.

Detaljerad information om hur lagerhållningsberäkningar för hur WMS-artiklar fungerar finns i dokumentet [Reservationer i Warehouse Management](https://www.microsoft.com/download/details.aspx?id=43284).

De dataenheter som exporteras till Dataverse kan ännu inte uppdatera kvantiteterna för WMS-artiklar. De kvantiteter som visas i dataenheterna är korrekta både för icke-WMS-artiklar och för kvantiteter som inte påverkas av WMS-logik (d.v.s. mått förutom `AvailPhysical`, `AvailOrdered`, `ReservPhysical` och `ReservOrdered` i `fno` datakällan).

Ändringar av WMS-artikelkvantiteter som lagras i datakällan för Supply Chain Management är förbjudna. Vad gäller andra funktioner för lagersynlighet tillämpas den här begränsningen för att förhindra konflikter.

## <a name="soft-reservations-on-wms-items-in-inventory-visibility"></a>Mjuka reservationer på WMS-artiklar i Lagersynlighet

I allmänhet stöds [mjuka reservationer](inventory-visibility-reservations.md) av WMS-artiklar. Du kan inkludera WMS-relaterade fysiska måtten i beräkningar av mjuk reservation. 

I en känd begränsning, stöds beräkningen *tillgängligt för reservation* för närvarande inte för WMS-artiklar. Om det finns reservationer över de aktuella dimensionerna där en mjuk reservation uppstår, blir därför beräkningen *tillgänglig för reservation* fel. Mjuk reservationer kommer inte att påverkas när alternativet **ifCheckAvailForReserv** är inaktiverat i [mjuk reservation API](inventory-visibility-api.md#create-one-reservation-event).

Denna begränsning gäller även för funktioner och anpassningar som baseras på mjuk reservationer (till exempel allokering).

## <a name="calculate-available-to-promise-quantities"></a>Beräkna kvantiteter som är tillgängliga att lova

Lösningen ger stöd för [disponibelt att lova (ATP)](inventory-visibility-available-to-promise.md) frö WMS-artiklar. Du kan definiera ATP-beräkningar utan att behöva oroa dig över WMS-specificerade detaljer.
