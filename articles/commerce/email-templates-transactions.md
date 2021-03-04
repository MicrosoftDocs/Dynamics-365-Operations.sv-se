---
title: Skapa e-postmallar för transaktionshändelser
description: I det här avsnittet beskrivs hur du skapar, överför och konfigurerar e-postmallar för transaktionshändelser i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ea484bfc1e9b293c53d7293c50630c4955000131
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415744"
---
# <a name="create-email-templates-for-transactional-events"></a>Skapa e-postmallar för transaktionshändelser

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar, överför och konfigurerar e-postmallar för transaktionshändelser i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Dynamics 365 Commerce tillhandahåller en färdig lösning för utskick av e-postmeddelanden som meddelar kunder om transaktionshändelser (t.ex. när en order har lagts, är klar för upphämtning eller har levererats). Det här avsnittet beskriver hur du skapar, överför och konfigurerar e-postmallar som används för att skicka transaktionsmeddelanden.

## <a name="create-an-email-template"></a>Skapa en e-postmall

Innan du kan mappa en specifik transaktionshändelse till en e-postmall måste du skapa mallen.

Gör så här om du vill skapa en e-postmall.

1. I Commerce-administration, gå till **Organisationens e-postmallar**, som är under **Retail och Commerce \> Administrationsinställning \> Organisationens e-postmallar** eller **Organisationsadministration \> Konfigurera \> Organisation e-postmallar**.
1. Välj **Ny**.
1. Under **Allmänt** anger du följande fält:

    - **ID för e-post** – ID för e-post är den unika identifieraren för en mall och är det värde som visas när du väljer en mall som ska mappas till en händelse.
    - **E-postbeskrivning** – Du kan använda det här valfria fältet för att ange en beskrivning av mallen. Värdet som du anger visas bara i Commerce Headquarters.
    - **Avsändarens namn** – Det namn som du anger visas i fältet "från" i de flesta e-postklienter.
    - **Avsändarens e-postadress** – Ange den e-postadress som ska användas för e-postmeddelanden som skickas med hjälp av den här mallen.
    - **Standardspråkkod** – Detta fält innehåller den lokaliserade versionen av det e-postmeddelande som skickas som standard om det inte finns något språk i kanalen som anropar den här mallen.

1. Under **Innehåll i e-postmeddelande** väljer du **Nytt**.
1. I fältet **Språk** anger du språket för e-postmallen. Du kan lägga till fler språk och lokaliserade mallar senare.
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

| Namn på platshållare    | Platshållarens värde                                                |
|---------------------|------------------------------------------------------------------|
| customername        | Namnet på den kund som lade beställningen.                   |
| salesid             | Försäljningsorderns ID.                                       |
| deliveryaddress     | Leveransadressen för levererade order.                         |
| customeraddress     | Kundens adress.                                     |
| deliverydate        | Leveransdatum.                                               |
| shipdate            | Transportdatum.                                                   |
| modeofdelivery      | Leveranssätt för ordern.                                  |
| avgifter             | Orderns totala kostnader.                                 |
| moms                 | Orderns totala moms.                                     |
| summa               | Orderns totala belopp.                                  |
| ordernetamount      | Det totala beloppet för ordern, minus total moms.             |
| rabatt            | Orderns totala rabatt.                                |
| storename           | Namnet på den butik som lade beställningen.                |
| storeaddress        | Adressen till den butik som lade beställningen.                  |
| storeopenfrom       | Öppningstiden för den butik som lade beställningen.             |
| storeopento         | Stängningstiden för den butik som lade beställningen.             |
| pickupstorename     | Namnet på den butik där ordern kommer att hämtas upp.         |
| pickupstoreaddress  | Adressen till den butik där ordern kommer att hämtas upp.      |
| pickupopenstorefrom | Öppningstiden för den butik där ordern kommer att hämtas upp. |
| pickupopenstoreto   | Stängningstiden för den butik där ordern kommer att hämtas upp. |

### <a name="order-line-placeholders-sales-line-level"></a>Platshållare för orderrad (försäljningsradnivå)

Följande platshållare hämtar och visar data för enskilda produkter (rader) i försäljningsordern.

| Namn på platshållare               | Platshållarens värde |
|--------------------------------|-------------------|
| productid                      | Produkt-ID för raden. |
| lineproductname                | Namnet på produkten. |
| lineproductdescription         | Produktbeskrivningen. |
| linequantity                   | Antalet enheter som beställts för raden, plus måttenheten (t.ex. **ea** eller **par**). |
| lineunit                       | Måttenheten för raden. |
| linequantity_withoutunit       | Antalet enheter som beställts för raden, utan måttenheten. |
| linequantitypicked             | När händelsen **PickOrder** används innebär detta det antal enheter som valts ut. I annat fall **0** (noll). |
| linequantitypicked_withoutunit | När händelsen **PickOrder** används innebär detta antalet enheter som valts ut, utan måttenhet. I annat fall **0** (noll). |
| linequantitypacked             | När händelserna **PackOrder** och **Order klar för upphämtning** används, innebär detta det antal enheter som har förpackats. I annat fall **0** (noll). |
| linequantitypacked_withoutuom  | När händelserna **PackOrder** och **Order klar för upphämtning** används, innebär detta det antal enheter som har förpackats, utan måttenhet. I annat fall **0** (noll). |
| linequantityshipped            | Alltid **0**, förutom när specifika händelser används, enligt beskrivningen på nästa rad. |
| linequantityshipped_withoutuom | När händelsen **ShipOrder** används innebär detta antalet enheter som valts ut, utan måttenhet. I annat fall **0** (noll). |
| lineprice                      | Priset för en enda enhet. |
| linenetamount                  | Priset för raden efter det att antalet enheter samt rabatten har tillämpats. |
| linediscount                   | Rabatten för en enskild enhet. |
| lineshipdate                   | Transportdatumet för raden. |
| linedeliverydate               | Leveransdatumet för raden. |
| linedeliverymode               | Leveranssättet för raden. |
| linedeliveryaddress            | Leveransadressen för raden. |
| giftcardnumber                 | Presentkortsnummer för produkter av typen presentkort. |
| giftcardbalance                | Presentkortssaldo för produkter av typen presentkort. |
| giftcardmessage                | Presentkortsmeddelande för produkter av typen presentkort. |
| giftcardpin                    | PIN-kod för presentkort, för produkter av typen presentkort. (Denna platshållare är specifik för externa presentkort.) |
| giftcardexpiration             | Utgångsdatum för presentkort, för produkter av typen presentkort. (Denna platshållare är specifik för externa presentkort.) |
| giftcardrecipientname          | Namnet på mottagare av presentkort, för produkter av typen presentkort. |
| giftcardbuyername              | Namnet på inköpare av presentkort, för produkter av typen presentkort. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Format för platshållare för orderrader i e-postmeddelandets text

När du skapar HTML för enskilda orderrader i e-postmeddelandets text omger du det upprepade blocket med HTML och platshållare för raderna med följande platshållare, som placeras i HTML-kommentartaggar.

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

- E-postmallens ID måste vara **emailRecpt**.
- Kvittotexten infogas i e-postmeddelandet med hjälp av platshållaren **%message%**. Om du vill vara säker på att kvittoinnehållet återges korrekt omger du platshållaren **%message%** med HTML-taggarna **&lt;pre&gt;** och **&lt;/pre&gt;**.
- Radbrytningar i HTML-kodens sidhuvud och sidfot konverteras till **&lt;br /&gt;**-taggar i HTML så att kvittotexten återges på rätt sätt. Om du vill ta bort det oönskade lodräta utrymmet i e-postkvittot tar du bort radbrytningar från alla platser i HTML-koden där det inte behövs något mellanrum.

För mer information om hur du konfigurerar e-postkvitton, se [Konfigurera e-postkvitton](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-email-receipts).

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

[Ställ in e-postinleveranser](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[Skicka e-postkvitton från Modern POS ](email-receipts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]