---
title: Lägg till copyrightmeddelande
description: I det här avsnittet beskrivs hur du lägger till ett copyrightmeddelande till din näthandelssajt.
author: psimolin
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2ea04854636fdd0c2b3223bb19d5f06a19836151
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206377"
---
# <a name="add-a-copyright-notice"></a>Lägg till copyrightmeddelande

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till ett copyrightmeddelande till din näthandelssajt.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan lägga till copyrightinformation till webbplatsen måste du ha följande objekt:

- En mall som innehåller ett avsnitt för delad sidfot.
- En sida som använder den mallen.

## <a name="add-a-copyright-notice"></a>Lägg till copyrightmeddelande

Om du vill lägga till copyrightinformation längst ned på varje sida som använder en viss mall följer du stegen nedan.

1. Gå till **Fragment** och välj sedan **Nytt**.
1. I dialogrutan **Nytt fragment**, välj modulen **Sidfot** och namnge fragmentet. Du kan t.ex. ange **Sidfot-Copyright**.
1. Välj **OK**.
1. I navigeringsfönstret väljer du ellipsknappen (**...**) bredvid **sidfot** och väljer sedan **Lägg till modul**.
1. I dialogrutan, välj **Sidfotskategori** och väljer sedan **OK**.
1. I navigeringsfönstret väljer du ellipsknappen bredvid **sidfotskategori** och väljer sedan **Lägg till modul**.
1. I dialogrutan, välj **Textblock** och väljer sedan **OK**.
1. Välj **textblock** i navigeringsfönstret.
1. I det här egenskapsfönstret till höger, i fältet **stycke** lägger du till ditt copyright-meddelande. Ange till exempel **(C) Fabrikam 2019**.
1. Välj **Spara**, välj **Slutför redigering** och sedan **Publicera**.
1. Gå till **mallar**, markera mallen och välj sedan **Redigera**.
1. Under **Siddisposition**, utöka **Brödtext** och utöka sedan **Standardsidan**.
1. Markera knappen med punkter för platsen **Sidfotsplats** och välj sedan **Lägg till fragment**.
1. Markera det fragment som du skapade tidigare och välj sedan **Välj**.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.

Sidfoten som innehåller copyrightinformationen visas automatiskt längst ner på alla sidor som använder den valda mallen.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägg till en logotyp](add-logo.md)

[Välj ett tema för webbplatsen](select-site-theme.md)

[Arbeta med CSS åsidosättningsfiler](css-override-files.md)

[Lägg till en favoritikon](add-favicon.md)

[Lägg till ett välkomstmeddelande](add-welcome-message.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]