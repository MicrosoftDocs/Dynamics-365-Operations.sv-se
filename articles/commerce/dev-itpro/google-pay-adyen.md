---
title: Konfigurera Google Pay med Adyen
description: I den här artikeln beskrivs hur du konfigurerar Google Pay med Adyen i Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 07/05/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: cdf950fc7b3720543d93e108d4e3c3c2ab254e09
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838402"
---
# <a name="configure-google-pay-with-adyen"></a>Konfigurera Google Pay med Adyen

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du konfigurerar Google Pay med Adyen i Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce erbjuder en färdig integrering för Google Pay när gatewaytjänsten för Adyen-betalning används. Google Pay är en digital plånboksmetod som använder ett Google Pay-handlarkonto tillsammans med betaltjänsten Adyen. Efter konfigurering blir knappen Google Pay tillgänglig som en valbar betalningsmetod när du checkar ut en order online. När användarna väljer **Google Pay** i en webbläsare eller enhet med stöd för detta vidarebefordras de till att utföra betalningen direkt med Google Pay-tjänsten. De skickas sedan tillbaka till onlinebutiken för att slutföra ordern.

När Google Pay används med modulen för snabbkassa i Handel fylls användarens betalkontoinformation i automatiskt i kassaformuläret i syfte att hjälpa användaren ta sig igenom kassaprocessen snabbare. Handel omfattar en modul för snabbetalning som aktiverar snabbkassa. Modulen för expressbetalning kan användas i ett fragment som inkluderas på en kassa- eller kundvagnssida. Referensen för anslutningsprogrammet för Dynamics 365-betalning för Google Pay-anslutningsprogrammet görs utöver anslutningsprogrammet mellan Dynamics 365-betalning för Adyen, detta i syfte att möjliggöra både alternativet för snabbetalning och alternativet för standardkassa när PayPal har konfigurerats. Google Pay kan även konfigureras med Adyen-betalningsterminaler och Commerce-kassa (POS) för användning i butiken.

## <a name="key-terms"></a>Nyckeltermer

| Villkor | Beskrivning |
|---|---|
| Google Pay | Google Pay, även kallat "Google Pay-knappen", är ett erbjudande om digital plånbok som stöds av Adyen-anslutningsprogrammet. Funktionen möjliggör den kundupplevelse och -integrering som stöds av Dynamics-anslutningsprogrammet Google Pay. |
| Plånbok | En betalningstyp som inte har traditionella betalningsegenskaper, såsom BIN (Bank Identification Number) och utgångsdatum, som används för att särskilja olika typer av kredit- och betalkort. |
| Modul för expressbetalning | En Dynamics 365 Commerce-modul som stöder snabbare kassabeteende när betalningsmetoder som stöds används. |

## <a name="prerequisites"></a>Förutsättningar

För att du ska kunna använda Google Pay med Adyen i Commerce måste du ha ett konto för Google-återförsäljare. Mer information om hur du konfigurerar ditt konto för Google-återförsäljare finns i [dokumentationen för Adyen på Google Pay](https://docs.adyen.com/payment-methods/google-pay/) samt Googles [integreringschecklista](https://developers.google.com/pay/api/web/guides/test-and-deploy/integration-checklist).

Betalningsmetoden Google Pay måste också integreras med ditt Adyen-konto. Anvisningar om integreringslänk finns i [Adyen Google Pay](https://www.adyen.com/payment-methods/google-pay).

Du måste också aktivera den förbättrade betalningsfunktionen i Dynamics 365 Commerce headquarters. Gå till **Arbetsytor \> Funktionshantering**, sök efter funktionen **Förbättrat stöd för digital plånbok samt betalningsförbättringar**, välj funktionen och välj sedan **Aktivera**. När funktionen har aktiverats kör du distributionsplanen **1110** för att göra ändringen tillgänglig i alla kanaler.

## <a name="map-the-google-pay-payment-method"></a>Mappa betalningsmetoden Google Pay

Google Pay är en digital plånboksmetod. Information om hur du konfigurerar betalningsmappning för Google Pay finns i [stöd för digital plånbok](../wallets.md).

Följ stegen nedan för att mappa betalningsmetoden Google Pay till kortbetalningstyper för såväl kassa- som onlinekanaler.

1. I Commerce headquarters går du till **Butik och handel \> Kanalinställning \> Betalningsmetoder \> Korttyper**.
1. Välj **Ny** för att lägga till en rad för Google Pay.
1. I fältet **ID** anger du **Google Pay**.
1. I fältet **Namn för elektronisk betalning** anger du **Google Pay**.
1. I fältet **Typ** anger du **Plånbok**.
1. I fältet **Utfärdare** anger du **Google**.
1. I åtgärdsfönstret väljer du **Processormappning** för att öppna dialogrutan **Mappningsmetoder för processorbetalning**.
1. Under **Betalningsmetoder med icke-mappade processorer** visas en lista över betalningsmetoder med icke-mappade processorer, varav samtliga synkroniserats med lämpligt anslutningsprogram. Följ dessa steg om du vill mappa icke-mappade betalningsmetoder för Google Pay-processorer till kortinnehavartyper.

    1. Välj en typ av kortinnehavare under **Kortinnehavartyper**.
    1. I kolumnen **Betalningsmetoder med icke-mappad processor** väljer du både anslutningsprogrammet **Anslutningsprogram för Dynamics 365-betalning för Adyen** (för användning i kassan) och anslutningsprogrammet **Anslutningsprogram för Dynamics 365-betalning för Google Pay** (för användning i onlinekanaler).
    1. Markera **Lägg till**. Valen läggs till i kolumnen **Betalningsmetoder med mappad processor**.

1. När du är färdig med att mappa betalningsmetoder väljer du **Spara**.
1. På sidan **Korttyper** väljer du **Spara**.

## <a name="configure-a-commerce-online-store-for-google-pay"></a>Konfigurera en Commerce-näthandelsbutik för Google Pay

Följ dessa steg om du vill konfigurera en Commerce-näthandelsbutik till att använda Google Pay.

1. I Commerce headquarters går du till **Butik och handel \> Kanaler \> Näthandelsbutiker**.
1. Välj näthandelsbutikens kanal för din webbplats genom att välja kanalens värde för **Butikskanals-ID**.
1. På snabbfliken **Betalningskonton**, under **Anslutningsprogram**, bekräftar du att anslutningsprogrammet **Anslutningsprogram för Dynamics 365-betalning för Adyen** finns med i listan. Om det inte finns med i listan följer du instruktionerna i [Konfigurera anslutningsprogram för Dynamics 365-betalning för Adyen](adyen-connector-setup.md) för lägga till det.

    > [!NOTE]
    > I de flesta fall måste anslutningsprogrammet **Anslutningsprogram för Dynamics 365-betalning för Adyen** vara listat som det första anslutningsprogrammet för din kanal (det första anslutningsprogrammet kallas även det "primära" anslutningsprogrammet). Det måste sedan följas av andra anslutningsprogram som ska användas, till exempel **Anslutningsprogram för Dynamics 365-betalning för PayPal** och **Anslutningsprogram för Dynamics 365-betalning för Google Pay**.

1. När anslutningsprogrammet **Anslutningsprogram för Dynamics 365-betalning för Adyen** har lagts till väljer du **Lägg till** för att lägga till anslutningsprogrammet **Anslutningsprogrammet för Dynamics 365-betalning för Google Play**. Konfigurera sedan följande egenskaper för anslutningsprogrammet.

    | Fält                  | Beskrivning | Obligatoriskt | Konfigureras automatiskt | Exempelvärde |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Namn på sammansättning          | Namnet på sammansättningen för anslutningsprogrammet för Dynamics 365-betalning för Google Pay. | Ja | Ja | *Binärt namn* |
    | Tjänstkonto-ID     | Den unika identifieraren för inställning av egenskaper för återförsäljare. Denna identifierare trycks på betalningstransaktioner och identifierar de återförsäljaregenskaper som ska användas av processer längre fram (exempelvis fakturering). | Ja | Ja | *GUID* |
    | ID för Google-återförsäljare     | Ange det ID för Google-återförsäljare som har tilldelats ditt konto för Google-återförsäljare. Den här egenskapen krävs för produktionsmiljöer, men är valfri för testmiljöer. Mer information finns på <https://pay.google.com/>. | Ja | Nej | *Numerisk identifierare* |
    | Handlarkonto-ID    | Ange den unika identifieraren för Adyen-återförsäljare. Det här värdet anges när du registrerar dig hos Adyen på det sätt som beskrivs i [Registrera dig hos Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Ja | Nej | *Identifierare för återförsäljare* |
    | Moln-API-nyckel          | Ange PI-nyckeln för Adyen-molnet. Hämta den här nyckeln genom att följa instruktionerna i [Hur du hämtar API-nyckeln](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Ja | Nej | "abcdefg" |
    | Gatewaymiljö    | Den miljö för Adyen-gateway som du ska mappa till. De möjliga värdena är **Test** och **Live**. Du bör endast ställa in det här fältet som **Live** för produktionsenheter och transaktioner. | Ja | Ja | "Live" |
    | Valutor som stöds   | De valutor som anslutningsprogrammet ska bearbeta. I scenarier med kort kan Adyen stödja ytterligare valutor via [Dynamisk valutakonvertering](https://www.adyen.com/pos-payments/dynamic-currency-conversion) efter att transaktionsförfrågan har skickats till betalningsterminalen. Kontakta Adyens support för att få en lista över vilka valutor som stöds. | Ja | Ja | "USD;EUR" |
    | Betalningsmedelstyper som stöds | De typer av betalningsmedel som anslutningsprogrammet ska bearbeta. | Ja | Ja | "GooglePay" |

1. När du har avslutat konfigureringen av egenskaperna för anslutningsprogrammet kör du tidsplansjobbet **1070 (Kanalkonfiguration**) för distribution.


### <a name="use-the-payment-express-module-with-google-pay"></a>Använd expressmodulen för betalning med Google Pay

Commerce-modulen för expressbetalning fungerar med de betalningsmetoder som stöds så att webbplatskunder kan välja att checka ut snabbare genom att använda sin kontoinformation för betalningstjänst under kassaprocessen. Modulen för expressbetalning refererar till den konfigurerade knappen för anslutningsprogram och returnerar användarifylld orderinformation (adress, kontaktinformation och betalningsmetod) för att förifylla kassaformuläret.

När modulen för expressbetalning används med Google Pay: Om kunder väljer knappen Google Pay i avsnittet **Expressbetalning** öppnas iframe-fönstret Google Pay. Användaren kan sedan logga sedan in på sitt Google-konto för att använda kontots leveransadress, faktureringsadress, e-postadress och Google Pay-betalningsmetod för att betala för transaktionen.

När användare slutför åtgärden i Google Pay-fönstret skickas de tillbaka till kassasidan för Commerce-webbplatsen, där kassaformuläret förifylls med personuppgifterna för deras Google Pay-konto. När användarna återvänder till kassasidan från Google Pay-fönstret visas följande information:

- I expressbetalningsflödet kommer det första leveransalternativet som är tillgängligt för leveransadressen som returnerades att förväljas för kunden.
- När Google Pay används returneras ingen e-postadress till någon kontakt. Användare av gästkassor måste ange en e-postadress i kontaktavsnittet på kassasidan. Inloggade användare få automatiskt sina kontaktdata ifyllda från kundkontot i Dynamics (den primära e-postadress som de använde för autentisering).

Kunderna har sedan möjlighet att granska order och ändra detaljer i kassaordern innan de väljer **Beställ** för att slutföra ordern.

### <a name="configure-google-pay-in-site-builder"></a>Konfigurera Google Pay i webbplatsverktyget 

Innan du konfigurerar dina fragment eller sidor med Google Pay måste du se till att webbplatsens säkerhetsprinciper för innehåll är inställda i Commerce-webbplatsverktyget.

Följ de här stegen om du vill vara säker på att din säkerhetspolicy för innehålla har ställts in i webbplatsverktyget.

1. På din webbplats går du till **Webbplatsinställningar \> Tillägg**.
1. På fliken **Säkerhetspolicy för innehåll** lägger du till en rad för `*.google.com` i direktiven **child-src**, **connect-src**, **frame-ancestors**, **frame-src**, **img-src**, **script-src** samt **style-src**.
1. Välj **Spara och publicera alla** när du är färdig.

### <a name="configure-the-payment-express-fragment-with-google-pay-in-site-builder"></a>Konfigurera fragmentet för expressbetalning med Google Pay i webbplatsverktyget

Följ dessa steg om du vill ställa in fragmentet för expressbetalning med Google Pay för onlinebutiken.

1. I webbplatsverktyget går du till **Fragment**.
1. Välj **Ny**.
1. I dialogrutan **Nytt fragment** väljer du modulen **Behållare**, anger ett fragmentnamn (till exempel **Snabbkassa**) och väljer sedan **OK**. 
1. Välj det nya fragmentets plats för **Standardbehållare**.
1. I fönstret för egenskaper till höger anger du egenskaperna för behållarmodulen:

    - **Rubrik** – Ange en rubrik som ska visas för snabbkasseavsnittet för din webbplats (till exempel **Snabbkassa**).
    - **Behållarlayout** – välj **Flöde**.
    - **Bredd** – Välj **Fyll behållare**.
    - **Underordnade visas** – Välj **Tre** om du vill ange det antal underordnade som ska få plats på en enskild rad i snabbkasseavsnittet på kassasidan (till exempel en textruta, snabbetalning för PayPal och snabbetalning för Google Pay).
    - **CSS-klassnamn** – Ange **msc-express-payment-container** (obligatoriskt).

    > [!IMPORTANT]
    > - Värdet för **CSS-klassnamn** måste vara inställt på **msc-express-payment-container** för att kontrollera behållarens beteende i kassan. Det här beteendet inkluderar att dölja, komprimera och andra åtgärder som gäller för snabbkasseavsnittet i kassaflödet. Klassen **msc-express-payment-container** fungerar tillsammans med de standardåtgärder som frisläpps med kassamodulen för modulbibliotek.
    > - Andra utföranden kan inkluderas mot **CSS-klassnamnet**. Om du anpassar modulens beteende kan du korskontrollerna designkontrollerna om du använder samma modulbibliotekskodade beteende i kassamodulen för snabbkasseåtgärder.

1. I facket **Standardbehållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Expressbetalning** och klicka sedan på **OK**.
1. I egenskapsrutan för modulen **Snabbetalning** anger eller justerar du värdet för **Höjd på iFrame** i pixlar (till exempel **60**).
1. I fältet **Betalningsmedelstyper som stöds** anger du **Google Pay**. Värdet måste matcha strängen **Betalningsmedelstyper som stöds** i det anslutningsprogram som konfigurerats för kanalen (enligt beskrivningen i avsnittet [Konfigurera en Commerce-onlinebutik för Google Pay](#configure-a-commerce-online-store-for-google-pay) tidigare i den här artikeln).

    > [!NOTE]
    > Du kan upprepa steg 6 till och med 9 om du vill lägga till moduler för **Snabbetalning** för andra betalningsmetoder. Justera värdet **Betalningsmedel som stöds** med de ytterligare konfigurerade betalningstyperna (till exempel **Paypal**).

1. Valfritt: Du kan lägga till en textblocksmodul i standardmodulen för behållare om du vill ta med instruktioner eller sekretessinformation. När du har lagt till modulen anger du önskad text i fältet **RTF-format** i egenskapsfönstret. Du kan placera texten ovanför eller under modulerna för snabbetalning genom att välja ellipsen (**...**) på platsen för **textblock** och sedan välja **Flytta upp** eller **Flytta ned**.
1. Välj **Spara** för att spara dina ändringar, och välj sedan **Avsluta redigering**.
1. Välj **publicera** om du vill publicera fragmentet.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Lägga till expressbetalningsfragment på kassasidan

För att lägga till ett fragment för snabbetalning på kassasidan följer du dessa steg.

1. Välj **Sidor** i webbplatsverktyget och välj sedan webbplatsens kassasida.
1. Välj **Redigera**.
1. På **Huvudplatsen** väljer du ellipsen (**...**) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I fönstret för egenskaper till höger anger du egenskaperna för behållarmodulen:

    - **Behållarens layout** – välj **Staplad**.
    - **Bredd** – Välj **Fyll behållare**.
    - **Underordnade visas** – Välj **Tre** om du vill ange det antal underordnade som ska få plats på en enskild rad i snabbkasseavsnittet på kassasidan (till exempel en textruta, snabbetalning för PayPal och snabbetalning för Google Pay).

1. I modulplatsen **Behållare** väljer du ellipsen (**...**) och sedan **Lägg till fragment**.
1. I dialogrutan **Välj ett fragment** letar du rätt på och väljer snabbetalningsfragmentet som du skapade tidigare och väljer sedan **OK**.
1. Välj **Spara** för att spara dina ändringar, och välj sedan **Avsluta redigering**.
1. Välj **Publicera** om du vill publicera sidan.

> [!NOTE]
> Om kassasidan redan innehåller en behållare som har kassafragmentet och du vill att modulen för snabbetalning ska visas ovanför den normala kassabehållaren, kan du placera den ovanför eller under den befintliga kassan genom att välja ellipsen **(...)** på **Huvudplatsen** och sedan välja **Flytta upp** eller **Flytta ned**.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Lägga till expressbetalningsfragment på kundvagnssidan

För att lägga till ett fragment för snabbetalning på kundvagnssidan följer du dessa steg.

1. Välj **Sidor** i webbplatsverktyget och välj sedan webbplatsens kundvagnssida.
2. Välj **Redigera**.
3. I översiktvyn expanderar du **Huvudplats** i trädvyn och letar sedan reda på den behållare som innehåller modulen **Kundvagn**.
4. I modulen **Kundvagn** väljer du platsen **Snabbetalning** väljer ellipsen (**...**) och sedan **Lägg till modul**.
5. I dialogrutan **Välj moduler**, välj modulen **Expressbetalning** och klicka sedan på **OK**.
6. Välj modulplatsen **Snabbetalning**. Under **Betalningsmedel som stöds** anger du **GooglePay** i egenskapsfönstret till höger. Värdet måste matcha strängen **Betalningsmedel som stöds** i det anslutningsprogram som konfigurerades för kanalen (enligt beskrivningen i avsnittet [Konfigurera en Commerce-onlinebutik för Google Pay](#configure-a-commerce-online-store-for-google-pay) tidigare i den här artikeln).
1. Välj **Spara** för att spara dina ändringar, och välj sedan **Avsluta redigering**.
1. Välj **Publicera** om du vill publicera sidan.

Användarna kan inkludera upp till tre **Snabbetalning**-moduler som stöds (med andra ord tre tillgängliga betalningsalternativ som stöds) i kundvagnens **Snabbetalning**-plats.

### <a name="set-up-google-pay-as-an-option-in-the-checkout-payment-section"></a>Konfigurera Google Pay som ett alternativ i avsnittet för kassabetalning

Du kan endast konfigurera Google Pay som ett alternativ i kassabetalningsavsnittet för funktioner av typen "endast betalning, ej snabbetalning". Kassaformuläret fylls i av användaren och sidan för Google Pay-betalning kommer endast att förbereda kassan för betalning via Google Pay. Ingen Google-kontoinformation används för att skriva över de ifyllda kassauppgifterna.

> [!NOTE]
> I följande procedur förutsätts det att din webbplats använder ett kassafragment som konfigurerats med upphämtningsinformation, en leveransadress, leveransalternativ, kontaktinformation, valfria allmänna villkor och ett avsnitt för kassaelement. Standardmodulbibliotekets kassamodul släpps med en kassaavsnittsbehållare som har textblock, förmånspoäng, presentkort och betalningsmoduler. Mer information finns i [Betalningsmodul](../payment-module.md).

Ställ in Google Pay som ett vanligt betalningsalternativ i avsnittet **Betalningsmetod** på kassasidan genom att följa stegen nedan.

1. Välj **Fragment** i webbplatsverktyget och välj sedan webbplatsens kassafragment.
1. Välj **Redigera**.
1. På platsen **Kassainformation** väljer du ellipsen (**...**) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler** väljer du modulen **Betalning** och sedan **OK**.
1. I egenskapsfönstret för modulen **Betalning** till höger anger du egenskaperna för behållarmodulen:

    - **Rubrik** – Ange en rubrik som ska visas för snabbkasseavsnittet för din webbplats (till exempel **Google Pay**).
    - **Höjd på iFrame** – Ändra värdet till önskad designhöjd i pixlar (till exempel **75**). 
    - **Betalningsmedel som stöds** – Ange **Google Pay** i syfte att matcha konfigurationen för anslutningsprogrammet för Google Pay i Commerce Headquarters.
    - **Är primär betalning** – Lämna kryssrutan avmarkerad. (Den här egenskapen är normalt aktiverad för kassamodulen för Adyen.)
    - **Åsidosättning av betalsätt** – Den här egenskapen stöds inte för konfiguration av Google Pay.
    - **Använd ID för anslutningsprogram** – Den här egenskapen måste vara vald om flera anslutningsprogram för betalning används på sidan.

1. Du kan placera modulen ovanför eller under andra betalningsmoduler genom att välja ellipsen (**...**) på platsen för **Betalning** och sedan välja **Flytta upp** eller **Flytta ned**.
1. Välj **Spara** för att spara dina ändringar, och välj sedan **Avsluta redigering**.
1. Markera **Publicera**.

### <a name="modes-of-delivery"></a>Leveranssätt

Med modulen för snabbetalning som använder Google Pay kommer det första leveransalternativet som returneras mot den leveransadress som valts för Google Pay-kontot att förifyllas. Användare har möjlighet att justera leveransadressen till ett annat alternativ om de vill.

Den ordning i vilken leveranssätten visas i modulen för snabbetalning konfigureras på kanalens sida för **Leveranssätt** i Commerce Headquarters. I Commerce headquarters går du till **Butik och handel \> Kanaler \> Nätbutiker** och väljer värdet **Butikskanal-ID** för din butik. På fliken **Inställningar** i åtgärdsfältet väljer du **Leveranssätt**. Leveranssätten i listan visas i samma ordning i modulen för snabbetalning. Om du vill lägga till eller ta bort leveranssätt för en butikskanal eller produkt väljer du **Hantera leveranssätt** i åtgärdsfönstret. Mer information om hur du konfigurerar leveranssätt finns i [Konfigurera leveranssätt](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Kassamodulen använder också modulen för leveransalternativ när leveranssätt återges i kassan. Mer information finns i [Modul för leveransalternativ](../delivery-options-module.md).

Leveranssätt visas när de läggs till i listan **Leveranssätt** i onlinebutiken.

## <a name="configure-commerce-pos-for-google-pay"></a>Konfigurera Commerce-kassa för Google Pay

Kassakonfigurationen använder inställningen i maskinvaruprofilens **EFT-tjänst**-fält för anslutningsprogrammet för Dynamics 365-betalning för Adyen. Information om hur du konfigurerar EFT-tjänsten (Electronic Funds Transfer) för anslutningsprogrammet för Dynamics 365-betalning för Adyen i Commerce headquarters finns i [Konfigurera ett avsnitt för hårdvaruprofil för Dynamics 365-kassa](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

Processormappningen för Adyen-anslutningsprogrammet registrerar de korttyper som Google Pay använder i kassaterminalen.

## <a name="additional-resources"></a>Ytterligare resurser

[Vanliga frågor om betalningar](payments-retail.md)

[Kassamodul](../add-checkout-module.md)

[Betalningsmodul](../payment-module.md)
