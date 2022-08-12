---
title: Katalogväljarmodul
description: Den här artikeln innehåller information om moduler för katalogplockning och beskriver hur du lägger till dem på Microsoft Dynamics 365 Commerce-e-handelsplatser för business-to-business (B2B).
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-04-21
ms.openlocfilehash: 642319eea7e40415fd32898f6ec07bfc86f3b1b1
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136951"
---
# <a name="catalog-picker-module"></a>Katalogväljarmodul

[!include [banner](includes/banner.md)]

Den här artikeln innehåller information om moduler för katalogplockning och beskriver hur du lägger till dem på Microsoft Dynamics 365 Commerce-e-handelsplatser för business-to-business (B2B).

En modul för katalogplockning är en särskild behållare som används för att visa alla produktkataloger som B2B-webbplatsanvändare kan handla på. Det finns för närvarande bara stöd för flera kataloger för B2B-webbplatser.

Illustrationen nedan visar ett exempel på en katalogväljarmodul.

![Exempel på en katalogväljarmodul som listar tre produktkataloger.](./media/Catalog-picker-sample.png)

## <a name="add-a-catalog-picker-module-to-your-site"></a>Lägg till en katalogväljarmodul på din webbplats

Om du vill lägga till en katalogväljar på din webbplats i Commerce-webbplatsverktyget följer du stegen nedan.

### <a name="create-a-catalog-picker-page"></a>Skapa en sida för katalogväljare

Skapa först en sida för katalogväljare.

1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Skapa en ny sida**, under **Sidnamn**, ange **Katalogväljare**.
1. Under **Sid-URL** anger du en URL för sidan och väljer sedan **Nästa**.

    ![Skapa en dialogruta för ny sida.](./media/Create-catalog-picker-page.png)

1. Under **Välj en mall** väljer du **Allmänt innehåll** och sedan **Nästa**.
1. Under **Välj en layout** väljer du **Flexibel layout** och sedan **Nästa**.
1. Under **Granska och slutför**, granska sidkonfiguration. Om du måste redigera sidinformationen väljer du **Bakåt**. Om sidinformationen är korrekt väljer du **Skapa sida**.
1. Under **Katalogväljare** väljer du huvudplats **Main slot** > ellipsen (**...**) och sedan **Lägg till modul**.

    ![Lägga till en modul på huvudplatsen under Katalogväljare.](./media/Author-web-page-catalog-picker-1.png)

1. I dialogrutan **Välj moduler**, välj modulen **Behållare** och klicka sedan på **OK**.
1. Välj platsen **Behållare**, välj ellipsen (**...**) och välj sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler** väljer du modulen **Katalogväljare** och klicka sedan på **OK**.
1. I egenskapsfönstret för **Katalogväljare**, under **Rubrik** väljer du **Kataloger** och anger sedan en rubrik för katalogväljarsidan.
1. Under **Rubriknivå** väljer du en rubriknivå och sedan **OK**.
1. Under **RTF-text** anger du text som ska visas högst upp på sidan för katalogväljaren.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

### <a name="add-a-link-on-your-account-page"></a>Lägg till en länk på kontosidan

Lägg sedan till en referens på din katalogväljarsida på din sida kallad **Mitt konto**.

1. Gå till **Sidor**, sök och välj webbplatsens sida kallad **Mitt konto** och välj sedan **Redigera**.
1. På sidans plats **Huvud** väljer du platsen **Allmän kontopanel**. 
1. I egenskapsrutan för **Allmän kontopanel**, under **Länkar**, väljer du **Lägg till åtgärdslänk** och sedan **Åtgärdslänk**.
1. I dialogrutan **Åtgärdslänk**, under **Länktext**, anger du länktexten för länken till din katalogväljarsida.
1. Under **Länkmål** väljer du **Lägg till en länk**.
1. I dialogrutan **Lägg till en länk** väljer du **Anpassad sida** och sedan **Nästa**.
1. Under **Namn** väljer du sidan för katalogval, väljer **Tillämpa** och sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

I följande illustration visas ett exempel på en kontosida med en referens till katalogsidan.

![Sidan Mitt konto med länk till katalog.](./media/my-accounts.png)

### <a name="add-a-link-from-the-header"></a>Lägg till en länk från rubriken

Lägg slutligen till en länk från rubriken på webbplatsen i katalogerna.

1. Gå till **Fragment**, leta upp och välj sin webbplats rubrikfragment och välj sedan **Redigera**.
1. Markera platsen **rubrik**. 
1. I åtgärdsfönstret för **Rubrik**, under **Mina kontolänkar**, väljer du **Lägg till åtgärdslänk** och sedan **Åtgärdslänk**.
1. I dialogrutan **Åtgärdslänk**, under **Länktext**, anger du länktexten för länken till din katalogväljarsida.
1. Under **Länkmål** väljer du **Lägg till en länk**.
1. I dialogrutan **Lägg till en länk** väljer du **Anpassad sida** och sedan **Nästa**.
1. Under **Namn** väljer du sidan för katalogval, väljer **Tillämpa** och sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in rubrikavsnittet och välj sedan **publicera** för att publicera den.

I följande illustration visas ett exempel på en webbplatsrubrik för näthandel med en länk till B2B-katalogen.

![Näthandels-webbplatsrubrik med länk till katalog i listruta.](./media/catalog-in-header.png)


## <a name="additional-resources"></a>Ytterligare resurser 

[Skapa handelskataloger för B2B-webbplatser](catalogs-b2b-sites.md)

[Utvidgningar av handelskataloger för B2B-anpassningar](catalogs-b2b-sites-dev.md)

[Vanliga frågor om handelskataloger för B2B](catalogs-b2b-sites-FAQ.md)

[Sidor och moduler för kontohantering](account-management.md)

[Rubrikmodul](author-header-module.md)
