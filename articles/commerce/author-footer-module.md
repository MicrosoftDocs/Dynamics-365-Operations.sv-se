---
title: Modul för sidfot
description: Det här avsnittet innehåller moduler för sidfot och hur du redigerar dem i Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f8e0290b5af9d0c1fc9ad0279b0d7f81c9feb2fc
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001172"
---
# <a name="footer-module"></a>Modul för sidfot  


[!include [banner](includes/banner.md)]

Det här avsnittet handlar om moduler för sidfot och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Modulen för sidfot är en särskild behållare som används som värd för modulerna som visas i sidfoten. Den kan till exempel innehålla länkar till olika sidor på webbplatsen, t.ex. sidorna **Kontakta oss** och **Butikspolicyer**.

## <a name="footer-module-properties"></a>Egenskaper för moduler för sidfot 

Precis som i de flesta behållare har en modul för sidfot stöd för egenskaper för rubriker och bredd. Den stöder också att du lägger till flera kategorimoduler för sidfötter. Varje kategorimodul för sidfot som läggs till återges som en kolumn i modulen sidfot.

## <a name="modules-available-in-a-footer-module"></a>Moduler tillgängliga i en modul för sidfot

**Sidfotsobjekt** – en modul för sidfotsobjekt kan innehålla en rubrik, en bild och en länk. Rubriken kan antingen användas separat eller tillsammans med en bild och en länk. Varje länk i sidfoten kan konfigureras så att den bara har text (t.ex. "kontakta oss" och "sekretess") eller så att den har både text och bild (t.ex. sociala medielänkar).

**Tillbaka till början** – modulen Tillbaka till början innehåller en länk för snabb navigering till sidans övre del. En destination måste anges. Standarddestinationen är #, vilket innebär att användaren kommer högst upp på sidan.

## <a name="author-a-footer-module"></a>Skriva en sidfotsmodul

1. I navigeringsfönstret, välj **fragment** och välj sedan **Nytt sidfragment**.
1. I dialogrutan **Nytt sidfragment** väljer du modul för sidfot, anger ett namn på sidan och väljer sedan **OK**.
1. I dispositionsträdet till vänster väljer du ellipsknappen (**...**) för modulen för sidfot och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen sidfotskategori och sedan **OK**.
1. I dispositionsträdet väljer du ellipsknappen (...) för modulen för sidfotskategori och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen sidfotsartikel och sedan **OK**.
1. Välj modul för sidfotsartikel i dispositionsträdet. I egenskapsrutan till höger konfigurerar du rubrik, länk och länktext och bilden efter behov.
1. Upprepa steg 5 till 7 om du vill lägga till fler sidfotsartiklar.
1. Om du vill lägga till länken "Tillbaka till början" väljer du ellipsknappen (...) för modulen för sidfotskategori och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen Tillbaka till början och sedan **OK**.
1. Välj modul för Tillbaka till början i dispositionsträdet. Konfigurera sedan tillbaka till modulen Tillbaka till början i egenskapsfönstret till höger efter behov.
1. Spara sidfragmentet, checka in det och publicera det.

Gör följande för varje sidmall som har skapats för webbplatsen:

1. Lägg till platsen **Huvud** för standardsidan i modulen för sidfot, lägg till det sidfotsfragment som du skapade.
1. Spara mallen, checka in den och publicera den.

Genom att lägga till sidfragment i sidmallar kan du säkerställa att sidfoten återges på varje sida.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Behållaremodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)
