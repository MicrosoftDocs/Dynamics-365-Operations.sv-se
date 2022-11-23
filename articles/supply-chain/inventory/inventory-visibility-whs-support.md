---
title: Inventory Visibility-stöd för WMS-artiklar
description: Denna artikel beskriver stöd för Lagersynlighet för artiklar som har aktiverats för lagerstyrningsprocesser (WMS-artiklar).
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: bed402ecf20c19e81b2687efd90dba600460971a
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762765"
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

Vi rekommenderar att du använder WMS-funktionen för Lagersynlighet i scenarier där alla följande villkor uppfylls:

- Du synkroniserar data i Supply Chain Management med lagersynlighet.
- Du använder WMS i Supply Chain Management.
- Användare gör reservationer för WMS-artiklar på andra nivåer under lagerställenivån (t.ex. nivå för registreringsskylt eftersom du använder lagerarbete).

I andra scenarier är resultaten av behållningsfrågan desamma, oavsett om den avancerade WMS-funktionen för lagersynlighet är aktiverad eller inte. Dessutom blir prestandan bättre om du inte aktiverar funktionen i dessa scenarier eftersom det finns färre beräkningar och mindre omkostnader.

## <a name="enable-the-wms-feature-for-inventory-visibility"></a>Aktivera den WMS-funktionen för lagersynlighet

Följ dessa steg för att aktivera WMS-funktionen för lagersynlighet.

1. Logga in i Supply Chain Management som administratör.
1. Öppna till arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera följande funktioner i denna ordning:

    1. *Integrering av lagersynlighet*
    1. *Aktivera lagerartiklar i lagersynlighet*

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för integrering av lagersynlighet**.
1. På fliken **Aktivera WMS-artiklar** anger du alternativet **Aktivera WMS-artiklar** som *Ja*.
1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
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

Alla andra fysiska mätvärden beräknas på samma sätt som när WMS-funktionen för Lagersynlighet inaktiveras.

Detaljerad information om hur lagerhållningsberäkningar för hur WMS-artiklar fungerar finns i dokumentet [Reservationer i Warehouse Management](https://www.microsoft.com/download/details.aspx?id=43284).

## <a name="on-hand-list-view-and-data-entity-for-wms-items"></a>Behållningslistevy och dataenhet för WMS-artiklar

Sidan **Förinläsa sammanfattning av lagersynlighet** ger en vy av entiteten *Behållningsindex av förinläsning av frågeresultat*. Till skillnad från entiteten *lagersammanfattning* ger entiteten *Behållningsindex av förinläsning av frågeresultat* en tillgänglig inventeringslista för produkter tillsammans med valda dimensioner. Lagersynlighet synkroniserar de förinlästa sammanfattningsdata var 15:e minut.

Om du använder lagersynlighet med WMS-artiklar och vill se beredskapslistan för WMS-artiklar rekommenderar vi att du aktiverar funktionen *Förinläs sammanfattningen av lagersynlighet* (se också [Förinläsning av strömlinjeformad behållningsfråga](inventory-visibility-power-platform.md#preload-streamlined-onhand-query)). En motsvarande dataenhet i Dataverse lagrar förinläsningsresultatet för frågan, som uppdateras var 15:e minut. Dataenhetens namn är `Onhand Index Query Preload Result`.

> [!IMPORTANT]
> Entiteten Dataverse är skrivskyddad. Du kan visa och exportera data i enheterna för Lagersynlighet men **inte ändra dem**.

Ändringar av WMS-artikelkvantiteter som lagras i datakällan för Supply Chain Management (`fno`) är förbjudna. Detta beteende matchar beteendet hos andra funktioner för lagersynlighet. Den här begränsningen tillämpas för att förhindra konflikter.

## <a name="wms-item-compatibility-for-other-functions-in-inventory-visibility"></a>WMS-artikelöverensstämmelse för andra funktioner i Lagerhantering

[Mjuka reservationer](inventory-visibility-reservations.md) och [lagerfördelning](inventory-visibility-allocation.md) av WMS-artiklar stöds. Du kan inkludera WMS-relaterade fysiska måtten i mjuk reservation och allokeringsberäkningar.

## <a name="calculate-available-to-promise-quantities"></a>Beräkna kvantiteter som är tillgängliga att lova

Lösningen ger stöd för [disponibelt att lova (ATP)](inventory-visibility-available-to-promise.md) frö WMS-artiklar. Du kan definiera ATP-beräkningar utan att behöva oroa dig över WMS-specificerade detaljer.
