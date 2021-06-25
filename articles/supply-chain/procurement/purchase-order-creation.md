---
title: Skapa inköpsorder
description: Den här artikeln innehåller en beskrivning av processen och alternativen för att skapa en inköpsorder manuellt.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 93053
ms.assetid: 25b1c9f1-20f8-4cf5-b87c-876e32f68846
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d09b6f693f3396da181a0f47051b7c961aa55e03
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188255"
---
# <a name="create-purchase-orders"></a>Skapa inköpsorder

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller en beskrivning av processen och alternativen för att skapa en inköpsorder manuellt.

När du skapar en inköpsorder (IO) anges allmän information om hela ordern i inköpsorderhuvudet och du kan sedan lägga till en eller flera inköpsorderrader. Den här artikeln innehåller en beskrivning av några av de vanligaste alternativen som finns.  

Du kan också skapa inköpsorder genom att kopiera rader från ett annat inköpsorderdokument eller från en försäljningsorder. I det här fallet kan du byta tecken på lagret på samma sätt som du skulle byta tecken på en faktura för att indikera kredit.  

Även om du kan skapa inköpsorder manuellt genereras de vanligtvis från andra processer. Order kan skapas automatiskt utifrån andra dokument såsom inköpsrekvisitioner. De kan också skapas som en del av huvudplaneringsprocessen via planerade inköpsorder. Om du använder inköpsavtal kan inköpsorder skapas av åtgärden **Frisläpp order**. Det finns även mer avancerade metoder för att skapa en inköpsorder automatiskt. Order kan exempelvis skapas när du använder direktleverans eller koncerninterna orderkedjor.

## <a name="creating-a-purchase-order-header"></a>Skapa ett inköpsorderhuvud
När du skapar en ny inköpsorder visas en dialogruta där du kan ange den vanligaste informationen för inköpsorderhuvudet. När du klickar på **OK** för att stänga dialogrutan skapas ordern och du kan därefter lägga till ytterligare information i huvudet.  

Den första detaljen du måste ta hänsyn till när du skapar en inköpsorder är ordertypen. **Inköpsorder** är den vanligaste typen. Om det krävs en kreditfaktura kan du dock använda typen **Returnerad order**.  

Du måste ange leverantören i fältet **Leverantörskonto**. I det här fältet kan söka du på kontot eller leverantörens namn. Om en leverantör levererar från flera platser, men enbart använder ett enda fakturakonto, kan du välja det fakturakontot i fältet **Fakturakonto** och sedan använda det till olika leverantörskonton. Om du måste skapa en inköpsorder för produkter som inte kommer att beställas flera gånger kan du använda alternativet **Engångsleverantör**. Med hjälp av det här alternativet skapas ett nytt leverantörskonto automatiskt. Kontot markeras som ett engångskonto för att stödja en kommande rensningsprocess för engångskonton i modulen **Leverantörsreskontra**. När du väljer ett leverantörskonto ärver många fält i inköpsorderhuvudet standardvärdena från den information som är kopplad till leverantörskontot. Till exempel kopieras standardwebbplatsen för leverans och lagerställe från leverantörsinformationen. Du kan dock åsidosätta standardvärdena om inköpet är avsett för en annan plats.  

Om leverantören har tillhandahållit ett referensnummer för ordern kan du registrera den informationen i fältet **Leverantörsreferens**. För returnerade order måste du ange ett värde i fältet **RMA** som en referens till leverantörens tillstånd för att bearbeta returen.  

Om ett inköpsavtal är kopplat till ordern måste du ange den informationen i fältet **Inköpsavtal**.  

Inköpsorderhuvudet innehåller även information om avgifter som gäller för hela ordern och inte enbart för enskilda rader. Avgifter kan läggas till i ordern automatiskt om automatiska avgifter har ställts in för leverantören eller leverantörens avgiftsgrupp. Du kan även lägga till avgifter manuellt i orderhuvudet genom att klicka på **Underhåll avgifter** i åtgärdsfönstret.

## <a name="adding-purchase-order-lines"></a>Lägga till inköpsorderrader
En inköpsorder kan avse fysiska produkter eller tjänster. En inställning i lagermodellgruppen anger om ett visst artikelnummer gäller för en produkt eller en tjänst. Vanligtvis registreras den artikel som anskaffas med ett artikelnummer. Om ordern gäller för produkter eller tjänster som konsumeras direkt kan du dock även registrera artikeln med hjälp av en anskaffningskategori.  

Inköpsorderrader innehåller många fält, men många av dessa fält har ett standardvärde eller ett värde som ärvs från orderhuvudet. Ytterligare fält ställs in när du väljer en produkt eller tjänst. Fälten för artikelnummer, kvantitet och begärt leveransdatum datum är de fält som oftast ställs in manuellt. Information om enhetspris och rabatter är också mycket viktig, men värdena i dessa fält bestäms ofta av handelsavtal eller inköpsavtal.  

Du kan söka på hela eller en del av produktens namn i stället för med hjälp av artikelnumret när du väljer en produkt. Om produkten har flera varianter såsom olika storlekar kan du se en översikt över tillgängliga varianter med hjälp av funktionen **Lägg till rader** eller med hjälp av sökning som är tillgänglig i fältet **Variantnummer**.  

Ofta behöver du ange flera dimensioner för den artikel som har valts för varje inköpsorderrad. Vilka dimensioner som måste anges beror på vilka dimensionsgrupper som har tilldelats till produktmallsdefinitionen. Exempelvis behöver du ofta ange en webbplats och ett lagerställe för att indikera vart produkten ska levereras. Du kan identifiera produktvarianter genom att ange ett variantnummer eller genom att ange värdena för en eller flera produktdimensioner såsom färg, storlek, konfiguration eller stil. Genom spårningsdimensioner såsom batch- och serienummer kan du identifiera varje lagerparti. När du har skapat en order kan du hämta dimensionsvärden på ordern med hjälp av åtgärden **Registrering**. Du kanske exempelvis har beställt fem enheter av en artikel. Senare registrerar du att tre av enheterna är svarta och att två är blå. Den här metoden är ett alternativ till hämtning av dimensionsinformation under införselregistreringen.  

Du kan kontrollera uppgifter om lagertransaktionsstatus för lagerförda produkter. Du kanske vill kontrollera lagerbehållningen för att kunna avgöra hur mycket du ska beställa. Alternativt kanske du vill granska lagerstatusen för en beställd kvantitet för att se om registreringen av inkommande artiklar har genomförts.  

En inköpsorderrad som används för att returnera en produkt till leverantören har en negativ kvantitet. Du kan välja att ett visst parti ska returneras med hjälp av åtgärden **Reservation**.  

Ibland kanske du vill dela upp kvantiteten du har beställt så att olika delar av den levereras vid olika tidpunkter. Du kan ställa in dessa leveranser med hjälp av åtgärden **Leveransplan** som finns i menyn **Inköpsorderrad** i vyn **Rader**.  

Avgifter kan läggas till på inköpsorderrader automatiskt om automatiska avgifter har ställts in för leverantören eller avgiftsgruppen för leverantören och för artikeln eller avgiftsgruppen för artikeln. Kostnader läggs dock oftast till manuellt på orderradnivå. Om du vill lägga till en avgift kan du öppna sidan **Underhåll avgifter** med hjälp av åtgärden **Underhåll avgifter** i menyn **Finance** i vyn **Rader**. Fördelen med att lägga till avgifter direkt på orderradnivå är att avgiften kan allokeras som en lagerkostnad. Använd debetalternativet **Artikel** för att ställa in avgiftskoder för kontoproduktkostnader. Dessa typer av avgifter ska allokeras från inköpsorderhuvudet till raderna innan ordern kan bekräftas. Du kanske vill allokera tillägg baserat på kvantiteten på varje rad. Avgiftskategorin påverkar även hur avgifter redovisas. Fasta avgifter till exempel anger ett fast belopp och avgifter i procent beräknas som en procentsats av nettobeloppet för orderraden. Inköpsorder kan tilldelas till en last och lasten kan innehålla en uppskattning av den förväntade utgiften för transportkostnader. Du kan allokera den här kostnaden från lasten tillbaka till inköpsorderraderna.

## <a name="purchase-order-actions"></a>Inköpsorderåtgärder
När du har lagt till huvudet och raderna i inköpsordern måste du ofta utföra ytterligare steg innan ordern är klar att bekräftas. Eftersom det finns så många alternativ kan det vara praktiskt att använda [Åtgärdssökning](../../fin-ops-core/fin-ops/get-started/action-search.md) för att hitta relevant menyalternativ.  

Du kan konfigurera produkter på ordern så att de har tilläggsartiklar. Tilläggsartiklar är produkter som måste eller kan köpas tillsammans med andra produkter. Tilläggsprodukter kan läggas till kostnadsfritt som medföljande produkter. Du kan även själv bestämma om du vill lägga till dem i ordern eller inte. Du kan granska tilläggsartiklarna efter att varje orderrad har lagts till. Du kommer dock troligtvis att tycka att det är enklare att granska och lägga till relevanta tilläggsartiklar för alla orderrader med hjälp av sidan **Tilläggsartiklar** som du kan öppna från åtgärdsfönstret.  

Rabatter läggs vanligtvis till på rader när de skapas. Vissa rabatter gäller dock för hela ordern:

-   Åtgärden **Total rabatt** beräknar en totalrabatt i procent som gäller för hela ordern. Blanda inte ihop den här rabatten med kassarabatten i procent. Kassarabatter används när fakturan är betald och är kopplade till betalningskvittning efter ett visst datum.
-   Om det gäller en samköpsrabatt måste du använda åtgärden **Samköpsrabatt** för att beräkna och tilldela den till ordern. Samköpsrabatter är rabatter som kan erbjudas om summan av flera olika produkter på ordern tillsammans överskrider ett visst tröskelvärde. Endast ett fåtal företag använder denna typ av rabatt.

Avgifter som har en avgiftskod som använder debettypen **Artikel** måste tilldelas på radnivå innan ordern kan bekräftas. Det kan vara praktiskt att tilldela dessa avgifter på orderhuvudnivå så att du kan ange det totala beloppet för avgiften. I det här fallet måste avgiften då sedan allokeras till varje rad innan ordern kan bekräftas. Du kan använda åtgärden **Allokera tillägg** för att fördela belopp från avgifter som har tilldelats på huvudnivå ned till orderrader. Avgifter kan delas upp enligt nettobeloppet för varje rad, enligt det antal som har beställts eller jämnt över orderraderna. När du har tilldelat avgifterna till raderna tas avgiften bort från orderhuvudet.  

Inköpsorder kan konfigureras till att kräva att budgetmedel allokeras till ordern innan den kan behandlas. I det här fallet kan du använda åtgärden **Budgetkontroll** för att allokera budgeten.  

Du kan behöva skjuta upp slutförandet av en inköpsorder. Du kan till exempel behöva ytterligare information om produkter eller tjänster eller så kanske du behöver få utgiften godkänd. Det finns flera sätt att hålla tillbaka en order. Till exempel kan du vänta med att bekräfta ordern. Om ett arbetsflöde för ändringshantering används ska du inte skicka ordern för godkännande. Om du måste blockera alla order för en viss leverantör kan du även markera leverantören som **Spärrad** för bearbetning i leverantörshuvudet. Det finns omständigheter som kan förhindra att ordern bearbetas. Bearbetning kan exempelvis förhindras om kreditgränser har överskridits eller om de budgetmedel som krävs inte är tillgängliga.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av inköpsorder](purchase-order-overview.md)

[Godkänn och bekräfta inköpsorder](purchase-order-approval-confirmation.md)

[Produktinleverans mot inköpsorder](product-receipt-against-purchase-orders.md)

[Översikt över leverantörsfakturor](../../finance/accounts-payable/vendor-invoices-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]