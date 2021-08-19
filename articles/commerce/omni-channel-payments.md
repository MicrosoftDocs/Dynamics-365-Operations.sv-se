---
title: Översikt över betalningar i flera kanaler
description: Det här ämnet innehåller en översikt betalningar i flera kanaler i Dynamics 365 Commerce.
author: rubendel
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom:
- "141393"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: AX 8.1.3
ms.openlocfilehash: 11198795ebc09acd740546e0b18260e8ea2ddfc1dcc2ff38feafecc220655f1f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743417"
---
# <a name="omni-channel-payments-overview"></a>Översikt över betalningar i flera kanaler

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller en översikt betalningar i flera kanaler i Dynamics 365 Commerce. Den innehåller en omfattande lista över scenarier som stöds, information om funktioner, inställningar och fel sökning samt beskrivningar av några vanliga problem.

## <a name="key-terms"></a>Nyckeltermer

| Villkor | Beskrivning |
|---|---|
| Token  | En sträng med data som en betalningsprocessor tillhandahåller som referens. Token kan motsvara betalningskortnummer, betalningsauktoriseringar och tidigare betalningsregistreringar. Token är viktiga eftersom de bidrar till att hålla känslig information utanför kassasystemet. De kallas ibland även för *referenser*. |
| Korttoken | Ett token som en betalningsprocessor tillhandahåller för lagring i kassasystemet. En korttoken kan bara användas av den handlare som tar emot det. Korttoken kallas ibland även för *kortreferenser*. |
| Autentiseringstoken (auth) | Ett unikt ID som en betalningsprocess ger som en del av svaret som den skickar till ett kassasystem när en auktoriseringsbegäran utförts av kassasystemet. Du kan använda en autentiseringstoken senare om behandlaren anropas för att utföra åtgärder som att återföra eller annullera auktoriseringen. Den används emellertid oftast för att samla in pengar när en order är uppfylld eller om en transaktion har slutförts. Autoriseringstoken kallas ibland även för *Autoriseringsreferenser*. |
| Insamlingstoken | En referens som en betalningsbehandlare använder för ett kassasystem när en betalning har slutförts eller registrerats. Insamlingstoken kan sedan användas för att referera till betalningsinsamlad i efterföljande operationer, t.ex. återbetalningsbegär. | 
| Kortet är inte tillgängligt | En term som refererar till betalningstransaktioner där ett fysiskt kort inte visas. Dessa transaktioner kan till exempel inträffa i scenarier med näthandel eller kundtjänst. För dessa transaktioner anges den betalningsrelaterade informationen manuellt på en näthandelssajt, i ett kundtjänstflöde, eller i POS eller i betalningsterminalen. |
| Kortet är tillgängligt | En term som refererar till betalningstransaktioner där ett fysiskt kort presenteras och används på en betalningsterminal som är ansluten till Microsoft Dynamics 365 kassasystemet. |

## <a name="overview"></a>Översikt

Vanligtvis beskriver termen *betalningar i flera kanaler* möjligheten att skapa en order i en kanal och utföra den i en annan kanal. Den nyckel som har stöd för betalningar i flera kanaler bevarar betalningsdetaljer tillsammans med resten av orderdetaljerna och använder sedan dessa betalningsdetaljer när ordern återkallas eller bearbetas i en annan kanal. Ett klassiskt exempel är scenariot "Köp online, hämta i butiken". I det här scenariot läggs betalningsdetaljerna till när ordern skapas online. De återkallas sedan i POS för att debitera kundens betalningskort vid tidpunkten för upphämtningen. 

Alla scenarier som beskrivs i det här avsnittet kan implementeras med hjälp av standard-SDK (Software Development Kit) som medföljer Commerce. [Dynamics 365 betalningsanslutning för Adyen](/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3) innehåller en färdig implementering av alla scenarier som beskrivs här. 

### <a name="prerequisites"></a>Förutsättningar

Alla scenarier som beskrivs i det här avsnittet kräver en betalningsanslutning betalningar i flera kanaler. Det går också att använda den färdiga Adyen-anslutningen eftersom den stöder scenarier som görs tillgängliga via SDK för betalningar. Mer information om hur du implementerar betalningsanslutningar och om Retail SDK i allmänhet finns på [startsidan för Retail för IT-proffs och utvecklare](/dynamics365/unified-operations/retail/dev-itpro/dev-retail-home-page#payment-connectors).

#### <a name="supported-versions"></a>Versioner som stöds

Betalningar i flera kanaler som beskrivs i det här avsnittet har getts ut som en del av Microsoft Dynamics 365 for Retail version 8.1.3. 

#### <a name="card-present-and-card-not-present-connectors"></a>Anslutningar "Kortet är tillgängligt" och "kortet är tillgängligt"

Betalnings-SDK bygger på två uppsättningar API (application programming interfaces). en första uppsättningen med API:er **iPaymentProcessor**. Det används för att implementera "Kortet är tillgängligt" betalningsanslutningar om kan användas i samtalsgrupper och med Microsoft Dynamics näthandelsplattformen. För mer information om gränssnittet **iPaymentProcessor**, se [Implementera en betalningsanslutningar och betalningsenhet](https://download.microsoft.com/download/e/2/7/e2735c65-1e66-4b8d-8a3c-e6ef3a319137/The%20Guide%20to%20Implementing%20Payment%20Connector%20and%20Payment%20Device_update.pdf) vitbok, som täcker betalningar. 

Den första uppsättningen med API:er **iNamedRequestHandler**. Den stöder implementering av "Kortet är tillgängligt" betalningsintegration som använder en betalningsterminal. Fär mer information om gränssnittet **iNamedRequestHandler** se [skapa en betalningsintegration för en betalningsterminal](/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension). 

### <a name="setup-and-configuration"></a>Installation och konfiguration

Följande komponenter och inställningssteg krävs:

- **eCommerce-integration** : en integration med Commerce krävs för att stödja scenarier där en order kommer från en onlinebutik. Mer information om Retail E-commerce SDK finns i [SKD (Software Development Kit) för näthandelsplattform](/dynamics365/unified-operations/retail/dev-itpro/ecommerce-platform-sdk). I en demomiljö har referensbutiken stöd för betalningsscenarier i flera kanaler. 
- **Konfiguration av onlinebetalningar:** inställningarna för onlinekanal måste inkludera en betalningsanslutning som har uppdaterats för att stödja betalningar i flera kanaler. Alternativt kan den färdiga betalningssndlutningen användas. Information om hur du konfigurerar Adyen för betalningsanslutning för onlinebutiker finns i [Adyen betalningsanslutning](/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3#e-commerce) Förutom de inställningssteg för näthandel som beskrivs i det avsnittet, måste parametern **Tillåt att spara betalningsinformation i näthandel** anges till **Sant** i inställningarna för Adyen-anslutningen. 
- **Konfiguration av betalningar i flera kanaler** I backoffice, gå till **Butik och handel \> Administrationsinställning \> Parametrar \> Gemensamma handelsparametrar**. sedan på fliken **Betalningar i flera kanaler** anger du alternativet **Använd betalningar i flera kanaler** till **Ja**. I Commerce versioner 10.0.12 och senare finns den här inställningen på arbetsytan **funktionshantering**. Välj funktionen **Betalningar i flera kanaler** och klicka på **Aktivera nu**. 
- **Betalningstjänster:** Kundtjänst använder standardbetalningsanslutningen på sidan **betalningstjänster** för att bearbeta betalningar. Om du vill stödja scenarier som t.ex. "Köp i kundtjänst, hämta i butik" måste den här standardbetalningsanslutningen vara Adyen betalningsanslutning eller en betalningsanslutning som uppfyller implementeringskraven för betalningar i flera kanaler.
- **EFT-tjänst** : betalningar via en betalningsterminal måste ställas in på snabbfliken **EFT** i maskinvaruprofilen. Adyen-anslutaren stöder färdiga scenarier för betalningar i flera kanaler. Andra betalningsanslutningar som stöder **iNamedRequestHandler**-gränssnittet kan även användas om de stöder betalningar i flera kanaler.
- **Tillgänglighet för betalningsanslutning:** när en order återkallas, inkluderar betalningsmedelsraderna som återkallas tillsammans med ordernamnet på betalningsanslutningen som användes för att skapa de auktoriseringar som är associerade med ordern. När ordern är uppfylld försöker betalnings-SDK använda samma anslutnnig som du använde när du skapade den ursprungliga auktoriseringen. Därför måste en betalningsanslutning med samma handelsegenskaper finnas tillgänglig för insamling. 
- **Korttyper:** för att scenarier ska fungera ordentligt måste varje kanal ha samma inställningar för betalningsmedelstyper som kan användas för flera kanaler. Dessa inställningar inkluderar betalningsmetod-ID:n och korttyp-ID:n. Om t.ex. **kortets** betalningsmedeltyp har ID **2** i inställningen för onlinebutik, ska det ha samma ID i butiksinställningarna. Samma krav gäller för kort typs-ID:n. Om kortnummer **12** är inställt på **VISA** i onlinebutiken ska samma ID ställas in för butiken. 
- Retail Modern POS för Windows eller Android med inbyggd maskinvarustation -eller-
- Modern POS för iOS eller Cloud POS med ansluten delad maskinvarustation. 

### <a name="basic-principle-supporting-omni-channel-payments"></a>Grundläggande princip som stöder betalningar i felra kanaler

Betalningsanslutningar och betalningsbehandlare använder token eller referenser för att referera till interaktioner som är relaterade till kortbetalningar. När t.ex. en betalningsauktorisering begärs ges en referens till denna auktorisering. Därför kan auktoriseringen refereras senare när fonder registreras vid tiden för uppfyllandet. Denna auktorisering är unik för handlaren, betalningsanslutning och processorn. 

Om en order som har skapats online hämtas i butiken, måste samma betalningsinformation för ordern återkallas och användas. När den ursprungliga informationen tillhandahålls som en del av begäran att fånga en betalning mot den ursprungliga auktorisationen, kan betalnings behandlaren hantera begäran och samla in betalningen. 

Om du vill referera till din onlinebeställning korrekt, måste du också ha ett "kort som inte är tillgängligt" som stöder samma processor. På detta sätt kan kassasystemet ha en processor för "kort är tillgängligt"-betalningar, men den kan också ha tillgång till andra betalningsanslutningar så att den kan uppfylla order som skapas i andra kanaler genom att använda olika betalningsprocessorer. 

## <a name="supported-scenarios"></a>Stödda scenarier

Följande scenarier för betalning i flera kanaler stöds:

- Köp online och hämta i butiken
- Köp i kundtjänst och hämta i butiken
- Köp i butik A och hämta i butik B
- Köp i butik A, leverera till kund

    > [!NOTE]
    > Betalningar som görs i kundtjänst och som är kopplade till betalningsfunktionen "normal" måste markeras som **Förskottsbetala** = **Ja** för att återspeglas i det belopp som ska förfalla vid återanrop av ordern i POS. Ej förskottsbetala betalningar av typen normal identifieras inte när ordern återkallas i POS. 

Variationer av dessa scenarier stöds också. En onlinebeställning kan till exempel inkludera både rader som ska levereras till kunden och de rader som ska hämtas i butiken. Alla alternativ för orderuppfyllelse stöds via betalningar i flera kanaler. 

I följande avsnitt beskrivs stegen för varje scenario och hur du kör scenariot med hjälp av demodata. 

### <a name="buy-online-pick-up-in-store"></a>Köp online och hämta i butiken

Innan du börjar måste du se till att följande förutsättningar är på plats:

- Du har en referensbutik där Adyen-anslutning har konfigurerats.
- Alternativet **Betalningar i flera kanaler** på sidan **Gemensamma handelsparametrar** är inställt på **Sant**. I senare versioner flyttas den här inställningen till arbetsytan **funktionshantering** där du kan välja funktionen **Betalningar i flera kanaler** och klicka på **Aktivera nu**. 
- Adyen-betalnings anslutnng har konfigurerats för Houston kassaregistret.
- Retail Modern POS för Windows eller Android med inbyggd maskinvarustation -eller-
- Modern POS för iOS eller Cloud POS med ansluten delad maskinvarustation. 

Följ dessa steg om du vill köra scenariet:

1. I en referensbutik skapar du en order för upphämtning i butik. Du måste välja butiken **Houston**. 
2. Gå igenom kassastegen och betala genom att använda ett testkreditkortsnummer. Du hittar testkreditkortsnummer på sidan [sidan Adyen testkreditkortsnummer](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description).
3. I Commerce använder du batchjobbet **Synkronisera order** och distributionsschema **P-001** för att skapa order i backoffice.
4. I POS på välkomstsidan väljer du åtgärden **order som ska hämtas** för att visa order för upphämtning i butik. 
5. Välj en eller flera rader från ordern som skapades i referensbutiken och **hämta**.

    Ordern hämtas från backoffice. 

6. När detaljerna för orderraderna hämtas från backoffice och en kortbetalning som kan användas för flera kanaler identifieras, informeras du om att ett betalsätt finns tillgänglig.
7. Välj **Använd den tillgängliga betalsättet** om du vill slutföra transaktionen med hjälp av kortinformationen som angavs i referensbutiken.

    Orderraderna läses in på transaktionssidan och förfallet saldo är 0 (noll). 

8. Välj fliken **betalningar** om du vill visa den betalningsmedelsrad som hämtades från online-ordern. 
9. Välj valfri betalningsmetod för att slutföra transaktionen. 

### <a name="buy-in-call-center-pick-up-in-store"></a>Köp i kundtjänst och hämta i butiken

1. I Commerce, på sidan **Kundtjänst** anger du **Karen Berg** i sökfältet och väljer sedan **Sök**. 
3. Välj **Karen Berg** i sökresultaten.
4. När Karen har lästs in till sidan **kundtjänst** väljer du **Ny försäljningsorder**.
5. På sidan ny försäljningsorder väljer du **rubrik** för att visa orderrubriken. 
6. På sidan **order rubrik** ställer du in webbplatsen till **central** och lagerstället till **Houston**.
7. På fliken **leverera** ställer du in **leveransmetod** till **60** för kundupphämtning.
8. Markera **rader** och lägg till en eller flera rader i ordern. 
9. Välj **Slutför** om du vill ange flödet för slutförande av order.
10. Bläddra ned till betalningssektionerna väljer du **Lägg** och välj sedan och där betalningsmetodtypen anges **Kortet**. 
11. Välj plus tecknet (**+**) om du vill lägga till en kortbetalning. 
12. Ange information om ett testkreditkortsnummer som du hittar på sidan [Adyen-testkreditkortsnummer](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description) och välj **OK**.

    > [!NOTE]
    > Om kortnumret som du angav skiljer sig från varumärket som valdes när betalningen initierades, kommer betalningen att gå igenom ändå. Den kommer dock att bokföras på konton som är kopplade till det kortmärke som du markerade i steg 10.

12. Klicka på **OK** igen för att stänga dialogrutan **Slutförande av order, betalningar**.
13. På sidan **Sammanfattning försäljningsorder** väljer du **skicka**.
14. I POS på välkomstsidan väljer du åtgärden **order som ska hämtas** för att visa order för upphämtning i butik. 
15. Välj en eller flera rader från ordern som skapades i referensbutiken och **hämta**.

    Ordern hämtas från backoffice. 

16. När detaljerna för orderraderna hämtas från backoffice och en kortbetalning som kan användas för flera kanaler identifieras, informeras du om att ett betalsätt finns tillgänglig.
17. Välj **Använd den tillgängliga betalsättet** om du vill slutföra transaktionen med hjälp av kortinformationen som angavs i referensbutiken.

    Orderraderna läses in på transaktionssidan och förfallet saldo är 0 (noll).

18. Välj fliken **betalningar** om du vill visa den betalningsmedelsrad som hämtades från online-ordern. 
19. Välj valfri betalningsmetod för att slutföra transaktionen. 

### <a name="buy-in-store-a-pick-up-in-store-b"></a>Köp i butik A och hämta i butik B

1. Starta POS för Houston-butiken.
2. På sidan **transaktion** lägger du till Karen Berg till transaktionen med hjälp av det numeriska tangentbordet för **2001**.
3. Lägg till en eller flera rader till transaktionen.
4. Välj **order** om du vill visa orderalternativen.
5. Välj **Hämta alla** och välj sedan när du uppmanas **kundorder**.
6. Ange **Seattle** i sökfältet och välj sedan butiken i **Stockholm** för upphämtning. 
7. Välj **OK** om du vill acceptera aktuellt datum som datum för upphämtningen.
9. Välj **Betalningskort** för att initiera betalningen.
10. Betalningsmedel kortbetalning för det belopp som förfaller till insättning. 
11. Slutför insättningsbetalningen på betalningsterminalen. 
12. När insättningen har betalats väljer du alternativet att använda samma kort för uppfyllelse och väntar på att ordern ska slutföras. 
13. Starta POS för Seattle-butiken.
14. I POS på välkomstsidan väljer du åtgärden **order som ska hämtas** för att visa order för upphämtning i butik. 
15. Välj en eller flera rader från ordern som skapades i referensbutiken och **hämta**.

    Ordern hämtas från backoffice. 

16. När detaljerna för orderraderna hämtas från backoffice och en kortbetalning som kan användas för flera kanaler identifieras, informeras du om att ett betalsätt finns tillgänglig.
17. Välj **Använd den tillgängliga betalsättet** om du vill slutföra transaktionen med hjälp av kortinformationen som angavs i referensbutiken.

    Orderraderna läses in på transaktionssidan och förfallet saldo är 0 (noll).

18. Välj fliken **betalningar** om du vill visa den betalningsmedelsrad som hämtades från online-ordern. 
19. Välj valfri betalningsmetod för att slutföra transaktionen. 

### <a name="buy-in-store-a-ship-to-customer"></a>Köp i butik A, leverera till kund

1. Starta POS för Houston-butiken.
2. På sidan **transaktion** lägger du till Karen Berg till transaktionen med hjälp av det numeriska tangentbordet för **2001**.
3. Lägg till en eller flera rader till transaktionen.
4. Välj **order** om du vill visa orderalternativen.
5. Välj **leverera alla** och välj sedan när du uppmanas **kundorder**.
6. På sidan för leveransmetod, välj **Standard på natten** och välj sedan **OK** för att acceptera dagens datum som leveransdatum. 
7. Välj **OK** om du vill acceptera aktuellt datum som datum för upphämtningen.
8. Välj **Betalningskort** för att initiera betalningen.
9. Betalningsmedel kortbetalning för det belopp som förfaller till insättning. 
10. Slutför insättningsbetalningen på betalningsterminalen. 
11. När insättningen har betalats väljer du alternativet att använda samma kort för uppfyllelse och väntar på att ordern ska slutföras.

När ordern plockas, förpackas och faktureras i backoffice kommer betalningsdetaljerna som finns i POS att användas för att samla in medel för de varor som levereras till kunden. 

## <a name="scenario-details"></a>Scenario-information

Förutom de grundläggande scenarier som just har beskrivits har flera förbättringar gjorts i betalnings-SDK:n för att stödja betalningar i flera kanaler. 

### <a name="pos"></a>Kassa

#### <a name="single-swipedip-for-customer-orders"></a>Enstaka dragningar för kundorder

Innan funktionen för betalning i flera kanaler implementerades, när kundorder som har inkluderat insättningar skapats i POS, behövde kunderna dra sina kort två gånger: en gång för att betala insättningen och en gång för att tokenisera kortet för efterföljande orderuppfyllelse. När funktionen för tokenisering av flera kanaler är aktiverad, måste kunden bara dra kortet en gång för att både betala insättningen och auktorisera beloppet som förfaller till betalning senare. Vid tiden för uppfyllandet registreras de godkända medlen. Innan funktionen för tokenisering av flera kanaler har implementerats skapas bara token för återkommande kort för efterföljande orderuppfyllelse. Därför var medlen för det väntande uppfyllandet inte tillåtet och eftersom dessa medel inte hölls för det aktuella inköpet var det sannolikt att de kunde samlas in senare.

> [!NOTE]
> Enkel dragning stöds inte i Retail versionen 8.1.3. Kundorder i version 8.1.3 använder samma flöde som användes innan funktionen för tokenisering av flera kanaler implementerades. 

### <a name="cards-that-cant-issue-recurring-card-tokens"></a>Kort som inte kan skicka token för återkommande kort

Vissa kort kan inte användas för betalningar i flera kanaler eftersom de inte har stöd för att utfärda token för återkommande kort. När en order skapas i POS och insättningen betalas med hjälp av ett kort som inte stöder token för återkommande kort, används föregående korttokeniseringsflöde. Därför måste en kund som vill ge en betalning som ska användas för efterföljande order uppvisa ett annat kort. Om det andra kortet inte stöder token för återkommande kort kommer tokeniseringsåtgärden att nekas och kassören uppmanas att be kunden att ange ett annat kort. 

### <a name="using-a-different-card"></a>Använda ett annat kort

En kund som kommer till butiken för orderupphämtning har möjlighet att använda ett annat kort. När kassören får uppmaningen **Använd tillgänglig betalningsmetod** i samband med att ordern hämtas kan kassören fråga om kunden vill använda samma kort. Om kunden har förlorat kortet som användes för att skapa ordern och vill betala för ordern genom att använda ett annat kort, kan kassören välja **Använd en annan betalningsmetod**. Om kunden kommer tillbaka senare för att hämta fler artiklar för samma order, och det ursprungliga kortets auktorisering fortfarande är giltigt, kan kassören åter fråga om kunden vill använda det kortet.

### <a name="invalid-authorizations"></a>Ogiltiga auktoriseringar

Om det kort som användes för att skapa en order inte längre är giltigt kommer begäran att misslyckas när du väljer produkter för upphämtning. Kassabetalningsanslutningen kommer sedan att försöka skapa en ny auktorisering och samla in med samma kortinformation. Om den nya auktoriseringen eller insamlingen misslyckas blir kassören informerad om att betalningen inte kunde behandlas. Kassören måste sedan få en ny betalning från kunden. 

### <a name="multiple-available-payments"></a>Flera tillgängliga betalningar

När en order som har flera betalningsmedel och flera rader hämtas, tar kassören först emot **Använd tillgängli betalningsmetod**. Om det finns flera kort, när kassören väljer **Använd tillgängli betalningsmetod**, registreras befintliga betalningsmedel för kortet tills saldot uppfylls för de varor som för närvarande hämtas. Kassören har inte möjlighet att välja det kort som ska användas för varorna som hämtas. 

## <a name="related-topics"></a>Relaterade ämnen

- [Vanliga frågor om betalningar](/dynamics365/unified-operations/retail/dev-itpro/payments-retail)
- [Dynamics 365-betalningskoppling för Adyen](/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3)
- [Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö](./cpe-bopis.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]