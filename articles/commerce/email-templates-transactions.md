---
title: Skapa e-postmallar för transaktionshändelser
description: I denna artikel beskrivs hur du skapar, överför och konfigurerar e-postmallar för transaktionshändelser i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: cc3ad01c60324d751ee52d83d93fe59593775a00
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279579"
---
# <a name="create-email-templates-for-transactional-events"></a>Skapa e-postmallar för transaktionshändelser

[!include [banner](includes/banner.md)]


I denna artikel beskrivs hur du skapar, överför och konfigurerar e-postmallar för transaktionshändelser i Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce tillhandahåller en färdig lösning för att skicka e-postmeddelanden som varnar kunder om transaktionshändelser. E-postmeddelanden kan till exempel skickas när en order läggs, är klar för upphämtning eller har levererats. Denna artikel beskriver hur du skapar, överför och konfigurerar e-postmallar som används för att skicka transaktionsmeddelanden via e-post.

## <a name="notification-types"></a>Meddelandetyper

Meddelanden kan konfigureras för att informera kunderna via e-post när specifika händelser inträffar som en del av orderns och kundens livscykel. Om du vill konfigurera meddelanden måste du mappa en e-postmall till en aviseringstyp genom att skapa en e-postnotifieringsprofil för Commerce. Mer information om hur du konfigurerar meddelandeprofiler för e-post finns i [Konfigurera profil för e-postmeddelande](email-notification-profiles.md).

Dynamics 365 Commerce har stöd för följande meddelandetyper.

### <a name="order-created"></a>Order skapad

Meddelandetypen *order som skapas* utlöses när en ny försäljningsorder skapas i Commerce headquarters.

> [!NOTE]
> Ordern skapade meddelandetypen som inte utlöses för hämtköpstransaktioner som sker vid en kassaterminal (POS). I det här fallet genereras ett e-postmeddelande och/eller ett utskrivet kvitto istället. Mer information finns i [Skicka e-postkvitton från Modern POS (MPOS)](email-receipts.md).

### <a name="order-confirmed"></a>Ordern är bekräftad

Meddelandetypen *order bekräftad* utlöses när ett orderbekräftelsedokument genereras för en försäljningsorder från Commerce headquarters.

### <a name="picking-completed"></a>Plockningen är slutförd

Meddelandetypen *plockning slutförd* utlöses när en plocklista för en order markeras som slutförd i Commerce headquarters.

> [!NOTE]
> Meddelandetypen slutförd plockning som utlöses när en artikel markeras som plockad i en kassaterminal.

### <a name="packing-completed"></a>Försändelsen har packats klart

Meddelandetypen *packning slutförd* utlöses när ett följesedeldokument genereras fören order markeras som slutförd i Commerce-kassaterminal.

Meddelandetypen förpackning klar stöder följande ytterligare e-postplatshållare för att underlätta "order klar för upphämtning" och sökning efter order från transaktionella e-postmeddelanden.

| Namn på platshållare    | Syfte |
| ------------------- | ------- |
| `pickupstorename`     | Namnet på butiken där ordern är tillgänglig för upphämtning. |
| `pickupstoreaddress`  | Adressen på butiken där ordern är tillgänglig för upphämtning. |
| `pickupstoreopenfrom` | Upphämtningsbutikens öppettider. |
| `pickupstoreopento` | Upphämtningsbutikens stängningstider. |
| `pickupchannelid`     | Butikskanal-ID för upphämtningsbutiken. |
| `packingslipid`      | ID för följesedeln för den order som kommer att hämtas. |
| `confirmationid`      | Orderbekräftelse-ID för den order som kommer att hämtas. (Detta ID kallas ibland för kanalreferens-ID.) |

För mer information om kundens incheckning och sökfunktioner, se [Ställa in geoidentifiering och omdirigering](geo-detection-redirection.md) och [Aktivera ordersökning för gästkassa](order-lookup-guest.md).

### <a name="order-ready-for-pickup"></a>Order klar för hämtning

Meddelandetypen *order klar för upphämtning* utlöses när en order markeras som packad och leveranssättet ställs in på **Upphämtning av kund** på en eller flera orderrader.

> [!NOTE]
> Ordern som är klar för upphämtning har avaktiverats i den packade notifieringstypen. Meddelandetypen anpassas efter leveranssätt.

### <a name="order-shipped"></a>Order levererad

Meddelandetypen *ordern levereras* utlöses när en order som har ett leveranssätt som inte finns i butiken faktureras.

> [!NOTE]
> Meddelandetypen ordern som levereras klar för upphämtning har avaktiverats i meddelandetypen kundorder. Meddelandetypen anpassas efter leveranssätt.

### <a name="order-invoiced"></a>Order fakturerad

Meddelandetypen *order som faktureras* utlöses när en order faktureras i kassa eller Commerce headquarters.

### <a name="issue-gift-card"></a>Utfärda presentkort

Meddelandetypen *Utfärda presentkort* utlöses när en försäljningsorder som innehåller en produkt av presentkortstyp faktureras.

> [!NOTE]
> E-postmeddelandet med presentkortet skickas till presentkortsmottagaren. Presentkortsmottagaren anges i Commerce headquarters på en enskild försäljningsorderrad på fliken **Förpackning** under **Raddetaljer**. Den kan anges antingen manuellt eller programmässigt.

Utbetalningsmeddelandetypen har stöd för följande ytterligare platshållare.

| Namn på platshållare      | Syfte |
| --------------------- | ------- |
| `giftcardnumber`        | Presentkortsnummer för produkter av typen presentkort. |
| `availablebalance` | Återstående saldo på presentkortet. |
| `giftcardmessage`       | Presentkortsmeddelande för produkter av typen presentkort. |
| `giftcardpin`         | PIN-kod för presentkort, för produkter av typen presentkort. (Denna platshållare är specifik för externa presentkort.) |
| `giftcardexpiration`    | Utgångsdatum för presentkort, för produkter av typen presentkort. (Denna platshållare är specifik för externa presentkort.) |
| `giftcardrecipientname` | Namnet på mottagare av presentkort, för produkter av typen presentkort. |
| `giftcardbuyername`     | Namnet på inköpare av presentkort, för produkter av typen presentkort. |

Mer information om presentkort finns i [digitala presentkort för näthandel](digital-gift-cards.md) och [stöd för externa för presentkort](dev-itpro/gift-card.md).

### <a name="order-cancellation"></a>Orderannullering

Meddelandetypen *orderannullering* utlöses när en order avbryts i Commerce headquarters.

### <a name="customer-created"></a>Kunden har skapats

Meddelandetypen *kund som skapas* utlöses när en ny kundentitet i Commerce headquarters. 

För att aktivera meddelanden som skapats av kunden i Commerce headquarters på **Butik och handel \> Administrationsinställning \> Parametrar \> Commerce-parametrar \> Allmänt**. I listrutan **E-postmeddelandeprofil** väljer du den e-postmeddelandeprofil som innehåller meddelandetypen som skapats av en kund. 

Som standard överförs händelser som skapats av kunder till administration med batchjobbet **Synkronisera kunder och kanalbegäranden**. Om du vill använda ett servicesamtal i realtid för att skicka dessa händelser ställer du in e-post-ID:t för den skapade mallen på **newCust**. Detta rekommenderas dock inte eftersom servicesamtal i realtid är "skicka och glömma"-samtal och därför inte har den reserv- eller omprövningslogik som finns i batchjobb.

> [!NOTE] 
> När du aktiverar meddelanden som skapats av kunder får kunder som skapas i alla kanaler inom den juridiska personen ett e-postmeddelande som skapas av kunden. För närvarande kan meddelanden skapade av kund inte begränsas till en enda kanal.  

När det startas via batchjobbet har meddelandetyper som skapats av kund stöd för följande platshållare.

| Namn på platshållare | Beskrivning                                                      |
| ---------------- | ------------------------------------------------------------ |
| customername     | För- och efternamn för den kund som skapade ett konto. |

När det startas via servicesamtal i realtid har meddelandetyper som skapats av kund stöd för följande platshållare.

| Namn på platshållare | Beskrivning                                                      |
| ---------------- | ------------------------------------------------------------ |
| Namn             | För- och efternamn för den kund som skapade ett konto. |
| E-postadress            | E-postadressen till kunden som skapade kontot.    |
| Telefon            | Telefonnummer till kunden som skapade kontot.      |
| URL              | URL-adressen som kunden angav när kontot skapades. |

### <a name="b2b-prospect-approved"></a>Potentiell B2B-kund godkänd

Meddelandetypen *godkänd potentiell B2B-kund* utlöses när en potentiell kunds introduktionsbegäran godkänns i Commerce headquarters. Mer information om hur du godkänner eller avvisar potentiella B2B-kunder finns i [Ställa in administratörsanvändare för en ny affärspartner](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

Meddelandetypen godkänd potentiell B2B-kund har stöd för följande ytterligare platshållare.

| Namn på platshållare | Syfte                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`       | Förnamnet på potentiell B2B-kund enligt angivet i programmet. |
| `lastname`         | Efternamnet på potentiell B2B-kund enligt angivet i programmet. |
| `company`          | Namnet på sökandes företag enligt angivet i programmet. |
| `email`            | E-postadressen för potentiell kund enligt angivet i programmet.   |
| `zipcode`          | Postnumret för potentiella kundens primära adress. |
| `comments`         | Kommentaren som den potentiella kunden har angett i appen. |
| `storename`        | Namnet på kanalen där potentiella kunden skapades. |
| `storeurl`         | Tomt som standard. Ett anpassat filnamnstillägg måste skapas för att platshållaren ska kunna användas. |

### <a name="b2b-prospect-rejected"></a>Potentiell B2B-kund avvisad

Meddelandetypen *avvisad potentiell B2B-kund* utlöses när en potentiell kunds introduktionsbegäran avvisad i Commerce headquarters. Mer information om hur du godkänner eller avvisar potentiella B2B-kunder finns i [Ställa in administratörsanvändare för en ny affärspartner](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

Meddelandetypen avvisad potentiell B2B-kund har stöd för följande ytterligare platshållare.

| Namn på platshållare | Syfte                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`        | Förnamnet på potentiell B2B-kund enligt angivet i programmet. |
| `lastname`         | Efternamnet på potentiell B2B-kund enligt angivet i programmet. |
| `company`          | Namnet på sökandes företag enligt angivet i programmet. |

## <a name="create-an-email-template"></a>Skapa en e-postmall

Innan du kan mappa en specifik transaktionshändelse till en e-postmall måste du skapa mallen.

Gör så här om du vill skapa en e-postmall.

1. I Commerce headquarters, gå till **Retail och Commerce \> Headquarters setup \> Organisationens e-postmallar** eller **Organisationsadministration \> Konfigurera \> Organisationens e-postmallar**.
1. Välj **Ny**.
1. Under **Allmänt** anger du följande fält:

    - **E-post-ID** – E-post-ID är den unika identifieraren för en mall. Det är det värde som visas när du väljer en mall som ska mappa till en händelse.
    - **E-postbeskrivning** – Du kan använda det här valfria fältet för att ange en beskrivning av mallen. Värdet som du anger visas bara i Commerce Headquarters.
    - **Avsändarens namn** – Det namn som du anger visas i fältet "från" i de flesta e-postklienter.
    - **Avsändarens e-postadress** – Ange den e-postadress som ska användas för e-postmeddelanden som skickas med hjälp av den här mallen.
    - **Standardspråkkod** – Detta fält innehåller den lokalanpassade versionen av det e-postmeddelande som skickas som standard om kanalen som anropar inte anger ett språk.

1. Under **Innehåll i e-postmeddelande** väljer du **Nytt**.
1. I fältet **Språk** anger du språket för e-postmallen. Du kan lägga till fler språk och lokalanpassade mallar senare.
1. I fältet **Ämne** anger du det e-postämne som ska visas i e-postmeddelandets ämnesfält.
1. Välj **Redigera** för att ladda upp e-postmallen.

## <a name="create-an-email-message-body-by-using-html"></a>Skapa en e-postmeddelandetext med hjälp av HTML

Texten i e-postmeddelandet består av HTML. Du kan använda alla layouter, format och märken som HTML och infogade övergripande formatmallar (CSS) tillåter. Du kan också använda avbildningar om du är värd för dem på en offentligt tillgänglig webbslutpunkt. Om du vill lägga till en bild anger du bildens URL i attributet **src** i HTML-taggen **&lt;img&gt;**.

> [!NOTE]
> E-postklienterna har begränsningar för layout och stil som kan kräva justeringar av HTML-koden och den CSS som du använder för meddelandetexten. Vi rekommenderar att du bekantar dig med de bästa metoderna för att skapa HTML-kod som stöds av de vanligaste e-postklienterna.

## <a name="add-placeholders-to-the-email-message-body"></a>Lägga till platshållare i e-postmeddelandets text

Din e-post kan innehålla platshållare som ersätts med kundspecifika och transaktionsspecifika värden när e-postmeddelandet genereras. Platshållare omges alltid av procent tecken (%) och infogas direkt i HTML-dokumentet.

Här är ett exempel:

```html
<p>
    Hello %customername%,<br />
    Order number %salesid%, can be picked up from the <b>%pickupstorename%</b> store.
</p>
```

### <a name="order-placeholders-sales-order-level"></a>Platshållare för order (försäljningsordernivå)

Följande platshållare hämtar och visar data som definieras på försäljningsordernivå (i motsats till försäljningsradnivå).

| Namn på platshållare     | Syfte                                                      |
| -------------------- | ------------------------------------------------------------ |
| `customername`         | Namnet på den kund som lade beställningen.               |
| `customeraddress`      | Kundens adress.                                 |
| `customeremailaddress` | E-postadressen som kunden angav i kassan.     |
| `salesid`              | Försäljningsorderns ID.                                   |
| `orderconfirmationid`  | Det korskanals-ID som genererades när en order skapades.   |
| `channelid`            | ID:t för detaljhandels- eller onlinekanal som ordern gjordes via. |
| `deliveryname`         | Namnet som anges för leveransadressen.         |
| `deliveryaddress`      | Leveransadressen för levererade order.                     |
| `deliverydate`         | Leveransdatum.                                           |
| `shipdate`             | Transportdatum.                                               |
| `modeofdelivery`       | Leveranssätt för ordern.                              |
| `ordernetamount`       | Det totala beloppet för ordern, minus total moms.         |
| `discount`            | Orderns totala rabatt.                            |
| `charges`              | Orderns totala kostnader.                             |
| `tax`                  | Orderns totala moms.                                 |
| `total`                | Orderns totala belopp.                              |
| `storename`            | Namnet på den butik som lade beställningen.            |
| `storeaddress`         | Adressen till den butik som lade beställningen.              |
| `storeopenfrom`        | Öppningstiden för den butik som lade beställningen.         |
| `storeopento`          | Stängningstiden för den butik som lade beställningen.         |
| `pickupstorename`      | Namnet på den butik där ordern kommer att hämtas upp.\*   |
| `pickupstoreaddress`   | Adressen till den butik där ordern kommer att hämtas upp.\* |
| `pickupopenstorefrom`  | Öppningstiden för den butik där ordern kommer att hämtas upp.\* |
| `pickupopenstoreto`    | Stängningstiden för den butik där ordern kommer att hämtas upp.\* |
| `pickupchannelid`     | Kanal-ID för butiken som har angetts för upphämtningssättet.\* |
| `packingslipid`        | ID:t för följesedeln som genererades när rader i en order packades.\* |

\*Dessa platshållare returnerar endast data när de används för **ordern klar för upphämtning** av meddelandetyp. 

### <a name="order-line-placeholders-sales-line-level"></a>Platshållare för orderrad (försäljningsradnivå)

Följande platshållare hämtar och visar data för enskilda produkter (rader) i försäljningsordern.

| Namn på platshållare               | Syfte |
|--------------------------------|-------------------|
| `productid`                      | <p>Produktens ID. Detta ID-konto för varianter.</p><p><strong>Obs!</strong> Denna platshållare har avaktiverats i syfte att använda `lineproductrecid`.</p> |
| `lineproductrecid`               | Produktens ID. Detta ID-konto för varianter. Den identifierar unikt en artikel på variantnivå. |
| `lineitemid`                     | Produkt-nivå-ID på produkten. (Det här ID:t tar inte hänsyn till varianter.) |
| `lineproductvariantid`           | Produktvariantens ID. |
| `lineproductname`                | Namnet på produkten. |
| `lineproductdescription`         | Produktbeskrivningen. |
| `linequantity`                   | Antalet enheter som beställts för raden, plus måttenheten (t.ex. **ea** eller **par**). |
| `lineunit`                       | Måttenheten för raden. |
| `linequantity_withoutunit`       | Antalet enheter som beställts för raden, utan måttenheten. |
| `linequantitypicked`             | När händelsen **PickOrder** används innebär detta det antal enheter som valts ut. I annat fall **0** (noll). |
| `linequantitypicked_withoutunit` | När händelsen **PickOrder** används innebär detta antalet enheter som valts ut, utan måttenhet. I annat fall **0** (noll). |
| `linequantitypacked`             | När händelserna **PackOrder** och **Order klar för upphämtning** används, innebär detta det antal enheter som har förpackats. I annat fall **0** (noll). |
| `linequantitypacked_withoutuom`  | När händelserna **PackOrder** och **Order klar för upphämtning** används, innebär detta det antal enheter som har förpackats, utan måttenhet. I annat fall **0** (noll). |
| `linequantityshipped`            | Alltid **0**, förutom när specifika händelser används, enligt beskrivningen på nästa rad. |
| `linequantityshipped_withoutuom` | När händelsen **ShipOrder** används innebär detta antalet enheter som valts ut, utan måttenhet. I annat fall **0** (noll). |
| `lineprice`                      | Priset för en enda enhet. |
| `linenetamount`                  | Priset för raden efter det att antalet enheter samt rabatten har tillämpats. |
| `linediscount`                   | Rabatten för en enskild enhet. |
| `lineshipdate`                   | Transportdatumet för raden. |
| `linedeliverydate`               | Leveransdatumet för raden. |
| `linedeliverymode`               | Leveranssättet för raden. |
| `linedeliveryaddress`            | Leveransadressen för raden. |
| `linepickupdate`                 | Upphämtningsdatum som kunden har angett för order där upphämtningssätt används. |
| `linepickuptimeslot`             | Tidsintervallet för upphämtning som kunden har angett för order där upphämtningssätt används. |
| `giftcardnumber`                 | Presentkortsnummer för produkter av typen presentkort. |
| `giftcardbalance`                | Presentkortssaldo för produkter av typen presentkort. |
| `giftcardmessage`                | Presentkortsmeddelande för produkter av typen presentkort. |
| `giftcardpin`                    | Presentkortets PIN-kod för produkter av typen presentkort. (Denna platshållare är specifik för externa presentkort.) |
| `giftcardexpiration`             | Utgångsdatum för presentkort, för produkter av typen presentkort. (Denna platshållare är specifik för externa presentkort.) |
| `giftcardrecipientname`          | Namnet på mottagare av presentkort, för produkter av typen presentkort. |
| `giftcardbuyername`              | Namnet på inköpare av presentkort, för produkter av typen presentkort. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Format för platshållare för orderrader i e-postmeddelandets text

När du skapar HTML för enskilda orderrader i e-postmeddelandets text omger du det upprepade blocket med HTML och platshållare för raderna med följande platshållare. Lägg märke till att platshållare finns i HTML-kommentarstaggar.

```html
<!--%tablebegin.salesline%-->

(Insert the repeating block of HTML and placeholders for individual lines here.)

<!--%tableend.salesline%-->
```

Här är ett exempel:

```HTML
<table>
    <tr>
        <td>Product name</td>
        <td>Quantity</td>
        <td>Price</td>
    </tr>
    <!--%tablebegin.salesline%-->
    <tr>
        <td>%lineproductname%</td>
        <td>%linequantity_withoutunit%</td>
        <td>%lineprice%</td>
    </tr>
    <!--%tableend.salesline%-->
</table>
```

## <a name="create-a-template-for-emailed-receipts"></a>Skapa en mall för e-postkvitton

Kvitton kan skickas via e-post till kunder som köper in i detaljhandelsbutik (POS). I allmänhet är stegen för att skapa mallen för e-post densamma som stegen för att skapa mallar för andra transaktionshändelser. Följande ändringar måste dock utföras:

- **%message%** platshållare används för att infoga texten på kvittot i e-postmeddelandet. Om du vill vara säker på att kvittoinnehållet återges korrekt omger du platshållaren **%message%** med HTML-taggarna **&lt;pre&gt;** och **&lt;/pre&gt;**.
- Platshållaren **%receiptid%** kan användas för att visa en QR-kod eller en streckkod som representerar inleverans-ID:t. (QR-koder och streckkoder genereras dynamiskt och serveras av en tredje parts tjänst.) Mer information om hur du visar en QR-kod eller streckkod i ett e-postkvitto finns i [Lägg till en QR-kod eller streckkod i transaktions- och mottagnings-e-postmeddelanden](add-qr-code-barcode-email.md).

## <a name="upload-the-email-html"></a>Överför HTML-koden för e-post

När du har skapat och testat HTML-koden för din meddelandetext måste den överföras till Commerce Headquarters. För närvarande kan HTML för e-post inte exporteras. Du måste därför underhålla huvudkopian av HTML-koden utanför Commerce Headquarters.

Följ dessa steg för att överföra en ny eller redigerad HTML-mallkod för e-post.

1. Gå till **Butik och handel \> Inställningar för Headquarters \> E-postmallar för organisation** i Commerce Headquarters.
1. Välj raden för det språk som du vill lägga till eller ersätta HTML-koden för. Du kan också välja **Ny** om du vill skapa en rad för ett nytt språk.
1. Välj **Redigera**.
1. I dialogrutan som visas väljer du **Bläddra**. Bläddra till det HTML-dokument som du vill överföra, markera det och välj sedan **Öppna**.
1. Välj **överför**.
1. När HTML-koden för e-post visas i förhandsgranskningsfönstret väljer du **OK**.
1. Se till att kryssrutan **Har brödtext** väljs för raden.

Om du redan har konfigurerat Commerce Headquarters för att skicka e-post, skickas det nya eller uppdaterade e-postmeddelandet till alla kunder som utför en transaktion som startar den händelse som har mappats till mallen.

För mer information om hur du konfigurerar e-post i Dynamics 365 Commerce, se [Konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md).

## <a name="additional-resources"></a>Ytterligare resurser 

[Ställa in en meddelandeprofil för e-post](email-notification-profiles.md)

[Konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md)

[Ställ in e-postinleveranser](/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[Skicka e-postkvitton från Modern POS ](email-receipts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
