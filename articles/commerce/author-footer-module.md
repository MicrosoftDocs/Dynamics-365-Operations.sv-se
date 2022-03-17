---
title: Modul för sidfot
description: Det här avsnittet innehåller moduler för sidfot och hur du redigerar dem i Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 03/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 81db5cf32f23b7ee1ca8325eeec2e6ceafda55e0
ms.sourcegitcommit: 90a553e271e7cd471fed2e4f006d753fdb67b47d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8374841"
---
# <a name="footer-module"></a>Modul för sidfot  

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om moduler för sidfot och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.

Modulen för sidfot är en särskild behållare som används som värd för modulerna som visas i sidfoten. Den kan till exempel innehålla länkar till olika sidor på webbplatsen, t.ex. sidorna **Kontakta oss** och **Butikspolicyer**.

Följande bild visar ett exempel på en sidfotsmodul på en webbplatssida.

![Exempel på en sidfotsmodul.](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a>Egenskaper för moduler för sidfot 

Precis som i de flesta behållare har en modul för sidfot stöd för egenskaper för rubriker och bredd. Den stöder också att du lägger till flera kategorimoduler för sidfötter. Varje kategorimodul för sidfot som läggs till återges som en kolumn i modulen sidfot.

## <a name="modules-available-in-a-footer-module"></a>Moduler tillgängliga i en modul för sidfot

**Sidfotsobjekt** – En modul för sidfotsobjekt kan innehålla antingen en rubrik eller en länk. Rubriken används vanligtvis som sidfotsavsnittsrubrik.  Varje länk i sidfoten kan konfigureras så att den bara har text (t.ex. "kontakta oss" och "sekretess") eller så att den har både text och bild (t.ex. sociala medielänkar). Om både rubrik och länk visas kommer rubrikegenskapen att ha företräde före länken. 

**Tillbaka till början** – modulen Tillbaka till början innehåller en länk för snabb navigering till sidans övre del. En destination måste anges. Standardmålet är \# vilket innebär att användaren kommer högst upp på sidan.

## <a name="create-a-footer-module"></a>Skapa en sidfotsmodul

1. Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.
1. I dialogrutan **Nytt fragment** väljer du modul för **Behållare**, anger ett namn på fragmentet och väljer sedan **OK**.
1. I facket **Standardbehållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **sidfotskategori** och sedan **OK**.
1. I facket **Sidfotskategori** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul** välj modulen **sidfotsartikel** och sedan **OK**.
1. Välj platsen **Sidfotskategori** och sedan i egenskapsrutan till höger konfigurerar du rubrik, länk och länktext och bilden efter behov.
1. Upprepa steg 5 till 7 om du vill lägga till fler sidfotsartiklar.
1. Om du vill lägga till länken "Tillbaka till början" väljer du ellipsknappen (**...**) i platsen **sidfotskategori** och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen **Tillbaka till början** och sedan **OK**.
1. Välj platsen **Tillbaka till början** och sedan i egenskapsrutan till höger konfigurerar du text och andra modulegenskaper efter behov.
1. Välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera det.

Om du vill garantera att ett sidhuvud visas på varje sida följer du stegen nedan för varje sidmall som skapas för webbplatsen.

1. På platsen **Sidfot** i modulen **standardsida** lägg till det sidfotsfragment som du skapade.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.

Genom att lägga till fragment i sidmallar kan du säkerställa att sidfoten återges på varje sida.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Behållarmodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
