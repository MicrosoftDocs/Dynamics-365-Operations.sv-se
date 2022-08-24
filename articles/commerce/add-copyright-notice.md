---
title: Lägga till ett copyrightmeddelande
description: I denna artikel beskrivs hur du lägger till ett copyrightmeddelande på din Commerce-näthandelssajt.
author: josaw1
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 044fdd958a7233322553c8d9b03163c6ce5c4cb3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270466"
---
# <a name="add-a-copyright-notice"></a>Lägga till ett copyrightmeddelande

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du lägger till ett copyrightmeddelande på din Commerce-näthandelssajt.

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

[Välja ett tema för webbplatsen](select-site-theme.md)

[Arbeta med CSS åsidosättningsfiler](css-override-files.md)

[Lägga till en favoritikon](add-favicon.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
