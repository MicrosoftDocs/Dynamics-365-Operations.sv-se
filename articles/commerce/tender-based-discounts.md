---
title: Betalningsmedelbaserade rabatter
description: Denna artikel beskriver en översikt över funktioner för betalningsmedelbaserad rabattsom gör att detaljhandlare kan konfigurera rabatter för olika typer av betalningsmedel i Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/19/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.openlocfilehash: 3c28297e62e5b2880a7a39381702d5a1448c91ac
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336766"
---
# <a name="tender-based-discount"></a>Betalningsmedelbaserad rabatt

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Denna artikel beskriver en översikt över funktioner för betalningsmedelbaserad rabattsom gör att detaljhandlare kan konfigurera rabatter för olika typer av betalningsmedel i Microsoft Dynamics 365 Commerce.

Det är en vanligt mellan återförsäljare att frisläppa privata, märkeskreditkort. Detaljhandlare drar nytta av detta eftersom de får förmånliga avgifter från bankerna. Eftersom dessa kreditkort också kan uppmuntra kunderna att besöka butiken ofta, bidrar de till att förbättra detaljhandlarens slutresultat. Därför har detaljhandlare ett incitament för att öka kundens användning av kreditkort. För att uppnå detta mål ger de ofta ytterligare rabatter till kunder som använder dessa kreditkort.

Alternativt kan återförsäljare som inte har anpassade kreditkort vilja uppmuntra kunderna att betala med hjälp av andra typer av betalningsmedel, t.ex. kassa, presentkort eller förmånspoäng. På så sätt kan de hjälpa till att minska kostnaderna för avgifterna för bearbetningskostnader för kreditkort. Därför kan detaljhandlare ge rabatter till kunder som använder dessa alternativa betalningsmedelstyper.

## <a name="tender-based-discount"></a>Betalningsmedelbaserad rabatt

Commerce stöder en *betalningsmedelbaserad rabatt* som gör att butikerna kan konfigurera en rabattprocent som tillämpas på en transaktion om transaktionssumman överstiger ett specifikt belopp och kunden betalar med den betalningstyp som föredras. Den betalningsmedelsbaserade rabatten är nivåbaserad, så att olika rabattprocent kan associeras med olika beloppströsklar. Kunden kan bestämma om en delbetalning eller en fullständig betalning ska utföras och prissättningsmotorn bestämmer rätt rabattbelopp. Den betalningsmedelsbaserade rabatten ges alltid på försäljningsraderna före skatt.

Betalningsmedelbaserade rabatter kan endast tillämpas på försäljningsrader där priserna inte är låsta, och den fördelas proportionellt till de kvalificerade raderna. Om nya försäljningsrader läggs till i en order, tillämpas den betalningsmedelbaserade rabatten på nya försäljningsrader endast under betalningen. När om en kundorder för upphämtning eller leverans har placerats, tillämpas den betalningsmedelbaserade rabatten endast på insättningsbeloppet. När ordern har placerats är priserna på försäljningsraderna låsta. Ingen betalningsmedelbaserade baserad tillämpas på något saldo som betalas under utleveransen eller godkänns under leveransen. Den betalningsmedelbaserade rabatten kan endast tillämpas på hela beloppet för en kundorder om återförsäljaren samlar hela beloppet som en insättning medan ordern placeras.

Betalningsmedelsbaserade rabatter konkurrerar inte med artikelbaserade rabatter som enkla rabatter, kvantitetsrabatter, tröskelrabatter, mixa och matcha-rabatter och manuella rabatter. Betalningsmedelsbaserade rabatter blandas alltid med artikelbaserade rabatter. Även om en exklusiv rabatt tillämpas på en artikel, tillämpas den betalningsmedelbaserade rabatten fortfarande ovanpå den exklusiva rabatten. På samma sätt gäller att om en tröskelrabatt har tillämpats på transaktionen och den begärda betalningsmedelbaserade rabatten minskar det totala under tröskelvärdet, tillämpas tröskelrabatten fortfarande på transaktionen.

Även om de betalningsmedelbaserade rabatterna minskar delsumman för transaktionen påverkas inte de automatiska tillägg som tillämpas på transaktionen. Om t.ex. leveransavgifterna beräknas som 5 $ eftersom delsumman var mer än 100 $ och den betalningsmedelbaserade rabatten minskar beloppet så att det blir mindre än 100 $, är leveransavgifterna 5 $ för ordern.

Den betalningsmedelbaserade rabatten är för närvarande begränsad till två betalningstyper: kreditkort och kassa. Om flera betalningsmedelbaserade rabatter har konfigurerats för en betalningstyp används endast den högsta betalningsmedelbaserade rabatten.

## <a name="pos-user-experience"></a>Användarupplevelse i kassa

Om den betalningsmedelbaserade rabatten har ställts in på kontanter och kassören i POS väljer en knapp **Betala kontanter** att checka ut en hämtköpstransaktion, tillämpas den betalningsmedelbaserade rabatten automatiskt på transaktionen. Det reducerade beloppet visas sedan som saldot. Om kassören däremot väljer knappen **bakåt** på betalningsskärmen tas rabatten bort och det ursprungliga beloppet visas på transaktionsskärmen. Den betalningsmedelbaserade rabatten tas bort om betalningsraden är annullerad.

För kreditkortbetalningar kan återförsäljare konfigurera den betalningsmedelbaserade rabatten på en eller flera typer av kreditkort. Systemet kan dock inte verifiera vilken typ av kreditkort som används om inte kortet är auktoriserat. Om rabatten tillämpas efter auktorisering får betalningsauktoriseringen ett större belopp, men betalningsinsamlingen blir för ett mindre belopp. För att förhindra den här situationen, om en kund betalar med kreditkort, ser kassören en dialogruta med en lista med kreditkort som ger kunden ytterligare rabatt. Kassören kan sedan fråga om kunden vill använda ett av de förvalda korten för att få en ytterligare rabatt. Om kassören använder ett prioriterat kort tillämpas den betalningsmedelbaserade rabatten på transaktionen och det reducerade beloppet visas på betalningsskärmen. Auktoriseringen kommer att vara för reducerat belopp. Om kunden infogar ett kort som skiljer sig från kortet som kassören har valt, visas ett felmeddelande och auktoriseringen annulleras.

## <a name="call-center-user-experience"></a>Användarupplevelse i kundtjänst

Om en användare av kundtjänst väljer **slutförd** under en kundtjänstorder visas skärmen **Summor**. Först inkluderar summorna på den här skärmen inte betalningsmedelbaserade rabatter eftersom betalsättet ännu inte har valts. På skärmen **Lägg till betalning** om användaren väljer det betalsätt som den betalningsmedelbaserade rabatten är konfigurerad för justeras betalningsbeloppet automatiskt så att det återspeglar det rabatterade beloppet. Precis som kunden i POS kan kunden i kundtjänst avgöra om den ska betala hela betalningen eller en delbetalning. Baserat på det belopp som betalas, tillämpas den avgiftsbelagda rabatten på försäljningsordern.

> [!NOTE]
> Kortvalidering utförs inte för kundtjänstorder. Om t.ex. kundtjänstanvändaren väljer Visa som kreditkort, men kunden använder MasterCard, används rabatten fortfarande i systemet.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
