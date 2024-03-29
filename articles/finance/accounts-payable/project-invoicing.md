---
title: Projektfakturering
description: Det här avsnittet ger en översikt över projektfakturering för Tids - och materialprojekt samt Fastprisprojekt. Här finns information om fakturaförslag (preliminära fakturor), fakturakontroll, à conto-fakturering, leverantörfakturering och kreditfakturor.
author: TaylorVH
ms.date: 07/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjInvoiceCashFlow, ProjInvoiceControl, ProjInvoiceListPage, ProjInvoiceProposalDetail, ProjInvoiceProposalListPage
audience: Application User, IT Pro
ms.reviewer: zezhangzhao
ms.custom: 23111
ms.assetid: 1812d6f2-8b34-4258-8f5f-dcf12281547f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-07-06
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 4af44127d80c943ed9cebeac21d7e9c8372910f3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861688"
---
# <a name="project-invoicing"></a>Projektfakturering

[!include [banner](../includes/banner.md)]

Det här avsnittet ger en översikt över projektfakturering för Tids - och materialprojekt samt Fastprisprojekt. Här finns information om fakturaförslag (preliminära fakturor), fakturakontroll, à conto-fakturering, leverantörfakturering och kreditfakturor.

Projekttypen bestämmer vilken faktureringsprocedur som ska användas. Endast de två externa projekttyperna, Tid och material och Fastpris, går att fakturera. Tids- och materialprojekt och fastprisprojekt är alltid kopplade till ett projektkontrakt.

-   **Fastprisprojekt** – Kundfakturabeloppet baseras på fakturabetalningsplaner. Faktureringen utförs med en à conto-inställning, som även kallas för faktureringstidsplan. Fastprisprojekt kan faktureras per projekt eller per projektkontrakt.
-   **Tids- och materialprojekt** – Kundfakturabeloppet baseras på de transaktionsrader som anges på projekten. Du kan fakturera projekttransaktioner per projekt eller per projektkontrakt.

Det finns tre sätt att koppla tids- och materialprojekt och fastprisprojekt till fakturaprojekt:

-   **À conto-fakturering** – Tids- och materialprojekt och fastprisprojekt kan faktureras à conto. Två olika typer av à conto-inställningar krävs, en för varje projekttyp.
-   **Fakturering i det periodiska avsnittet** – Via de periodiska funktionerna, kan transaktionerna faktureras över projekten. De periodiska funktionerna ger en översikt över de transaktioner som måste faktureras.
-   **Användning av kreditnotor vid fakturering** – En kreditnota kan skapas för både tids- och materialprojekt och fastprisprojekt.

## <a name="invoice-proposals"></a>Fakturaförslag
Innan du skapar en kundfaktura för ett projekt kan du skapa en preliminär faktura eller ett fakturaförslag. I ett fakturaförslag kan du välja projekttransaktioner som ska inkluderas i en projektfaktura. Du kan sedan granska fakturadetaljerna innan du bokför projektfakturan och skickar den till kunden eller annan finansieringskälla.

### <a name="creating-invoice-proposals"></a>Skapar fakturaförslag

Du kan skapa fakturaförslag, genom att manuellt välja en transaktion från en lista över tillgängliga transaktioner för ett visst projekt. Du kan även ställa in faktureringsregler som anger när du automatiskt vill skapa ett fakturaförslag. Du kan till exempel skapa en faktureringsregel om du vill skapa ett fakturaförslag när arbetet med ett projekt är 25 procent, 50 procent, 75 procent och 100 procent slutfört. 

Fakturaförslag kan skapas för följande transaktioner:

-   Timmar, utgifter och andra projekttransaktioner
-   Belopp som undandras av kunderna på föregående projektfakturor.
-   Kreditfakturor
-   Belopp som en kund betalar dig innan ett projekt har startats

> [!NOTE]
> Med funktionen **Aktivera sortering per resurs under skapande av projektfakturaförslag** kan projektrevisorn sortera de projekttransaktioner som är tillgängliga för fakturering av resursen när ett nytt projektfakturaförslag skapas. Rutnätet som visar de tillgängliga projekttransaktionerna kommer att ha separata fält för **resurs-ID** och **resurs**. Med hjälp av dessa fält kan du filtrera och sortera resursnamnet. Den här funktionen är inaktiverad som standard. Den kan aktiveras med hjälp av sidan **Funktionshantering** (**Arbetsytan > funktionshantering**). Kontakta systemadministratören om du vill ha hjälp med att aktivera den här funktionen.

Du kan du skapa avgiftstransaktioner i ett fakturaförslag. Du kan också ändra försäljningspriset på tim-, utgifts-, artikel- och avgiftstransaktioner. När du bokför ett fakturaförslag kommer de uppdaterade priserna och transaktionerna att läggas till i projektrapporter och transaktionshistoriken. 

För att skapa flera kundfakturor för ett projekt måste du skapa ett fakturaförslag för varje faktura. Du kan till exempel skapa fakturor som baseras på transaktionstyp. För att ange timmar på en kundfaktura och artiklar på en annan faktura måste du skapa separata fakturaförslag för timtransaktioner och avgiftstransaktioner. 

Om ett projekt har mer än en finansieringskälla kan du skapa ett separat fakturaförslag för varje finansieringskälla. På sidan **Finansieringsregelallokeringar** kan du definiera procentadel av transaktionsbeloppet att tilldela varje finansieringskälla och källan till bokföring av avrundningsdifferenser.

### <a name="creating-customer-invoices-from-invoice-proposals"></a>Skapar kundfakturor från fakturaförslag

När du har skapat och bokfört ett fakturaförslag skapas en kundfaktura automatiskt för de transaktioner som ingår i fakturaförslaget. 

Innan du bokför ett fakturaförslag kan du lägga till eller ta bort transaktioner i det. Du kan till exempel ta bort utgiftstransaktioner som bokförts i ett projekt, men inte kan debiteras kunden. 

Om din organisation kräver att fakturaförslag granskas innan de bokförs, kan du behöva godkännas med arbetsflödet Granska projektfakturaförslag innan det bokförs.

### <a name="view-grant-information-on-project-invoice-list-pages"></a>Visa anslagsinformation på listsidor för projektfakturor

Användare i offentlig sektor kan lägga till **anslags-ID** och **anslagsnamn** på **listsidorna för projektfakturaförslag** och **projektfakturor**. Dessa kolumner aktive ras med funktionen **Lägg till anslagsinformation till listsidor för projektfakturor**. Denna funktion är inaktiverad som standard och kan aktiveras i **Arbetsytor > Funktionshantering**. Kontakta systemadministratören om du vill ha hjälp med att aktivera den här funktionen.

## <a name="on-account-invoicing"></a>A conto-fakturering
Det belopp som du anger i en à conto-faktura för ett projekt baseras på timingen, slutförandeprocenten och andra faktureringsvillkor som anges i det relaterade projektkontraktet. Beloppet beräknas inte utifrån de timmar, artiklar, utgifter eller avgifter som bokförts till projektet. 

Du måste först skapa en à conto-transaktion för ett Tid och material-projekt eller ett Fastpris-projekt, innan du kan lägga till det i à conto-transaktionen på en projektfaktura. På à conto-transaktionen anger du beloppet att fakturera en kund. Skapa en preliminär faktura (fakturaförslag) om du vill skapa en projektfaktura för beloppet. Välj à-conto-transaktionen i fakturaförslaget. Du kan granska à conto informationen i fakturaförslaget, innan du skapar en faktura för den projekt. 

### <a name="fixed-price-projects"></a>Fastprisprojekt
För fastprisprojekt baseras à conto-transaktioner på en avtalad milstolpe, leveransenhet eller delfaktureringsarrangemang som anges i ett projektkontrakt. En rad skapas för varje betalning som måste tas emot från projektkunden. Inga avdrag krävs.

### <a name="time-and-material-projects"></a>Tids- och materialprojekt

För tids- och materialprojekt kan du fakturera en kund eller annan finansieringskälla för en förskottsbetalning genom att använda ett à conto-fakturaförslag. Ange à conto-transaktioner som en rad. Du kan även ange ytterligare rader som avdrag för att räkna av eventuella förskottsbetalningar som kunden redan har gjort. Skapa avdragsrader genom att sätta minustecken före beloppet.

## <a name="invoice-control"></a>Fakturakontroll
Du kan använda fakturakontroll för att spåra både fakturerade och ej fakturerade transaktioner och analysera dessa transaktioner mot offerter för en sammanfattade vy av projekt från offert till slutförande. Du kan se vilka transaktioner som har debiterats till ett specifikt projekt och vilka rader som har fakturerats. Du kan också visa enskilda transaktioner så att du kan justera dem när de har bokförts.

## <a name="invoicing-fixed-price-projects"></a>Fakturera Fastprisprojekt
Om du vill fakturera ett fastprisprojekt måste du definiera en faktureringstidsplan och slutföra faktureringsprocessen.

### <a name="billing-schedule"></a>Faktureringstidsplan

Du kan fakturera fastprisprojekt på en faktureringstidsplan. Faktureringstidsplanen definieras som en eller flera milstolpar för projektet. För varje milstolpe kan du definiera ett visst datum, försäljningsvaluta, försäljningspris och aktivitet. 

Du kan till exempel ställa in följande faktureringstidsplan:

-   20 procent när projektkontraktet undertecknas
-   30 procent vid första leveransen
-   15 procent vid andra leveransen
-   35 procent vid slutleveransen

### <a name="invoicing-procedure"></a>Faktureringsprocedur

När milstolpsbetalningarna är klara att faktureras använder du proceduren för att fakturera à conto-belopp.

## <a name="vendor-invoicing"></a>Fakturering av leverantör
När du har beställt en artikel från en leverantör och tilldelar artikeln till ett projekt, bestämmer radegenskapen som du väljer för inköpsorderraden för den artikeln, om den inköpta artikeln ska faktureras till en kund. Om du ställer in standardegenskaperna visas de för artikeln på inköpsorderraden Radinformation (**Radinformation > Projekt > Radegenskapsbelopp**). Det finns två sätt att ändra radegenskapen:

-   Fakturera projektets kund för artikeln. För att göra detta ange radegenskapen för artikeln till ett debiterbart värde på inköpsordern och fakturera sedan kunden genom att använda rätt projektfaktureringsmetod.
-   Fakturera inte projektets kund för artikeln. Det gör du genom att inte välja den **debiterbara** radegenskapen på inköpsorderraden för artikeln. Det går sedan att fakturera inköpsordern och inga vidare åtgärder krävs.

> [!NOTE] 
> Frisläpp av kvarhållningsrader är inte debiterbara som standard. Det innebär att möjlighet att skapa ett fakturaförslag för den frisläppta kvarhållningen inte är aktiverad.

## <a name="credit-notes"></a>Kreditfakturor
När ett belopp på en kundfaktura har ett negativt värde klassificeras fakturan som en kreditfaktura. När dokumentet skrivs ut har det rubriken Kreditfaktura. 

När du skapar en kreditfaktura för att kreditera ett belopp som tidigare fakturerats, måste du först välja det fakturerade beloppet för kreditering. Därefter skapar du en kreditfaktura genom att följa samma procedur som du använder för att skapa en vanlig kundfaktura. Du måste välja transaktionerna som tidigare har bokförts i en kundfaktura och sedan skapa och bokföra ett kreditfakturaförslag. 

Samma dokument kan inkludera transaktioner som markerat för kreditering, kredittransaktioner och transaktioner som har bokförts. Dokumentet klassificeras antingen som en faktura eller en kreditfaktura beroende på om totalsumman är positiv eller negativ. 

För att kreditera ett fakturerat belopp måste du först välja det fakturerade beloppet att kreditera och sedan skapa en kreditfaktura. Skapa en kreditfaktura genom att följa samma procedur som du använder för att skapa en vanlig kundfaktura. 

Du kan skapa en faktura med negativt belopp, vilken klassificeras som en kreditfaktura. För att skapa och skriva ut kreditfakturan måste du välja transaktionerna som tidigare bokfördes för en kundfaktura och sedan ändra transaktionerna. Med undantag för juridiska personer vars primära adress är Tyskland, är titeln på fakturan Korrigeringsfaktura.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
