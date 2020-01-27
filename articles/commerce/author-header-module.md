---
title: Modul för sidhuvud
description: Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: cc98419077f6f563ea2265d4e68ba809971cfbd6
ms.sourcegitcommit: ff93b8f6a11993f2cd00be2da7aa77ef0d950ab8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885488"
---
# <a name="header-module"></a>Modul för sidhuvud

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En sidhuvudmodul är en särskild behållare som används för att vara värd för alla moduler som ska visas i sidans huvud. Det kan till exempel vara en webbplats logotyp, länkar till navigeringsnoden, länkar till andra sidor på webbplatsen och sökfältet.

En sidhuvudmodul optimeras automatiskt för enheten som platsen visas på (dvs. en stationär enhet eller en mobil enhet). Om du till exempel använder en mobil enhet döljs navigeringsfältet i **meny**-knapp (som ibland kallas en *hamburgarmeny*).

## <a name="properties-of-a-header"></a>Egenskaper för sidhuvud

Liksom generiska behållare stöder en sidhuvudmodul egenskaperna **rubrik** och **bredd**.

En sidhuvudmodul har flera platser. Det finns till exempel kortplatser för informationsmeddelanden, navigeringsmeny, logotyp, sökfält, ikon för vagn, ikon för önskelista och kontoinformation. Varje plats stöder en viss uppsättning moduler.

## <a name="modules-that-are-available-in-a-header-module"></a>Moduler som är tillgängliga i en sidhuvudmodul

Följande moduler kan användas i en sidhuvudmodul:

- **Navigeringsmeny** – navigeringsmenyn representerar en hierarki för kanaler och andra statiska navigeringslänkar. Du kan konfigurera kanalnavigeringshierarkin i Dynamics 365 Retail. Konfigurerade artiklar visas sedan som sidhuvudnavigering. Dessutom kan statiska navigeringslänkar konfigureras och relativa länkar till andra sidor på näthandelsplatsen kan tillhandahållas. Själva sidhuvudet kan justeras åt vänster, höger eller centrerat.
- **Vagnikon** – vagnikonen är en särskild ikon som representerar vagnen. Det visas i sidhuvudet och anger antalet artiklar i vagnen. En länk till vagnsidan ska medfölja vagnikonen, så att kunder kan dirigeras om till vagnsidan när de interagerar med ikonen.
- **Ikonen önskelista** – Ikonen önskelista visas i sidhuvudet och anger antalet artiklar som har lagts till i kundens önskelista. En länk till sidan för önskelista ska medfölja den här ikonen, så att kunder kan dirigeras om till sidan för önskelista när de interagerar med ikonen.
- **Inloggningsmodul** – inloggningsmodulen visas i sidhuvudet. Kunder kan antingen logga in på sitt konto eller registrera sig för ett konto. Om kunden redan är inloggad kan modulen konfigureras så att den visar länkar till kontosidan, sidan för orderhistorik eller en annan sida.
- **Logotypmodul** – den här modulen visar logotypen som representerar återförsäljaren och varumärket. Det är en bild som har en länk. Länken konfigureras vanligtvis så att den har en omdirigering till startsidan, vilket innebär att kunderna snabbt kan gå tillbaka till startsidan från vilken sida som helst på webbplatsen.
- **Varning** – en notifiering visas i sidhuvudet och används för att visa ett infogat meddelande som gäller alla sidor på webbplatsen. En notifiering kan till exempel visa ett meddelande som "årlig rea slutar om 2 dagar."
- **Sökfält** – Sökfältet låter användarna ange söktermer så att de kan söka efter produkter. Modulen måste konfigureras med URL:en för sökresultatsidan. Frågesträngparametern (standardvärde) kan konfigureras (standardvärdet är **"q"**). Sökfältet har en plats frö automatiska förslag där den automatiska förslagsmodulen ska läggas till.
- **Föreslå automatiskt** – modulen föreslå automatiskt visar automatiskt föreslagna resultat. Resultaten kan vara nyckelord, produkter eller kategorier där söktermen finns.

## <a name="create-a-header-module"></a>Skapa en sidhuvudmodul

Gör så här om du vill skapa en sidhuvudmodul.

1. Skapa ett sidfragment som innehåller en sidhuvudmodul.
1. Lägg till moduler till platserna i sidhuvudmodulen.
1. Uppdatera inställningarna för varje modul.
1. Spara sidfragmentet. 
1. Checka in sidan och publicera den.

Om du vill garantera att ett sidhuvud visas på varje sida följer du stegen nedan för varje sidmall som skapas för webbplatsen.

1. På standardsidan lägger du till sidfragment som innehåller sidhuvudmodulen till sidhuvudplatsen.
1. Spara mallen. 
1. Checka in mallen och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Behållaremodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)
