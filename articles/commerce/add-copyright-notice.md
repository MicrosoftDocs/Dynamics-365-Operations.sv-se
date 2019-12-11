---
title: Lägg till copyrightmeddelande
description: I det här avsnittet beskrivs hur du lägger till ett copyrightmeddelande till din näthandelsplats.
author: psimolin
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 39135a2eca25336097ee9eddf06dc6709c102571
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696955"
---
# <a name="add-a-copyright-notice"></a>Lägg till copyrightmeddelande

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till ett copyrightmeddelande till din näthandelsplats.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan lägga till copyrightinformation till webbplatsen måste du ha följande objekt:

- En mall som innehåller ett avsnitt för delad sidfot.
- En sida som använder den mallen.

## <a name="add-a-copyright-notice"></a>Lägg till copyrightmeddelande

Om du vill lägga till copyrightinformation längst ned på varje sida som använder en viss mall följer du stegen nedan.

1. Gå till **fragment** och välj **nytt sidfragment**.
1. I dialog rutan väljer du modulen **sidfot** och namnger fragmentet. Du kan t.ex. ange **Sidfot-Copyright**.
1. Välj **OK**.
1. I navigeringsfönstret väljer du ellipsknappen (**...**) bredvid **sidfot** och väljer sedan **Lägg till modul**.
1. I dialogrutan, välj **Sidfotskategori** och väljer sedan **OK**.
1. I navigeringsfönstret väljer du ellipsknappen bredvid **sidfotskategori** och väljer sedan **Lägg till modul**.
1. I dialogrutan, välj **innehållsrikt blockobjekt** och väljer sedan **OK**.
1. I navigeringsfönstret, välj **innehållsrika blockobjekt**.
1. I det här egenskapsfönstret till höger, i fältet **stycke** lägger du till ditt copyright-meddelande. Ange till exempel **(C) Fabrikam 2019**.
1. Välj **Spara**, välj **Checka in** och sedan **Publicera**.
1. Gå till **mallar**, markera mallen och välj sedan **Checka ut**.
1. Under **Siddisposition**, utöka **Brödtext** och utöka sedan **Standardsidan**.
1. Markera knappen med punkter för platsen **Sidfotsplats** och välj sedan **Lägg till fragment**.
1. Markera det fragment som du skapade tidigare och välj sedan **Välj**.
1. Checka in mallen och publicera den.

Sidfoten som innehåller copyrightinformationen visas automatiskt längst ner på alla sidor som använder den valda mallen.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägg till en logotyp](add-logo.md)

[Välj ett tema för webbplatsen](select-site-theme.md)

[Lägg till en favicon](add-favicon.md)

[Lägg till ett välkomstmeddelande](add-welcome-message.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)

