---
title: Konfigurera betalsätt för kundkonto på B2B-näthandelssajter
description: I denna artikel beskrivs hur du konfigurerar betalningsmetoden för kundkontot i Microsoft Dynamics 365 Commerce. Det beskriver också hur kreditgränser påverkar à conto-betalningar på näthandelsplatser mellan företag (B2B).
author: josaw1
ms.date: 04/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: b8424920c3a177e01b71fc1c288b7acdd97ef191
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272028"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Konfigurera betalsätt för kundkonto på B2B-näthandelssajter

[!include [banner](../../includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar betalningsmetoden för kundkontot i Microsoft Dynamics 365 Commerce. Det beskriver också hur kreditgränser påverkar à conto-betalningar på näthandelsplatser mellan företag (B2B).

Återförsäljare kan acceptera olika typer av betalning i utbytet mot de produkter och tjänster man säljer i en näthandelskanal. Varje betalningstyp som en återförsäljare godtar, måste konfigureras i Dynamics 365 Commerce när systemet installeras. Kundkontots betalsätt (eller "on account") måste stödjas på B2B-näthandelssajter. 

## <a name="prerequisites"></a>Förutsättningar

1. Lägg till betalsättet för kundkonto i Commerce headquarters.
2. Koppla betalsättet för kundkontot till näthandelskanalen.
3. Kontrollera att egenskapen **Tillåt a conto** har aktiverats för kunden på **Butik och Handel \> Kunder \> Alla kunder \> Betalningsstandarder** i Commerce headquarters.

    > [!NOTE]
    > Om alla kunder ska tillåtas ha betalningsmetoden på konto aktiverad kan du konfigurera egenskapen **Tillåt a conto** till **Ja** för standardkund för kanalen som är associerad med B2B-webbplatsen. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Aktivera betalsättet för kund i Commerce-webbplatsbyggaren 

För att aktivera betalsättet för kund i Commerce-webbplatsbyggaren följer du dessa steg.

1. Gå till **Webbplatsinställningar \> Tillägg**.
1. Ställ in egenskapen **Aktivera kundkontobetalningar** som **Aktiverad för B2B-kunder**. 
1. Välj **Spara och publicera**.

> [!NOTE]
> De nya webbplatsinställningarna träder i kraft först när filen app.settings.json har uppdaterats. Mer information finns i [SDK- och modulbiblioteksuppdateringar](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Aktivera betalsättet för kundkonto på kassasidan för B2B-näthandelssajten

Följ dessa steg om du vill aktivera betalsättet för kundkonto på kassasidan för B2B-näthandelssajten.

1. Sök efter och redigera kassasidan eller det fragment som innehåller kassamodulen för B2B-näthandelssajten i Commerce-webbplatsbyggaren.
1. I fältet **Behållare för kassaavsnitt** väljer du **Lägg till modul** innan du lägger till en **Kundkontobetalning**-modul.
1. Placera **Kundkontobetalning**-modulen genom att välja ellipsen (**...**) och sedan **Flytta upp** eller **Flytta ner** efter behov.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Bekräfta att betalsättet för kundkontot har aktiverats och publicerats

För att bekräfta att betalsättet för kundkontot har aktiverats följer du dessa steg.

1. Logga in på näthandelssajten.
1. Lägg till en produkt i kundvagnen.
1. Gå till kassasidan. Du bör se det nya betalsättet **Kundkonto**.

## <a name="work-with-credit-limits"></a>Arbeta med kreditgränser

När funktionerna för kundkontobetalningar har aktiverats på B2B-webbplatsen vill organisationer vanligtvis visa information om kreditgränser och kreditgränssaldon under orderinfångningsprocessen. Kreditgränsen för en kund definieras av egenskapen **Kreditgräns** på snabbfliken **Kredit och inkasso** för kundposten i Commerce headquarters. Vid B2B-scenarier ska dock en order som en kund gör ofta ska faktureras kontot för den organisation som kunden tillhör. Därför måste du konfigurera egenskapen **Fakturakonto** på snabbfliken **Faktura och leverans** för kundposten till organisationens kundkonto-ID. När kunden sedan beställer en order på B2B-webbplats, faktureras ordern till organisationen. B2B-webbplats använder även organisationens kreditgräns i stället för den kreditgräns som har definierats för kundposten.

Kreditgränsberäkningen och saldot som visas på B2B-webbplatsen beror på inställningen av egenskapen för **kreditgränstyp** i Commerce headquarters. Placeringen av denna fastighet varierar beroende på om **Kredithantering** har aktiverats i arbetsytan **Funktionshantering**:

- Om funktionen **Kredithantering** är aktiverad finns egenskapen på snabbfliken **Kreditgränser** på **Kredit och inkasso \> Inställningar \> Kredit och inkassoparametrarna \> Kredit**. 
- Om funktionen **Kredithantering** är inaktiverad, finns egenskapen under **Kreditbedömning** på **Kundreskontra \> Inställningar \> Parametrar för kundreskontra \> Kreditbedömning**.

Värdena som egenskapen för **kreditgränstyp** stöder är **Ingen**, **Saldo**, **Saldo + följesedel eller produktinleverans** och **Saldo + Alla**. Mer information om dessa värden finns i [värden för kreditgränstyper](/dynamics365/supply-chain/sales-marketing/credit-limits-customers).

> [!NOTE]
> Vi rekommenderar att du konfigurerar egenskapen **Kreditgränstyp** till **Saldo + förpackningsföljesedel eller produktföljesedel** så att öppna försäljningsorder inte bidrar till saldoberäkningen. Om dina kunder sedan lägger framtida order behöver de inte se det som att dessa order påverkar deras aktuella saldo.

En annan egenskap som påverkar kontoordern är egenskapen **Obligatorisk kreditgräns** som finns på snabbfliken **Kreditera och inkasso** för kundposten. Genom att ange egenskapen till **Ja** för vissa kunder kan du tvinga systemet att kontrollera sin kreditgräns, även om egenskapen för **kreditgränstyp** har satts till **Ingen** för att ange att kreditgränsen inte ska kontrolleras för någon kund.

För närvarande kan en kund som använder kontobetalningsmetoden inte betala mer än det återstående kreditsaldot för en order. Om kundens återstående kreditsaldo är 1 000 USD men ordern är värd ett 1 200 USD kan kunden till exempel bara betala 1 000 USD med à conto-metoden. Kunden måste sedan använda någon annan betalningsmetod för att betala saldot. I en framtida version innebär en handelskonfiguration att användarna kan lägga ut mer än sin kreditgräns när de gör beställningar.

Modulen **Kredit - och inkasso** har nya funktioner för kredithantering. För att aktivera dessa funktioner, aktivera **Kredithantering** i arbetsytan **funktionshantering**. En av de nya funktionerna gör det möjligt att spärra försäljningsorder baserat på spärregler. Kreditchefen kan sedan frisläppa eller avvisa order efter vidare analys. Möjligheten att parkera försäljningsorder är dock inte tillämplig på Commerce-order, eftersom försäljningsorder ofta har en förskottsbetalning och **kredithantering** funktionen inte helt stöder scenarier för förskottsbetalning. 

Oavsett om **kredithantering** funktionen är aktiverad innehar inte försäljningsordern om ett kundsaldo går över kreditgränsen under uppfyllelsen av ordern. I stället genererar Commerce antingen ett varningsmeddelande eller ett felmeddelande, beroende på värdet för **meddelandet när kreditgränsen överskrids** på snabbflikarna **Kreditgränser**.

Egenskapen **Exkludera från kredithantering** som hindrar Commerce försäljningsorder från att stängas finns i försäljningsorderrubriken (**Butik och handel \> Kunder \> Alla försäljningsorder**). Om egenskapen har värdet **Ja** (standardvärdet) för Commerce-försäljningsorder exkluderas orderna från innehar arbetsflödet för kredithantering. Även om egenskapen kallas **Exkludera från kredithantering** används den definierade kreditgränsen fortfarande under uppfyllelse av ordern. Orderna går inte att innehar.

Möjligheten att spärra Commerce-försäljningsorder baserat på spärrningsregler planeras för framtida Commerce-versioner. Tills det stöds kan du, om du måste tvinga Commerce-försäljningsorder att gå igenom de nya kredithanteringsflödena, anpassa följande XML-filer i Visual Studio-lösningen. Ändra logiken i filerna så att **CredManExcludeSalesOrder**-flaggor ställs in på **Nej**. På det här sättet ställs egenskapen **Exkludera från kredithantering** som standard in på **Nej** för försäljningsorder om Commerce.

- RetailCreateCustomerOrderExtensions_CredMan_Extension.xml
- RetailCallCenterOrderExtensions_CredMan_Extension.xml

Om flaggorna **CredManExcludeSalesOrder** in på **Nej** och en B2B-kund kan köpa från butikerna genom att använda kassaprogrammet (POS), kan bokföringen av hämtköpstransaktioner misslyckas. Det finns till exempel en spärrregel för kontantbetalningstypen och B2B-kunden har köpt vissa artiklar i butiken med kontanter. I så fall faktureras inte den resulterande försäljningsordern eftersom den sätts i följd. Bokföringen misslyckas därför. Därför rekommenderar vi att du genomför tester från slutet till slut efter att du har implementerat den här anpassningen.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera en näthandelsplats för B2B](set-up-b2b-site.md)

[Hantera B2B-affärspartners med hjälp av kundhierarkier](partners-customer-hierarchies.md)

[Hantera affärspartneranvändare på näthandelsplatser för B2B](manage-b2b-users.md)

[Ange produktkvantitetsgränser för B2B-näthandelssajter](quantity-limits.md)

[Uppdateringar av SDK och modulbibliotek](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
