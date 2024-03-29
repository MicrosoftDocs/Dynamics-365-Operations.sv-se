---
title: Flytta potentiell kund till kontantdata från dataintegrerare till dubbelriktad skrivning
description: Detta ämne beskriver hur du flyttar potentiell kund till kontantdata från dataintegrerare till dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 02/01/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-26
ms.openlocfilehash: bbf5a7c2f409003816e2becf1a58ee7d7d5aafb2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289093"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Flytta potentiell kund till kontantdata från dataintegrerare till dubbelriktad skrivning

[!include [banner](../../includes/banner.md)]

Potentiell kund till pengar-lösningen som är tillgänglig för Dataintegrerare är inte kompatibel med dubbelriktad skrivning. Orsaken till detta är msdynce_AccountNumber index för kontoregistret som följde som en del av lösningen Potentiell kund till pengar. Om det finns ett sådan index kan du inte skapa samma kundkontonummer i två olika juridiska personer. Du kan antingen välja att börja om med dubbelriktad skrivning genom att migrera Potentiell kund till kontanter från Dataintegrerare till dubbelriktad skrivning eller så kan du installera den sista "vilande" versionen av Potentiell kund till kontanter-lösningen. I den här artikeln beskrivs båda dessa metoder.

## <a name="install-the-last-dorman-version-of-the-data-integrator-prospect-to-cash-solution"></a>Installera den sista "vilande" versionen av Dataintegrerare Potentiell kund till kontanter-lösningen

**P2C Version 15.0.0.2** anses vara den sista "vilande" versionen av Dataintegrerare Potentiell kund till kontanter-lösningen. Du kan hämta den från [FastTrack for Dynamics 365](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/P2C).

Du måste installera den manuellt. Efter installationen förblir allt exakt detsamma, förutom vid msdynce_AccountNumber tas bort.

## <a name="steps-to-migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Steg för att migrera potentiell kund till kontantdata från dataintegrerare till dubbelriktad skrivning

Följ dessa steg för att migrera din potentiell kund till kontantdata från dataintegrerare till dubbelriktad skrivning.

1. Kör potentiell kund till kontant dataintegererare jobb för att göra en slutgiltig fullständig synkronisering. På det här sättet ser du till att båda systemen (appar för ekonomi och drift samt kundengagemangsappar) har all data.
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
5. Skapa en dubbelriktad anslutning mellan appen för ekonomi och drift och kundengagemangsapp för en eller flera juridiska personer.
6. Aktivera dubbelriktade registermappningar och kör den initiala synkroniseringen för nödvändiga referensdata. (Mer information finns i [Att tänka på vid ursprunglig synkronisering](initial-sync-guidance.md).) Exempel på obligatoriska data är kundgrupper, betalningsvillkor och betalningsscheman. Aktivera inte dubbelriktade mappningar för register som kräver initialisering, till exempel konto, offert, offertrad, order och orderradsregister.
7. I kundengagemangsappen, gå till **Avancerade inställningar \> Systeminställningar \> Datahantering \> Duplicera detekteringsregler** och inaktivera alla regler.
8. Initiera registren som listas i steg 2. Instruktioner finns i de återstående avsnitten i den här artikeln.
9. Öppna appen för ekonomi och drift och aktivera tabellmappningarna, till exempel konto, offert, offertrad, order och orderrad. Kör sedan initial synkronisering. (Mer information finns i [Att tänka på vid första synkronisering](initial-sync-guidance.md).) Den här processen synkroniserar ytterligare information från appen för ekonomi och drift, till exempel bearbetningsstatus, leverans- och faktureringsadresser, webbplatser och lagerställen.

## <a name="account-table"></a>Kontoregister

1. I kolumnen **Företag** anger du företagsnamnet, till exempel **USMF**.
2. I kolumnen **Relationstyp**, ange **Kund** som ett statiskt värde. Du kanske inte vill klassificera varje kontopost som en kund i din affärslogik.
3. I kolumnen **Kundgrupps-ID** anger du kundgruppsnumret från appen för ekonomi och drift. Standardvärdet från potentiell kund till kontantlösning är **10**.
4. Om du använder potentiell kund till en kontantlösning utan anpassning av **kontonummer**, ange ett värde för **kontonummer** i kolumnen **partnummer**. Om det finns anpassningar och du inte känner till partnumret hämtar du denna information från appen för ekonomi och drift.

## <a name="contact-table"></a>Kontaktregister

1. I kolumnen **Företag** anger du företagsnamnet, till exempel **USMF**.
2. Ställ in följande kolumner baserat på värdet **IsActiveCustomer** i CSV-filen:

    - Om **IsActiveCustomer** anges till **Ja** i CSV-filen, ange kolumnen **Säljbar** till **Ja**. I kolumnen **Kundgrupps-ID** anger du kundgruppsnumret från appen för ekonomi och drift. Standardvärdet från potentiell kund till kontantlösning är **10**.
    - Om **IsActiveCustomer** anges till **Nej** i CSV-filen ställer du in kolumnen **Säljbart** till **Nej** och ställer in kolumnen **Kontakt för** på **Kund**.

3. Om du använder potentiell kund till en kontantlösning utan anpassning av **kontaktnumret** ställer du in följande kolumner:

    - Flytta kontaktnumret från CSV-filen (**msdynce\_contactnumber**) till kontaktnumret i tabellen **kontakt** (**msdyn\_contactnumber**).
    - Använd värden från tabellen **Kontaktnummer** i kolumnen **Partnummer**.
    - Använd värden från tabellen **Kontaktnummer** i kolumnen **Kontonummer/kontaktperson-ID**.

## <a name="invoice-table"></a>Fakturaregister

Eftersom data från tabellen **Faktura** har utformats för att flöda åt ett visst håll, från appen för ekonomi och drift till kundengagemangsappen, krävs ingen initialisering. Kör den ursprungliga synkroniseringen om du vill migrera alla nödvändiga data från appen för ekonomi och drift till kundengagemangsappen. Mer information finns i [Att tänka på vid ursprunglig synkronisering](initial-sync-guidance.md).

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

Eftersom data från tabellen **Produkter** har utformats för att flöda åt ett visst håll, från appen för ekonomi och drift till kundengagemangsappen, krävs ingen initialisering. Kör den ursprungliga synkroniseringen om du vill migrera alla nödvändiga data från appen för ekonomi och drift till kundengagemangsappen. Mer information finns i [Att tänka på vid ursprunglig synkronisering](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Produktregister för offert och offert

För tabellen **offert**, följ instruktionerna i avsnittet [orderregistret](#order-table) tidigare. För tabellen **offertprodukt**, följ instruktionerna i avsnittet [orderproduktregistret](#order-products-table) tidigare.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

