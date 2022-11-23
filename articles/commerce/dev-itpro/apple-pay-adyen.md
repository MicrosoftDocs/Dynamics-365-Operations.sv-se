---
title: Konfigurera Apple Pay med Adyen i Dynamics 365 Commerce
description: I den här artikeln beskrivs hur du konfigurerar Apple Pay med Adyen i Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: 0949b9d7a4b181605d43956932b4fc095940bd64
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780381"
---
# <a name="set-up-apple-pay-with-adyen-in-dynamics-365-commerce"></a>Konfigurera Apple Pay med Adyen i Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

I den här artikeln beskrivs hur du konfigurerar Apple Pay med Adyen i Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Nyckeltermer

| Villkor | Beskrivning |
|---|---|
| Apple Pay | Apple Pay, även kallat "Apple Pay-knappen", är ett erbjudande om digital plånbok som stöds av Adyen-anslutningsprogrammet. Funktionen möjliggör den kundupplevelse och -integrering som stöds av Microsoft Dynamics 365 Apple Pay-anslutningsprogrammet. |
| Plånbok | En betalningstyp som inte har traditionella betalningsegenskaper, såsom BIN (bankidentifieringnummer) och utgångsdatum, som används för att särskilja olika typer av kredit- och betalkort. |

Dynamics 365 Commerce erbjuder en färdig integrering för Apple Pay när gatewaytjänsten för Adyen-betalning används. Apple Pay är en digital plånboksmetod som använder ett Apple Pay-handlarkonto tillsammans med betaltjänsten Adyen. Efter konfigurering blir knappen Apple Pay en valbar betalningsmetod som ingår in en nätbutiks kassasida. Knappen Apple Pay visas bara som betalningsalternativ för de Apple Pay-enheter som stöds. När användarna väljer **Apple Pay** i en webbläsare eller enhet med stöd för detta vidarebefordras de till att utföra betalningen direkt med Apple Pay-tjänsten. De skickas sedan tillbaka till onlinebutiken för att slutföra ordern.

Referensen för anslutningsprogrammet för Dynamics 365-betalning för Apple Pay-anslutningsprogrammet görs utöver anslutningsprogrammet mellan Dynamics 365-betalning för Adyen för att aktivera Apple Pay och kreditkortsbetalningar på en webbplats. Apple Pay kan även konfigureras för användning i butiker där Adyen-betalningsterminaler använder Dynamics 365 betalningskoppling för Adyen med Commerce-kassan (POS). I det här fallet hanterar Dynamics 365 betalningskoppling för Adyen Apple-betalningsenheten via terminalen.

## <a name="prerequisites"></a>Förutsättningar

Ett Apple handelskonto krävs för att använda Apple Pay med Adyen i Commerce. Information om hur du ställer in Apple Pay i ditt testkundområde finns i [Apple Pay med Drop-in-integrering](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#set-up-apple-pay). Information om vad du ska göra när du är klar att börja bo i produktionsmiljön finns i [Publicera](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).

Betalningsmetoden Apple Pay måste också integreras med ditt Adyen-konto. Adyen kan hjälpa dig att ställa in betalningsmetoden och kan också hjälpa till att säkerställa att domänerna som du ska använda certifikatet för används tillsammans med certifikatet.

För att aktivera den förbättrade plånboksfunktionen flagga in Commerce headquarters, gå till **Arbetsytor \> Funktionshantering** och sök efter funktionen **Utökat stöd för plånbok och betalningsförbättringar**. Välj funktionen och välj sedan **aktivera**. När funktionen har aktiverats kör du distributionsplanen **1110** för att göra ändringen tillgänglig i alla kanaler.

## <a name="map-the-apple-pay-payment-method"></a>Mappa betalningsmetoden Apple Pay

Apple Pay är en digital plånboksmetod. Information om hur du konfigurerar betalningsmappning för Apple Pay finns i [stöd för digital plånbok](../wallets.md).

Följ dessa steg för att mappa Apple-betalningsmetoden i Commerce headquarters.

1. Gå till **Butik och handel \> Kanalinställning \> Betalningsmetoder \> Korttyper**.
1. Välj **Ny** för att lägga till en rad för Apple Pay och konfigurera följande värden:

    - **ID:** ApplePay
    - **Namn på elektronisk betalning:** Apple Pay
    - **Typ:** Plånbok
    - **Utfärdare:** Apple

1. Välj **Processormappning** för att öppna dialogrutan **Mappningsmetoder för processorbetalning**. Kolumnen **Betalningsmetoder med icke-mappade processorer** anger de betalningsmetoder som stöds för varje tillgänglig anslutning (Adyen, PayPal och Apple).
1. Mappa de betalningsmetoder som stöds som du vill ha för både anslutningsprogrammet **Dynamics 365 betalningskoppling för Adyen** (för användning i kassan) och anslutningsprogrammet **Dynamics 365 betalningskoppling för Apple Pay** (för användning i onlinekanaler).
1. På varje mappningsrad, i kolumnen **Betalningsmetoder med icke-mappade processorer** välj rad som stöds och välj sedan **Lägg till** för att flytta valen till kolumnen **Betalningsmetoder med mappad processor**.
1. Välj **OK** och sedan sidan **Korttyper** välj **Spara**.

## <a name="set-up-the-apple-pay-certificate-for-your-site"></a>Ställa in Apple Pay-certifikat för din webbplats

För varje webbplats måste du ladda upp domänens associeringsfil (även känd som Apple Pay-certifikatet) enligt beskrivningen i [Adyen Apple Pay-dokumentation](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live). Du kan använda Commerce-webbplatsbyggaren om du vill överföra domänens associeringsfil till mediebiblioteket för din webbplats.

Följ de här stegen om du vill konfigurera Apple Pay-certifikat i webbplatsskaparen.

1. Hämta certifikatet (domänens associeringsfil) från [Adyen](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).
1. Lägg till filnamnstillägget .txt i domänens associeringsfil.
1. I webbplatsverktyget [ladda upp](../upload-serve-static-files.md) domänens associeringsfil till webbplatsens mediebibliotek.
1. Gå till **URL**.
1. Välj **Nytt \> Ny URL**.
1. I dialogrutan **Ny URL** väljer du **Mediebibliotekstillgång**.
1. Ange URL-sökvägen i fältet **URL-sökväg** (om den inte redan har angetts). Efter URL-adressen för domänens bas ska du ange följande obligatoriska sträng: `<domain>/.well-known/apple-developer-merchantid-domain-association.txt`
1. Välj **Nästa**. Mediebiblioteket visar alla uppladdade medietillgångar tillhörande **dokument** (.txt)-typ.
1. Markera den domänens associeringsfil som ska betjänas för begäranden till den URL som du definierade tidigare.
1. Markera **Skapa**.

I det här läget har den URL som du skapade statusen "utkast". Publicera URL för att slutföra processen. Filen som URL:en pekar mot kommer inte att returneras förrän URL:en publiceras.

## <a name="configure-a-commerce-online-store-for-apple-pay"></a>Konfigurera en Commerce-näthandelsbutik för Apple Pay

Följ dessa steg om du vill konfigurera en Commerce-näthandelsbutik till att använda Apple Pay.

1. I Commerce headquarters går du till **Butik och handel \> Kanaler \> Näthandelsbutiker**.
1. Välj värde **Butikskanal-ID** av din webbplats onlinebutikskanal.
1. På snabbfliken **Betalningskonton** lägger du till **Dynamics 365 betalningskoppling för Adyen** om den inte redan är inställd, genom att följa instruktionerna i [Ställ in Dynamics 365 betalningskoppling för Adyen](adyen-connector-setup.md).
1. När Adyen-anslutningen har konfigurerats väljer du **Lägg till** för att lägga till **Dynamics 365 betalningskoppling för Apple Pay**.
1. Ange värden för kopplingsegenskaperna för handlare.

    | Egenskap               | Beskrivning | Obligatoriskt | Konfigureras automatiskt | Exempelvärde |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Namn på sammansättning          | Namnet på sammansättningen för anslutningsprogrammet för Dynamics 365-betalning för Apple Pay. | Ja | Ja | Binärt namn |
    | Tjänstkonto-ID     | Den unika identifieraren för inställning av egenskaper för återförsäljare. Denna identifierare trycks på betalningstransaktioner och identifierar de återförsäljaregenskaper som ska användas av processer längre fram (exempelvis fakturering). | Ja | Ja | Guid |
    | Handlarkonto-ID    | Ange den unika identifieraren för Adyen-återförsäljare. Det här värdet anges när du registrerar dig hos Adyen på det sätt som beskrivs i [Registrera dig hos Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Ja | Nej | MerchantIdentifier |
    | Moln-API-nyckel          | Ange PI-nyckeln för Adyen-molnet. Hämta den här nyckeln genom att följa instruktionerna i [Hur du hämtar API-nyckeln](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Ja | Nej | abcdefg |
    | Gatewaymiljö    | Ange miljö för Adyen-gateway som du ska mappa till. De möjliga värdena är **Test** och **Live**. Du bör endast ställa in det här fältet som **Live** för produktionsenheter och transaktioner. | Ja | Ja | Live |
    | Valutor som stöds   | Ange valutor som anslutningsprogrammet ska bearbeta. I scenarier med kort kan Adyen stödja ytterligare valutor via [Dynamisk valutakonvertering](https://www.adyen.com/pos-payments/dynamic-currency-conversion) efter att transaktionsförfrågan har skickats till betalningsterminalen. Kontakta Adyens support för att få en lista över vilka valutor som stöds. | Ja | Ja | USD;EUR |
    | Betalningsmedelstyper som stöds | Ange typer av betalningsmedel som anslutningsprogrammet ska bearbeta. | Ja | Ja | ApplePay |

1. När informationen om handlaren har angetts kör du jobbet för distributionsschema för **1070**-kanalskonfiguration .

## <a name="configure-commerce-pos-for-apple-pay"></a>Konfigurera Commerce-kassa för Apple Pay

Kassakonfigurationen använder konfiguration i maskinvaruprofilens **EFT-tjänst**-fält för anslutningsprogrammet för Dynamics 365-betalning för Adyen. I Commerce headquarters, konfigurera EFT-tjänsten för anslutningsprogrammet för Dynamics 365-betalning för Adyen som beskrivs i [Konfigurera ett avsnitt för hårdvaruprofil för Dynamics 365-kassa](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

Se till att du lägger till **ApplePay** listan över betalningsmedelstyper i fältet **Betalningsmedelstyper som stöds**. Använd semikolon (;) till separata typer av betalningsmedel i listan.

Processormappningen för Adyen-anslutningsprogrammet registrerar de korttyper som Apple Pay använder i kassaterminalen.

### <a name="configure-content-security-policies-in-site-builder"></a>Konfigurera säkerhetspolicy för innehåll i webbplatsskaparen

Innan du konfigurerar dina fragment eller sidor med Apple Pay måste du se till att webbplatsens säkerhetsprinciper (CSP) för innehåll är inställda i Commerce-webbplatsverktyget för din webbplats.

Följ de här stegen om du vill konfigurera säkerhetspolicyer för innehåll i webbplatsverktyget.

1. Gå till **Webbplatsinställningar \> Tillägg**.
1. På fliken **Säkerhetspolicy för innehåll**, välj **Lägg till** för att lägga till en rad som har `https://applepay.cdn-apple.com/jsapi/v1/apple-pay-sdk.js` till avsnitten **child-src**, **connect-src**, **frame-src**, **img-src**, **script-src** och **style-src**.
1. När du är klar väljer du **Spara och publicera** för att göra ändringarna.

### <a name="set-up-apple-pay-as-a-checkout-payment-option"></a>Ställa in kontantbetalning som ett alternativ för Apple Pay

Ställ in Apple Pay som ett utcheckningsbetalning alternativ på din webbplats (ej express) kassasida genom att följa dessa steg.

1. Välj **Fragment** i webbplatsverktyget och välj sedan webbplatsens kassafragment.
1. Välj **Redigera**.
1. På platsen **Behållare för kassaavsnitt** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **Apple Pay** och klicka sedan på **OK**.
1. Välj **Spara**.
1. Välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera det.

Inställningar för modulen **Apple Pay** är inbyggda i modulen och ansluter till den konfigurerade Dynamics 365 betalningskoppling för Apple Pay som är inställd för onlinekanalen i Commerce headquarters.

### <a name="apple-pay-payment-behavior"></a>Apple Pay betalningsbeteende

Knappen **Apple Pay** visas bara på de enheter för Apple Pay som stöds (iPhones, iPads och Safari webbläsare som stöder Apple Pay). Om en användare inte använder någon av dessa enheter är betalningsknappen **Apple Pay** dold.

När en användare väljer betalningsknappen **Apple Pay** visas dialogrutan **Apple Pay**. Där kan användaren autentisera mot sin Apple Pay-enhet eller webbläsare. Dialogrutan **Apple Pay** visar en sammanfattning av beställningsbeloppet och den betalningsmetod som användaren har konfigurerat mot sin Apple plånbok. Användaren kan granska dessa uppgifter och sedan välja **Betala** för att slutföra betalningen. När betalningen har slutförts skickas användaren till webbplatssidan **Slutför order** som innehåller en detaljerad ordersammanfattning för den slutförda transaktionen.

## <a name="additional-resources"></a>Ytterligare resurser

[Vanliga frågor om betalningar](payments-retail.md)

[Kassamodul](../add-checkout-module.md)

[Betalningsmodul](../payment-module.md)
