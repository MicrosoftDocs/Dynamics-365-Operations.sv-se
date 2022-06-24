---
title: Översikt över leverantörsfakturor
description: Det här avsnittet innehåller allmän information om leverantörsfakturor.
author: abruer
ms.date: 02/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b88390085d86956c38c0fc167395509d0c54f860
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894183"
---
# <a name="vendor-invoices-overview"></a>Översikt över leverantörsfakturor

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Det här avsnittet innehåller allmän information om leverantörsfakturor. Leverantörsfakturor är förfrågningar gällande betalning av varor och tjänster. Leverantörsfakturor kan komma att representera en faktura för pågående tjänster eller också baseras på inköpsorder för specifika varor och tjänster.

## <a name="vendor-invoices"></a>Leverantörsfakturor

En leverantörsfaktura från en inköpsorder skapas när produkter eller tjänster tas emot enligt en inköpsorder som skickats till en leverantör. Leverantörsfakturor innehåller en rubrik och en eller flera rader för artiklar eller tjänster. En leverantörsfaktura slutför cykeln från inköpsordern till produktinleveransen till leverantörsfakturan.

Även om vissa leverantörsfakturor är kopplade till en inköpsorder kan leverantörsfakturor också innehålla rader som inte motsvarar inköpsorderrader. Du kan också skapa leverantörsfakturor som inte är kopplade till en inköpsorder. Dessa leverantörsfakturor kan representera pågående tjänster, till exempel en elräkning. Du behöver inte referera till en inköpsorder när du lägger till en pågående tjänst.

Det finns flera sätt att ange en leverantörsfaktura:

- Leverantörsfakturaregistret låter dig ange fakturor som inte refererar till en inköpsorder snabbt så att du kan periodisera utgiften. Med godkännandejournalen för leverantörsfaktura väljer du dessa fakturor och bokför dem i leverantörssaldot för att återföra periodiseringen.
- I leverantörsfakturajournalen kan du snabbt ange fakturor som inte refererar till en inköpsorder i ett enda steg.
- Tillsammans med leverantörsfakturapoolen kan du snabbt ange fakturorna som ska periodisera utgiften i leverantörsfakturaregistret. Du kan öppna kopplade inköpsorder senare för att bokföra fakturan mot utgiftskonto.
- Sidorna **Öppna leverantörsfakturor** och **Väntande leverantörsfakturor** gör det möjligt att skapa leverantörsfakturor från bekräftade inköpsorder.

Följande diskussion innehåller mer information om hur du använder sidorna **Öppna leverantörsfakturor** eller **Väntande leverantörsfakturor** för att skapa en leverantörsfaktura från en inköpsorder.

## <a name="understanding-invoice-line-quantities"></a>Förstå fakturaradkvantiteter

När du öppnar en leverantörsfaktura från en relaterad inköpsorder skapar systemet fakturarader från inköpsordern. Som standard tar systemet kvantiteterna från produktinleveransen. Du kan dock använda en av följande standardinställningar:

- **Kvantitet för Inleverera nu** – Använd det här alternativet för delförsändelser. Standardvärdet i fältet **Kvantitet** anges till den kvantitet som anges i fältet **Inleverera nu** på inköpsordern.
- **Beställd kvantitet** – Använd det här alternativet för fullständiga försändelser. Standardvärdet i fältet **Kvantitet** anges som den kvantitet som anges i fältet **Beställt** på inköpsordern.
- **Registrerad kvantitet** – Använd det här alternativet om artikeln måste registreras på sättet som anges på sidan **Artikelmodellgrupper**. Standardvärdet i fältet **Kvantitet** är den fysiska uppdaterade kvantiteten som har registrerats.
- **Kvantitet för produktinleverans** – Använd det här alternativet om en produktinleverans redan har inlevererats för ordern. Standardvärdet i fältet **Kvantitet** är den totala kvantiteten i tillgängliga produktinleveranser.
- **Registrerade kvantitet och tjänster** – Använd det här alternativet om kvantiteter har registrerats i införseljournaler för artiklar i lager eller artiklar som inte lagras. Det här alternativet inkluderar tjänster, oavsett om de registreras inte.

Om din juridiska person använder fakturamatchning kan du visa resultaten på kvantiteten som matchar i kolumnen **Matchning av kvantitet för produktinleverans**. Du kan också använda knappen **Matcha detaljer** på fliken **Granska** på åtgärdsfönstret om du vill visa resultatet av kvantitetsmatchningen.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Lägga till en rad som inte finns på inköpsordern

Du kan lägga till en rad som inte fanns i inköpsordern till leverantörsfakturan. Du måste välja en artikelnummer eller anskaffningskategori. Du kan sedan lägga till kvantiteter, priser och belopp på raden. Raden tas bara med i matchningspolicyer för fakturasummor.

## <a name="submitting-a-vendor-invoice-for-review"></a>Skicka in en leverantörsfaktura för granskning

Organisationen kan använda arbetsflöden för att hantera granskningen för leverantörsfakturor. Arbetsflödesgranskningen kan krävas för fakturahuvudet, fakturaraden eller båda. Arbetsflödeskontrollerna används för sidhuvudet eller raden beroende på var fokus ligger innan du väljer kontrollen. Istället för knappen **Bokför** skickar knappen **Skicka** leverantörsfakturan genom granskningsprocessen.

### <a name="preventing-invoice-from-being-submitted-to-workflow"></a>Förhindra att faktura skickas till arbetsflödet 

Nedan kan du på flera sätt förhindra att en faktura skickas till ett arbetsflöde.

- **Fakturatotal och den registrerade totalen är inte lika.** Den person som har skickat fakturan får en notifiering om att summorna inte är identiska. Notifieringen ger dig möjlighet att korrigera saldona innan du skickar fakturan till arbetsflödet på nytt. Den här funktionen är tillgänglig om parametern **förbjuden överföring till arbetsflödet när faktura summan och den registrerade faktura summan inte lika** på sidan **funktionshantering** är aktiverad. 
- **Fakturan innehåller icke-allokerade tillägg.** Den person som skickade fakturan får en notifiering om att fakturan innehåller icke-allokerade tillägg så att de kan korrigera fakturan innan den skickas vidare till arbetsflödet. Den här funktionen är tillgänglig om parametern **förbjuden överföring där det finns icke-allokerade tillägg på en leverantörsfaktura** på sidan **funktionshantering** är aktiverad.
- **Fakturan innehåller samma fakturanummer som en annan bokförd faktura.** Den person som har skickat fakturan får ett meddelande om att en faktura med ett dubblettnummer har hittats. Dubblettnumret kan korrigeras innan fakturan skickas till arbetsflödet på nytt. Denna notifiering visas när parametern **Kontrollera använt fakturanummer** under Leverantörsreskontra anges som **Avvisa dubblett**. Den här funktionen är tillgänglig om parametern **Förbud att skicka till arbetsflöde när fakturanumret redan finns på en bokförd faktura och ditt system inte är inställt för att acceptera duplicerade fakturanummer** på sidan **funktionshantering** aktiveras.
- **Fakturan innehåller en rad där fakturakvantiteten är mindre än den matchade produktinleveranskvantiteten.** Den person som skickar fakturan eller försöker att bokföra får ett meddelande om att kvantiteterna inte är lika. Detta meddelande ger dig möjlighet att korrigera värdena innan du skickar fakturan till arbetsflödet på nytt. Den här funktionen är tillgänglig om parametern **Blockera bokföring och inlämning av leverantörsfakturor till arbetsflödet** på sidan **Funktionshantering** aktiveras och parametern **Blockera publicering och inlämning till arbetsflöde** på sidan **Parametrar för leverantörsreskontra** aktiveras.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Matcha leverantörsfakturor mot produktinleveranser

Du kan ange och spara information för leverantörsfakturor, och du kan matcha fakturarader mot produktinleveransrader. Det går även att matcha delkvantiteter på en rad.

Du kan skapa en leverantörsfaktura som baseras på de radartiklar i produktinleveransen som har inlevererats till nuvarande datum, även om alla artiklar för en viss inköpsorder ännu inte har inlevererats. Använd det här alternativet om till exempel providern skickar en faktura per månad som täcker alla leveranser som skickas den månaden. Varje produktinleverans representerar en del av eller hela leveransen av artiklarna på inköpsordern.

När en faktura är i arbetsflödet kan godkännaren uppdatera fakturakvantiteter så att dessa matchar värdet i fältet **Produktinleveranskvantitet-att-matcha**. Detta gör du genom att välja funktionen **Uppdatera fakturakvantiteter så att dessa matchar produktinleveranskvantiteterna i arbetsflödet** i arbetsytan **Funktionshantering** och sedan **Aktivera**. Om en godkännare i arbetsflödesprocessen har tagit bort alla träffar från alla produktinleveranser från fakturaraden, tas fakturaraden bort. Om den här funktionen inte är aktiverad, uppdateras inte fakturakvantiteter för fakturor i arbetsflödet.

När du bokför fakturan uppdateras kvantiteten **Fakturarest** för varje artikel med summan av de inlevererade kvantiteterna från de valda produktinleveranserna. Om både kvantiteten **Fakturarest** och kvantiteten **Leveransrest** för alla artiklar på inköpsordern är noll, ändras statusen för inköpsordern till **Fakturerad**. Om kvantiteten **Fakturarest** inte är noll, ändras inte inköpsorderns status och ytterligare fakturor kan registreras för den.

Det här alternativet förutsätter det att minst en produktinleverans har bokförts för inköpsordern. Leverantörsfakturan baseras på dessa produktinleveranser och återspeglar kvantiteterna från dem. Den ekonomiska informationen för fakturan baseras på informationen som registreras när du bokför fakturan.

Mer information finns i [Registrera leverantörsfakturan och matcha mot mottagen kvantitet](../accounts-payable/tasks/record-vendor-invoice-match-against-received-quantity.md)

## <a name="configure-an-automated-task-for-vendor-invoice-workflow-to-post-the-vendor-invoice-using-a-batch-job"></a>Konfigurera en automatisk uppgift för ett arbetsflöde för leverantörsfakturor så här bokför du leverantörsfakturan med ett batch-jobb

Du kan lägga till en automatisk bokföringsuppgift i arbetsflödet för leverantörsfakturor så att fakturor bearbetas i en batch. Om du bokför fakturor i en batch kan arbetsflödesprocessen fortsätta utan att behöva vänta på att bokföringen ska slutföras, vilket förbättrar övergripande prestanda för alla uppgifter som skickas till arbetsflödet.

Om du vill bokföra en leverantörsfaktura i en batch, på sidan **funktionshantering**, aktivera parametern **Batch-bokföring av leverantörsfaktura**. Arbetsflöden för leverantörsfakturor konfigureras genom att gå till **Leverantörsreskontra > Inställningar > Leverantörsreskontra**.

Du kan se uppgiften **bokföra leverantörsfakturan med ett batch-jobb** i arbetsflödesredigeraren oavsett om funktionsparametern **Batch-bokföring av leverantörsfaktura** är aktiverad. Om funktionsparametern inte är aktiverad kommer en faktura som innehåller **Bokför leverantörsfakturan med en batch-uppgift** inte att bearbeta i arbetsflödet förrän parametern har aktiverats. Uppgiften **Bokför leverantörsfakturan med hjälp av en batch** får inte användas i samma arbetsflöde som automatiska uppgiften **Bokför leverantörsfakturor**. Dessutom bör uppgiften **Bokför leverantörsfakturan med hjälp av en batch** bör vara det sista elementet i arbetsflödeskonfigurationen.

Du kan ange antalet fakturor som ska inkluderas i batchen och antalet timmar att vänta innan en batch omplaneras, genom att gå till **leverantörsreskontra > inställningarna > parametrar för leverantörsreskontra > faktura > arbetsflöde för faktura**. 

## <a name="working-with-multiple-invoices"></a>Arbeta med flera fakturor

Du kan arbeta med flera fakturor samtidigt och bokföra dem samtidigt. Om du måste skapa flera fakturor, använd sidan **Väntande leverantörsfakturor**. Om du måste bokföra och skriva ut flera leverantörsfakturor använder du **fakturagodkännandejournalen**. Om du använder **fakturagodkännandejournalen** måste minst en produktinleverans vara bokförd för inköpsordern och en faktura för inköpsordern ha bokförts i ett fakturaregister. Den ekonomiska informationen för fakturan kommer från fakturan som bokfördes i registret.

## <a name="recovering-vendor-invoices-that-are-being-used"></a>Återställer leverantörsfakturor som används

När en leverantörsfaktura används kan den inte redigeras av en annan användare. Men statusen för en faktura kan ibland indikera att fakturan används, även om den inte redigeras aktivt. Till exempel kanske programmet slutar svara när fakturan har redigerats eller en användare kanske lämnat fakturan öppen i programmet av misstag.

Du kan använda sidan **Återställa leverantörsfakturor** om du vill återställa eller frisläppa leverantörsfakturor som har använts under längre än fyra timmar, så att de kan redigeras. Du kan öppna den här sidan från navigeringen **Periodisk uppgift** eller en panel på arbetsytan **Leverantörsfakturaregistrering**. När en faktura har återskapats blir den tillgänglig för redigering på sidan **leverantörsfakturan**.

Du kan endast komma åt sidan **återställa leverantörsfakturor** om säkerhetsprogrambehörighet och privilegium **återställa leverantörsfakturor som används** har tilldelats till dig. Dessutom måste parametern **Tillåt återställning av leverantörsfaktura** på sidan **Parametrar för leverantörsreskontra** måste vara aktiverad.

## <a name="resetting-the-workflow-status-for-vendor-invoices-from-unrecoverable-to-draft"></a>Återställa arbetsflödesstatus för leverantörsfakturor från Oåterkalleligt till Utkast

En arbetsflödesinstans som har stoppats på grund av ett oåterkalleligt fel får arbetsflödesstatusen **oåterkalleligt**. När statusen för ett arbetsflöde för leverantörsfakturor är **Oåterkalleligt** kan du återställa den till **Utkast** genom att välja **Återkalla**. Du kan sedan redigera leverantörsfakturan. Den här funktionen är tillgänglig om parametern **Återställa arbetsflödesstatus för leverantörsfakturor från Oåterkalleligt till Utkast** på sidan **Funktionshantering** är aktiverad.

På sidan **Arbetsflödeshistorik** för leverantörsfakturor kan du återställa arbetsflödesstatusen till **utkast**. Du kan öppna den här sidan från **leverantörsfakturan** eller från navigeringen **Allmänt > Förfrågningar > Arbetsflöde**. Om du vill återställa arbetsflödesstatus **utkast**, välj **återkalla**. Du kan också återställa arbetsflödesstatus till utkast genom att välja åtgärden **återkalla** på sidan **leverantörsfaktura** eller **väntande leverantörsfakturor**. När arbetsflödesstatusen har återställts till **Utkast** blir den tillgänglig för redigering på sidan **leverantörsfaktura**.

## <a name="viewing-the-invoice-total-on-the-pending-vendor-invoices-page"></a>Visa fakturasumman på sidan Väntande leverantörsfakturor

Du kan visa fakturasumman på sidan **Väntande leverantörsfakturor** genom att aktivera parametern **Visa fakturasumma i listan med pågående leverantörsfakturor** på sidan **Parametrar för leverantörsreskontra**. 

## <a name="vendor-open-transactions-report"></a>Rapport med öppna leverantörstransaktioner

Rapporten **Öppna leverantörstransaktioner** innehåller detaljerad information om de öppna transaktionerna för varje leverantör per det datum som du anger. Den här rapporten används ofta under granskningsproceduren för att verifiera saldon mellan leverantörsbokstransaktioner och redovisningskontotransaktioner.

För varje transaktion innehåller rapporten följande information:

- Fakturanummer
- Transaktionsdatum
- Verifikationsnummer
- Transaktionsbelopp i transaktionsvalutan och i redovisningsvalutan
- Kreditsaldo i transaktionsvalutan och i redovisningsvalutan
- Debetsaldo i transaktionsvalutan och i redovisningsvalutan
- Delsummabelopp i redovisningsvaluta
- Betalningens förfallodatum

### <a name="filter-the-data-on-the-report"></a>Filtrera data i rapporten

När du genererar rapporten **Öppna leverantörstransaktioner** visas följande standardparametrar. Du kan använda dem om du vill filtrera vilka data som ska ingå i rapporten.

- **Exkludera framtida kvittning** – Markera den här kryssrutan om du vill exkludera transaktioner som kvittas efter det datum som har angetts i **öppna transaktioner per** fält.
- **Öppna transaktioner per** – Ange ett datum om du vill inkludera transaktioner som är öppna från och med detta datum. Om du inte anger något datum används maximalt datum i det här fältet. (Det högsta datumet är det senaste datumet som systemet accepterar, 31 december 2154.) Nästa gång rapporten körs ställs det här fältet som standard in det senaste datumet som angavs i den.

Du kan använda filtren under fältet **Post att inkluderas** om du vill ta med fält om du ytterligare vill begränsa transaktionsdata som inkluderas i rapporten.

## <a name="additional-resources"></a>Ytterligare resurser

- [Ställ in leverantörsfakturapolicyer](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md)
- [Huvudfakturadata i AP-system med hjälp av leverantörsfakturan](tasks/key-invoice-data-ap-system-vendor-invoice.md)
- [Mata in fakturadata i leverantörsreskontra genom att använda en godkänd journal](tasks/key-invoice-data-into-ap-system-approval-journal.md)
- [Mata in fakturadata i LR-systemet genom att använda fakturapool](tasks/key-invoice-data-into-ap-system-invoice-pool.md)
- [Registrera en leverantörsfaktura i fakturajournalen](tasks/record-vendor-invoice-invoice-journal.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
