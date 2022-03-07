---
title: Kundtjänstkataloger
description: Det här avsnittet innehåller en beskrivning av den callcenterspecifika funktionen för kataloger i Dynamics 365 Commerce.
author: josaw1
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a091e059d4528c356a5038c750cac3a3f31a7edb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799668"
---
# <a name="call-center-catalogs"></a>Kundtjänstkataloger

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller en beskrivning av den callcenterspecifika funktionen som är länkad till kataloger i Dynamics 365 Commerce.

Katalogfunktionerna i Commerce kan användas för flera ändamål. Ursprungligen skapades funktionerna för katalogen för näthandelsintegration för tredje part. Katalogens konfiguration tillät att företag kunde skapa en grupp med produkter och attribut som kunde publiceras externt för förbrukning av en tredje parts näthandelslösning.

När kundtjänsts supportkanal lades till utökades katalogkonceptet till att lägga till ytterligare funktioner för stöd och hantering relaterade till traditionella marknadsföringskataloger för försäljning direkt till konsument. Ett direkt till konsument-företag ger ofta ut tryckta kataloger som sedan skickas till ett eller flera segment med kunder. Dessa kataloger har vanligtvis särskilda erbjudanden och erbjudanden som bara gäller om kunden anger en katalogidentifieringskod när beställningen görs.

Försäljning direkt till konsument-företag är mycket fokuserade på att följa upp svar på dessa kataloger så att kostnaderna för att tillverka och skicka dem är berättigade. För att spåra svar skrivs en kod traditionellt ut på baksidan av katalogen och denna kod begärs sedan och tillämpas när katalogmottagaren ringer för att göra en beställning per telefon (eller nu mer traditionellt kan koden anges när kunden gör en beställning online). Det finns olika branschtermer som har använts för att identifiera den här katalogen artikelspårningskod (inklusive nyckelkod, kampanjkod, katalogkod, källkoden) avses koden i Commerce som **Källkods-ID**.

## <a name="basic-catalog-setup"></a>Grundläggande kataloginställningar

Gå till **Butik och handel** \> **kataloger och sortiment** \> **alla kataloger** för att konfigurera katalogen.

När du skapar en ny katalog måste du först koppla katalogen minst en kanal. Detta görs på snabbfliken **handelskanaler** på formuläret **kataloginställningar**. Klicka på **Lägg till** och välj en eller flera kanaler. Endast artiklar som är kopplade till den valda kanalen [sortiment](https://docs.microsoft.com/dynamics365/unified-operations/retail/assortments) kan användas när du skapar katalogen.

Om du vill lägga till produkter i en katalog måste en navigeringshierarkin väljas. Kategoristrukturen stöder navigeringshierarkin för katalogen. Du måste välja från en av de navigeringshierarkier som är kopplade till återförsäljare som valts på snabbfliken **Handelskanaler** på sidan **katalog**. Om en navigeringskanal inte har kopplats till en kanal tidigare, går du till **Butik och handel** \> **Kanalinställning** \> **Kanalkategorier och produktattribut** för att koppla standardnavigeringshierarkin till var och en av dina kanaler.

På menyfliken **kataloger** på sidan **Kataloginställning** klickar du på **lägga till produkter** för att konfigurera produkter som ska läggas till katalogen eller väljer en nod i navigeringshierarkin (när du markerar en nod ändras skärmpresentationen och du kan lägga till produkter direkt till en kategori i katalogen).

Klicka på toppnoden i kataloghierarkin för att gå tillbaka till huvudkatalogens rubrikvy. Konfigurera giltighetsdatumet och utgångsdatumet efter behov på snabbfliken **Allmänna**.

Innan du kan använda katalogen måste den publiceras. Klicka på **Validera katalogen** på menyn **Kataloger** om du vill bearbeta en validering. Detta är begärd åtgärd och verifierar att de nödvändiga inställningarna är korrekta. Klicka på **Visa resultat** om du vill visa detaljer för valideringen. Om fel påträffas måste du korrigera data och köra validering igen tills valideringen är klar.

När valideringen har bekräftats, klickar du på **arbetsflöde** på menyn för att starta arbetsflödet för godkännande. Klicka på **skicka** på menyn **arbetsflöde** om du vill köra processen. Konfigurera stegen och behöriga användare för arbetsflöde från **Butik och handel** \> **Inställningar för huvudkontor** \> **Arbetsflöden (handel)**. Arbetsflödet definierar de steg som krävs för att hämta katalogen till status **Godkänd**. När katalogen har status **godkänd** kan du klicka på alternativet **publicera** på menyn **kataloger** för att slutföra processen. När katalogen är i status **publicerad** kan den användas vid orderregistrering för kundtjänst och skicka katalogprocesser.

## <a name="use-catalogs-to-drive-sales-order-pricing-and-promotions"></a>Använd kataloger till prissättning av försäljningsorder och kampanjer

En huvudorsak för att definiera en katalog med en kundtjänst är att kunna konfigurera specifika priser och erbjudanden för den katalogen. Kunder som beställer från den här katalogen får dessa priser och det erbjudanden vid orderregistrering för kundtjänst om katalogens **Källkods-ID** används för orderrubrik eller rader.

Om du vill konfigurera specifika priser väljer du alternativet **prisgrupper** från fliken **kataloger** för att länka en eller flera prisgrupper i katalogen. Alla handelsavtal, journaler för prisjusteringar och avancerade rabatter (tröskelvärde, kvantitet, mixa och matcha) som har länkats till samma prisgrupp kommer att tillämpas när kunderna beställer från den här katalogen.

På snabbfliken **källkoder** klickar du på **Lägg till** för att lägga till en eller flera identifierare av **Källkods-ID** i katalogen. Detta är den kod som kommer att gälla vid orderregistrering för kundtjänst till försäljningsorderns rubrik (och rader). Den här koden används för att koppla försäljningsordern till katalogen och slutligen till prisgrupperna och särskilda priser och kampanjer som har konfigurerats.

## <a name="use-the-source-id-to-track-costs-and-response-rates"></a>Använd käll-ID för att spåra kostnader och svarsfrekvenser

När du definierar **källkods-ID** kan du alternativt koppla detta ID till ett **Målmarknad-ID**. **Målmarknad-ID** kan definieras i **Butik och handel** \> **Kunder** \> **Målmarknad**. Målmarknaden är en lista med kunder och/eller potentiella kunder som hör till ett användardefinierat segment. Att länka data för kunder eller potentiella kunder till källkod-ID ger bättre insyn i mottagarna av katalogen. Om en kund är kopplad till en målmarknad och denna målmarknad är kopplad till en aktiv källkod-ID/katalog kan användare av kundtjänst kunna se vilka kataloger som kunden har fått genom att välja menyalternativet **källkoder** på menyfliken **Kunder** på sidan **kundtjänst**. Under orderregistreringen kan användare av kundtjänst också se vissa kataloger som en kund har skickats i listrutan **källa** i försäljningsorderrubriken. Att ändra filtret från **alla** till **inriktade** tillåter användare att se de specifika aktiva katalogerna som kunden har skickats. Detta är användbart i situationer där kunden kan ha glömt sin katalog eller inte kan hitta eller läsa katalogkoden när de ringer för att skapa en försäljningsorder.

Det går att länka flera källkod-ID till en katalog. Det behövs ofta när ett företag vill följa upp svarsfrekvensen av olika segment. Företaget får en unik katalogkod till olika kundsegment som tillåter att spåra svarsfrekvensen ner till segmentnivån i en viss kataloghändelse.

Att välja en viss **källkod-ID som** och klicka på alternativet **information** på snabbfliken **källkoder** ger ytterligare fält där försäljningsprognoser, portokostnader och datum då utskicket sänds kan hämtas. Informationen är användbar för att göra detaljerad analys av katalogens effektivitet. Användare kan återgå till den här sidan med tiden och använda knapparna **källkodsanalys** och **jämför erbjudanden** för att utlösa analytiska rapporter utifrån aktuella försäljningsdata och jämföra kostnader och budget till verkliga värden.

## <a name="configure-catalog-specific-order-and-item-scripts"></a>Konfigurera katalogspecifik order och artikelskript

När en användare av kundtjänst skapar en försäljningsorder kan de använda skript på skärmen. Dessa textbaserade skript kan ge ytterligare information som användaren ska säga till kunden eller det kan vara interna noteringar/påminnelser som användaren av kundtjänst ska granska och reagera på när de skapar försäljningsordern.

Det är ofta användbart att ha olika typer av skript för olika kataloger. På snabbfliken **skript** kan fördefinierade skript kopplas till en katalog. Använd fältet **tidpunkt** för att avgöra om skriptet visas i början av ordern (så snart som källkod-ID anges i orderrubriken) eller i slutet av ordern (i försäljningsorderns sammanfattningsformulär).

När du väljer en nod i katalogens hierarki och arbetar med data på snabbfliken **produkter** kan användare också länka skript som är specifika för kataloger eller artiklar med hjälp av åtgärden **skript**.

## <a name="configure-catalog-specific-up-sell-and-cross-sell-items"></a>Konfigurera katalogspecifika artiklar för merförsäljning och korsförsäljning

Att koppla förslag till merförsäljning eller korsförsäljning för en artikel kan göras från produktinställningen, men i vissa fall kanske ett företag vill marknadsföra merförsäljning/korsförsäljning av artiklar till kunder som beställer en viss produkt från en viss katalog. På snabbfliken **produkter** väljer du en artikel och klickar på **Artiklar för merförsäljning/korsförsäljning** för att konfigurera produkter för att merförsäljas eller korsförsäljas till kunder som köper de valda artiklarna från katalogen. Vid orderregistrering för kundtjänst visas katalogspecifika artiklar för merförsäljning/korsförsäljning på skärmen i stället för att skapa produkter för merförsäljning/korsförsäljning som har konfigurerats för den artikeln via vanlig produktkonfiguration.

Artiklar för merförsäljning eller korsförsäljning kan också utnyttja skriptfunktionerna för att visa specifika meddelanden som användaren kommer att se när artikeln för merförsäljning/korsförsäljning visas under orderregistreringsskriptet. Skript som är kopplade till produkter för merförsäljning/korsförsäljning som konfigurerats specifikt för en katalogprodukt visas endast när katalogens källkod används vid orderregistrering för kundtjänst.

## <a name="catalog-page-analysis"></a>Katalogsidaanalys

På fliken **kataloger** finns alternativ att konfigurera **katalogsidor**. Den här funktionen låter dig definiera särskilda sidor och sidtyper för utskrivna katalogen och deras associerade kostnader.

När du konfigurerar produkter i katalogen, använd åtgärden **Produktsidlayout** för att definiera specifika sidor, procentandel av sidan och placering av sidinformation för artikeln. Genom att konfigurera denna information kommer användarna att kunna dra nytta av **Rapport över katalogområdesanalys**. Rapporten finns genom att gå till **Butik och handel** \> **Kundtjänstrapporter** \> **Katalogområdesanalys**. Rapporten analyserar försäljningen mot katalogen (försäljningsorder där käll-ID för katalogen var knuten till orderrubriken eller raden) och deras associerade procentandel av sidan och kostnader för en traditionell rapport av direkt marknadsföring **Analys av kvadrattum**.

## <a name="catalog-requests"></a>Katalogförfrågningar

Medan kataloger som konfigurerats och publiceras i Commerce kan funktionen **skicka katalog** användas. Den här funktionen finns på sidan **kundsökning** och **kundtjänst**. När du har valt en kundpost genom **Sök efter kund** eller medan du visar ett konto för valda kunder från **kundtjänst** kan användarna välja alternativet **skicka katalog** som leder till en dialogruta som tillåter användaren att välja från en lista över alla publicerade och aktiva kataloger. Användaren kan välja en katalog och en kvantitet och ett visst källkod-ID som ska skickas. När de klickar på knappen **skicka** kommer en begäran att lagras som sedan kan hanteras genom att skriva ut rapporten **Katalogförfrågningar**. Rapporten finns genom att gå till **Butik och handel** \> **Kundtjänstrapporter** \> **Katalogförfrågningar – rapport**. Den listar alla katalogförfrågningar, inklusive kundinformation för namn och adress till kunden som begärde ändringen av katalogen. Rapporten kan användas internt eller data kan överföras till tredje part underliggande externa processer för att fysiskt skicka katalogen till kunden.

## <a name="additional-features"></a>Ytterligare funktioner

På fliken **kataloger**, finns även alternativ för att konfigurera en **betalningsplan** och **gratisprodukter** tillgängliga. Om källkod-ID länkat till katalogen används vid orderregistrering för kundtjänst kommer kunden att berättigas kostnadsfria produkter eller användning av katalogbetalningsplaner enligt definitionen. Om det är nödvändigt att begränsa kunden till att endast kunna välja från betalplann kopplade till deras katalog och inte alla aktiva betalningsplaner i systemet kan kryssrutan **Tillåt endast katalogplaner** markeras för minst ett källkod-ID som definierats för att framtvinga denna begränsning.

## <a name="additional-notes"></a>Ytterligare noteringar

När en källkod-ID gäller för en försäljningsorder i kundtjänst, används den för närvarande för att skapa priser, erbjudanden, skript och merförsäljning/korsförsäljnings som är katalogspecifika. Systemet kommer inte att förbjuda eller hindra att en produkt som inte finns i katalogen beställs på försäljningsordern. Om en artikel är beställd som inte tillhör katalogen, kommer systemet först att använda prisgrupp som definieras i kundtjänstkanalen **Prisgrupp** som definieras i kundtjänstkanalen (**Butik och handel** \> **Kanaler** \> **Kundtjänst** \> **Alla kundtjänster**) för artikelpris eller erbjudanden. Om du inte hittar något specifikt kanalpris, används det grundläggande försäljningspriset för artikeln.


[!INCLUDE[footer-include](../includes/footer-banner.md)]