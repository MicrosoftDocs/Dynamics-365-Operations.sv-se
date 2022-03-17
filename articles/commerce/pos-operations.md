---
title: Verksamhet för online- och offlinekassor (POS)
description: Det här avsnittet innehåller information om kassaoperation i Dynamics 365 Commerce. Det anger var i programmet somoperationerna kan anropas och om de är tillgängliga i offlineläge.
author: jblucher
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-09-27
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0c62e11cc6d39c351321419bb862a5169b162fb7
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349727"
---
# <a name="online-and-offline-point-of-sale-pos-operations"></a>Verksamhet för online- och offlinekassor (POS)

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

De flesta åtgärder som användare vidtar i kassan anses vara operationer. Operationer konfigureras och hanteras i formuläret i Dynamics 365 Commerce backoffice. Många operationer kan läggas till i knapparna i kassaknappsatsen. Användarna kan sedan välja knappar för att starta operationer och utföra deras funktioner. Andra åtgärder som ingår i kassahuvudprogrammet och startas från knappar på skärmen eller tillsammans med andra arbetsflöden eller processer.

Följande tabell innehåller information om de åtgärder som är tillgängliga i Modern POS och Cloud POS. Tabellen aner också var i programmet som operationerna kan anropas och om de är tillgängliga när POS är i offlineläge.

Vissa åtgärder är inte tillgängliga i eller Modern POS och Cloud POS. Vissa av dessa åtgärder är antingen språkspecifika åtgärder som kräver ytterligare tillägg och konfiguration. Övriga är funktioner Microsoft Dynamics AX 2012 som inte stöds för närvarande.

Följande kolumner anger var operationerna kan startas:

- **Knappsats** – operationen kan tilldelas till knappar i kassaknappsatser som ingår i en kassaskärmlayout.
- **Transaktionsskärmen** – operationen kan startas från kassaknappsatser som har konfigurerats på kassatransaktionsskärmen.
- **Välkomstskärmen** – operationen kan startas från kassaknappsatser som har konfigurerats på kassavälkomstskärmen.

> [!NOTE]
> Åtgärderna i listan nedan gäller den senaste versionen av Commerce. Vissa operationer kan ha ändrats eller kanske inte är tillgängliga i tidigare versioner.


| ID | Åtgärd | beskrivning | Knappsats | Transaktionsskärm | Välkomstskärm | Tillgänglig offline | Språkspecifik |
|----|-----------|-------------|-------------|--------------------|----------------|-------------------|-----------------|
| 707 | Aktivera enhet | Aktivera aktuell enhet genom att låta en autentiserad användare ange anslutningsinformationen och tilldela en enhet och registrer-ID. | Nej | Nej | Nej | Nej | Nej |
| 134 | Lägg till anknytning | Lägg till en förvald anknytning till en transaktion. Välj anknytningen på sidan **Knappegenskaper**. | Ja | Ja | Nej | Ja | Nej |
| 135 | Lägg till anknytning från lista | Lägg till en anknytning till en transaktion i en lista. | Ja | Ja | Ja | Ja | Nej |
| 137 | Välj en anknytning till en kund | Lägg till en anknytning till en kund på sidan **kunduppgifter**. | Nej | Nej | Nej | Ja | Nej |
| 138 | Ta bort anknytning från kund | Ta bort en anknytning på sidan **kunduppgifter**. | Nej | Nej | Nej | Ja | Nej |
| 643 | Lägg till kupongkod | Lägg till en kupong genom att ange dess kod i POS. | Ja | Ja | Nej | Ja | Nej |
| 141 | Lägg till huvudavgifter | Lägg till en tilläggsavgift i orderrubriken. | Ja | Ja | Nej | Nej| Nej |
| 141 | Lägg till radavgifter | Lägga till en tilläggsavgift till en vald försäljningsrad. | Ja | Ja | Nej | Nej| Nej |
| 117 | Lägg till förmånskort | Uppmana användaren att ange ett förmånskortnummer som ska läggas till den aktuella transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 136 | Lägg till serienummer | Den här operationen låter användaren ange ett serienummer för den aktuella produkten. | Ja | Ja | Nej | Ja | Nej |
| 1214 | Lägg till leveransadress | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 519 | Lägg till på presentkort | Pengar läggs till på det angivna presentkortet. | Ja | Ja | Nej | Nej | Nej |
| 6000 | Tillåt hoppa över räkenskapsregister | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 1212 | Bankinsättning | Registrerar det belopp som skickas till banken samt annan information, till exempel bankpåsens numret. | Ja | Ja | Ja | Ja | Nej |
| 923 | Verifiering av banksummor | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 915 | Tom operation | Operationen representerar en anpassningsbar knapp som kan ändras på programmeringsnivå av en utvecklare. Knappen kan ändras till en specialiserad operation som företaget behöver. | Ja | Ja | Ja | Ja | Nej |
| 1053 | Stäng skift dolt | Ange den aktuella övergången till skift som har stängts dolt och användaren loggar ut. Ett skift som har stängts dolt är stängt för ytterligare transaktioner, men är fortfarande öppet för kassaoperationer såsom borttagning av betalningsmedel och kassaavstämning. | Ja | Ja | Ja | Nej | Nej |
| 310 | Beräkna summa | När beräkningen är försenad initierar operationen åtgärden beräkningen för den aktuella transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 642 | Utför alla produkter | Ange leveranssätt för alla rader till **Utför**. | Ja | Ja | Nej | Ja\* | Nej |
| 641 | Utför alla valda produkter | Ange leveranssätt för valda rader till **Utför**. | Ja | Ja | Nej | Ja\* | Nej |
| 647 | Ändra leveranssätt | Ändra leveranssättet för förkonfigurerade försäljningsrader. | Ja | Ja | Nej | Nej| Nej |
| 1215 | Ändra lösenord | Denna operation låter kassaanvändaren ändra sitt lösenord. | Ja | Ja | Ja | Nej | Nej |
| 123 | Ändra måttenhet. | Ändra måttenheten för den valda radartikeln. | Ja | Ja | Nej | Ja | Nej |
| 639 | Rensa standardförsäljningsrepresentant på transaktion | Ta bort provisionssäljgruppen (säljare) från transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 106 | Rensa kvantitet | Återställ kvantiteten på den markerade raden till **1**. | Ja | Ja | Nej | Ja | Nej |
| 640 | Rensa säljare på rad | Ta bort provisionssäljgruppen (säljare) från den markerade raden. | Ja | Ja | Nej | Ja | Nej |
| 121 | Ta bort säljare | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 1055 | Stäng skift | Stäng det aktuella skiftet, skriv ut en Z-rapport och logga ut användaren ur systemet. | Ja | Ja | Ja | Nej | Nej |
| 139 | Genomför transaktion | Uppmanar användaren att välja betalningsmetod | Ja | Ja | Nej | Ja | Nej |
| 925 | Kopiera bankchecken | Den här operationen stöds inte. | Inte aktuellt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 620 | Skapa kundorder | Konvertera kassatransaktionen till en kundorder. | Ja | Ja | Nej | Ja\* | Nej |
| 621 | Skapa offert | Konvertera kassatransaktionen till en försäljningsoffert. | Ja | Ja | Nej | Ja\* | Nej |
| 636 | Skapa butikstransaktion | Skapa en försäljningstransaktion som standard när standardkassabeteendet är att skapa kundorder. | Ja | Ja | Nej | Ja | Nej |
| 600 | Kund | Lägg till den angivna kunden till transaktionen. | Nej | Nej | Nej | Ja | Nej |
| 1 100 | Insättning på kundkonto | Utför en betalning till en kunds konto. | Ja | Ja | Ja | Ja | Ja |
| 612 | Lägga till kund | Skapa en ny kundpost. | Ja | Ja | Ja | Ja† | Nej |
| 603 | Rensa kund | Ta bort kunden från den aktuella transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 602 | Sök efter kund | Sök efter en kundpost genom att navigera till kundsöksidan i kassan. | Ja | Ja | Ja | Ja | Nej |
| 609 | Kundtransaktioner | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 917 | Status för databasanslutning | Visa aktuella anslutningsinställningar och växla mellan online- och offlinelägen. | Ja | Ja | Ja | Ja | Nej |
| 1200 | Stäm av startbelopp | Deklarera det belopp som finns i kassalådan när dagen eller skiftet startar. | Ja | Ja | Ja | Ja | Nej |
| 132 | Insättningsåsidosättning | Åsidosätta standardinsättningen för kundorder. | Ja | Ja | Nej | Ja\* | Nej |
| 913 | Inaktivera designläge | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 912 | Aktivera designläge | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 1217 | Dela upp paket | Demontera ett paket till komponentprodukter. | Ja | Ja | Ja | Ja | Nej |
| 624 | Visa återbetalningsbelopp | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 513 | Visa summa | Visa summan för transaktionen på kundskärmen. | Ja | Ja | Ja | Ja | Nej |
| 623 | Redigera kund | Redigera detaljer för den aktuella kunden. | Ja | Ja | Nej | Nej | Nej |
| 614 | Redigera kundorder | Återkalla den valda ordern så att den går att ändra i POS. | Nej | Nej | Nej | Nej | Nej |
| 615 | Redigera offert | Återkalla den valda offerten så att den går att ändra i POS. | Nej | Nej | Nej | Nej | Nej |
| 518 | Utgiftskonton | Registrera pengar som tas bort ur kassalådan för tillfälliga utgifter. | Ja | Ja | Ja | Ja | Nej |
| 919 | Förlängd inloggning | Tilldela eller ta bort behörighet att logga in genom att skanna en streckkod eller genom att dra ett kort. | Ja | Ja | Ja | Ja | Nej |
| 1201 | Växelpost | Lägg till ytterligare pengar i den aktuella kassalådan eller skift. | Ja | Ja | Ja | Ja | Nej |
| 1218 | Tvinga upp lås av kringutrustning | Systemet använder denna operation internt för att låsa upp kringutrustning för kassa. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 520 | Presentkortssaldo | Visa presentkortssaldo. | Ja | Ja | Nej | Nej | Nej |
| 708 | Inaktiv enhet | Inaktivera aktuell enhet så att den inte kan användas som en kassaapparat. | Nej | Nej | Nej | Nej | Nej |
| 804 | Inkommande åtgärd | Komma åt funktionerna för hantering av inkommande lager. | Ja | Nej | Ja | Nej| Nej |
| 517 | Inkomstkonton | Registrera pengar, som sätts till kassalådan för en orsak annan än en försäljning. | Ja | Ja | Ja | Ja | Nej |
| 801 | Lagersökning | Slå upp kvantiteter för disponibelt, på ordern, och disponibelt att lova (ATP) för den aktuella butiken och andra tillgängliga platser. | Ja | Ja | Ja | Nej | Nej |
| 806 | Lagerjustering | Justera lagret in eller ut från butikslagerstället med justerings- eller flyttningsjournal. | Ja | Ja | Ja | Nej | Nej |
| 807 | Lagerrörelse | Flytta artiklar från en lagerplats till en annan inom ett butikslager. | Ja | Ja | Ja | Nej | Nej |
| 122 | Fakturakommentar | Lägg till en kommentar om den aktuella transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 511 | Utfärda kreditfaktura | Utfärda en kreditnota för en verifikation i stället för återbetalning. | Ja | Ja | Nej | Nej | Nej |
| 512 | Utfärda presentkort | Utfärda ett nytt presentkort för det angivna beloppet. | Ja | Ja | Nej | Nej | Nej |
| 625 | Utfärda förmånskort | Utfärda ett förmånskort till en kund så att kunden kan delta i butikens bonusprogram. | Ja | Ja | Ja | Nej | Nej |
| 300 | Radrabattbelopp | Ange ett rabattbelopp för en radartikel i transaktionen. Denna operation används endast för artiklar som kan ha rabatt och bara i de angivna rabattgränserna. | Ja | Ja | Nej | Ja | Nej |
| 301 | Radrabatt i procent | Ange en rabatt i procent för en radartikel i transaktionen. Denna operation används endast för artiklar som kan ha rabatt och bara i de angivna rabattgränserna. | Ja | Ja | Nej | Ja | Nej |
| 703 | Lås kassa | Lås det aktuella registret så att det inte kan användas, men logga inte ut den aktuella användaren. | Nej | Nej | Nej | Ja | Nej |
| 701 | Logga ut | Logga ut den aktuella användaren från registret. | Ja | Ja | Ja | Ja | Nej |
| 521 | Förmånskortspoäng saldo | Visa poängsaldot på det angivna bonuskortet. | Ja | Ja | Nej | Nej | Nej |
| 142 | Hantera avgifter | Visa och hantera tillägg som tillämpas på transaktionen. | Ja | Ja | Nej | Nej| Nej |
| 918 | Hantera skift | Visa en lista över aktiva, uppskjutna och skift som har stängts dolt. | Ja | Ja | Ja | Nej | Nej |
| 914 | Minimera kassafönstret | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 1000 | Öppna kassalåda | Utför en "ingen försäljning"-operation och öppna den valda kassalådan. | Ja | Ja | Ja | Ja | Nej |
| 928 | Orderuppfyllelse | Den här åtgärden låter användare plocka, packa, skicka eller återkalla order för hämtade i butik. | Ja | Ja | Ja | Nej | Nej |
| 805 | Utgående åtgärder | Åtkomstfunktioner för hantering av försändelser av utgående överföringsorder. | Ja | Nej | Ja | Nej| Nej |
| 129 | Åsidosätt radproduktskatt | Åsidosätt momsen på den valda radartikeln och använd en annan angiven skatt. | Ja | Ja | Nej | Ja | Nej |
| 130 | Åsidosätt radproduktskatt från lista | Åsidosätt momsen på den valda radartikeln och använd en skatt som användaren väljer i en lista. | Ja | Ja | Nej | Ja | Nej |
| 127 | Åsidosätt transaktionsskatt | Åsidosätt momsen på en transaktion med en annan angiven skatt. | Ja | Ja | Nej | Ja | Nej |
| 128 | Åsidosätt transaktionsskatt från lista | Åsidosätt momsen på en transaktion med en skatt som användaren väljer i en lista. | Ja | Ja | Nej | Ja | Nej |
| 131 | Följesedel | Skapa en följesedel för den valda försäljningsordern. | Nej | Nej | Nej | Nej | Nej |
| 710 | Parkoppla maskinvarustation | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 201 | Kortbetalning | Acceptera ett kort såsom ett kreditkort eller betalkort som betalning. | Ja | Ja | Nej | Ja | Nej |
| 200 | Kontantbetalning | Ta emot kontanter som betalning. | Ja | Ja | Nej | Ja | Nej |
| 206 | Exakt kontantbetalning | Slutför transaktionen med en knapptryckning och acceptera beloppet som ska betalas kontant (exakt växel). | Ja | Ja | Nej | Ja | Nej |
| 204 | Checkbetalning | Ta emot en check som betalning. | Ja | Ja | Nej | Ja | Nej |
| 213 | Tillgodokvittobetalning | Acceptera en kreditnota (verifikation) som har utfärdats av butiken. | Ja | Ja | Nej | Nej | Nej |
| 203 | Betalning i annan valuta | Ta emot betalning i olika valutor. | Ja | Ja | Nej | Ja | Nej |
| 202 | Kundkontobetalning | Läs in transaktionen till en kunds konto. Den här betalsättet är inte giltig för kundens orderinsättningar. | Ja | Ja | Nej | Nej | Nej |
| 214 | Presentkortsbetalning | Acceptera ett presentkort som har utfärdats av butiken. | Ja | Ja | Nej | Nej | Nej |
| 207 | Betala förmån | Acceptera ett förmånskort för betalning och lös in poäng mot produkter som uppfyller kraven. | Ja | Ja | Nej | Nej | Nej |
| 634 | Betalningshistorik | Visa kundens betalningshistorik för den aktuella kundordern. | Ja | Ja | Nej | Nej | Nej |
| 803 | Plockning och mottagning | Öppna sidan **plockning och mottagning** där du kan välja order, plocka eller ta emot i lagret. | Ja | Ja | Ja | Nej | Nej |
| 632 | upphämta alla produkter | Ange uppfyllelsemetoden till **butiksupphämtning** för alla rader. | Ja | Ja | Nej | Ja\* | Nej |
| 631 | upphämta valda produkter | Ange uppfyllelsemetoden till **butiksupphämtning** för valda rader. | Ja | Ja | Nej | Ja\* | Nej |
| 400 | Popup-meny | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 101 | Priskontroll | Den här operationen låter användaren leta upp priset för en viss produkt. | Ja | Ja | Ja | Ja | Nej |
| 104 | Prisåsidosättning | Åsidosätter priset på en produkt, om produkten har ställts in på att tillåta prisåsidosättning. | Ja | Ja | Nej | Ja | Nej |
| 1058 | Skriv ut skatt X | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 1059 | Skriv ut skatt Z | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 927 | Skriv ut artikeletikett | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 926 | Skriv ut hylletikett | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 1056 | Skriv ut X | Skriv ut X rapport för aktuellt skift. | Ja | Ja | Ja | Nej | Nej |
| 103 | Produktkommentar | Lägg till en kommentar på den valda radartikeln i transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 100 | Produktförsäljning | Lägg till en specifierad produkt i transaktionen. | Ja | Ja | Ja | Ja | Nej |
| 108 | Produktsökning | Sök efter en produkt genom att navigera till produktsöksidan i kassan. | Ja | Ja | Ja | Ja | Nej |
| 633 | Utgångsdatum för offert | Visa eller ändra förfallodatum för en försäljningsoffert. | Ja | Ja | Nej | Ja\* | Nej |
| 627 | Beräkna om | Beräkna om alla kundorderrader och skatter, baserat på den aktuella konfigurationen. | Ja | Ja | Nej | Ja\* | Nej |
| 143 | Räkna om avgifter | Beräkna om de automatiska avgifter som tillämpas på ordern. | Ja | Ja | Nej | Nej| Nej |
| 515 | Återkalla order | Sök efter och återkalla kundorder och försäljningsofferter. | Ja | Ja | Ja | Nej | Nej |
| 504 | Återkalla transaktion | Återkalla en tidigare uppskjuten transaktion från den aktuella butiken. | Ja | Ja | Nej | Ja‡ | Nej |
| 305 | Utnyttja förmånspoäng | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Ja |
| 635 | Återbetala leveransavgifter | Återbetala fraktkostnader för en annullerad order. | Nej | Nej | Nej | Nej | Nej |
| 644 | Ta bort kupongkod | Uppmana användaren till att ta bort kuponger genom att markera dem i en lista över kuponger som associeras med transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 1057 | Skriv ut Z igen | Skriv ut Z-rapporten igen för föregående skift. | Ja | Ja | Ja | Nej | Nej |
| 1216 | Ange ett nytt lösenord | Den här operationen låter användaren med behörighet att återställa lösenord för en annan medarbetares med hjälp av ett tillfälligt lösenord. | Ja | Ja | Ja | Nej | Nej |
| 1219 | Öppna URL i kassa | Öppna en adminkonfigurerad URL i kassan. | Ja | Ja | Ja | Ja | Nej |
| 109 | Returnera produkt | Utför en retur av enskilda produkter. Nästa skannade produkt visas som en returnerad produkt som har en negativ kvantitet och pris. | Ja | Ja | Nej | Ja | Nej |
| 114 | Returtransaktion | Återställa en tidigare transaktion genom dess kvittonummer för att returnera några eller alla produkter. | Ja | Ja | Ja | Ja§ | Nej |
| 1211 | Lämna pengar i kassaskåp | Flytta pengar från POS till ett kassaskåp. | Ja | Ja | Ja | Ja | Nej |
| 516 | Försäljningsfaktura | Den här åtgärden kan kunden göra betalningar till den valda fakturan. | Ja | Ja | Nej | Nej | Nej |
| 502 | Säljare | Ange värdet **Mottagare** på en försäljningsorder för kundorder i POS. | Ja | Ja | Nej | Ja\* | Nej |
| 2000 | Hantering av tidsplan | Åtgärden stöds inte ännu. | Ja | Ja | Ja | Nej | Nej |
| 2001 | Tidsplanera begäranden | Åtgärden stöds inte ännu. | Ja | Ja | Ja | Nej | Nej |
| 622 | Sök efter order | Denna operation låter användare förkonfigurera kassaknappar för att utföra sökningar efter artikel, kund eller kategori. | Ja | Ja | Ja | Ja | Nej |
| 1213 | Sök leveransadress | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 709 | Välj hardware station | Välj maskinvarustation i en lista med tillgängliga maskinvarustationer. | Ja | Ja | Ja | Ja | Nej |
| 637 | Ställ in standardförsäljningsrepresentant på transaktion | Välj här operationen låter användaren välja ett av de berättigade provisionssäljgrupperna (säljare) som standard säljare för rader som läggs till senare. | Ja | Ja | Nej | Ja | Nej |
| 105 | Ställ in kvantitet | Ändra kvantiteten för en radartikel i transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 638 | Ange säljare på rad | Välj ett av de berättigade provisionssäljgrupperna (säljare) för den nuvarande valda raden. | Ja | Ja | Nej | Ja | Nej |
| 630 | Leverera alla produkter | Anger uppfyllelseläget till **leverans** för alla radartiklar. | Ja | Ja | Nej | Ja\* | Nej |
| 629 | Leverera valda produkter | Ange uppfyllelseläget till **Leverans** för valda rader. | Ja | Ja | Nej | Ja\* | Nej |
| 115 | Visa journal | Visa butikens journal. Du kan visa transaktioner, skriva ut kvitton och presentkvitton och återkalla för retur. | Ja | Ja | Ja | Ja\*\* | Nej |
| 802 | Lagerinventering | Skapa eller ändra lagrets inventeringsjournaler för fysiskt lager eller rullande inventeringar. | Ja | Ja | Ja | Nej | Nej |
| 401 | Undermeny | Denna operation tar användaren till en annan länkad knappsats. | Ja | Ja | Ja | Ja | Nej |
| 1054 | Skjut upp skift | Avbryt det aktuella skiftet så att ett nytt eller annat skift kan aktiveras på den aktuella journalen. | Ja | Ja | Ja | Nej | Nej |
| 503 | Skjut upp transaktion | Avbryt den aktuella transaktionen, så att den kan återställas senare i butiken. | Ja | Ja | Nej | Ja‡ | Nej |
| 1004 | Uppgiftsregistrering | Öppna uppgiftsregistrering om du vill registrera procedurmässig steg i POS. | Nej | Nej | Nej | Ja | Nej |
| 1052 | Kassaavstämning | Ange penningbelopp i kassan för varje räknat betalningssätt. | Ja | Ja | Ja | Ja | Nej |
| 1210 | Borttagning av betalningsmedel | Ta bort pengar från den aktuella kassalådan eller skiftet. | Ja | Ja | Ja | Ja | Nej |
| 920 | Stämpelklocka | Stämpla in och stämpla ut från arbetsskift och raster. | Ja | Ja | Ja | Nej | Nej |
| 302 | Totalt rabattbelopp | Ange ett rabattbeloppet för transaktionen. Denna operation gäller endast för artiklar som kan ha rabatt och bara i de angivna rabattgränserna. | Ja | Ja | Nej | Ja | Nej |
| 303 | Totalrabatt i procent | Ange en rabattprocent för transaktionen. Denna operation gäller endast för artiklar som kan ha rabatt och bara i de angivna rabattgränserna. | Ja | Ja | Nej | Ja | Nej |
| 501 | Transaktionskommentar | Lägg till en kommentar i den nuvarande transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 922 | Visa produktinformation | Öppna produktinformationssidan för den valda radartikeln. | Ja | Ja | Nej | Ja | Nej |
| 1003 | Visa rapporter | Visa rapporter som har konfigurerats för den aktuella användaren. | Ja | Ja | Ja | Nej | Nej |
| 921 | Visa stämpelklocksregistreringar | Visa stämpelklocksregistreringarna för alla anställda i butiken. | Ja | Ja | Ja | Nej | Nej |
| 211 | Annullera betalning | Annullera den markerade betalningsraden från transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 102 | Annullera produkt | Annullera den markerade radartikeln från transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 500 | Annullera transaktion | Annullera den aktuella transaktionen. | Ja | Ja | Nej | Ja | Nej |
| 916 | Windows Workflow Foundation | Den här operationen stöds inte. | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej |
| 924 | X-rapport för bankkort | Den här operationen stöds inte. | Inte aktuellt | Inte aktuellt | Inte aktuellt | Inte aktuellt | Ja |
| 311 | Ta bort systemrabatter från transaktioner | Ta bort alla tillämpade rabatter i systemet, inklusive kupongbaserade rabatter, från transaktionen. Detta innebär inte att manuella rabatter tas bort. | Ja | Ja | Ja | Ja | Nej |
| 312 | Återanvända systemrabatter | Återanvänd systemrabatter på transaktionen om de tagits bort med hjälp av åtgärden **Ta bort systemrabatter från transaktion**. | Ja | Ja | Ja | Ja | Nej |

\*Operationen är endast tillgänglig i offlineläge när en kundorder eller försäljningsoffert skapas, och om offlineskapade av kundorder och försäljningsofferter som har konfigurerats i kassafunktionsprofilen. Operationen kan inte utföras när order skapas med Realtidstjänst eller när en order har återkallats eller redigeras.

† Operationen kan utföras i frånkopplat läge bara när POS är konfigurerad för att skapa kunder offline i kassafunktionalitetsprofilen.

‡ När POS är offline kan uppskjutna transaktioner endast återställas från aktuella kassans offlinedatabas. Användare kan inte göra uppehåll och återkalla transaktioner genom journaler.

§ När POS är offline kan endast transaktioner i den aktuella offlinedatabasen återställas för retur.

\*\* När POS är offline kan endast transaktioner i den aktuella offlinekanaldatabasen visas i journalen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
