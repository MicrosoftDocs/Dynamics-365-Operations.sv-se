---
title: Kalendrar och huvudplanering
description: Det här avsnittet innehåller en översikt över logistikkalendrar och hur de påverkar huvudplanering.
author: t-benebo
ms.date: 08/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7a53efb753a75916c85dc4a45a3c64872a7f5d32
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908381"
---
# <a name="calendars-and-master-planning"></a>Kalendrar och huvudplanering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en översikt över logistikkalendrar och hur de påverkar huvudplanering.  Olika kalendrar som används i huvudplaneringsmotorn beskrivs, bland annat hur de påverkar datumen leverans- och mottagningsdatum i de planerade orderna. Dessutom ges rekommendationer om tilldelning, användning och uppdatering av kalendrarna.

## <a name="definition-of-a-calendar"></a>Definition av kalender.

Du kan definiera en kalender som ska användas i din organisation på sidan **Organisationsadministration > Inställningar > kalendrar > kalendrar**. 

Varje datumpost i en kalender kan vara **öppen** eller **stängd** eller **baskalender**. Detta anges i kolumnen **kontroll** på sidan **arbetstider**. För varje datum: 
- **Öppna** - anger att arbete utförs på den valda dagen. Kalendern uppdateras enligt arbetstidsmallen.
- **Stängd** - anger att arbete inte utförs under den valda dagen. 
- **Baskalender** - anger att ett visst datum ärver arbetstider och öppen/stängd från baskalendern. När baskalendern uppdateras kommer därför den valda kalendern att ärva operationstider från den. 

För alla stängda datum tilldelas kryssrutan **stängd för upphämtning** automatiskt. För öppna datum kan du manuellt välja alternativ **stängd för upphämtning**. Detta betyder att arbetet utförs på datumet, men leverans utförs inte. 

## <a name="calendars-that-affect-master-planning"></a>Kalendrar som påverkar huvudplanering

### <a name="calendar-for-a-coverage-group"></a>Kalender för en disponeringsgrupp
En disponeringsgrupp anger en gemensam uppsättning parametrar som används för påfyllning av artiklar som tillhör den angivna disponeringsgruppen. 

För att lägga till en kalender för en disponeringsgrupp, gå till **Huvudplanering > Disponering > Disponeringsgrupper**. Hitta den disponeringsgrupp du vill tilldela till kalendern och klicka på fältet **kalender**.

Disponeringsgruppen kan tilldelas på olika sidor: 
    - På sidan **Information om frisläppt produkt** för en artikel. För att visa disponeringsgruppen för en artikel, gå till **produktinformationshantering > produkter > frisläppta produkter** och välj artikeln för att gå till sidan **uppgifter om frisläppta produkter**. Du ser artikelns disponeringsgrupp under snabbfliken **planera**.
    - På sidan **artikeldisponering**. På informationssidan om frisläppta produkter, klicka på **artikeldisponering** för att gå till sidan för artikeldisponering. På översiktsfliken visas olika parametrar för påfyllnad beroende på webbplats, lagerställe och produktdimensioner. Disponeringsgruppen för varje artikel ärvs från disponeringsgruppen på sidan **Information om frisläppt produkt**. Detta kan åsidosättas med **Använd specifika inställningar** eller **Åsidosätta gruppinställningen** på fliken **allmänna**.
    - På sidan **huvudplaneringsparametrar**. Om en artikel inte har en disponeringsgrupp angiven på föregående sidor, tar huvudplanering den allmänna disponeringsgruppen som anges på huvudplaneringsparametrar. Detta ställs in i **Huvudplanering > Inställningar > Huvudplaneringsparametrar** i fältet **Allmän disponeringsgrupp**. 

### <a name="calendar-for-a-vendor"></a>Kalender för en leverantör
Om du vill ange arbetsdagar från en leverantör du kan tilldela en kalender för inköpsorder till leverantören på sidan **standardvärden för inköpsorder** för en leverantör. 

Om du vill skapa en kalender för en leverantör måste du skapa kalendern i **Organisationsadministration > Kalendrar > Kalendrar**. Du måste tilldela leverantören när kalendern skapas. Gå till **Leverantörsreskontra > leverantörer > alla leverantörer** och välj den leverantör som du vill tilldela en kalender. Klicka sedan på leverantörens sida på snabbfliken **standardvärden för inköpsorder** och tilldela den nya kalendern för inköp med hjälp av den nedrullningsbara menyn. 

Kalendern för en leverantör anger vilka dagar som de godkänner placeringen av inköpsordern och datum då de kan leverera order till ditt företag. Följaktligen kommer orderdatum för inköpsorder för leverantören med en inköpskalender definieras som öppen i kalendern. Leveransdatum för dessa order betraktas också som öppna dagar och påverkar därför ledtiden för den inköpta artikeln. 

#### <a name="define-the-lead-time-for-a-purchased-item"></a>Definiera produktionstiden för en inköpt artikel

För att ange inköpsproduktionstiden (och om endast arbetsdagar ska betraktas) för en artikel måste du gå till inställningssidan för produkten under **produktinformationshantering > produkter > frisläppta produkter** och sedan välja **standardorderinställningar**. 

> [!Note]
> **Arbetsdagar** under inköpsproduktionstiden anger arbetsdagar från leverantören. Till exempel en kalender för leverans endast på tisdagar och en produktionstid på 10 dagar och arbetsdagar markerat att det skulle ta 10 veckor (10 tisdagar) för artikeln att levereras.
Det betyder i de flesta fall att det inte rekommenderas att välja arbetsdagar för produktionstider för inköpsorder.

#### <a name="define-lead-times-from-the-trade-agreements-page"></a>Ange produktionstider från sidan Handelsavtal

Huvudplanering kan ställas in för att inkludera alla handelsavtal för leverantörer. Handelsavtalen är fasta priser eller rabattavtal som har ställts in för en eller flera kunder eller leverantörer för försäljning eller inköp av en eller flera produkter. Gå till **Huvudplanering > Inställningar > Huvudplaneringsparametrar** och fliken **Planerade order** och välj **Sök efter handelsavtal** ska inkluderas när du planerar handelsavtalen. Huvudplanering kan välja leverantören med **minsta produktionstid** eller **lägsta pris**.

### <a name="calendar-for-a-warehouse"></a>Kalender för ett lagerställe
Du kan tilldela en kalender till ett lagerställe för att visa öppna datum för mottagning och leverans. Om ett lagerställe har tilldelats ett lagerställe antas att den är öppen alla dagar. 

> [!Note]
> Tilldela en kalender till ett transitlager har inte någon inverkan. Transitlager används för överföringsorder. Gällande leverans- eller inleveransdatum för order definieras av öppna dagar i "från" lagerställe och "till" lagerställe och leveranssättkalendern.

#### <a name="closed-for-pickup-policy"></a>Stängd för upphämtning-policy
För att indikera att ett lagerställe som är öppet för inleverans men upphämtning är inte möjligt kan du använda **stängd för upphämtning-policy** i kalendern för lagerstället. Detta gäller även för upphämtning av kund. 

### <a name="transport-calendar"></a>Transportkalender 
För att ange de datum som är tillgängliga för leverans av överföringsorder från ett **från lagerställe**, kan du tilldela en **transportkalendern**. Du kan ställa in en transportkalender per leveranssätt eller per leveranssätt och från lagerställe. Transportkalendern ställs in i **Försäljning och marknadsföring > Inställningar > Distribution > Leveranssätt**. Välj ett leveranssätt och klicka på knappen **Transportkalender**.

En rad kan skapas för varje lagerställe och leveranssätt där kalendern läggs till i kolumnen **transportkalender**. Den anger transportkalendern som tillämpas när varorna levereras från lagerstället med det angivna leveranssättet. Du tillämpar en transportkalender för alla försändelser med ett visst leveranssätt, en rad kan skapas utan att ange lagerstället.  Den påverkar alla försändelser med det angivna leveranssättet oavsett lagerstället. 

Om ingen transportkalender är tilldelad antas det att alla dagar är öppna för transport.

### <a name="calendar-for-a-customer"></a>Kalender för en kund
För att ange datum då en kund kan acceptera leveranser kan du tilldela en inleveranskalender till kunden. Om ingen kalender är kopplad till en kund, antas det att kunden kan ta emot order under alla dagar. Detta påverkar inleveransdatum på försäljningsorderrader. Om du väljer ett datum i försäljningsorderrader som inte är ”öppen” i kundkalendern indikerar systemet att inleveransdatum inte är giltigt. 

Observera att det går bara att inkludera en kalender per kund. Om du vill inkludera en kalender för en annan adress för en kund måste du skapa en kund per adress och tilldela deras respektive kalender. 

Det begärda inleveransdatumet på försäljningsorderraderna påverkas av kundkalendern och kontrollmetoden för leveransdatum. Du kan läsa mer om hur det tidigaste leveransdatumet beräknas i [Orderlöfte](/dynamics365/unified-operations/supply-chain/sales-marketing/delivery-dates-available-promise-calculations).

### <a name="shipping-calendar-for-a-legal-entity"></a>Leveranskalender för en bestämd juridisk person
Om du vill ange de datum då en juridisk person kan leverera varor kan du ställa in en leveranskalender under **Organisationsadministration > organisationer > juridiska personer**. Välj den juridiska personen och lägg till kalendern på fliken **Utländsk handel och logistik** i fältet **Leveranskalender**. Leveranskalendern fungerar som standard för alla kalendrar i lagerstället i den juridiska personen. 

## <a name="how-calendars-affect-dates-in-planning"></a>Hur kalendrar påverkar vid planering

### <a name="order-date-of-a-planned-purchase-order"></a>Orderdatum för planerade inköpsorder 
Orderdatum i en planerad inköpsorder anger det datum då ordern görs. Det blir ett öppet datum både i leverantörskalendern och kalendern för artikeldisponering. Ibland behöver leverantörer några dagars marginal mellan när de tar emot inköpsordern och när de kan leverera varorna . Dessa datum anges i leverantörens marginaldagar. Men om artikeln har tilldelats till en disponeringsgrupp med marginaldagar kommer dessa marginaldagar åsidosätta leverantörens marginaldagar.

### <a name="delivery-date-of-a-planned-purchase-order"></a>Leveransdatum för planerade inköpsorder
Inleveransdatumet för ett inköp visas det datum då varorna tas emot. Det ska vara ett öppet datum i kalendern. Kalendern som tas hänsyn till för att ange vilka dagar som inköpsorder kan inlevereras är följande, från högsta till lägsta prioritet: 
1. Leverantörens kalender
1. Kalender för en disponeringsgrupp
1. Kalender för lagerstället för speditionslagret

Observera att kalendern för disponeringsgruppen ställs in på olika sidor och prioriteras i följande ordning:
1. Disponeringsgrupp för artikeln på sidan **artikeldisponering**
1. Disponeringsgrupp för artikeln på sidan **uppgifter om frisläppta produkter**
1. Standardartikeldisponeringsgrupp i **huvudplaneringsparametrar**

### <a name="shipping-date-of-a-planned-transfer-order"></a>Leveransdatum för planerade överföringsorder
När du skapar en överföringsorder mellan två lagerställen med leveransdatum och inleveransdatum i överföringsorderhuvudet tillsammans med lagerstället ”från” lager och ”till” lager. Skillnaden mellan dessa två datum är förväntade transporttiden (i dagar) mellan lagerställen.

Leveransdatum för planerade överföringsorder anger det datum då varorna levereras från ”från” lager. Följande kalendrar används för att ange tillgängliga leveransdatum anges med prioritet: 
1. Lagerställekalender med ”från” lager
1. Disponering för gruppkalender blir (se reservorder för den här kalendern ovan) om det inte finns en lagerställekalender kommer leveransdatum vara ett öppet datum i kalendern. Om det inte finns en lagerställekalender tar den kalendern för disponeringsgruppen. 

### <a name="receipt-date-of-a-planned-transfer-order"></a>Inleveransdatum för planerade överföringsorder
Inleveransdatum för planerade överföringsorder anger det datum då varorna inlevereras från ”till” lager.

Följande kalendrar används för att ange tillgängliga inleveransdatum anges med prioritet: 
1. Kalender för en disponeringsgrupp 
1. Kalender för lagerstället för ”till” lager om det finns en disponeringskalender kommer inleveransdatum vara ett öppet datum i kalendern. Om det inte finns en kalender för disponeringsgrupp tar den kalendern för lagerställe. 

När man hittar inleverans- och mottagandedatum för den planerade överföringen, kommer också de marginaler som användaren fastställer för leverans och mottagande att övervägas. 

## <a name="using-calendars-in-master-planning"></a>Använda kalendrar i huvudplanering

### <a name="assignment-of-scm-calendars"></a>Tilldelning av SCM-kalendrar
Det är viktigt att ställa in kalendrar för att identifiera arbetsdagar i företaget. Bästa implementeringen är att ange en kalender för varje element med olika arbetsdagar. Med andra ord alla externa kalendrar (kund, leverantör) och alla interna (lagerställe, disponeringsgrupp och leveranssätt) relaterade till företaget.

### <a name="recommendation-on-warehouse-calendars"></a>Rekommendation om lagerställekalendrar
Du rekommenderas att använda en kalender per lagerställe för att inkludera de ändringar som endast påverkar lagret. Två eller flera lagerställen kan till exempel ha samma arbetsdagar men en annan upphämtningsprincip. I sådana fall är en kalender för varje lagerställe med sin respektive upphämtningsprincip bästa implementering för att systemet ska ta med bästa datum för planerade order för inköp, överföring och produktion. Om ingen lagerställekalender ställs kan juridisk person-kalender användas som standard för lagerställekalender. 

### <a name="recommendation-of-coverage-group-calendars"></a>Rekommendation av kalender för disponeringsgrupp
För kalender för disponeringsgrupp är det viktigt att beakta som har ett övergripande problem avseende mottagandedatum i huvudplaneringen. Därför rekommenderas att använda den försiktigt. Den är särskilt användbar i fall när påfyllning måste vara göras för specifika dagar i veckan. 

### <a name="updating-scm-related-calendars"></a>Uppdatera SCM-relaterade kalendrar
Medan det är viktigt att alla relevanta kalendrar tilldelas på deras respektive plats (leverantör, kund, lager, leveranssätt eller täckningsgrupp), är uppdatering av dem lika viktiga så att de speglar ändringarna. Systemet definierar produktions-, överförings-, inköps- och försäljningsorderdatum beroende på kombinationen av de tilldelade kalendrarna. Det är lämpligt att förtydliga vem som har ansvaret för att tilldela och uppdatera kalendrar i motsvarande områden. Vid en uppdelning eller någon annan ovanlig förändring på arbetsdagarna är det viktigt att uppdatera kalendrarna enligt det. Alla aktiviteter som är beroende av kalendrar, till exempel huvudplanering och produktionsplanering, måste köras när kalendrar uppdateras. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]