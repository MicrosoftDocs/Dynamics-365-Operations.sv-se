---
title: Ekonomiska dimensioner
description: Den här ämnet beskriver de olika typerna av ekonomiska dimensioner och hur de ställs in.
author: aprilolson
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ems.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 0715d3e4e4cb167c55d9c7d98cdf599187bf3b43
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448123"
---
# <a name="financial-dimensions"></a>Ekonomiska dimensioner

[!include [banner](../includes/banner.md)]

Den här ämnet beskriver de olika typerna av ekonomiska dimensioner och hur de ställs in.

Använd sidan **Ekonomiska dimensioner** om du vill skapa ekonomiska dimensioner som du kan använda som kontosegment för delade kontoplaner. Det finns två typer av ekonomiska dimensioner: anpassade dimensioner och enhetsbaserad dimensioner. Anpassade dimensioner delas av alla juridiska personer, och värdena anges och hanteras av användaren. För enhetsbaserade dimensioner definieras värden på andra ställen i systemet, till exempel kunder och butiker. Vissa enhetsbaserade dimensioner delas av alla juridiska personer och enhetsbaserade dimensioner är företagsspecifka.

Använd formuläret om du vill tilldela ytterligare egenskaper för varje **Värden för ekonomiska dimensioner** efter att du har skapat ekonomiska dimensioner.

Du kan använda ekonomiska dimensioner som representerar juridiska personer. Du behöver inte skapa juridiska personer i Dynamics 365 Finance. Ekonomiska dimensioner är inte emellertid avsedda för för juridiska personers drift- eller affärskrav. Internredovisningsfunktionen i Finance har utformats för att endast fokusera på de redovisningsposter som skapas av varje transaktion.

Utvärdera dina arbetsprocesser i följande områden för att avgöra, innan du ställer in ekonomiska dimensioner som juridiska personer, om den här inställningen kommer att fungera i din organisation:

- Lager
- Försäljning och inköp mellan ekonomiska dimensioner och juridiska personer
- Mmomsberäkning och rapportering
- Driftsrapportering

Nedan följer några av begränsningarna:

- Du kan bara använda momsfunktioner med juridiska personer, inte med ekonomiska dimensioner.
- Vissa rapporter omfattar inte ekonomiska dimensioner. Därför kan du behöva ändra rapporterna om du vill rapportera per ekonomiska dimension.

## <a name="custom-dimensions"></a>Anpassade dimensioner

Om du vill skapa en användardefinierad ekonomisk dimension väljer du **Anpassad dimension** i fältet **Använd värden från**.

Du kan även ange en kontomask för att begränsa beloppet och typen av information som du kan ange för dimensionsvärden. Du kan ange tecken som ska vara oförändrade för varje dimensionsvärde, till exempel bokstäver eller ett bindestreck (-). Du kan även ange nummertecken (\#) och et-tecken (&) som platshållare för tecken som ska ändras varje gång ett dimensionsvärde skapas. Använd ett nummertecken (\#) som platshållare för ett nummer och ett et-tecken (&) som platshållare för en bokstav. Det här fältet för formatmask är bara tillgängligt när du väljer du **Anpassad dimension** i fältet **Använd värden från**.

**Exempel**

Om du vill begränsa dimensionsvärdet till bokstäverna "CC" och tre siffror anger du **CC-\#\#\#** som formatmask.

## <a name="entity-backed-dimensions"></a>Enhetsstödda dimensioner

Om du vill skapa en enhetsstödd ekonomisk dimension väljer du en systemdefinierad enhet på vilken den ekonomiska dimensionen ska baseras i fältet **Använd värden från**. Värden för ekonomisk dimension skapas utifrån den här entiteten. Om du till exempel vill skapa dimensionsvärden för projekt väljer du **Projekt**. Ett dimensionsvärde skapas sedan för varje projektnamnet. Sidan **värden för ekonomiska dimensioner** visar värdena för entiteten. Om dessa värden är företagsspecifika visar sidan också företaget.

## <a name="activating-dimensions"></a>Dimensionsaktivering

När du aktiverar en ekonomisk dimension uppdateras registret så att det inkluderar namnet på den ekonomiska dimensionen. Borttagna dimensioner raderas. Du kan ange dimensionsvärden innan du aktiverar en ekonomisk dimension. Men en ekonomisk dimension kan inte utnyttjas någonstans tills den har aktiverats. Du kan t.ex. inte lägga till en ekonomisk dimension till en kontostruktur förrän den ekonomiska dimensionen har aktiverats. När du väljer **aktivera**, uppdateras alla dimensioner och visar statusändringar.

## <a name="translations"></a>Översättningar

På sidan **textöversättning** kan du ange text för den valda ekonomiska dimensionen på olika språk. På sidan **Huvudkontoöversättning** kan du ange text för huvudkontot på olika språk. 

## <a name="legal-entity-overrides"></a>Juridisk person åsidosätter

Alla dimensioner är inte giltiga för alla juridiska personer. Vissa dimensioner är dessutom endast relevanta för en viss period. I dessa fall kan du använda avsnittet **Juridisk person åsidosätter** för att identifiera vilka företag som dimensionen ska uppskjutas för, vem ägaren är och tidsperioden dimensionen är aktiv i.

## <a name="deleting-financial-dimensions"></a>Ta bort ekonomiska dimensioner

För att upprätthålla datans referensintegritet kan ekonomiska dimensioner sällan tas bort. Om du försöker ta bort en ekonomisk dimension utvärderas följande kriterier:

- Har den ekonomiska dimensionen använts på bokförda eller ej bokförda transaktioner eller någon typ av dimensionsvärdekombination?
- Är den ekonomiska dimensionen i en aktiv kontostruktur, avancerad regelstruktur, eller ekonomisk dimension angiven?
- Ingår den ekonomiska dimensionen i standardformat för integrering av ekonomisk dimension?
- Har den ekonomiska dimensionen ställts in som standarddimension?

Du kan inte radera den ekonomiska dimensionen om något av villkoren är uppfyllda.

## <a name="default-dimension-values"></a>Standarddimensionsvärden

Du kan använda värden från huvudposter, till exempel kund och leverantör som standardvärden för nya dimensioner. När de nya dimensionerna skapas anges huvudpost-ID i dimensionsvärdena för dessa huvudposter. När du t.ex skapar en ny kund anges kund-ID i kunddimensionen. När du skapar försäljningsorder, fakturor eller andra dokument som kräver ett kund-ID används de befintliga standardreglerna och kund-ID som läggs till i dokumentet.

Den här funktionen kontrolleras av en inställning i dimensionen. Den här inställningen kallas **kopiera värdena till denna dimension för varje ny DimensionName skapas**, där **DimensionName** är namnet på dimensionen. Funktionen är avstängd som standard. Det kan dock sättas på när som helst.

Om det redan finns poster för dimensionen uppdateras huvudposterna när du aktiverar funktionen. Men befintliga dokument och transaktioner uppdaterade.

Om du använder en mall för att skapa en huvudpost, kontrollera att mallvärdet för huvuddimensionen är tomt. Om du till exempel skapar kunder från en mall, kontrollera att kunddimensionen i mallen är tom. Kunddimensionsvärdet hämtas som standard från det nya kundnumret när du skapar en ny kund.  

## <a name="derived-dimensions"></a>Härledda dimensioner

Du kan konfigurera en dimension så att information för andra dimensioner automatiskt anges när du anger den dimensionen i ett dokument Om du anger kostnadsställe 10, ett värde på exempelvis **20** kan anges automatiskt i avdelningsdimensionen.

Du kan ställa in härledda värden på sidan för dimensioner.

1. Välj en dimension och sedan **Härledda dimensioner**.

    Sidan **Härledda dimensioner** innehåller ett rutnät. Det valda dimensionsegmentet är den första kolumnen i det här rutnätet.

2. Lägg till de segment som ska härledas. Varje segment visas som en kolumn.

Ange dimensionskombinationer som bör härledas från dimensionen i den första kolumnen. Om du vill använda kostnadsstället som dimensionen avdelning och plats härleds från t.ex. kostnadsställe 10, avdelning 20, lokal 30. Sedan när du anger kostnadsställe 10, i en huvudpost eller på en sida för transaktionssidan, avdelning 20 och plats 30 anges som standard.

### <a name="overriding-existing-values-with-derived-dimensions"></a>Åsidosättning av befintliga dimensionsvärden med härledda dimensioner
 
Som standard åsidosätter inte den härledda dimensionsprocessen befintliga härledda dimensioner. Till exempel om du anger kostnadsställe 10 och inga andra dimensionen anges, anges avdelning 20 och plats 30 som standard. Om du ändrar kostnadsställe ändras dock inte de värden som redan har upprättats. Därför kan du upprätta standarddimensioner för huvudposter och dessa dimensioner ändras inte efter härledda dimensioner.

Du kan ändra beteendet för härledda dimensioner att åsidosätta befintliga värden genom att markera kryssrutan **Ersätt befintliga dimensionsvärden med härledda värden** på sidan **härledda dimensioner**. Om detta fält är markerat kan du ange en dimension med härledda dimensionsvärden och de härledda dimensionsvärdena åsidosätter eventuella värden som redan finns. Med föregående exempel, om du anger kostnadsställe 10 och inga andra dimensionen anges, anges avdelning 20 och plats 30 som standard. Om värdet redan var avdelning 50 och plats 60 ändras emellertid värdena men nu till avdelning 20 och plats 30.
 
Härledda dimensioner med denna inställning ersätter inte automatiskt befintliga standardvärden för dimension när dimensionsvärdena är standard. Dimensionsvärden åsidosätts bara när du anger ett nytt dimensionsvärde på en sida och det finns befintliga härledda värden för den aktuella dimensionen på sidan.

### <a name="preventing-changes-with-derived-dimensions"></a>Förhindra ändringar med härledda dimensioner
 
När du använder **Lägg till segment ”** på sidan **Härledda dimensioner** om du vill lägga till ett segment som en härledd dimension finns ett alternativ längst ned på sidan **Lägg till segment** som låter dig förhindra ändringar till den dimensionen när den hämtas på en sida. Standardinställningen är av så att den inte förhindrar härledda dimensionsvärdena från att ändras. Ändra inställningen till **Ja** om du vill förhindra att dimensionen ändras när de har härletts. Till exempel om värdet för avdelningsdimensionen härleds från värdet för kostnadsställedimensionen kan avdelningsvärdet inte ändras om inställningen **Förhindra ändringar** är **Ja**. 
 
Inställningen inte ändras om dimensionsvärdet är giltig, men visas inte i listan över härledda dimensioner. Till exempel om avdelning 20 härleds från kostnadsställe 10 och du anger kostnadsställe 10 kommer du inte att kunna redigera avdelning 20. Men om du anger kostnadsställe 20 och det är inte i listan över härledda dimensionerna för kostnadsställe, kan du redigera värdet avdelning. 
 
I samtliga fall kommer kontovärdet och alla dimensionsvärden fortfarande valideras mot kontostrukturerna efter att de härledda dimensionsvärden har använts. Om du använder härledda dimensioner och de inte kan valideras när de används på en sida, måste du ändra härledda dimensionsvärden på sidan för härledda dimensioner innan du kan använda dem i transaktioner. 
 
När du ändrar dimensionerna på snabbfliken **ekonomiska dimensioner** kommer den dimension som har markerats för att förhindra ändringar inte att vara redigerbar. Om du anger ett konto och dimensioner i kontrollen av segmenterade poster på en sida, kan dimensionerna redigeras. Men när du flyttar markeringen från kontroll av segmenterade poster och flyttar till annat fält eller utför en åtgärd kommer kontot och dimensionerna att valideras mot listan med härledda dimensioner och kontostrukturer för att se till att du har angett lämpliga värden. 

### <a name="derived-dimensions-and-entities"></a>Härledda dimensioner och enheter

Du kan ställa in dimensioner härledda segment och värden med hjälp av enheter.

- Härledda dimensioner ordnar upp dimensioner och segment som används för dessa dimensioner.
- Härledda entiteters dimensionsvärde låter dig importera de värden som ska härledas för varje huvuddimension.

När du använder en enhet för att importera data, om den enheten importerar dimensioner tillämpas reglerna för härledd dimension under importen, om inte enheten specifikt åsidosätter dessa dimensioner.

Mer information finns i följande avsnitt:

- [Definiera ekonomiska dimensioner](tasks/define-financial-dimensions.md)
- [Underhåll standardmallar för ekonomisk dimension](tasks/maintain-financial-dimension-default-templates.md)
