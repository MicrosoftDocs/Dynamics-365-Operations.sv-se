---
title: "Vanliga frågor för produktrelaterade översättningar"
description: "I det här avsnittet beskrivs hur du hanterar översättningar för produkter, produktdimensionvärden och produktattribut."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d232473a1df0b821c6f39553ad826c61ff9ecff8
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="product-related-translations-faq"></a>Vanliga frågor för produktrelaterade översättningar

[!include[banner](../includes/banner.md)]


I det här avsnittet beskrivs hur du hanterar översättningar för produkter, produktdimensionvärden och produktattribut. 

<a name="what-product-related-data-can-be-translated"></a>Vilka produktrelaterade data kan översättas?
--------------------------------------------

Du kan skapa översättningar för följande produktrelaterade information:
-   Namn och beskrivningar av produkter.
-   Beskrivningar, användarvänliga namn och hjälptext om produktattributvärden.
-   Namn och beskrivningar av produktdimensionsvärden.

Du kan översätta produktrelaterad information till valfritt språk som är tillgängligt på sidan **Textöversättning**. För mer information, se **Hur skapar jag översättningar för produktrelaterad information**.

## <a name="where-can-i-view-the-translated-information"></a>Var kan jag visa den översatta informationen?
Du kan visa översättningar av produktrelaterad information i alla externa källdokument, till exempel en faktura, som använder ett språk där översättningar är tillgängliga.

## <a name="how-do-i-create-translations-for-productrelated-information"></a>Hur skapar jag översättningar för produktrelaterad information?
Följ dessa steg för att skapa översättningar för en produkt:
1.  Klicka på **Produktinformationshantering** &gt; **Allmänt** &gt; **Frisläppta produkter**.
2.  Välj en produkt och klicka på **Översättningar** i gruppen **Språk**.
3.  På sidan **Textöversättning**, i fältet **Språk**, väljer du ett språk. Expandera fältet **Språk** och klicka sedan på **OK**.
4.  I gruppen **Översatt text** anger du översättningar i fälten **Beskrivning** och **Produktnamn**.

Följ dessa steg för att skapa översättningar för produktattribut:
1.  Klicka på **Produktinformationshantering** &gt; **Allmänt** &gt; **Frisläppta produkter**.
2.  Under **Inställningar** klickar du på **Attribut** och sedan på **Attribut**.
3.  På sidan **Attribut** klickar du på **Översätt**.
4.  På sidan **Textöversättning**, i fältet **Språk**, väljer du ett språk. Expandera fältet **Språk** och klicka sedan på **OK**.
5.  I gruppen **Översatt text** anger du översättningar i fälten **Beskrivning**, **Eget namn** och **Hjälptext**.

Följ dessa steg för att skapa översättningar för produktdimensionsvärden:
1.  Klicka på **Produktinformationshantering** &gt; **Allmänt** &gt; **Frisläppta produkter**.
2.  Välj en produkt och klicka sedan på **Produktdimensioner**.
3.  Välj en av länkarna för produktdimensioner: **Configurations**, **Sizes**, **Colors** eller **Style**.
4.  Välj ett dimensionsvärde och klicka sedan på **Översätt**.
5.  På sidan **Textöversättning**, i fältet **Språk**, väljer du ett språk. Expandera fältet **Språk** och klicka sedan på **OK**.
6.  I gruppen **Översatt text** anger du översättningar i fälten **Namn** och **Beskrivning**.

## <a name="can-the-names-of-product-variants-be-translated"></a>Kan namnen på produktvarianter översättas?
Produktvarianter baseras på dimensionerna för en frisläppt produkt. Produktvariantnamn baseras på en kombination av dimensionsvärden. När dimensionsvärdena, som är kopplad till en produktvariant översätts, visas namnet på produktvarianten i den översatta versionen.  

**Exempel**  

Din produkt är en T-tröja som finns i olika storlekar och färger och namnen och varianterna baseras på följande information:
-   Produktnummer: \#3
-   Dimensioner: Storlek och färg
-   Storlekdimensionsvärden: Liten, medium, stor
-   Färgdimensionsvärden: Rött, Grönt, Svart

Namnet på en produktvariant som baseras på dimensionsvärdena Liten (Small) och Röd (Red) blir **\#3:Small:Red**.  

En kund vill köpa några små röda t-shirts och namnet på t-shirten måste visas på franska på fakturan. Du översätter dimensionsvärdena Liten (Small) och Red (Röd) till franska, och namnet på produktvarianten blir **\#3:Petit:Rouge**.
<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tips!</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Om du vill ange önskat språk för en kund, följ dessa steg:
<ol>  
<li>Klicka på <strong>Försäljning och marknadsföring</strong> &gt; <strong>Allmänt</strong> &gt; <strong>Kund</strong> &gt; <strong>Alla</strong> <strong>kunder</strong>.</li>
<li>Dubbelklicka på en kund för att öppna sidan <strong>Customers</strong>. På fliken <strong>Allmänt</strong>, i fältet <strong>Språk</strong> väljer du <strong>språk</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="what-happens-if-a-customer-has-a-preferred-language-for-which-no-translations-are-available"></a>Vad händer om en kund har ett prioriterat språk som inga översättningar är tillgängliga för?
Om översättningar inte är tillgängliga på kundens prioriterade språk, visas namnen och beskrivningarna på det globala språket för ditt företag.

## <a name="can-i-manage-translations-for-a-series-of-dimension-values-at-the-same-time"></a>Kan jag hantera översättningar för en serie dimensionsvärden samtidigt?
Dimensionsvärden är produktspecifika och du kan hantera översättningar av dimensionsvärden för varje produkt. Men om du skapar en dimensionsvärdegrupp och skapar översättningar för värdena i värdegruppen är det enklare att hantera översättningarna.   

**Exempel**  

Ditt företag tillverkar T-tröjor i olika stilar, och varje stil finns i storlekarna Small, Medium och Large. Storlekarna samlas i en dimensionsvärdegrupp. När ett nytt T-tröjutförande läggs till, kan du koppla det till dimensionsvärdegruppen som används för storlekar, så att alla storlekar är tillgängliga för produkten. Du kan också lägga till, eller ändra översättningar för storlekarna i dimensionsvärdet gruppera när som helst.  

Ett dimensionsvärde som är associerat med en produkt via en dimensionsvariantgrupp måste underhållas från produktvariantgruppen.   
Gör så här om du vill skapa dimensionsvärdegrupp:
1.  Klicka på **Produktinformationshantering** &gt; **Inställning** &gt; **Variantgrupper**.
2.  Välj **Storlek** **grupper**, **Färggrupper** eller **Utförandegrupper**.
3.  Klicka på **Ny** och ange sedan ett namn för gruppen i fälten**Storleks****grupp**, **Färggrupp**, eller **Formatgrupp**. Klicka på **Sizes**, **Colors** eller **Styles** för att skapa rader för grupper.
4.  I **Format****grupp**rader, **Färg****grupp****rader**, eller sidan **Utförandegrupprader** klickar du på **Ny** och skapar sedan storlekar, färger och utföranden för grupperna.

Om du vill hantera översättningar för värden i ett dimensionsvärdegrupp, följ dessa steg:
1.  Följ stegen i den föregående proceduren för att skapa en dimensionsvärdesgrupp som ska öppna sidan **Storleksgrupprader**, **Färggrupprader** eller **Utförandegruppsrader**.
2.  Klicka på **Textöversättning**. På sidan **Textöversättning** i gruppen **Översatt text** anger du översättningar i fälten **Namn** och **Beskrivning**.

## <a name="when-can-translations-of-productrelated-information-be-managed"></a>När kan översättningar av produktrelaterad information hanteras?
Översättningar av produktrelaterad information kan hanteras när som helst. När översättningar uppdateras för ett dimensionsvärde som är kopplat till en produkt, uppdateras produktinformationen, oavsett om produkten har transaktioner.






