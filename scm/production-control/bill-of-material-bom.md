---
title: Strukturlistor och formler
description: "Denna artikel innehåller information om strukturlistor och formler, som är en central del av definitionen av produkterna och produktvarianterna. Strukturlistor och formler anger nödvändiga material eller komponenter för en viss produkt. Formler kan också ange samprodukter och biprodukter som tas emot i en bestämd produktionskontext."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, EcoResProductProcessManufacturingWorkspace
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19331
ms.assetid: c19b437a-2de2-4728-9477-2bcb0c2b1f5e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5a23acfa95bb93dbc5990bf3839bbc629f15cc2f
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="bills-of-materials-and-formulas"></a>Strukturlistor och formler

[!include[banner](../includes/banner.md)]


Denna artikel innehåller information om strukturlistor och formler, som är en central del av definitionen av produkterna och produktvarianterna. Strukturlistor och formler anger nödvändiga material eller komponenter för en viss produkt. Formler kan också ange samprodukter och biprodukter som tas emot i en bestämd produktionskontext. 

<a name="bills-of-materials"></a>Strukturlistor
------------------

En strukturlista definierar de komponenter som behövs för att tillverka en produkt. Komponenterna kan vara råmaterial, halvfabrikat och ingredienser. I vissa fall kan också tjänster ingå i en strukturlista. Strukturlistorna beskriver dock vanligen de *materialresurser* som krävs.  

När strukturlistan kombineras med ett produktionsflöde som beskriver operationer och resurser som krävs för att bygga en produkt, utgör strukturlistan grunden för beräkning av uppskattad kostnad för produkten.  

En strukturlista är en enskild enhet som beskrivs i följande information:

-   Strukturliste-id
-   Strukturlistenamn
-   Strukturlisteraderna som beskriver komponenterna och ingredienserna
-   Strukturlisteversionerna som definierar produkten och perioden som strukturlistan kan användas för

En enskild strukturlista beskriver en nivå som kan identifieras med ett unikt id. Komponenter kan ha egna strukturlistor som strukturlisteversioner hänvisar till. Du kan visa och redigera den färdiga hierarkin av strukturlistor för en specifik produkt i strukturlistedesignern.

### <a name="formulas-co-products-and-by-products"></a>Formler, samprodukter och biprodukter

En formel är en undertyp av strukturlista som normalt används för processtillverkning. Förutom komponenter och ingredienser beskriver en formel samprodukter och biprodukter. Definitionen av samprodukter och biprodukter för formeln kräver formelversionen i den aktuella versionen. En formel definieras vanligtvis för en specifik slutprodukt (en formel eller planeringsartikel) som definieras i formelversionen.

### <a name="boms-in-the-product-lifecycle"></a>Strukturlistor i produktens livscykel

Under produktens livscykel kan många typer av strukturlistor skapas av olika orsaker:

-   **Utkaststrukturlista** – strukturlistan innehåller en uppskattning av material som behövs i en tidig konstruktionsfas och gör att du kan göra ett överslag av kostnader och attribut för produkter. Denna strukturlista används normalt inte i resursplanering i företag (ERP).
-   **Teknikstrukturlista** – den här strukturlistan används normalt när du utformar produkter som baseras på befintliga produktportföljer. Teknikstrukturlistor är upplagda för att förenkla designprocessen och slå samman sammansatta produkter i teknikmoduler. För enkla produkter kan det vara möjligt till att ta fram teknikstrukturlistor som används i den aktuella produktionsprocessen. För andra produkter måste emellertid teknikstrukturlistan konverteras till en produktionsstrukturlista. Teknikstrukturlistor visas vanligtvis som fiktiva listor i strukturlistehierarkin. Även om teknikstrukturlistorna kan användas för planeringen och till tillverkningsoperationer kan detta tillvägagångssätt leda till ineffektivitet, särskilt i repetitiva operationer där många order skapas.
-   **Planeringsstrukturlista** – den här strukturlistan används för planeringen av materialbehovet. Behovet av komponenter och ingredienser beräknas baserat på behovet av de färdiga produkterna. På samma sätt som kostnadsredovisningsstrukturlistor, kan planeringsstrukturlistor representera en specifik blandning av material som används under en period.
-   **Produktionsstrukturlista** – detta är den egentliga strukturlistan som används för en viss produktion. En produktionsstrukturlista måste ta hänsyn till de verkliga resurserna som används för att producera produkten. När en produktionsorder, batchorder eller kanban skapas, komprimeras de olika nivåerna i strukturlistorna som representeras av fiktiva listor till en nivå och fördelas över operationerna för ordern.
-   **Kostnadsredovisningsstrukturlista** – den här strukturlistan används för att kunna beräkna den uppskattade kostnaden för en produkt. Du kan t.ex. använda en kostnadsredovisningsstrukturlista när standardkostnad används eller den beräknade planerade kostnaden för en viss produkt beräknas. Kostnadsredovisningstrukturlistor kan referera till en viss blandning av material och resurser som förväntas användas. Därför kan du använda kostnadsredovisningsstrukturlistan om du vill skapa en representativ uppskattad kostnad för en period och för att undvika avvikelser över tid.

Vilka typer av strukturlistor som de facto används i en implementering beror på implementeringen, samt även på affärsscenarier och behov. I enkla implementeringar kan en planeringsstrukturlista, produktionsstrukturlista och en kostnadsredovisningsstrukturlista slås samman till en strukturlista. I tillverkningsmiljöer där det ofta förekommer teknikändringar och flera alternativa flöden krävs det troligen fler strukturlistetyper.

### <a name="approval-of-boms-and-formulas"></a>Godkännande av strukturlistor och formler

Varje strukturlista och formel går att godkänna och upphäva separat. Vanligtvis sker godkännande av en strukturlista eller formel när den första relevanta strukturlisteversionen är godkänd. I vissa affärsscenarier kan dessa godkännanden emellertid bestå av olika steg i processen och innefatta olika processägare.  

Observera att om en strukturlista inte är godkänd är alla relaterade strukturlisteversioner heller inte godkända.

## <a name="bom-and-formula-versions"></a>Strukturlisteversioner och formelversioner
Om du vill koppla en specifik strukturlista eller formel till en produktvariant som kan produceras, måste du skapa en strukturlisteversion eller en formelversion. Giltigheten för strukturlisteversioner och formelversioner kan begränsas per period, kvantitet, plats, specifika produktdimensioner och andra kriterier. Formelversioner har fler viktiga attribut, t.ex. avkastning, sam - och biproduktdefinitioner och kostnadsfördelningsinstruktioner för formeln.

### <a name="approval-of-bom-and-formula-versions"></a>Godkännande av strukturlisteversioner och receptversioner

Innan en strukturlisteversion kan användas i planeringen eller tillverkningsprocessen, måste den godkänns. När en strukturlisteversion godkänns, kan tillhörande strukturlista också godkännas, beroende på användarens val och autentiseringsrättigheter. Observera att en strukturlisteversion bara kan godkännas om om den relaterade strukturlistan har godkänts.

### <a name="activation-of-the-default-bom-or-formula-version"></a>Aktivering av standardstrukturlisteversionen eller formelversionen

Om du vill ställa in en specifik strukturlista eller formel som standardversion som ska användas i huvudplaneringen eller för att skapa tillverkningsorder måste du aktivera versionen. När en version har aktiverats, verifieras versionens unikhet för angivna villkor (till exempel period, plats eller antal). Du får ett felmeddelande om versionen som du försöker aktivera står i konflikt med en version som redan är aktiv. Du måste sedan antingen inaktivera den motstridiga versionen eller ändra versionsbegränsningarna (vanligtvis perioden) för att förhindra en oklar aktivering.

### <a name="product-change-with-case-management"></a>Produktändring med ärendehantering

Produktändringsärendet för godkännande och aktivering av nya eller ändrade strukturlistor och strukturlisteversioner är ett enkelt sätt att visa en översikt över begränsningarna för strukturlisteversioner. Du kan även godkänna och aktivera alla strukturlistor och formler som är relaterade till en specifik ändring på ett aktiveringsdatum.

### <a name="alternative-bom-versions"></a>Alternativa strukturlisteversioner

Ibland ska den aktiva strukturlisteversionen eller formelversionen inte används i prognoser, försäljningar eller överordnade produkter. I sådana fall kan du välja en specifik godkänd strukturlista som en del av kravet (prognosraden, försäljningsrad, eller strukturlisterad), om en godkänd strukturlisteversion eller formelversion finns för den alternativa strukturlistan eller formeln.  

När planerade order, tillverkningsorder eller kanban skapas, kan planeraren eller arbetsledaren använda alla godkända strukturlisteversioner som är giltiga för det begärda planerade produktionsdatumet för att planera för eller producera en viss produkt. Strukturlisteversionen, som används måste inte aktiveras som standardstrukturlisteversion.

## <a name="bom-and-formula-lines"></a>Strukturlisterader och formelrader
En strukturlisterad skapas för varje materialpost, tjänst och ingrediens. Raden definierar den planerade förbrukningen av den angivna produktvarianten och anger även de olika attributen som är relaterade till den planerade förbrukningen.  

Strukturlisterader kan ha följande radtyper: **Artikel**, **Fiktiv**, **Fixerad vara**, **Leverantör**.

### <a name="item"></a>Artikel

Välj radtypen **Artikel** för material eller tjänster som förbrukas direkt, och som inte kräver ytterligare nedbrytning eller peggad leverans.

### <a name="phantom"></a>Fiktiv

Välj **Fiktiv** när du vill bryta ned artiklar på lägre nivåer i strukturlistan som finns på strukturlisteraden. I huvudplaneringen i den planerade kostnadsberäkning eller vid uppskattning av en produktionsorder som använder strukturlisterader av typen **Fiktiv**, ersätts den överordnade strukturlisteraden som refererar till en produktvariant, som har en fiktiv strukturlista med komponentartiklarna som anges som strukturlisterader för strukturlistan, enligt gällande aktiv strukturlisteversion för produktvariant. Om produktvarianten har användbart aktivt flöde sammanslås operationer i flödet med det överordnade flödet.  

Observera att fiktiva element vanligtvis används för att förenkla teknikprocessen. Omfattande användning av fiktiva strukturlistor på många nivåer har effekt på systemets prestanda, särskilt i tillverkning med många upprepningar. För förbättrade prestanda bör du undvika djupa hierarkier av fiktiva listor. Använd i stället förnedbrutna produktionsstrukturlistor och flöden.

### <a name="pegged-supply"></a>Peggad leverans

Välj radtypen **Peggad leverans** när du vill skapa en delproduktion, en händelsekanban för en strukturlista eller en direkt inköpsorder för alla produktvarianter som strukturlisteraden hänvisar till. Delproduktionen, händelsekanban eller inköpsordern skapas när du uppskattar produktionsordern. De begärda artikelkvantiteterna reserveras automatiskt för produktionsordern.

### <a name="vendor"></a>Säljare

Välj radtypen **Leverantör** om produktionsprocessen använder en underleverantör och du vill att en delproduktion eller inköpsorder ska skapas automatiskt för underleverantören.  

**Observera om underleverantörsoperationer i en strukturlista:** Tjänsten eller arbetet som utförs av underleverantören måste skapas som en serviceartikel som kan spåras i lagret. Du måste koppla serviceartikeln till den överordnade artikeln som en strukturlisterad. Flödet måste innehålla en operation som är tilldelad underleverantörens verksamhetsresurs.




