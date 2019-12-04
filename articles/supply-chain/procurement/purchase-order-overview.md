---
title: Översikt över inköpsorder
description: Den här artikeln innehåller allmän information om inköpsorder (PO) och länkar till fler artiklar som är relaterade till de olika stegen som en inköpsorder geomgår.
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 93083
ms.assetid: e9b7bc5b-1d7e-4ec2-97be-d655274b0613
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c527735ea65dad84c5d3d405eac2ead35d3c792d
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815375"
---
# <a name="purchase-order-overview"></a>Översikt över inköpsorder

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller allmän information om inköpsorder (PO) och länkar till fler artiklar som är relaterade till de olika stegen som en inköpsorder geomgår.

En inköpsorder (IO) är ett dokument som representerar ett avtal med en leverantör om att köpa varor eller tjänster. Dokumentet kan också hålla reda på produktinleveranser som gjorts mot ordern och senare redovisning av leverantörsfakturor som leverantören debiterar mot ordern.  

Sidan **Inköpsorder** innehåller en översikt över tillgängliga order och du kan ändra dessa order. När du öppnar en inköpsorder kan du välja vyn **Rubrik** som innehåller information som endast anges en gång för varje inköpsorder, till exempel information om leverantören. Alternativt kan du välja vyn **Rader** där du kan ändra orderrader. Vanligtvis ska du växla mellan dessa två vyer när du ändrar inköpsorder. Avgifter visas inte direkt på sidan **Inköpsorder**, men nås via menyerna i orderhuvudet och på orderraderna.  

Det finns många rapporter där du kan visa information om inköpsorder, produktinleveranser och leverantörsfakturor. Rapporter finns i modulerna **Anskaffning och källa** och **Leverantörsreskontra**.  

På arbetsytorna **Inköpsorderförberedelse** och **Inleverans av inköpsorder och uppföljning** kan du visa listor över inköpsorder i olika statusar som de har nått. De ger också en sammanfattning av de åtgärder som ska vidtas. Arbetsytan **Inköpsorderförberedelse** fokuserar på skapandet av inköpsorder och granskning, bearbetning av order via godkännande och bekräftelse från leverantören. Arbetsytan **Inleverans av inköpsorder och uppföljning** fokuserar på att bearbeta inleverans av varor eller tjänster mot inköpsorder. Den innehåller listor som ger insikt om inleveranser som är försenade, eller som snart ska levereras av leverantören. Arbetsytorna används inte för att utföra de relaterade inleveransaktiviteterna som utförs på lagerstället. Dessa aktiviteter utförs med hjälp av sidorna i modulerna **Lagerhantering** och **Lagerstyrning**. Bearbetning av leverantörsfakturor ska utföras med hjälp av arbetsytan **Leverantörsfakturaregistrering** och betalningar ska utföras med hjälp av arbetsytan **Leverantörsbetalningar**.  

Följande artiklar innehåller en översikt över de olika stegen som en inköpsorder genomgår:

-   [Skapa inköpsorder](purchase-order-creation.md)
-   [Godkänn och bekräfta inköpsorder](purchase-order-approval-confirmation.md)
-   [Produktinleverans mot inköpsorder](product-receipt-against-purchase-orders.md)
-   [Översikt över leverantörsfakturor](../../financials/accounts-payable/vendor-invoices-overview.md)

## <a name="types-of-purchase-orders"></a>Typer av inköpsorder
Det finns tre typer av inköpsorder. Du måste ange typ när du skapar en inköpsorder. Du kan ställa in en standardordertyp för nya order på sidan **Anskaffnings- och källparametrar**.

| Inköpsordertyp        | Beskrivning                                                                                                                                                                                                                                                                           |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Journal        | Använd den här typen när du vill skapa en utkastorder. Den här typen påverkar inte lagerkvantiteter och skapar inga lagertransaktioner. Inköpsorderjournalrader inkluderas inte i huvudplaneringen.                                                                                                       |
| Inköpsorder | Använd den här typen för att skapa en inköpsorder när ordern bekräftas av en leverantör och när ordern bearbetas via inleverans och fakturering innan betalningen till leverantören görs. Den här typen av inköpsorder är den vanligaste.                                                                          |
| Returnerad order | Använd den här typen när du returnerar varor till leverantören. Den här typen av order kräver att du anger returnumret (RMA) som leverantören ger dig. Du kan ange RMA-numret på fliken **Allmänt** för inköpsordern. Orderraderna måste ha negativa kvantiteter. |

## <a name="purchase-order-statuses"></a>Statusar på inköpsorder
Inköpsorder omfattar flera statusfält som visar orderns förlopp. Alla fält som är synliga i vyn **Rubrik** visar ordern och några av dem är även synliga i översikten över alla order. Fältet **Status** visar statusen för kvantiteter på ordern. Följande värden finns:

-   **Öppen order** – Ordern har skapats och kvantiteterna är angivna på ordern.
-   **Mottagen** – Vissa av kvantiteterna har inlevererats men inte fakturerats ännu.
-   **Fakturerad** – Hela kvantiteten på ordern har fakturerats. **Obs!** Om en order har fakturerats *delvis* är varken statusen **Mottagen** eller **Fakturerad** lämplig. Ordern kommer därför fortfarande att ha statusen **Öppen order**.
-   **Annullerad** – En order bekräftades men annullerades sedan. Denna status anger därför att det inte längre finns några öppna kvantiteter på ordern.

Fältet **Dokumentera status** hjälper dig att snabbt kontrollera orderförloppet för dokument som har bearbetats. Det visar statusen för det senaste dokumentet som har slutförts för ordern. Följande värden finns:

-   **Inga** – Inga dokument har bearbetats för ordern ännu.
-   **Inköpsförfrågan** – En inköpsförfrågan har skapats och ordern väntar på feedback från leverantören.
-   **Inköpsorder** – Bekräftelse har bearbetats på ordern.
-   **Produktinleverans** – Produktinleveransen har bearbetats på ordern.
-   **Faktura** – En faktura har redovisats med ordern.

Fältet **Godkännandestatus** används när en inköpsorder genomgår en granskningsprocess eller ett arbetsflöde. Följande värden finns:

-   **Utkast**, **Under granskning** och **Avvisad** – Dessa statusvärden används enbart när ett arbetsflöde för godkännande används för inköpsordern.
-   **Godkänd** – Den här statusen tilldelas order med slutfört arbetsflöde för godkännande. Order som har skapats utan ett arbetsflöde för godkännande får statusen **Godkänd** direkt.
-   **Under extern granskning** – Den här statusen används i scenarier där en inköpsorderförfrågan skickas till leverantören, så att leverantören kan bekräfta villkoren för inköpsordern. Denna status används också i processen som inleds med åtgärden **Bekräftelsebegäran**. För den här processen ombeds leverantören bekräfta villkoren för inköpsordern genom att ansluta systemet och registrera om ordern ska bekräftas eller avvisas.
-   **Bekräftad** – Den här statusen tilldelas när ordern har bekräftats. Denna status är vanligtvis den sista godkännandestatusen som tilldelas till en order.


<a name="additional-resources"></a>Ytterligare resurser
--------

[Skapa inköpsorder](purchase-order-creation.md)

[Godkänn och bekräfta inköpsorder](purchase-order-approval-confirmation.md)

[Produktinleverans mot inköpsorder](product-receipt-against-purchase-orders.md)

[Översikt över leverantörsfakturor](../../financials/accounts-payable/vendor-invoices-overview.md)



