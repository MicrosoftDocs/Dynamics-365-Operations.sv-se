---
title: Översikt över leverantörsfakturor
description: Det här avsnittet innehåller allmän information om leverantörsfakturor. Leverantörsfakturor är förfrågningar för betalning av varor och tjänster som togs emot. Leverantörsfakturor kan representera en faktura för pågående tjänster eller baseras på inköpsorder för vissa varor och tjänster.
author: abruer
manager: AnnBe
ms.date: 03/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13971
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d7cec48b1e01d308cfc67260ac82a50a8d76844
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509508"
---
# <a name="vendor-invoices-overview"></a>Översikt över leverantörsfakturor

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Det här avsnittet innehåller allmän information om leverantörsfakturor. Leverantörsfakturor är förfrågningar för betalning av varor och tjänster som togs emot. Leverantörsfakturor kan representera en faktura för pågående tjänster eller baseras på inköpsorder för vissa varor och tjänster. 

## <a name="vendor-invoices"></a>Leverantörsfakturor

En leverantörsfaktura från en inköpsorder är en faktura som skapas när produkter eller tjänster tas emot enligt en inköpsorder som skickades till en leverantör. Leverantörsfakturor innehåller en rubrik och en eller flera rader för artiklar eller tjänster. En leverantörsfaktura slutför cykeln från inköpsordern till produktinleveransen till leverantörsfakturan. 

Även om en del leverantörsfakturor är kopplade till en inköpsorder, kan leverantörsfakturor också innehålla rader som inte motsvarar inköpsorderrader. Du kan också skapa leverantörsfakturor som inte är kopplade till en inköpsorder. Dessa leverantörsfakturor kan representera pågående tjänster, såsom en elräkning, och du måste inte referera till en inköpsorder när du lägger till dem. 

Det finns flera sätt att ange en leverantörsfaktura:

-   Leverantörsfakturaregistret låter dig ange fakturor som inte refererar till en inköpsorder snabbt så att du kan periodisera utgiften. Med godkännandejournalen för leverantörsfaktura väljer du dessa fakturor och bokför dem i leverantörssaldot för att återföra periodiseringen.
-   I leverantörsfakturajournalen kan du snabbt ange fakturor som inte refererar till en inköpsorder i ett enda steg.
-   Tillsammans med leverantörsfakturapoolen kan du snabbt ange fakturorna som ska periodisera utgiften i leverantörsfakturaregistret. Du kan öppna kopplade inköpsorder senare för att bokföra fakturan mot utgiftskonto.
-   Sidorna **Öppna leverantörsfakturor** och **Väntande leverantörsfakturor** gör det möjligt att skapa leverantörsfakturor från bekräftade inköpsorder.

Följande diskussion innehåller mer information om hur du använder sidorna **Öppna leverantörsfakturor** eller **Väntande leverantörsfakturor** för att skapa en leverantörsfaktura från en inköpsorder.

## <a name="understanding-invoice-line-quantities"></a>Förstå fakturaradkvantiteter
När du öppnar en leverantörsfaktura från en relaterad inköpsorder skapas fakturarader från inköpsordern. Som standard tas kvantiteterna från produktinleveranskvantiteten. Du kan dock använda en av följande standardinställningar:

-   **Kvantitet för Inleverera nu** – Använd det här alternativet för delförsändelser. Standardvärdet i fältet **Kvantitet** hämtas från kvantitetsfältet **Inleverera nu** på inköpsordern.
-   **Beställd kvantitet** – Använd det här alternativet för fullständiga försändelser. Standardvärdet i fältet **Kvantitet** hämtas från kvantitetsfältet **Beställd** på inköpsordern.
-   **Registrerad kvantitet** – Använd det här alternativet om artikeln måste registreras på sättet som anges på sidan **Artikelmodellgrupper**. Standardvärdet i fältet **Kvantitet** är den fysiska uppdaterade kvantiteten som har registrerats.
-   **Kvantitet för produktinleverans** – Använd det här alternativet om en produktinleverans redan har inlevererats för ordern. Standardvärdet i fältet **Kvantitet** hämtas från den totala kvantiteten i tillgängliga produktinleveranser.
-   **Registrerade kvantitet och tjänster** – Använd det här alternativet om kvantiteter har registrerats i införseljournaler för artiklar i lager eller artiklar som inte lagras. Det här alternativet inkluderar tjänster, oavsett om de registreras inte.

Om din juridiska person använder fakturamatchning kan du visa resultaten på kvantiteten som matchar i kolumnen **Matchning av kvantitet för produktinleverans**. Du kan också använda menykommandot **Matcha detaljer** på fliken **Granska** om du vill visa resultatet av kvantitetsmatchningen.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Lägga till en rad som inte finns på inköpsordern
Du kan lägga till en ny rad som inte fanns i inköpsordern till leverantörsfakturan. Du måste välja en artikelnummer eller anskaffningskategori. Du kan sedan lägga till kvantiteter, priser och belopp på raden. Raden tas bara med i matchningspolicyer för fakturasummor.

## <a name="submitting-a-vendor-invoice-for-review"></a>Skicka in en leverantörsfaktura för granskning
Organisationen kan använda arbetsflöden för att hantera granskningen för leverantörsfakturor. Arbetsflödesgranskningen kan krävas för fakturahuvudet, fakturaraden eller båda. Arbetsflödeskontrollerna används för sidhuvudet eller raden beroende på var fokus ligger innan du klickar på kontrollen. Istället för knappen **Bokför** ser du knappen **Skicka** som skickar leverantörsfakturan över granskningen.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Matcha leverantörsfakturor mot produktinleveranser
Du kan ange och spara information för leverantörsfakturor, och du kan matcha fakturarader mot produktinleveransrader. Det går även att matcha delkvantiteter på en rad. 

Du kan skapa en leverantörsfaktura som baseras på de radartiklar i produktinleveransen som har inlevererats hittills, även om alla artiklar för en viss inköpsorder ännu inte har inlevererats. Använd det här alternativet om till exempel leverantören skickar en faktura per månad som täcker alla leverantörens leveranser den månaden. Varje produktinleverans representerar en del av eller hela leveransen av artiklarna på inköpsordern. 

När du bokför fakturan uppdateras kvantiteten **Fakturarest** för varje artikel med summan av de inlevererade kvantiteterna från de valda produktinleveranserna. Om både kvantiteten **Fakturarest** och kvantiteten **Leveransrest** för alla artiklar på inköpsordern är noll, ändras statusen för inköpsordern till **Fakturerad**. Om kvantiteten **Fakturarest** inte är noll, ändras inte inköpsorderns status och ytterligare fakturor kan registreras för den.

Det här alternativet förutsätter det att minst en produktinleverans har bokförts för inköpsordern. Leverantörsfakturan baseras på dessa produktinleveranser och återspeglar kvantiteterna från dem. Den ekonomiska informationen för fakturan baseras på informationen som registreras när du bokför fakturan.

Mer information finns i [Registrera leverantörsfakturan och matcha mot mottagen kvantitet](../accounts-receivable/tasks/record-vendor-invoice-match-against-received-quantity.md)

## <a name="working-with-multiple-invoices"></a>Arbeta med flera fakturor

Du kan arbeta med flera fakturor samtidigt och bokföra dem samtidigt. Om du måste skapa flera fakturor, använd sidan **Väntande leverantörsfakturor**. Om du måste bokföra och skriv ut flera leverantörsfakturor, använd sidan med fakturagodkännandejournalen. Om du använder fakturagodkännandejournalen måste minst en produktinleverans vara bokförd för inköpsordern och att en faktura för inköpsordern har bokförts i ett fakturaregister. Den ekonomiska informationen för fakturan kommer från fakturan som bokfördes i registret.

## <a name="recovering-vendor-invoices-that-are-in-use"></a>Återställer leverantörsfakturor som används

När en leverantörsfaktura används kan den inte redigeras av en annan användare. Men statusen för en faktura kan ibland indikera att fakturan används, även om den inte redigeras aktivt. Till exempel kanske programmet slutar svara när fakturan har redigerats eller en användare kanske lämnat fakturan öppen i programmet av misstag.

Du kan använda sidan **Återställa leverantörsfakturor** om du vill återställa eller frisläppa leverantörsfakturor som har använts under längre än fyra timmar, så att de kan redigeras. Du kan öppna den här sidan från navigeringen **Periodisk uppgift** eller en panel på arbetsytan **Leverantörsfakturaregistrering**. När en faktura har återskapats blir den tillgänglig för redigering på sidan **leverantörsfakturan**.

Du kan endast komma åt sidan **återställa leverantörsfakturor** om säkerhetsprogrambehörighet och privilegium **återställa leverantörsfakturor som används** har tilldelats till dig. Dessutom måste parametern **Tillåt återställning av leverantörsfaktura** på sidan **Parametrar för leverantörsreskontra** måste vara aktiverad.

## <a name="additional-resources"></a>Ytterligare resurser

 - [Ställ in leverantörsfakturapolicyer](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md) 

 - [Mata in fakturadata i leverantörsreskontra genom att använda en leverantörsfaktura](tasks/key-invoice-data-ap-system-vendor-invoice.md)

 - [Mata in fakturadata i leverantörsreskontra genom att använda en godkänd journal](tasks/key-invoice-data-into-ap-system-approval-journal.md)

 - [Mata in fakturadata i LR-systemet genom att använda fakturapool](tasks/key-invoice-data-into-ap-system-invoice-pool.md)

 - [Registrera en leverantörsfaktura i fakturajournalen](tasks/record-vendor-invoice-invoice-journal.md)

