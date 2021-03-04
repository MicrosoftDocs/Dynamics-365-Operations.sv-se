---
title: Verksamhet för online- och offlinekassor (POS)
description: Det här avsnittet innehåller information om kassaoperation i Dynamics 365 Commerce. Det anger var i programmet somoperationerna kan anropas och om de är tillgängliga i offlineläge.
author: jblucher
manager: AnnBe
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-09-27
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7dc9f85bf90e6ddf9badf656eb136e28a71b036f
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594123"
---
# <a name="online-and-offline-point-of-sale-pos-operations"></a>Verksamhet för online- och offlinekassor (POS)

[!include [banner](includes/banner.md)]

De flesta åtgärder som användaren vidtar i kassan anses vara operationer. Operationer konfigureras och hanteras i formuläret i Dynamics 365 Commerce backoffice. Många operationer kan läggas till i knapparna i kassaknappsatsen. Användarna kan sedan välja knappar för att starta operationer och utföra deras funktioner. Andra åtgärder som ingår i kassahuvudprogrammet och startas från knappar på skärmen eller tillsammans med andra arbetsflöden eller processer.

Följande tabell innehåller information om de åtgärder som är tillgängliga i Modern POS och Cloud POS. Tabellen aner också var i programmet som operationerna kan anropas och om de är tillgängliga när kassan är i offlineläge.

Vissa åtgärder är inte tillgängliga i eller Modern POS och Cloud POS. Vissa av dessa åtgärder är antingen språkspecifika åtgärder som kräver ytterligare tillägg och konfiguration. Övriga är funktioner Microsoft Dynamics AX 2012 som inte stöds för närvarande.

Följande kolumner anger var operationerna kan startas:

- **Knappsats** – operationen kan tilldelas till knappar i kassaknappsatser som ingår i en kassaskärmlayout.
- **Transaktionsskärmen** – operationen kan startas från kassaknappsatser som har konfigurerats på kassatransaktionsskärmen.
- **Välkomstskärmen** – operationen kan startas från kassaknappsatser som har konfigurerats på kassavälkomstskärmen.

> [!NOTE]
> Åtgärderna i listan nedan gäller den senaste versionen av Handel. Vissa operationer kan ha ändrats eller kanske inte är tillgängliga i tidigare versioner.

| ID | Åtgärd | beskrivning | Knappsats | Transaktionsskärm | Välkomstskärm | Tillgänglig offline | Språkspecifik  |
|----|-----------|-------------|-------------|--------------------|----------------|-------------------|-----------------|
| 707 | Aktivera enhet | Aktivera aktuell enhet genom att låta en autentiserad användare ange anslutningsinformationen och tilldela en enhet och registrer-ID. | Nr | Nr | Nr | Nr | Nr |
| 134 | Lägg till anknytning | Lägg till en förvald anknytning till en transaktion. Välj anknytningen på sidan **Knappegenskaper**. | Ja | Ja | Nr | Ja | Nr |
| 135 | Lägg till anknytning från lista | Lägg till en anknytning till en transaktion i en lista. | Ja | Ja | Ja | Ja | Nr |
| 137 | Välj en anknytning till en kund | Lägg till en anknytning till en kund på sidan **kunduppgifter**. | Nr | Nr | Nr | Ja | Nr |
| 138 | Ta bort anknytning från kund | Ta bort en anknytning på sidan **kunduppgifter**. | Nr | Nr | Nr | Ja | Nr |
| 643 | Lägg till kupongkod | Lägg till en kupong genom att ange dess kod i kassan. | Ja | Ja | Nej | Ja | Nej |
| 141 | Lägg till huvudavgifter | Lägg till en tilläggsavgift i orderrubriken. | Ja | Ja | Nej | Nej| Nej |
| 141 | Lägg till radavgifter | Lägga till en tilläggsavgift till en vald försäljningsrad. | Ja | Ja | Nej | Nej| Nej |
| 117 | Lägg till förmånskort | Uppmana användaren att ange ett förmånskortnummer som ska läggas till den aktuella transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 136 | Lägg till serienummer | Den här operationen låter användaren ange ett serienummer för den aktuella produkten. | Ja | Ja | Nr | Ja | Nr |
| 1214 | Lägg till leveransadress | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 519 | Lägg till på presentkort | Pengar läggs till på det angivna presentkortet. | Ja | Ja | Nr | Nr | Nr |
| 6000 | Tillåt hoppa över räkenskapsregister | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 1212 | Bankinsättning | Registrerar det belopp som skickas till banken samt annan information, till exempel bankpåsens numret. | Ja | Ja | Ja | Ja | Nr |
| 923 | Verifiering av banksummor | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 915 | Tom operation | Operationen representerar en anpassningsbar knapp som kan ändras på programmeringsnivå av en utvecklare. Knappen kan ändras till en specialiserad operation som företaget behöver. | Ja | Ja | Ja | Ja | Nr |
| 1053 | Stäng skift dolt | Ange den aktuella övergången till skift som har stängts dolt och användaren loggar ut. Ett skift som har stängts dolt är stängt för ytterligare transaktioner, men är fortfarande öppet för kassaoperationer såsom borttagning av betalningsmedel och kassaavstämning. | Ja | Ja | Ja | Nr | Nr |
| 310 | Beräkna summa | När beräkningen är försenad initierar operationen åtgärden beräkningen för den aktuella transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 642 | Utför alla produkter | Ange leveranssätt för alla rader till **Utför**. | Ja | Ja | Nr | Ja\* | Nr |
| 641 | Utför alla valda produkter | Ange leveranssätt för valda rader till **Utför**. | Ja | Ja | Nej | Ja\* | Nej |
| 647 | Ändra leveranssätt | Ändra leveranssättet för förkonfigurerade försäljningsrader. | Ja | Ja | Nej | Nej| Nej |
| 1215 | Ändra lösenord | Denna operation låter kassaanvändaren ändra sitt lösenord. | Ja | Ja | Ja | Nr | Nr |
| 123 | Ändra måttenhet | Ändra måttenheten för den valda radartikeln. | Ja | Ja | Nr | Ja | Nr |
| 639 | Rensa standardförsäljningsrepresentant på transaktion | Ta bort provisionssäljgruppen (säljare) från transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 106 | Rensa kvantitet | Återställ kvantiteten på den markerade raden till **1**. | Ja | Ja | Nr | Ja | Nr |
| 640 | Rensa säljare på rad | Ta bort provisionssäljgruppen (säljare) från den markerade raden. | Ja | Ja | Nr | Ja | Nr |
| 121 | Ta bort säljare | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 1055 | Stäng skift | Stäng det aktuella skiftet, skriv ut en Z-rapport och logga ut användaren ur systemet. | Ja | Ja | Ja | Nej | Nej |
| 139 | Genomför transaktion | Uppmanar användaren att välja betalningsmetod | Ja | Ja | Nej | Ja | Nej |
| 620 | Skapa kundorder | Konvertera kassatransaktionen till en kundorder. | Ja | Ja | Nej | Ja\* | Nej |
| 925 | Kopiera bankchecken | Den här operationen stöds inte. | Inte aktuellt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 620 | Skapa kundorder | Konvertera kassatransaktionen till en kundorder. | Ja | Ja | Nr | Ja\* | Nr |
| 621 | Skapa offert | Konvertera kassatransaktionen till en försäljningsoffert. | Ja | Ja | Nr | Ja\* | Nr |
| 636 | Skapa butikstransaktion | Den här operationen låter användaren skapa en försäljningstransaktion som standard när standardkassabeteendet är att skapa kundorder. | Ja | Ja | Nr | Ja | Nr |
| 600 | Kund | Lägg till den angivna kunden till transaktionen. | Nr | Nr | Nr | Ja | Nr |
| 1 100 | Insättning på kundkonto | Utför en betalning till en kunds konto. | Ja | Ja | Ja | Ja | Ja |
| 612 | Lägga till kund | Den här operationen låter användaren skapa en ny kundpost. | Ja | Ja | Ja | Ja† | Nr |
| 603 | Rensa kund | Ta bort kunden från den aktuella transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 602 | Sök efter kund | Denna operation låter användaren söka efter en kundpost genom att navigera till kundsöksidan i kassan. | Ja | Ja | Ja | Ja | Nr |
| 609 | Kundtransaktioner | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 917 | Status för databasanslutning | Den här operationen låter användaren visa aktuella anslutningsinställningar och växla mellan online- och offlinelägen. | Ja | Ja | Ja | Ja | Nr |
| 1200 | Stäm av startbelopp | Deklarera det belopp som finns i kassalådan när dagen eller skiftet startar. | Ja | Ja | Ja | Ja | Nr |
| 132 | Insättningsåsidosättning | Åsidosätta standardinsättningen för kundorder. | Ja | Ja | Nr | Ja\* | Nr |
| 913 | Inaktivera designläge | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 912 | Aktivera designläge | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 1217 | Dela upp paket | Demontera ett paket till komponentprodukter. | Ja | Ja | Ja | Ja | Nr |
| 624 | Visa återbetalningsbelopp | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 513 | Visa summa | Visa summan för transaktionen på kundskärmen. | Ja | Ja | Ja | Ja | Nr |
| 623 | Redigera kund | Redigera detaljer för den aktuella kunden. | Ja | Ja | Nr | Nr | Nr |
| 614 | Redigera kundorder | Återkalla den valda ordern så att den går att ändra i kassan. | Nr | Nr | Nr | Nr | Nr |
| 615 | Redigera offert | Återkalla den valda offerten så att den går att ändra i kassan. | Nr | Nr | Nr | Nr | Nr |
| 518 | Utgiftskonton | Registrera pengar som tas bort ur kassalådan för tillfälliga utgifter. | Ja | Ja | Ja | Ja | Nr |
| 919 | Förlängd inloggning | Tilldela eller ta bort behörighet att logga in genom att skanna en streckkod eller genom att dra ett kort. | Ja | Ja | Ja | Ja | Nej |
| 1201 | Växelpost | Den här operationen låter användaren lägga till ytterligare pengar i den aktuella kassalådan eller skift. | Ja | Ja | Ja | Ja | Nr |
| 1218 | Tvinga upp lås av kringutrustning | Systemet använder denna operation internt för att låsa upp kringutrustning för kassa. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 520 | Presentkortssaldo | Visa presentkortssaldo. | Ja | Ja | Nr | Nr | Nr |
| 708 | Inaktiv enhet | Inaktivera aktuell enhet så att den inte kan användas som ett kassaregister. | Nej | Nej | Nej | Nej | Nej |
| 804 | Inkommande åtgärd | Komma åt funktionerna för hantering av inkommande lager. | Ja | Nej | Ja | Nej| Nej |
| 517 | Inkomstkonton | Registrera pengar, som sätts till kassalådan för en orsak annan än en försäljning. | Ja | Ja | Ja | Ja | Nr |
| 801 | Lagersökning | Slå upp kvantiteter för disponibelt, på ordern, och disponibelt att lova (ATP) för den aktuella butiken och andra tillgängliga platser. | Ja | Ja | Ja | Nr | Nr |
| 122 | Fakturakommentar | Den här operationen låter användaren skriva en kommentar om den aktuella transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 511 | Utfärda kreditfaktura | Utfärda en kreditnota för en verifikation i stället för återbetalning. | Ja | Ja | Nr | Nr | Nr |
| 512 | Utfärda presentkort | Utfärda ett nytt presentkort för det angivna beloppet. | Ja | Ja | Nr | Nr | Nr |
| 625 | Utfärda förmånskort | Utfärda ett förmånskort till en kund så att kunden kan delta i butikens bonusprogram. | Ja | Ja | Ja | Nr | Nr |
| 300 | Radrabattbelopp | Ange ett rabattbelopp för en radartikel i transaktionen. Denna operation används endast för artiklar som kan ha rabatt och bara i de angivna rabattgränserna. | Ja | Ja | Nr | Ja | Nr |
| 301 | Radrabatt i procent | Ange en rabatt i procent för en radartikel i transaktionen. Denna operation används endast för artiklar som kan ha rabatt och bara i de angivna rabattgränserna. | Ja | Ja | Nr | Ja | Nr |
| 703 | Lås kassa | Lås det aktuella registret så att det inte kan användas, men logga inte ut den aktuella användaren. | Nr | Nr | Nr | Ja | Nr |
| 701 | Logga ut | Logga ut den aktuella användaren från registret. | Ja | Ja | Ja | Ja | Nr |
| 521 | Förmånskortspoäng saldo | Visa poängsaldot på det angivna bonuskortet. | Ja | Ja | Nej | Nej | Nej |
| 142 | Hantera avgifter | Visa och hantera tillägg som tillämpas på transaktionen. | Ja | Ja | Nej | Nej| Nej |
| 918 | Hantera skift | Visa en lista över aktiva, uppskjutna och skift som har stängts dolt. | Ja | Ja | Ja | Nr | Nr |
| 914 | Minimera kassafönstret | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 1000 | Öppna kassalåda | Utför en "ingen försäljning"-operation och öppna den valda kassalådan. | Ja | Ja | Ja | Ja | Nr |
| 928 | Orderuppfyllelse | Den här åtgärden låter användare plocka, packa, skicka eller återkalla order för hämtade i butik. | Ja | Ja | Ja | Nej | Nej |
| 805 | Utgående åtgärder | Åtkomstfunktioner för hantering av försändelser av utgående överföringsorder. | Ja | Nej | Ja | Nej| Nej |
| 129 | Åsidosätt radproduktskatt | Åsidosätt momsen på den valda radartikeln och använd en annan angiven skatt. | Ja | Ja | Nr | Ja | Nr |
| 130 | Åsidosätt radproduktskatt från lista | Åsidosätt momsen på den valda radartikeln och använd en skatt som användaren väljer i en lista. | Ja | Ja | Nr | Ja | Nr |
| 127 | Åsidosätt transaktionsskatt | Åsidosätt momsen på en transaktion med en annan angiven skatt. | Ja | Ja | Nr | Ja | Nr |
| 128 | Åsidosätt transaktionsskatt från lista | Åsidosätt momsen på en transaktion med en skatt som användaren väljer i en lista. | Ja | Ja | Nr | Ja | Nr |
| 131 | Följesedel | Skapa en följesedel för den valda försäljningsordern. | Nr | Nr | Nr | Nr | Nr |
| 710 | Parkoppla maskinvarustation | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 201 | Kortbetalning | Acceptera ett kort såsom ett kreditkort eller betalkort som betalning. | Ja | Ja | Nr | Ja | Nr |
| 200 | Kontantbetalning | Ta emot kontanter som betalning. | Ja | Ja | Nr | Ja | Nr |
| 206 | Exakt kontantbetalning | Slutför transaktionen med en knapptryckning och acceptera beloppet som ska betalas kontant (exakt växel). | Ja | Ja | Nr | Ja | Nr |
| 204 | Checkbetalning | Ta emot en check som betalning. | Ja | Ja | Nr | Ja | Nr |
| 213 | Tillgodokvittobetalning | Acceptera en kreditnota (verifikation) som har utfärdats av butiken. | Ja | Ja | Nr | Nr | Nr |
| 203 | Betalning i annan valuta | Ta emot betalning i olika valutor. | Ja | Ja | Nr | Ja | Nr |
| 202 | Kundkontobetalning | Läs in transaktionen till en kunds konto. Den här betalningsmetoden är inte giltig för kundens orderinsättningar. | Ja | Ja | Nr | Nr | Nr |
| 214 | Presentkortsbetalning | Acceptera ett presentkort som har utfärdats av butiken. | Ja | Ja | Nr | Nr | Nr |
| 207 | Betala förmån | Acceptera ett förmånskort för betalning och lös in poäng mot produkter som uppfyller kraven. | Ja | Ja | Nr | Nr | Nr |
| 634 | Betalningshistorik | Visa kundens betalningshistorik för den aktuella kundordern. | Ja | Ja | Nr | Nr | Nr |
| 803 | Plockning och mottagning | Öppna sidan **plockning och mottagning** där du kan välja order, plocka eller ta emot i lagret. | Ja | Ja | Ja | Nr | Nr |
| 632 | upphämta alla produkter | Ange uppfyllelsemetoden till **butiksupphämtning** för alla rader. | Ja | Ja | Nr | Ja\* | Nr |
| 631 | upphämta valda produkter | Ange uppfyllelsemetoden till **butiksupphämtning** för valda rader. | Ja | Ja | Nr | Ja\* | Nr |
| 400 | Popup-meny | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 101 | Priskontroll | Den här operationen låter användaren leta upp priset för en viss produkt. | Ja | Ja | Ja | Ja | Nr |
| 104 | Prisåsidosättning | Åsidosätter priset på en produkt, om produkten har ställts in på att tillåta prisåsidosättning. | Ja | Ja | Nr | Ja | Nr |
| 1058 | Skriv ut skatt X | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 1059 | Skriv ut skatt Z | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 927 | Skriv ut artikeletikett | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 926 | Skriv ut hylletikett | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 1056 | Skriv ut X | Skriv ut X rapport för aktuellt skift. | Ja | Ja | Ja | Nr | Nr |
| 103 | Produktkommentar | Lägg till en kommentar på den valda radartikeln i transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 100 | Produktförsäljning | Lägg till en specifierad produkt i transaktionen. | Ja | Ja | Ja | Ja | Nr |
| 108 | Produktsökning | Denna operation låter användaren söka efter en produkt genom att navigera till produktsöksidan i kassan. | Ja | Ja | Ja | Ja | Nr |
| 633 | Utgångsdatum för offert | Den här operationen låter användaren visa eller ändra förfallodatum för en försäljningsoffert. | Ja | Ja | Nr | Ja\* | Nr |
| 627 | Beräkna om | Beräkna om alla kundorderrader och skatter, baserat på den aktuella konfigurationen. | Ja | Ja | Nej | Ja\* | Nej |
| 143 | Räkna om avgifter | Beräkna om de automatiska avgifter som tillämpas på ordern. | Ja | Ja | Nej | Nej| Nej |
| 515 | Återkalla order | Den här operationen låter användaren söka efter och återkalla kundorder och försäljningsofferter. | Ja | Ja | Ja | Nr | Nr |
| 504 | Återkalla transaktion | Den här operationen låter användaren återkalla en tidigare uppskjuten transaktion från den aktuella butiken. | Ja | Ja | Nr | Ja‡ | Nr |
| 305 | Utnyttja förmånspoäng | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 635 | Återbetala leveransavgifter | Den här operationen låter användaren återbetala leveransavgifter på avbrutna order. | Nr | Nr | Nr | Nr | Nr |
| 644 | Ta bort kupongkod | Uppmana användaren till att ta bort kuponger genom att markera dem i en lista över kuponger som associeras med transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 1057 | Skriv ut Z igen | Skriv ut Z-rapporten igen för föregående skift eller ett markerat skift. | Ja | Ja | Ja | Nr | Nr |
| 1216 | Ange ett nytt lösenord | Den här operationen låter användaren med behörighet att återställa lösenord för en annan medarbetares med hjälp av ett tillfälligt lösenord. | Ja | Ja | Ja | Nr | Nr |
| 1219 | Öppna URL i kassan | Denna åtgärd låter användaren öppna en administratörkonfigurerad URL i kassan. | Ja | Ja | Ja | Ja | Nr | 
| 109 | Returnera produkt | Utför en retur av enskilda produkter. Nästa skannade produkt visas som en returnerad produkt som har en negativ kvantitet och pris. | Ja | Ja | Nr | Ja | Nr |
| 114 | Returtransaktion | Återställa en tidigare transaktion genom dess kvittonummer för att returnera några eller alla produkter. | Ja | Ja | Ja | Ja§ | Nr |
| 1211 | Lämna pengar i kassaskåp | Flytta pengar från kassan till ett kassaskåp. | Ja | Ja | Ja | Ja | Nr |
| 516 | Försäljningsfaktura | Den här åtgärden kan kunden göra betalningar till den valda fakturan. | Ja | Ja | Nr | Nr | Nr |
| 502 | Säljare | Den här operation låter användaren ange värdet **Mottagare** på en försäljningsorder för kundorder i kassan. | Ja | Ja | Nej | Ja\* | Nej |
| 2000 | Hantering av tidsplan | Åtgärden stöds inte ännu. | Ja | Ja | Ja | Nej | Nej |
| 2001 | Tidsplanera begäranden | Åtgärden stöds inte ännu. | Ja | Ja | Ja | Nej | Nej |
| 622 | Sök efter order | Denna operation låter användare förkonfigurera kassaknappar för att utföra sökningar efter artikel, kund eller kategori. | Ja | Ja | Ja | Ja | Nr |
| 1213 | Sök leveransadress | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 709 | Välj maskinvarustation | Den här operationen låter användaren välja maskinvarustation i en lista med tillgängliga maskinvarustationer. | Ja | Ja | Ja | Ja | Nr |
| 637 | Ställ in standardförsäljningsrepresentant på transaktion | Den här operationen låter användaren välja ett av de berättigade provisionssäljgrupperna (säljare) som standard säljare för rader som läggs till senare. | Ja | Ja | Nr | Ja | Nr |
| 105 | Ställ in kvantitet | Ändra kvantiteten för en radartikel i transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 638 | Ange säljare på rad | Den här operationen låter användaren välja ett av de berättigade provisionssäljgrupperna (säljare) för den nuvarande valda raden. | Ja | Ja | Nr | Ja | Nr |
| 630 | Leverera alla produkter | Anger uppfyllelseläget till **leverans** för alla radartiklar. | Ja | Ja | Nr | Ja\* | Nr |
| 629 | Leverera valda produkter | Ange uppfyllelseläget till **Leverans** för valda rader. | Ja | Ja | Nr | Ja\* | Nr |
| 115 | Visa journal | Visa butikens journal. Du kan visa transaktioner, skriva ut kvitton och presentkvitton och återkalla för retur. | Ja | Ja | Ja | Ja\*\* | Nr |
| 802 | Lagerinventering | Den här operationen låter användaren skapa eller ändra lagrets inventeringsjournaler för fysiskt lager eller rullande inventeringar. | Ja | Ja | Ja | Nr | Nr |
| 401 | Undermeny | Denna operation tar användaren till en annan länkad knappsats. | Ja | Ja | Ja | Ja | Nr |
| 1054 | Skjut upp skift | Avbryt det aktuella skiftet så att ett nytt eller annat skift kan aktiveras på den aktuella journalen. | Ja | Ja | Ja | Nr | Nr |
| 503 | Skjut upp transaktion | Avbryt den aktuella transaktionen, så att den kan återställas senare i butiken. | Ja | Ja | Nr | Ja‡ | Nr |
| 1004 | Uppgiftsregistrering | Öppna uppgiftsregistrering om du vill registrera procedurmässig steg i kassan. | Nr | Nr | Nr | Ja | Nr |
| 1052 | Kassaavstämning | Den här operationen låter användaren ange penningbelopp i kassan för varje räknat betalningssätt. | Ja | Ja | Ja | Ja | Nr |
| 1210 | Borttagning av betalningsmedel | Den här operationen låter användaren ta bort pengar från den aktuella kassalådan eller skift. | Ja | Ja | Ja | Ja | Nr |
| 920 | Stämpelklocka | Den här operationen låter användare stämpla in och stämpla ut från arbetsskift och raster. | Ja | Ja | Ja | Nr | Nr |
| 302 | Totalt rabattbelopp | Ange ett rabattbeloppet för transaktionen. Denna operation gäller endast för artiklar som kan ha rabatt och bara i de angivna rabattgränserna. | Ja | Ja | Nr | Ja | Nr |
| 303 | Totalrabatt i procent | Ange en rabattprocent för transaktionen. Denna operation gäller endast för artiklar som kan ha rabatt och bara i de angivna rabattgränserna. | Ja | Ja | Nr | Ja | Nr |
| 501 | Transaktionskommentar | Lägg till en kommentar i den nuvarande transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 922 | Visa produktinformation | Öppna produktinformationssidan för den valda radartikeln. | Ja | Ja | Nr | Ja | Nr |
| 1003 | Visa rapporter | Visa rapporter som har konfigurerats för den aktuella användaren. | Ja | Ja | Ja | Nr | Nr |
| 921 | Visa stämpelklocksregistreringar | Visa stämpelklocksregistreringarna för alla anställda i butiken. | Ja | Ja | Ja | Nr | Nr |
| 211 | Annullera betalning | Annullera den markerade betalningsraden från transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 102 | Annullera produkt | Annullera den markerade radartikeln från transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 500 | Annullera transaktion | Annullera den aktuella transaktionen. | Ja | Ja | Nr | Ja | Nr |
| 916 | Windows Workflow Foundation | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nr |
| 924 | X-rapport för bankkort | Den här operationen stöds inte. | Inte aktuellt | Inte aktuellt | Inte aktuellt | Inte aktuellt | Ja |
| 311 | Ta bort systemrabatter från transaktioner | Ta bort alla tillämpade rabatter i systemet, inklusive kupongbaserade rabatter, från transaktionen. Detta innebär inte att manuella rabatter tas bort. | Ja | Ja | Ja | Ja | Nr |
| 312 | Återanvända systemrabatter | Återanvänd systemrabatter på transaktionen om de tagits bort med hjälp av åtgärden **Ta bort systemrabatter från transaktion**. | Ja | Ja | Ja | Ja | Nr |

\*Operationen är endast tillgänglig i offlineläge när en kundorder eller försäljningsoffert skapas, och om offlineskapade av kundorder och försäljningsofferter som har konfigurerats i kassafunktionsprofilen. Operationen kan inte utföras när order skapas med Realtidstjänst eller när en order har återkallats eller redigeras.

† Operationen kan utföras i frånkopplat läge bara när kassan är konfigurerad för att skapa kunder offline i kassafunktionalitetsprofilen.

‡ När kassan är offline kan uppskjutna transaktioner endast återställas från aktuella kassans offlinedatabas. Användare kan inte göra uppehåll och återkalla transaktioner genom journaler.

§ När kassan är offline kan endast transaktioner i den aktuella offlinedatabasen återställas för retur.

\*\* När kassan är offline kan endast transaktioner i den aktuella offlinekanaldatabasen visas i journalen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]