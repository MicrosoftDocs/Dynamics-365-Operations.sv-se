---
title: "Översättningar produktrelaterade frågor och svar"
description: "I det här avsnittet beskrivs hur du hanterar översättningar för produkter, produktdimensionvärden och produktattribut."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysTranslationDetail, SysTranslationLanguage, SysTranslationList
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 201853
ms.assetid: c0286bba-f54b-42de-904c-81fd796bdd1d
ms.search.region: global
ms.search.industry: Product information
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: a9c991a5afaebd10b8812dfc1d67120ed4ebdfd2
ms.lasthandoff: 03/31/2017


---

# <a name="product-related-translations-faq"></a>Översättningar produktrelaterade frågor och svar

I det här avsnittet beskrivs hur du hanterar översättningar för produkter, produktdimensionvärden och produktattribut. 

<a name="what-product-related-data-can-be-translated"></a>Vilka produktrelaterade data kan översättas?
--------------------------------------------

Du kan skapa översättningar för följande produktrelaterade information:
-   Namn och beskrivningar av produkter.
-   Beskrivningar, användarvänliga namn och hjälptext om produktattributvärden.
-   Namn och beskrivningar av produktdimensionsvärden.

Du kan översätta produktrelaterad information till valfritt språk som är tillgängligt på sidan **Text translation**. För mer information, se **How do I create translations for product-related information**.

## <a name="where-can-i-view-the-translated-information"></a>Var kan jag visa den översatta informationen?
Du kan visa översättningar av produktrelaterad information i alla externa källdokument, till exempel en faktura, som använder ett språk där översättningar är tillgängliga.

## <a name="how-do-i-create-translations-for-productrelated-information"></a>Hur skapar jag översättningar för productrelated information
Följ dessa steg för att skapa översättningar för en produkt:
1.  Klicka på **produktinformationshantering**&gt;**gemensamma**&gt;**frisläppta produkter**.
2.  Välj en produkt och i åtgärdsfönstret, i den **språk** grupp genom att klicka på **översättningar**.
3.  På sidan **Text translation**, i fältet **Language**, väljer du ett språk. Lägg till fler språk genom att expandera den **språk** och klicka sedan på **OK**.
4.  I gruppen **Translated text** anger du översättningar i fälten **Description** och **Product name**.

Följ dessa steg för att skapa översättningar för produktattribut:
1.  Klicka på **produktinformationshantering**&gt;**gemensamma**&gt;**frisläppta produkter**.
2.  Under **Setup** klickar du på **Attributes** och sedan på **Attributes**.
3.  På sidan **Attributes** klickar du på **Translate**.
4.  På sidan **Text translation**, i fältet **Language**, väljer du ett språk. Lägg till fler språk genom att expandera den **språk** och klicka sedan på **OK**.
5.  I gruppen **Translated text** anger du översättningar i fälten **Description**, **Friendly name** och **Help text**.

Följ dessa steg för att skapa översättningar för produktdimensionsvärden:
1.  Klicka på **produktinformationshantering**&gt;**gemensamma**&gt;**frisläppta produkter**.
2.  Välj en produkt och klicka sedan på **Product dimensions**.
3.  Välj en av länkarna för produktdimensioner: **Configurations**, **Sizes**, **Colors** eller **Style**.
4.  Välj ett dimensionsvärde och klicka sedan på **Translate**.
5.  På sidan **Text translation**, i fältet **Language**, väljer du ett språk. Lägg till fler språk genom att expandera den **språk** och klicka sedan på **OK**.
6.  I den **översatt text** gruppera genom att ange översättningarna i den **namn** och **beskrivning** fält.

## <a name="can-the-names-of-product-variants-be-translated"></a>Kan namnen på produktvarianter översättas?
Produktvarianter baseras på dimensionerna för en frisläppt produkt. Produktvariantnamn baseras på en kombination av dimensionsvärden. När dimensionsvärdena, som är kopplad till en produktvariant översätts, visas namnet på produktvarianten i den översatta versionen.  

**Exempel**  

Din produkt är en T-tröja som finns i olika storlekar och färger och namnen och varianterna baseras på följande information:
-   Produktnummer: \#3
-   Dimensioner: Storlek och färg
-   Storlekdimensionsvärden: Liten, medium, stor
-   Färgdimensionsvärden: Rött, Grönt, Svart

Namnet på en produktvariant som baseras på dimensionen värden mindre och rött är **\#3:Small:Red**.  

En kund vill köpa några små röda t-shirts och namnet på t-shirten måste visas på franska på fakturan. Du översätta dimensionsvärdena, liten och rött till franska och produktvarianten heter **\#3: Petit: Rouge**.
<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tip</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Om du vill ange önskat språk för en kund, följ dessa steg:
<ol>  
<li>Klicka på <strong>försäljnings- och</strong>&gt;<strong>gemensamma</strong>&gt;<strong>kunder</strong>&gt;<strong>alla</strong> <strong>kunder</strong>.</li>
<li>Dubbelklicka på en kund för att öppna sidan <strong>Customers</strong>. På fliken <strong>General</strong>, i fältet <strong>Language</strong> väljer du <strong>språk</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="what-happens-if-a-customer-has-a-preferred-language-for-which-no-translations-are-available"></a>Vad händer om en kund har ett prioriterat språk som inga översättningar är tillgängliga för?
Om översättningar inte är tillgängliga på kundens prioriterade språk, visas namnen och beskrivningarna på det globala språket för ditt företag.

## <a name="can-i-manage-translations-for-a-series-of-dimension-values-at-the-same-time"></a>Kan jag hantera översättningar för en serie dimensionsvärden samtidigt?
Dimensionsvärden är produktspecifika och du kan hantera översättningar av dimensionsvärden för varje produkt. Men om du skapar en dimensionsvärdegrupp och skapar översättningar för värdena i värdegruppen är det enklare att hantera översättningarna.   

**Example**  

Ditt företag tillverkar T-tröjor i olika stilar, och varje stil finns i storlekarna Small, Medium och Large. Storlekarna samlas i en dimensionsvärdegrupp. När ett nytt T-tröjutförande läggs till, kan du koppla det till dimensionsvärdegruppen som används för storlekar, så att alla storlekar är tillgängliga för produkten. Du kan också lägga till, eller ändra översättningar för storlekarna i dimensionsvärdet gruppera när som helst.  

Ett dimensionsvärde som är associerat med en produkt via en dimensionsvariantgrupp måste underhållas från produktvariantgruppen.   
Gör så här om du vill skapa dimensionsvärdegrupp:
1.  Klicka på **produktinformationshantering**&gt;**inställningar**&gt;**Variantgrupper**.
2.  Välj **Size** **groups**, **Color groups** eller **Style groups**.
3.  Klicka på **nytt**, och ange sedan ett namn för gruppen i den **storlek****grupp**, **färggrupp**, eller **utförandegrupp** fält. Klicka på **Sizes**, **Colors** eller **Styles** för att skapa rader för grupper.
4.  I den **storlek****grupp** linjer **färg****grupp****rader**, eller **formatera rader** klickar du på **New**, och skapa sedan storlekar, färger och utföranden för grupper.

Om du vill hantera översättningar för värden i ett dimensionsvärdegrupp, följ dessa steg:
1.  Följ stegen i den föregående proceduren för att skapa en dimensionsvärdesgrupp som ska öppna sidan **Size group lines**, **Color group lines** eller **Style group lines**.
2.  Klicka på **Text translation**. I den **textöversättning** sidan i den **översatt text** gruppera genom att ange översättningarna i den **namn** och **beskrivning** fält.

## <a name="when-can-translations-of-productrelated-information-be-managed"></a>Om översättningar av productrelated information hanteras?
Översättningar av produktrelaterad information kan hanteras när som helst. När översättningar uppdateras för ett dimensionsvärde som är kopplat till en produkt, uppdateras produktinformationen, oavsett om produkten har transaktioner.



