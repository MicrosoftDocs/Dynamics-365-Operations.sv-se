---
title: Modul för delning på sociala nätverk
description: Denna artikel handlar om moduler för social delning och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 88bc5469e3072b625836cc942efbd2206f6dd6ba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284695"
---
# <a name="social-share-module"></a>Modul för delning på sociala nätverk

[!include [banner](includes/banner.md)]

Denna artikel handlar om moduler för social delning och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.

Med hjälp av modul för social delning kan användarna dela webbadresser för näthandelssajter på sociala medier som exempelvis Facebook, Twitter, Pinterest och LinkedIn. Webbadresser till webbplatssidan kan också delas via e-post. Moduler för social delning används ofta på produktinformationssidor (PDP) för att hjälpa användarna att dela produktinformation.

Varje modul för social delning är en behållare för artikelmoduler för social delning. Varje artikelmodul för social delning kan konfigureras så att den pekar mot en specifik plats för sociala medier. Integrering med Facebook, Twitter, Pinterest, LinkedIn och e-post stöds i kartongen. När en webbplats användare väljer en symbol för sociala medier, startas en HTML iFrame för respektive socialt medieplats. I iFrame kan användaren logga in och bokföra det sidinnehåll som de visade.

Varje plattform för sociala medier kan spåra cookies, så den här modulen kräver att webbplats användarna accepterar meddelandet om att ett meddelande ska skickas till en cookie. När cookie-tillstånd inte godkänns, döljs modulen på sidan. Mer information finns i [kompatibilitet med cookies](cookie-compliance.md).

Följande bild visar ett exempel på en modul för social delning som används på en produktinformationssida.

![Exempel på en modul för social delning.](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a>Egenskaper för modul för social delning

| Egenskapsnamn             | Värde                 | beskrivning |
|---------------------------|-----------------------|-------------|
| Rubrik                  | Text | Den här egenskapen anger en rubrik för modulen. |
| Orientering | **Horisontell** eller **Vertikal**  | Den här egenskapen definierar orienteringen för de sociala medieartiklarna. |

## <a name="social-share-item-module-properties"></a>Egenskaper för artikelmodul för social delning
| Egenskapsnamn             | Värde                 | beskrivning |
|---------------------------|-----------------------|-------------|
| Sociala medier              | **Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **post** | En nedrullningsbar meny med en lista över sociala medieplattformar. |
| Ikon |Bild    | Detta är den bild som kommer att visas för respektive socialt media. Du bör läsa den sociala medieplattformens SDK för den rekommenderade bilden som ska användas för varje plattform. |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a>Lägg till en modul för social delning för en modul för inköpsruta

Följ dessa steg för att lägga till en social delningsmodul till en köpboxmodul.

1. På webbplatsen Fabrikam väljer du **sidor** och väljer sedan sidan **DefaultPDP** för att öppna sidan produktinformation. 
1. I facket **inköpsruta (krävs)** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **social delning** och klicka sedan på **OK**.
1. I facket **social delning** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **SocialShare** och klicka sedan på **OK**.
1. I egenskapsfönstret i modulen **social delning**, under **orientering** välj **horisontell**. Lägg till en undertext efter behov.
1. I facket **SocialShare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **SocialShareItem** och klicka sedan på **OK**.
1. I egenskapsfönstret i modulen **social delningsartikel**, under **sociala medier** välj **Facebook**.
1. I egenskapsfönstret i modulen **social delningsartikel**, under **Ikon** välj **+ Lägg till en bild**.
1. I dialogrutan **Mediaväljare** välj modulen Facebook-logotyp och välj sedan **OK**. Om det inte finns någon Facebook logotypbild kan du välja **överför ny medieartikel** för att ladda upp ett.
1. Lägg till och konfigurera ytterligare moduler för **social delningsartikel** efter behov.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. På sidan visas modulen för modul för social delning.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Modul för inköpsruta](add-buy-box.md)

[Cookie-kompatibilitet](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
