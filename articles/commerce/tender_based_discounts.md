---
title: Betalningsmedelbaserade rabatter
description: Det här ämnet innehåller en översikt över funktioner som gör att detaljhandlare kan konfigurera rabatter för olika typer av betalningsmedel.
author: bebeale
manager: AnnBe
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: 9f6747ff9d68c29612346254928e869d6d34d433
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962945"
---
# <a name="tender-based-discounts"></a>Betalningsmedelbaserade rabatter

[!include [banner](includes/banner.md)]


Det är en vanligt mellan återförsäljare att frisläppa privata, märkeskreditkort. Detaljhandlare drar nytta av detta eftersom de får förmånliga avgifter från bankerna. Eftersom dessa kreditkort också kan uppmuntra kunderna att besöka butiken ofta, bidrar de till att förbättra detaljhandlarens slutresultat. Därför har detaljhandlare ett incitament för att öka kundens användning av kreditkort. För att uppnå detta mål ger de ofta ytterligare rabatter till kunder som använder dessa kreditkort.

Alternativt kan återförsäljare som inte har anpassade kreditkort vilja uppmuntra kunderna att betala med hjälp av andra typer av betalningsmedel, t.ex. kassa, presentkort eller förmånspoäng. På så sätt kan de hjälpa till att minska kostnaderna för avgifterna för bearbetningskostnader för kreditkort. Därför kan detaljhandlare ge rabatter till kunder som använder dessa alternativa betalningsmedelstyper.

I Microsoft Dynamics 365 Commerce kan detaljhandlare konfigurera en procentuell rabatt som tillämpas på kvalificerade rader om kunden betalar med den föredragna betalningsmedeltypen. Kunden kan bestämma om en delbetalning eller en fullständig betalning ska utföras och Commerce bestämmer rätt rabattbelopp. Observera att rabatten alltid anges på beloppet för de kvalificerade artiklarnas belopp före skatt.

Betalningsmedelbaserade rabatter konkurrerar inte med artikelbaserade rabatter, t.ex. periodiska eller manuella rabatter. De är alltid sammansatta över artikelrabatterna. Även om en exklusiv periodisk rabatt tillämpas på en artikel, tillämpas den betalningsmedelbaserade rabatten fortfarande ovanpå den exklusiva periodiska rabatten. På samma sätt gäller att om en tröskelrabatt har tillämpats på transaktionen och den begärda betalningsmedelbaserade rabatten minskar det totala under tröskelvärdet, tillämpas tröskelrabatten fortfarande på transaktionen.

Även om de betalningsmedelbaserade rabatterna minskar delsumman för transaktionen påverkas inte de automatiska tillägg som tillämpas på transaktionen. Om t.ex. leveransavgifterna beräknas som 5 $ eftersom delsumman var mer än 100 $ och den betalningsmedelbaserade rabatten minskar beloppet så att det blir mindre än 100 $, är leveransavgifterna 5 $ för ordern.


> [!NOTE]
> Betalningsmedelbaserade rabatter distribueras proportionellt mot kvalificerade försäljningsrader och minskar beloppet för före skatt för de enskilda raderna. Om flera betalningsmedelbaserade rabatter har konfigurerats för en typ av betalningsmedel (t.ex. kontanter) används endast den högsta betalningsmedelbaserade rabatten.

Endast betalningsmedelbaserade rabatter kan tillämpas på försäljningsrader där priserna inte är låsta. Om nya försäljningsrader läggs till i en order, tillämpas den betalningsmedelbaserade rabatten på nya försäljningsrader endast under betalningen. Även om en kundorder för upphämtning eller utleverans har placerats, tillämpas den betalningsmedelbaserade rabatten endast på insättningsbeloppet. När ordern har placerats är priserna på försäljningsraderna låsta. Därför tillämpas ingen betalningsmedelbaserade baserad på något saldo som betalas under utleveransen eller godkänns under leveransen. Den betalningsmedelbaserade rabatten kan endast tillämpas på hela beloppet för en kundorder om återförsäljaren samlar hela beloppet som en insättning medan ordern placeras.

> [!IMPORTANT]
> I Commerce är de betalningsmedelbaserade rabatterna för närvarande begränsade till två betalningstyper: kreditkort och kassa.

## <a name="pos-user-experience"></a>Användarupplevelse i kassa

Om den betalningsmedelbaserade rabatten har ställts in på kontanter och kassören i POS väljer en knapp som är mappad till åtgärden Kontantbetalning, används den betalningsmedelbaserade rabatten automatiskt för transaktionen. Det reducerade beloppet visas sedan som saldot. Om kassören däremot väljer knappen **bakåt** på betalningsskärmen tas rabatten bort och det ursprungliga beloppet visas på transaktionsskärmen. Den betalningsmedelbaserade rabatten tas bort om betalningsraden är annullerad.

För kortbetalningar kan återförsäljare ställa in den betalningsmedelbaserade rabatten på en eller flera typer av kreditkort. Systemet kan dock inte verifiera vilken typ av kreditkort som används om inte kortet är auktoriserat. Om rabatten tillämpas efter auktorisering får betalningsauktoriseringen ett större belopp, men betalningsinsamlingen blir för ett mindre belopp.

För att förhindra den här situationen, om en kund betalar med kreditkort, ser kassören en dialogruta med en lista med kreditkort som ger kunden ytterligare besparingar. Kassören kan sedan fråga om kunden vill använda ett av de förvalda korten för att få en ytterligare rabatt. Om kassören använder ett prioriterat kort tillämpas den betalningsmedelbaserade rabatten på transaktionen och det reducerade beloppet visas på betalningsskärmen. Auktoriseringen kommer att vara för reducerat belopp. Om kunden infogar ett kort som skiljer sig från kortet som kassören har valt, visas ett felmeddelande och auktoriseringen annulleras.


## <a name="call-center-user-experience"></a>Användarupplevelse i kundtjänst

När användaren väljer **slutförd** under en kundtjänstorder visas skärmen **Summor**. Först inkluderar summorna på den här skärmen inte betalningsmedelbaserade rabatter eftersom betalsättet ännu inte har valts. På skärmen **Lägg till betalning** om användaren väljer det betalsätt som den betalningsmedelbaserade rabatten är konfigurerad för justeras betalningsbeloppet automatiskt så att det återspeglar det rabatterade beloppet. Precis som kunden i POS kan kunden i kundtjänst avgöra om den ska betala hela betalningen eller en delbetalning. Baserat på det belopp som betalas, tillämpas den avgiftsbelagda rabatten på försäljningsordern.

> [!NOTE]
> Kortvalidering utförs inte för kundtjänstorder. Om t.ex. kundtjänstanvändaren väljer Visa som kreditkort, men kunden använder MasterCard, används rabatten fortfarande i systemet.

## <a name="exclude-items-from-discounts"></a>Exkludera artiklar från rabatter

Återförsäljare väljer ofta att exkludera vissa produkter, t.ex. nya artiklar eller artiklar på begäran, från rabatter. De kan dock fortfarande vilja använda betalningsmedelbaserade rabatter. En återförsäljare konfigurerar till exempel Commerce så att artikelbaserade rabatter eller manuella rabatter inte tillåts. Om kunden betalar med hjälp av det prioriterade betalningsmedlet, kommer Commerce fortfarande rabatten att tillämpas på den betalningsmedelbaserade rabatten. Om du vill ställa in Commerce på det här sättet måste du gå till **Produktinformationshantering > Produkter > Frisläppta produkter**, markera artikeln och sedan på snabbfliken **Commerce** ange alternativen **Förhindra alla rabatter** och **Förhindra betalningsmedelbaserade rabatter** till **Nej** och alternativen **Förhindra butiksrabatter** och **Förhindra manuella rabatter** till **Ja**.

> [!NOTE]
> När konfigurationen **Förhindra alla rabatter** är inställd på **Ja** tillämpas inga rabatter på produkten. Inte heller betalningsmedelbaserade rabatter kommer att användas.
