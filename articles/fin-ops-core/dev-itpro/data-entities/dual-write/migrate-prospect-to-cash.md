---
title: Flytta potentiell kund till kontantdata från dataintegrerare till dubbelriktad skrivning
description: Detta ämne beskriver hur du flyttar potentiell kund till kontantdata från dataintegrerare till dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 01/04/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: d119a9e5874f73e024cedc4cdb581f947e5bf1a0
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782515"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Flytta potentiell kund till kontantdata från dataintegrerare till dubbelriktad skrivning

[!include [banner](../../includes/banner.md)]

Följ dessa steg för att migrera din potentiell kund till kontantdata från dataintegrerare till dubbelriktad skrivning.

1. Kör potentiell kund till kontant dataintegererare jobb för att göra en slutgiltig fullständig synkronisering. På det här sättet ser du till att båda systemen (Finance and Operations-appar och kundengagemangsappar) har all data.
2. Om du vill förhindra dataförlust kan du exportera potentiell kund till kontantdata från Microsoft Dynamics 365 Sales till en Excel-fil eller en CSV-fil. Exportera data från följande enheter:

    - [Konto](#account-table)
    - [Kontakt](#contact-table)
    - [Faktura](#invoice-table)
    - Fakturera produkter
    - [Order](#order-table)
    - [Orderprodukter](#order-products-table)
    - [Produkter](#products-table)
    - [Offert](#quote-and-quote-product-tables)
    - [Offertprodukter](#quote-and-quote-product-tables)

3. Avinstallera lösningen Potentiell kund till kontantlösning från Sales-miljön. Detta steg tar bort kolumnerna och motsvarande data som lösningen Potentiell kund till kontantlösningen innehåller.
4. Installera lösningen för dubbelriktad skrivning.
5. Skapa en dubbelriktad koppling mellan Finance and Operations-app och kundengagemangsapp för en eller flera juridiska personer.
6. Aktivera dubbelriktade registermappningar och kör den initiala synkroniseringen för nödvändiga referensdata. (Mer information finns i [Att tänka på vid ursprunglig synkronisering](initial-sync-guidance.md).) Exempel på obligatoriska data är kundgrupper, betalningsvillkor och betalningsscheman. Aktivera inte dubbelriktade mappningar för register som kräver initialisering, till exempel konto, offert, offertrad, order och orderradsregister.
7. I kundengagemangsappen, gå till **Avancerade inställningar \> Systeminställningar \> Datahantering \> Duplicera detekteringsregler** och inaktivera alla regler.
8. Initiera registren som listas i steg 2. Instruktioner finns i de återstående avsnitten i det här avsnittet.
9. Öppna Finance and Operations-appen och aktivera registermappningar, till exempel konto, offert, offertrad, order och orderrad registermappningar. Kör sedan initial synkronisering. (Mer information finns i [Att tänka på vid ursprunglig synkronisering](initial-sync-guidance.md).) Den här processen synkroniserar ytterligare information från Finance and Operations-appen, till exempel bearbetningsstatus, leverans- och faktureringsadresser, platser och lagerställen.

## <a name="account-table"></a>Kontoregister

1. I kolumnen **Företag** anger du företagsnamnet, till exempel **USMF**.
2. I kolumnen **Relationstyp**, ange **Kund** som ett statiskt värde. Du kanske inte vill klassificera varje kontopost som en kund i din affärslogik.
3. I kolumnen **kundgrupp-ID**, ange kundgruppnumret från Finance and Operations-app. Standardvärdet från potentiell kund till kontantlösning är **10**.
4. Om du använder potentiell kund till en kontantlösning utan anpassning av **kontonummer**, ange ett värde för **kontonummer** i kolumnen **partnummer**. Om det finns anpassningar, och du inte känner till partnumret, hämtar du denna information från Finance and Operations-appen.

## <a name="contact-table"></a>Kontaktregister

1. I kolumnen **Företag** anger du företagsnamnet, till exempel **USMF**.
2. Ställ in följande kolumner baserat på värdet **IsActiveCustomer** i CSV-filen:

    - Om **IsActiveCustomer** anges till **Ja** i CSV-filen, ange kolumnen **Säljbar** till **Ja**. I kolumnen **kundgrupp-ID**, ange kundgruppnumret från Finance and Operations-app. Standardvärdet från potentiell kund till kontantlösning är **10**.
    - Om **IsActiveCustomer** anges till **Nej** i CSV-filen ställer du in kolumnen **Säljbart** till **Nej** och ställer in kolumnen **Kontakt för** på **Kund**.

3. Om du använder potentiell kund till en kontantlösning utan anpassning av **kontaktnumret** ställer du in följande kolumner:

    - Flytta kontaktnumret från CSV-filen (**msdynce\_contactnumber**) till kontaktnumret i tabellen **kontakt** (**msdyn\_contactnumber**).
    - Använd värden från tabellen **Kontaktnummer** i kolumnen **Partnummer**.
    - Använd värden från tabellen **Kontaktnummer** i kolumnen **Kontonummer/kontaktperson-ID**.

## <a name="invoice-table"></a>Fakturaregister

Eftersom data från tabellen **faktura** har utformats för att flöda ett sätt, från Finance and Operations-appen till kundengagemangsappen krävs inte initialisering. Kör den ursprungliga synkroniseringen om du vill flytta alla nödvändiga data från Finance and Operations-appen till kundengagemangsappen. Mer information finns i [Att tänka på vid ursprunglig synkronisering](initial-sync-guidance.md).

## <a name="order-table"></a>Orderregister

1. I kolumnen **Företag** anger du företagsnamnet, till exempel **USMF**.
2. Kopiera värdet i kolumnen **Order-ID** i CSV-filen till kolumnen **Försäljningsordernummer**.
3. Kopiera värdet i kolumnen **Kund** i CSV-filen till kolumnen **Fakturakundnummer**.
4. Kopiera värdet på kolumnen **Leverera till land/region** i CSV-filen till kolumnen **Leverera till land/region**. Exempel på detta värde inkluderar **US** och **USA**.
5. Ställ in kolumnen **Begärt inleveransdatum**. Om du inte använder ett kvittodatum använder du kolumnerna **Begärt leveransdatum**, **Uppfyllt datum** och **Skickat datum** i CSV-filen. Ett exempel på detta värde är **2020-03-27T00:00:00Z**.
6. Ställ in kolumnen **Språk**. Ett exempel på detta värde är **en-us**.
7. Ange kolumnen **Ordertyp** genom att använda kolumnen **Artikelbaserad**.

## <a name="order-products-table"></a>Register för orderprodukter

- I kolumnen **Företag** anger du företagsnamnet, till exempel **USMF**.

## <a name="products-table"></a>Register för produkter

Eftersom data från tabellen **Produkter** har utformats för att flöda ett sätt, från Finance and Operations-appen till kundengagemangsappen krävs inte initialisering. Kör den ursprungliga synkroniseringen om du vill flytta alla nödvändiga data från Finance and Operations-appen till kundengagemangsappen. Mer information finns i [Att tänka på vid ursprunglig synkronisering](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Produktregister för offert och offert

För tabellen **offert**, följ instruktionerna i avsnittet [orderregistret](#order-table) tidigare. För tabellen **offertprodukt**, följ instruktionerna i avsnittet [orderproduktregistret](#order-products-table) tidigare.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]