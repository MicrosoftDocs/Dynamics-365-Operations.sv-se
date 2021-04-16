---
title: Konstruktionsversioner och kategorier av konstruktionsprodukter
description: Det här avsnittet innehåller information om konceptet konstruktionsversioner. Konstruktionsversioner säkerställer att olika tillstånd för en produkt och dess data hålls aktuella och tydliga, och att de kan visualiseras i systemet.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgLookupDynastring, EngChgProductVersionNumberRule, EngChgEcmProductRoute, EngChgEcmRequestProducts, EngChgEcmProductRoute, EngChgEcmProductPreview,EngChgEcmProductBOMItemIdLookup, EngChgEcmProductBOMConsistOf, EngChgEcmProductCreate, EngChgEcmProductLookup, EngChgProductVersionPrCompany, ngChgProductTypeLookup, EngChgProductType, EngChgProductItemPart, EngChgProductItem, EngChgEcmCategory, EngChgEcmBomDesignerEditBom, EngChgEcmBomDesigner, EngChgEcmBOMCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 1ebcb43b6c62ce895d3b1b36d7793f90208ca23e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836648"
---
# <a name="engineering-versions-and-engineering-product-categories"></a>Konstruktionsversioner och kategorier av konstruktionsprodukter

[!include [banner](../includes/banner.md)]

Tekniska produkter utvecklas under produktens livscykel av många skäl. Till exempel kan ändringar införas för att förbättra produktservicen, ändra en komponent eftersom leverantören inte längre erbjuder den, svara på nya insikter eller korrigera misstag i den ursprungliga designen. Det finns också många anledningar till att dessa ändringar ska lagras som en del av en pågående produkt, på ett sätt som tidigare data inte skrivs över. Här följer några av dessa orsaker:

- Du vill hålla reda på produkten när den tillverkas och levereras till kunderna i föregående livscykeltillstånd.
- Du behöver en ledtid innan du godkänner och tillämpar ändringarna.
- Du vill ha en tidsstämpel för varje ändring och du vill kunna leverera tidigare tillverkade produkter separat från varandra.

*Konstruktionsversioner* säkerställer att olika tillstånd för en produkt och dess data hålls aktuella och tydliga, och att de kan visualiseras i systemet. Det här konceptet hjälper dig att upprätthålla enhetlighet, låsa strukturlistan för produktion, eliminera skillnader och enkelt identifiera ändringar.

Vanligtvis används regeln *form-lämplighet-funktion* för att avgöra om en ändring kräver en ny produkt, en ny version eller en uppdatering av en befintlig version. Var och en av de tre termerna i den här regelns namn hänvisar till en specifik aspekt av en del, vilket gör att teknikerna kan matcha delar mot behov. Regeln för form-lämplighet-funktion ökar flexibiliteten i designändringar, eftersom det krävs minimal dokumentation och designkostnader för att ändra en del, förutsatt att produktens passning, form och funktion upprätthålls.

- **Lämplighet** syftar på möjligheten för delen eller funktionen att ansluta till, att delta i eller ansluta till en annan funktion eller en del av en sammansättning. Med lämplighet kan delen uppfylla de nödvändiga monteringstoleranserna så att den kan vara användbar.
- **Form** refererar till egenskaper för en del eller en sammansättning, t.ex. externa dimensioner, vikt, storlek och visuellt utseende. Form är den aspekt som mest påverkas av ingenjörens estetiska val. Den innehåller höljet, chassit och kontrollpanelen, som blir den utåtgående "sidan av produkten".
- **Funktion** är ett villkor som är uppfyllt när delen på ett effektivt och tillförlitligt sätt utför den. I en elektronikprodukt kan exempelvis funktionen vara beroende av de komponenter som används och programvaran eller den inbyggda programvaran. Ofta kan det också vara beroende av funktionerna i den valda inneslutningen. Två av de vanligaste orsakerna till att en inneslutning kan misslyckas är att funktionskriteriet är dåligt placerat eller dåligt märkta portar, och vilseledande eller saknad etikett. 

## <a name="engineering-versions"></a>Konstruktionsversioner

När du använder teknikprodukter har varje produkt minst en konstruktionsversion. Den första konstruktionsversionen skapas automatiskt när du skapar en konstruktionsprodukt. I varje konstruktionsversion lagras de tekniska relevanta data som är specifika för den versionen. Här följer några exempel på denna data:

- Versionsnummer och tidigare versionsnummer (om tillämpligt)
- De effektiva från och effektiva till datumen
- Produktversionens aktiva status, som anger om versionen kan frisläppas och användas i transaktioner (mer information finns i [produktberedskap](product-readiness.md) .)
- Det teknikföretag som skapade och äger produkten (mer information finns i [tekniska företag och dataägarskapsregler](engineering-org-data-ownership-rules.md)).
- Relaterade tekniska dokument, t.ex. en monteringsmanual, användarinstruktioner, bilder och länkar
- De tekniska attributen (mer information finns i [Tekniska attribut och sökning efter tekniska attribut](engineering-attributes-and-search.md)).
- Tekniska strukturlistor
- Tekniska rutter

Du kan uppdatera dessa data på en befintlig version, eller skapa en ny version, genom att använda en *teknisk ändringsorder*. (Mer information finns i [Hantera ändringar av tekniska produkter](engineering-change-management.md)). Om du skapar en ny version av en produkt kopierar systemet alla tekniska relevanta data till den nya versionen. Du kan sedan ändra informationen för den nya versionen. På det här sättet kan du spåra specifika data för varje version i följd. Om du vill jämföra skillnaderna mellan olika tekniker versioner, inspekterar du den tekniska ändringsordern, som inkluderar ändringstyper som anger alla ändringar.

Som har nämnts skapas den första konstruktionsversionen automatiskt när du skapar en konstruktionsprodukt. Versionsnumret för den här versionen följer versionsnummerregeln som definieras i produktens tekniska kategori. Om du vill övergå till en senare version måste du lägga till produkten i en teknisk ändringsorder som en rad, och du måste ställa in fältet **påverkan** till *ny version*. I den tekniska ändringsordern ingår information om ändringen från den aktuella versionen till nästa version.

Observera att en konstruktionsprodukt bara kan finnas i en teknisk ändringsorder åt gången. Denna begränsning säkerställer dataprecisionen och bidrar till att undvika överlappande eller motstridiga ändringar i produkten. Observera också att fältet **tekniker** i vyn **huvud** för teknisk ändringsorder visar den tekniker som är ansvarig för ändringsordern. Om teknikern tillhör ett team som har definierats i systemet visar fältet **ansvarig** ledaren för det teamet.

## <a name="track-versions-in-transactions"></a>Spåra versioner i transaktioner

När du använder konstruktionsändringshantering innehåller dina produktmalldata alltid en eller flera konstruktionsversioner. I din inställning av tekniska produkter kan du välja om teknik versionen även ingår i *logistik transaktioner*. (Mer information finns i avsnittet [Ställ in kategorier av konstruktionsprodukter](#product-category) senare i det här avsnittet). Om den logistiska effekten är relevant, skiljer den sig per produkt och per företag. Ibland används bara den senaste versionen av en produkt. När du introducerar en ny version kan därför den tidigare versionen inte längre användas. I andra fall krävs den föregående versionen i logistik transaktioner för att lösa följande utmaningar:

- Logistikavdelningen måste leverera två delar av en produkt till en kund. I så fall måste du bestämma om du vill att två olika versioner ska kunna levereras.
- Ett problem har upptäckts och det är relaterat till en viss ändring. I det här fallet kan det vara praktiskt att avgöra exakt vilken version som levererades i varje order.
- Företag vill först leverera gamla versioner, för att fasa in dem ur lager. I synnerhet för produkter med låg volym kan den här metoden hanteras ofta genom att fastställa de effektiva datumen för den nya versionen i relation till förutsägelser om när lagret i den gamla versionen kommer att ta slut. Ibland kanske du däremot inte kan göra jämförelsen, eller så kanske du anser att en osäkerhet på lagernivå förutsägelserna är för höga.

Beslutet om huruvida versioner som är synliga i lagret beror på faktorer som tidigare nämnts, plus företagspraxis och andra överväganden som är specifika för respektive företag. Du kan ange beteendet för den *konstruktionsproduktkategorin*. Den gäller sedan för alla produkter som skapas från den kategorin för alla företag som produkten har frisläppts till.

För produkter som har ställts in så att de har logistisk påverkan måste den tekniska versionen anges för varje transaktion. Även om systemet kommer att föreslå den *senaste aktiva versionen*, kan du välja bland alla aktiva versioner som är tillgängliga för företaget. För produkter som har ställts in så att de inte har logistisk påverkan måste den tekniska versionen inte anges för transaktioner. Systemet använder emellertid den senaste aktiva versionen. Om du till exempel lägger till en produkt i en produktions strukturlista, kommer den senaste versionen att användas och när du kör huvudplaneringen antas den senaste versionen.

## <a name="set-up-engineering-product-categories"></a><a name="product-category"></a>Ställa in kategorier av konstruktionsprodukter

En kategori av konstruktionsprodukter utgör grunden för att skapa en specifik konstruktionsprodukt. Varje kategori upprättar en uppsättning standardvärden och standardprinciper. När du skapar en teknisk produkt väljer du därför först den kategori du vill skapa den från.

Observera att en ny typ av kategorihierarki (*konstruktionsprodukthierarki*) ställs in automatiskt. Du kan skapa kategorierna manuellt genom att gå till **Konstruktionsändringshantering \> Inställning \> Information om konstruktionsproduktkategori**.

Varje information om konstruktionsproduktkategori upprättar standardbeteendet för de konstruktionsprodukter som skapas utifrån den kategorin. När du har skapat en konstruktionsprodukt kan du inte ändra den konstruktionsproduktkategorin. Om du däremot väljer felaktig kategori kan du ta bort produkten och sedan återskapa den igen.

När en konstruktionsproduktkategori skapas kan du inte ändra följande inställningar:

- Konstruktionsföretag
- Produkttyp
- Delprodukttyp
- Produktdimensionsgrupp
- Konfigurationsteknik
- Versionsnummerregel

Andra inställningar kanske ärver standardvärden som har ställts in för den tekniska produktkategorin. Enligt systemreglerna kan emellertid dessa värden ändras.

För att arbeta med konstruktionsproduktkategorier gå till **Konstruktionsändringshantering \> Inställning \> Information om konstruktionsproduktkategori**. Gör sedan något av följande.

- Om du vill skapa en ny kategori väljer du **ny** i åtgärdsfönstret och anger sedan fälten enligt beskrivningen i följande underavsnitt.
- Om du vill redigera en befintlig kategori markerar du den i listvyn, väljer **Redigera** i åtgärdsfönstret och anger sedan fälten enligt beskrivningen i följande underavsnitt.
- Om du vill ta bort en befintlig kategori markerar du den i list rutan och väljer sedan **ta bort** i åtgärdsfönstret.

### <a name="header"></a>Siduvud

Ange följande fält i rubriken för en teknisk produktkategori.

| Fält | beskrivning |
|---|---|
| Namn | Ange ett beskrivande konstruktionsproduktkategori. |
| Konstruktionsföretag | Välj det konstruktionsföretag där produkter i den här produktkategorin kan skapas och var de ska underhållas. |

### <a name="details-fasttab"></a>Snabbfliken information

Ange följande fält snabbfliken **Detaljer** en konstruktionsproduktkategori.

| Fält | beskrivning |
|---|---|
| Produkttyp | Välj om kategorin gäller för produkter eller tjänster. |
| Spåra versioner i transaktioner | Välj om versionen av produkten ska märkas med alla transaktioner (logistisk påverkan). Om du till exempel spårar versionen i transaktioner kommer varje försäljningsorder att visa vilken specifik version av produkten som såldes i den försäljningsordern. Om du inte spårar versionen i transaktioner visar inte försäljningsorder vilken specifik version som såldes. De visar i stället alltid den senaste versionen.<ul><li>Om det här alternativet är inställt på *Ja* skapas en produktmall för produkten och varje version av produkten är en variant som använder *version* produktdimensionen. Fältet **Delprodukttyp** ställs automatiskt in på *Produktmall* och du måste välja en produktdimensionsgrupp där dimensionen *version* är aktiv. Endast produktdimensionsgrupper där *version* är en aktiv dimension visas. Du kan skapa nya produktdimensionsgrupper genom att klicka på knappen **Redigera** (pennsymbol).</li><li>Om det här alternativet är inställt på *Nej* används inte produktdimensionen *version*. Du kan sedan välja om du vill skapa en produkt eller en produktmall som använder de andra dimensionerna.</li></ul><p>Det här alternativet används ofta för produkter som har en kostnadsskillnad mellan versioner, eller produkter där olika villkor gäller i relation till kunden. Därför är det viktigt att ange vilken version som användes i varje transaktion.</p> |
| Delprodukttyp | Välj om kategorin ska innehålla produkter eller produktmallar. För produktmallar kommer produktdimensioner att användas.
| Produktdimensionsgrupp | Inställningarna för **Spåra versioner i transaktioner** hjälper dig att välja produktens undertyp. Om du har anvisats att du vill spåra versionen i transaktioner kommer de produktdimensionsgrupper där dimensionen *version* används att visas. Annars är endast produktdimensionsgrupper där dimensionen *version* som inte används visas. |
| Produktens livscykeltillstånd när den skapas | Ställ in den standard livscykelstatus för produkt som en teknisk produkt ska ha när den först skapas. Mer information finns i [produktens livscykeltillstånd och transaktioner](product-lifecycle-state-transactions.md). |
| Versionsnummerregel | Välj den versionsnummerregel som gäller för kategorin:<ul><li>**Manuell** – du väljer versionsnummer för varje ny version.</li><li>**Automatiskt** – systemet ställer in versionsnumret baserat på ett format som du definierar. När du ställer in formatet ska du använda ett nummertecken (\#) för att representera en siffra och andra tecken som representerar ett konstant värde. Om du till exempel definierar formatet *V-\#\#*, blir den första versionen "V-01" den andra versionen blir "V-02" och så vidare.</li><li>**Lista** – systemet tar nästa nummer från en fördefinierad lista med anpassade värden som du definierar.</li></ul> |
| Framtvinga giltighetsdatum | Välj om de tekniska effektiv datum ska vara sammanhängande, eller om det kan finnas luckor och överlappningar. Den här inställningen påverkar hur fälten **Effektiv från** och **Effektiv till** för varje teknisk version där kategorin gäller.<ul><li>Om det här alternativet är inställt på *Ja* måste ett värde **Effektiv från** måste anges för varje version och varken överlappar eller luckor tillåts mellan versioner. Datumintervallet för varje teknisk version är direkt anslutet till föregående och nästa teknik, om de finns. I det här scenariot används alltid den senaste versionen och äldre versioner används inte längre.</li><li>Om det här alternativet är inställt på **Nej** finns det inga begränsningar för effektivt datumfält för konstruktionsversioner och både överlappningar och luckor är tillåtna. I det här scenariot kan flera versioner vara aktiva samtidigt och du kan arbeta med alla aktiva versioner.</li></ul><p>Det här alternativet påverkar även strukturlistor och flöden som är kopplade till en produktversion. Mer information finns i avsnittet [Ansluta strukturlistor och flöden till konstruktionsversioner](#boms-routes) senare i det här avsnittet.</p> |
| Använd nomenklatur för nummerregel | Ställ in det här alternativet på *Ja* om du vill aktivera regler för att definiera ett produktnummer med hjälp av nummerserier, tekniska attributnamn och värden samt textkonstanter som segment. För att skapa eller ändra regler, välj knappen **Redigera**. |
| Använd nomenklatur för namnregel | Ställ in det här alternativet på *Ja* om du vill aktivera regler för att definiera ett namn med hjälp av tekniska attributnamn, tekniska attributvärden samt textkonstanter som segment. För att skapa eller ändra regler, välj knappen **Redigera**. |
| Använd nomenklatur för beskrivningsregel | Ställ in det här alternativet på *Ja* om du vill aktivera regler för att definiera en beskrivning med hjälp av tekniska attributnamn, tekniska attributvärden samt textkonstanter som segment. För att skapa eller ändra regler, välj knappen **Redigera**. |

### <a name="attributes-fasttab"></a>Snabbfliken attribut

Använd rutnätet på snabbfliken **attribut** om du vill ställa in de tekniska attribut som gäller för produkter som tillhör den här kategorin. För information om hur du skapar tekniska attribut, se [Tekniska attribut och sökning efter tekniska attribut](engineering-attributes-and-search.md).

Använd knapparna på snabbfliken **attribut** du vill lägga till, ta bort och arrangera attribut i rutnätet.

Om du ändrar urvalet av attribut för en konstruktionskategori, och det redan finns produkter som baseras på den kategorin, måste du bestämma om du ska tillämpa ändringarna på dessa produkter. Om du vill att befintliga produkter ska återspegla ändringarna väljer du **Uppdatera befintliga produkter** på snabbfliken **attribut**.

Ange följande fält för varje rad som du lägger till i rutnätet:

| Fält | beskrivning |
|---|---|
| Namn | Välj det attribut som ska läggas till. |
| Värde | Välj standardvärdet för attributet. |
| Obligatoriskt | För attribut av typen *boolesk* om det här alternativet har värdet *Ja* måste användarna ställa in attributet på *Ja*. Om alternativet är inställt på *Nej* kan användarna ställa in attributet på antingen *Ja* eller *Nej*. För andra datatyper är inställningen av det här alternativet bara information. |
| Batchattribut | Välj om attributet ska spridas via batch-funktionen. |

### <a name="readiness-policy-fasttab"></a>Snabbfliken beredskapspolicy

Använd fältet **produktberedskapspolicy** för att välja den beredskapspolicy som gäller för produkter som tillhör den här kategorin. Mer information finns i [Produktberedskap](product-readiness.md).

### <a name="release-policy-fasttab"></a>Snabbfliken frisläppningspolicy

Använd fältet **produktfrisläppningspolicy** för att välja den frisläppningspolicy som gäller för produkter som tillhör den här kategorin. Mer information finns i [Frisläppa produktstruktur](release-product-structure.md).

## <a name="connect-boms-and-routes-to-engineering-versions"></a><a name="boms-routes"></a>Ansluta strukturlistor och flöden till konstruktionsversioner

Inställningen av alternativet **Påtvinga effektivitet** är viktigt för anslutningen av strukturlistor och flöden till respektive teknisk version. Du kan bara aktivera flera strukturlistor eller flöden per produkt om det finns en skillnad i följande inställningar:

- Produktdimension
- Kvantitet
- Site
- Effektivitetsdatum

Konstruktionsstrukturlistor och flöden skapas från den konstruktionsversion där de gäller. De kan identifieras med bockmarkeringen i kryssrutan **tekniskt kontrollerad**. När du arbetar med teknikstrukturlistor och flöden kan du vanligtvis utforma dem med hjälp av olika kvantiteter. Du kommer heller inte heller att utforma olika strukturlistor per plats. För teknikstrukturlistor och flöden hämtas dessutom effektivitetsdatum alltid från teknik versionen. En teknisk version, dess strukturlista och dess flöde kommer därför att ha samma effektivitetsdatum.

För produkter där du använder produktdimensionen *version* (tillsammans med logistisk påverkan på transaktionerna) läggs versionen även till i strukturlistorna och flödena. Det här beteendet gör det enklare att särskilja strukturlistor och flöden i sammanhängande versioner, oavsett inställningen **påtvinga effektivitet**.

För produkter där du inte använder produktdimensionen *version* (utan logistisk påverkan på transaktionerna) läggs versionen inte till i strukturlistorna eller flödena. Därför kommer det inte att finnas någon skillnad mellan strukturlistorna och flödena i efterföljande versioner. I det här fallet rekommenderar vi starkt att du ställer in alternativet **Påtvinga effektivitet** till *Ja*. På det här sättet bidrar till att undvika konstruktionsversioner från att överlappa, och du kan även aktivera strukturlistan och flödet för en nyare version utan att först inaktivera strukturlistan och flödet för den föregående versionen. Om du ställer in alternativet **Påtvinga effektivitet** till *Ja* i det här fallet måste du manuellt inaktivera strukturlistorna och flödena av äldre versioner innan du kan aktivera den senaste versionen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]