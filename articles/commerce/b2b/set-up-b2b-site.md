---
title: Konfigurera en B2B-näthandelssajt
description: I detta ämne beskrivs hur du ställer in en B2B-näthandelssajt ("business-to-business") i Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ac6f6511f4f96c00e10369329b2111a46f23d1a2
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035969"
---
# <a name="set-up-a-b2b-e-commerce-site"></a>Konfigurera en B2B-näthandelssajt

[!include [banner](../../includes/banner.md)]

näthandelssajter mellan företag (B2B) innehåller ett antal viktiga funktioner som optimerar arbetsflödet för en B2B-användare. I detta ämne beskrivs hur du ställer in en B2B-näthandelssajt ("business-to-business") i Microsoft Dynamics 365 Commerce. Ämnet avhandlar de moduler och webbplatsinställningar som måste konfigureras för att B2B-specifika scenarier ska kunna aktiveras.

## <a name="prerequisites"></a>Förutsättningar

- Om du vill ställa in en näthandelssajt för B2B måste du aktivera och konfigurera specifika funktioner i Commerce-administrationen enligt beskrivningen i det här avsnittet.
- Kärnerfarenheter, till exempel produktidentifiering, produktinformationssidor, kundvagnen och POS drivs av samma moduler som används för näthandelssajter för företag till konsument (B2C). Webbplatsutformare bör känna till alla moduler som Dynamics 365 Commerce stöder. Mer information finns i [Översikt över modulbibliotek](../starter-kit-overview.md).
- I det här avsnittet förutsätts det att webbplatsutformare förstår grunderna i webbplatsbyggare, mallar, fragment och sidor för Commerce, så att de kan aktivera B2B-funktionerna för näthandelssajter.

## <a name="site-level-settings"></a>Inställningar på webbplatsnivå

Du får åtkomst till inställningar på webbplatsnivå i webbplatsbyggaren på **Webbplatsinställningar \> Tillägg**. Följande två inställningar på webbplatsnivå gäller för B2B-scenarier:

- **Aktivera kundkontobetalningar** – Med denna egenskap kan användarna betala för order med hjälp av kundkonton. Tillgängliga värden är **Aktiverat för B2B-kunder**, **Aktiverat för B2C-kunder**, **Aktiverat för alla kunder** samt **Inaktiverat för alla kunder**. Om B2B-webbplatsen har stöd för kundkonton bör du välja **Aktiverat för B2C-kunder**.
- **Aktivera orderkvantitetsgränser** – Med den här egenskapen kan du ange gränser för antalet artiklar som kan beställas för respektive produkt eller kategori. Tillgängliga värden är **Aktiverat för B2B-kunder**, **Aktiverat för B2C-kunder**, **Aktiverat för alla kunder** samt **Inaktiverat för alla kunder**.

> [!NOTE]
> När du uppgraderar till den senaste versionen av modulbiblioteket måste du följa fler steg för att säkerställa att de webbplatsinställningar som beskrivs ovan är tillgängliga i din miljö. Mer information finns i [Uppdatera filen app.settings.json](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="create-business-partner-sign-up-pages"></a>Skapa inloggningssidor för affärspartner

Om användarna ska kunna bli affärspartner måste de först skicka in en begäran. En länk till din begärandesida för affärspartner finns på B2B-startsidan, så att användarna kan starta processen. När användarna har skickat en affärspartnerbegäran får de en bekräftelse på att förfrågningen har skickats. 

### <a name="create-a-business-partner-request-page"></a>Skapa en begärandesida för affärspartner

Modulen **Partnerregistrering** på en begärandesida för affärspartner används för att initiera användarförfrågningar om att bli affärspartners. I den här modulen kan du samla in den användarinformation som krävs för registreringsprocessen. Modulen **Adress för affärskonto** för att samla in användarens adress.

Följ de här stegen om du vill ställa in och konfigurera begärandesidan för affärspartner i webbplatsskaparen.

1. Skapa en mall som kallas **Registrering**. Denna mall bör innehålla följande moduler:

    - Partnerregistrering
    - Synlig sökväg
    - Siduvud
    - Sidfot
    - Innehållsblock
    - Textblock
    - Produktsamling

1. Använd mallen **Registrering** om du vill skapa en sida kallad **Affärspartnerbegäran**.
1. I posten för **Sidhuvud** anger du det rubrikfragment som förkonfigurerats med webbplatsens sidhuvud.
1. I posten för **Sidfot** anger du det sidfotsfragment som förkonfigurerats med webbplatsens sidfot.
1. I posten **Main** anger du en **Container**-modul. I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**.
1. I posten **Container** anger du en **Breadcrumb**-modul. Under **Länkar** i fönstret för modulegenskaper konfigurerar du en länk till startsidan och anger **Start** som länktext.
1. I posten **Container** lägger du till en **Partnerregistrering**-modul under modulen **Breadcrumb**. Under **Rubrik** i förnstret förmodulegenskaper anger du **Bli affärspartner**.
1. I posten **Partnerregistrering** lägger du till en **Adress för företagskonto**-modul.
1. I posten **Container** lägger du till en **Textblock**-modul under modulen **Partnerregistrering**. Här kan du definiera vissa villkor för registreringsprocessen.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.
1. Publicera sidans webbadress (URL).

### <a name="create-a-business-partner-request-confirmation-page"></a>Skapa en bekräftelsesida för affärspartnerbegäran

När en affärspartnersbegäran har skickats ska en bekräftelsesida visas för användaren som bekräftar överföringen. 

Följ de här stegen om du vill ställa in och konfigurera bekräftelsesidan i webbplatsskaparen.

1. Använd mallen **Registrering** som du skapade tidigare för att skapa en sida kallad **Bekräftelse för partnerbegäran**.
1. I posten för **Sidhuvud** anger du det rubrikfragment som förkonfigurerats med webbplatsens sidhuvud.
1. I posten för **Sidfot** anger du det sidfotsfragment som förkonfigurerats med webbplatsens sidfot.
1. I posten **Main** anger du en **Container**-modul. I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**.
1. I posten **Container** lägger du till en **Innehållsblock**-modul. Under **Rubrik** i modulens egenskapsfönster anger du **Begäran har skickats in**. I fältet **RTF** anger du **Din begäran har skickats in**. Under **Länkar** konfigurerar du en länk till startsidan och anger sedan **Fortsätt handla** som länktext.
1. Lägg till ytterligare en **Container**-modul och lägg sedan till en **Produktsamling**-modul till denna.
1. Konfigurera modulen **Produktsamling** med den rekommendation eller kategorilista som du vill visa på sidan.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.
1. Publicera sidans webbadress (URL).

Följ de här stegen om du vill lägga till en länk på bekräftelsesidan i webbplatsskaparen.

1. Gå till sidan **Begäran om affärspartner** som du skapade tidigare och välj **Redigera**. 
1. Välj modulplatsen **Partnerregistrering**. Under **Länk till bekräftelsesida för registrering** konfigurerar du länken till den begärandesida för affärspartner som du skapade tidigare. 
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

### <a name="add-a-business-partner-request-link-to-the-home-page"></a>Lägg till en begärandelänk för affärspartner på startsidan

När sidorna för registrering av begäran för affärspartner samt bekräftelse har skapats måste du göra registreringssidan tillgänglig via en länk på startsidan. Du kan utföra denna åtgärd genom att lägga till länken i valfri **Innehållsblock**-modul på startsidan.

Följ de här stegen om du vill lägga till en begärandelänk för affärspartner på startsidan i webbplatsskaparen.

1. Gå till startsidan för din webbplats och välj **Redigera**.
1. Välj en modulplats för **Innehållsblock**. Under **Länkar** i fönstret för modulegenskaper konfigurerar du en länk till den begärandesida för affärspartner som du skapade tidigare och anger **Registrera dig nu för att bli affärspartner** eller liknande som länktext. Lägg till en bild efter behov.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="account-management-landing-page"></a>Landningssidan Kontohantering

Landningssidan för kontohantering innehåller all kontohanteringsinformation som krävs för både B2B- och B2C-näthandelssajter. Endast inloggade användare kan visa den här sidan.

Följ de här stegen om du vill skapa och konfigurera en B2B-kontohanteringssida i webbplatsskaparen.

1. Skapa en mall som kallas **Kontohantering**. Denna mall bör innehålla följande moduler:

    - Siduvud
    - Sidfot
    - Synlig sökväg
    - Välkomstpanel för konto
    - Allmän panel för konto
    - Panel för kontoadress
    - Panel för kontots önskelista
    - Panel för kontoadress
    - Bonuspanel för konto
    - Saldopanel för kundkonto
    - Panel för kontots ordermallar
    - Organisationsanvändare
    - Lista för företagsorganisation
    - Saldo på kundkonto
    - Rader i ordermall
    - Ordermallista
    - Fakturapanel för konto
    - Fakturalista
    - Fakturadetaljer

1. Använd mallen **Kontohantering** om du vill skapa en sida kallad **Mitt konto**.
1. I posten för **Sidhuvud** anger du det rubrikfragment som förkonfigurerats med webbplatsens sidhuvud.
1. I posten för **Sidfot** anger du det sidfotsfragment som förkonfigurerats med webbplatsens sidfot.
1. I posten **Main** anger du en **Container**-modul. I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**. 
1. I posten **Container** anger du en **Breadcrumb**-modul. Under **Länkar** i fönstret för modulegenskaper konfigurerar du en länk till startsidan och anger **Start** som länktext.
1. I posten **Container** lägger du till en **Välkomstpanel**-modul. Under **Rubrik** i modulens egenskapsfönster anger du **Välkommen**.
1. I posten **Primärt** lägger du till ytterligare en **Container**-modul (**Container 2**). I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**. Ange värdet **Underordnade som visas** som **Två**. 
1. I posten **Container 2** lägger du till en **Allmän panel för konto**-modul. Under **Rubrik** i egenskapsfönstret för modulegenskaper anger du **Min profil**. Under **Länkar** konfigurerar du en länk till sidan **Min profil**. 
1. I posten **Container 2** lägger du till ytterligare en **Allmän panel för konto**-modul. Under **Rubrik** i fönstret för modulegenskaper anger du **Orderhistorik**. Under **Länkar** konfigurerar du en länk till sidan för orderhistorik.
1. I posten **Primärt** lägger du till ytterligare en **Container**-modul (**Container 3**). I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**. Ange värdet **Underordnade som visas** som **Två**. 
1. I posten **Container 3** lägger du till en **Adresspanel för konto**-modul. Under **Rubrik** i egenskapsfönstret för modul anger du **Min adress**. Under **Länkar** konfigurerar du en länk till sidan **Min adress**. 
1. I posten **Container 3** lägger du till en **Önskelistepanel för konto**-modul. Under **Rubrik** i egenskapsfönstret för modul anger du **Min önskelista**. Under **Länkar** konfigurerar du en länk till sidan **Min önskelista**.
1. I posten **Primärt** lägger du till ytterligare en **Container**-modul (**Container 4**). I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**. Ange värdet **Underordnade som visas** som **Två**. 
1. I posten **Container 4** lägger du till en **Organisationsanvändare**-modul. Under **Rubrik** i modulens egenskapsfönster anger du **Organisationsanvändare**. 
1. I posten **Container 4** lägger du till en **Kundsaldopanel för konto**-modul. Under **Rubrik** i fönstret för modulegenskaper anger du **Kontokredit**. 
1. I posten **Primärt** lägger du till ytterligare en **Container**-modul (**Container 5**). I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**. Ange värdet **Underordnade som visas** som **Två**. 
1. I posten **Behållare 5** lägger du till en **Ordermallpanel för konto**-modul. Under **Rubrik** i egenskapsfönstret för moduler anger du **Ordermallar**. 
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

> [!NOTE] 
> Vissa av avsnitten som du lagt till i steg 13 till 18 visas inte på arbetsytan "vad du ser är vad du får" (WYSIWIG) i webbplatsskaparen, detta eftersom de behöver ett inloggat B2B-konto.

## <a name="create-and-configure-customer-balance-pages-and-modules"></a>Skapa och konfigurera saldosidor och moduler för kunder 

Kundkonton kan användas för att betala för order. Tillgängligt saldo för ett kundkonto kan visas från en användares kontohanteringssida.

### <a name="create-a-customer-balance-page"></a>Skapa en kundsaldosida 

Innan inloggade B2B-användare kan visa sitt kundsaldo måste du skapa en kundsaldosida. 

Om du vill skapa en kundsaldosida i webbplatsskaparen följer du stegen nedan.

1. Använd mallen **Kontohantering** som du skapade tidigare för att skapa en sida med namnet **Kundsaldo**.
1. I posten för **Sidhuvud** anger du det rubrikfragment som förkonfigurerats med webbplatsens sidhuvud.
1. I posten för **Sidfot** anger du det sidfotsfragment som förkonfigurerats med webbplatsens sidfot.
1. I posten **Primärt** lägger du till ytterligare en **Container**-modul (**Container 3**). I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**. Ange värdet **Underordnade som visas** som **Två**.
1. I posten **Container** anger du en **Breadcrumb**-modul. Under **Länkar** i fönstret för modulegenskaper konfigurerar du en länk till startsidan för kontoadministreringen och anger **Mitt konto** som länktext.
1. I posten **Behållare** lägger du till en **Saldo för kundkonto**-modul. Under **Rubrik** i fönstret för modulegenskaper anger du **Kontosaldo**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.
1. Publicera sidans webbadress (URL).
1. Gå till den landningssida för kontohantering (**Mitt konto**) som du skapade tidigare.
1. I egenskapsfönstret för modulen **Saldopanel för kontokund** lägger du till en länk till kundens saldosida. 
1. Spara och publicera sidan.

Kundsaldosidan har nu skapats, och användarna kan komma åt den från landningssidan för kontohantering.

### <a name="configure-a-checkout-page-so-that-the-customer-balance-can-be-used-as-a-form-of-payment"></a>Konfigurera en kassasida så att kundsaldot kan användas som ett formulär för betalning

Modulen **Kundkontobetalning** krävs för att kundsaldot ska kunna användas som betalsätt. Denna modul modulen bör läggas till på kassasidan som ett betalsätt. Information om hur du konfigurerar en kassasida och de moduler som krävs för kassan, inklusive alla betalningsdetaljer, finns i [modulen Kassa](../add-checkout-module.md).

När du har konfigurerat en kassasida måste du lägga till modulen **Kundkontobetalning** i betalningsavsnittet och därefter spara samt publicera sidan. B2B-användare kan sedan logga in på näthandelssajten och använda sitt tillgängliga kundsaldon på order i POS.

På **Webbplatsskapare \> Tillägg** måste du dessutom säkerställa att egenskapen **Aktivera kundkontobetalningar** är inställt på **Aktiverat för B2B-kunder**.

## <a name="create-order-template-pages"></a>Skapa ordermallsidor

Två ordermallsidor kan ställas in för en B2B-näthandelssajt: en listsida för ordermall och en radsida för ordermall.

På en listsida för ordermall visas en lista över alla tillgängliga ordermallar. Du konfigurerar den genom att använda modulen **Lista för ordermall**. På listsidan för ordermallar kan du skapa eller ta bort en mall och lägga till artiklar i en mall i kundvagnen.

På en sida för en ordermallrad visas information om ordermallen som väljs på en listsida för ordermallar. Du konfigurerar den genom att använda modulen **Rad för ordermall**. När en användare väljer namnet på en mall på en listsida för ordermallar, visas ordermallens radsida och visar information om mallen. Användaren kan sedan visa och redigera artiklarna i mallen.

### <a name="create-an-order-templates-list-page"></a>Skapa en listsida för ordermallar

Om du vill skapa en listsida för ordermallar i webbplatsskaparen följer du stegen nedan.

1. Använd mallen **Kontohantering** som du skapade tidigare för att skapa en sida med namnet **Ordermallar**.
1. I posten för **Sidhuvud** anger du det rubrikfragment som förkonfigurerats med webbplatsens sidhuvud.
1. I posten för **Sidfot** anger du det sidfotsfragment som förkonfigurerats med webbplatsens sidfot.
1. I posten **Main** anger du en **Container**-modul. I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**.
1. I posten **Container** anger du en **Breadcrumb**-modul. Under **Länkar** i fönstret för modulegenskaper konfigurerar du en länk till startsidan för kontoadministreringen och anger **Mitt konto** som länktext.
1. I posten **Behållare** lägger du till en **Lista för ordermall**-modul.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.
1. Publicera sidans webbadress (URL).
1. Gå till den landningssida för kontohantering (**Mitt konto**) som du skapade tidigare.
1. I egenskapsfönstret för modulen **Kontopanel för ordermall**, under **Länkar**, konfigurerar du en länk till den listsida för ordermallar som du just skapade.
1. Spara och publicera sidan.

Ordermallsidan har nu skapats, och användarna kan komma åt den från landningssidan för kontohantering.

### <a name="create-an-order-template-lines-page"></a>Skapa en radsida för ordermallar

Om du vill skapa en radsida för ordermallar i webbplatsskaparen följer du stegen nedan.

1. Använd mallen **Kontohantering** som du skapade tidigare för att skapa en sida med namnet **Ordermallrader**.
1. I posten för **Sidhuvud** anger du det rubrikfragment som förkonfigurerats med webbplatsens sidhuvud.
1. I posten för **Sidfot** anger du det sidfotsfragment som förkonfigurerats med webbplatsens sidfot.
1. I posten **Main** anger du en **Container**-modul. I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**.
1. I posten **Container** anger du en **Breadcrumb**-modul. Under **Länkar** i fönstret för modulegenskaper konfigurerar du en länk till startsidan för kontoadministreringen och anger **Mitt konto** som länktext.
1. I posten **Behållare** lägger du till en **Ordermallrader**-modul.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.
1. Publicera sidans webbadress (URL).

## <a name="onboard-business-partner-users"></a>Registrera affärspartneranvändare

På sidan för organisationsanvändare kan administratören av en affärspartnerorganisation registrera fler användare från organisationen till B2B-näthandelssajten. Du konfigurerar denna genom att använda modulen **Lista för affärsorganisation**. Från sidan över organisationsanvändare kan en administratör lägga till eller ta bort användare, definiera kontosaldon samt begära utdrag för en användare.

Om du vill skapa en sida för organisationsanvändare i webbplatsskaparen följer du stegen nedan.

1. Användmallen **Kontohantering** som du skapade tidigare för att skapa en sida kallad **Organisationsanvändare**.
1. I posten för **Sidhuvud** anger du det rubrikfragment som förkonfigurerats med webbplatsens sidhuvud.
1. I posten för **Sidfot** anger du det sidfotsfragment som förkonfigurerats med webbplatsens sidfot.
1. I posten **Main** anger du en **Container**-modul. I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**.
1. I posten **Container** anger du en **Breadcrumb**-modul. Under **Länkar** i fönstret för modulegenskaper konfigurerar du en länk till startsidan för kontoadministreringen och anger **Mitt konto** som länktext.
1. I posten **Behållare** lägger du till en **Lista för affärsorganisation**-modul. Under **Rubrik** i modulens egenskapsfönster anger du **Organisationsanvändare**.
1. I egenskapsfönstret i modulen **Lista för affärsorganisation** aktiverar du egenskaperna **Registersortering** och **Registernumrering**. Ange numreringsantalet till **5**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.
1. Publicera sidans webbadress (URL).
1. Gå till den landningssida för kontohantering (**Mitt konto**) som du skapade tidigare.
1. I egenskapsfönstret för modulen **Användarpanel för organisation**, under **Länkar**, konfigurerar du en länk till den sida för organisationsanvändare som du just skapade. 
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="create-invoice-pages"></a>Skapa fakturasidor

En listsida för fakturor visar en lista med alla tillgängliga fakturor. Du konfigurerar den genom att använda modulen **InvoicesList**. Från listsidan med fakturor kan användarna betala av eller begära fakturor. 

På en detaljsida för fakturor visas information om den faktura som valts på en listsida för fakturor. Du konfigurerar den genom att använda modulen **Fakturadetaljer**. När en användare väljer ett faktura-ID på en listsida för en faktura, visas sidan med fakturainformation.

### <a name="create-an-invoices-list-page"></a>Skapa en listsida för fakturor

Om du vill skapa en listsida för fakturor i webbplatsskaparen följer du stegen nedan.

1. Använd mallen **Kontohantering** som du skapade tidigare för att skapa en sida med namnet **Fakturalista**.
1. I posten för **Sidhuvud** anger du det rubrikfragment som förkonfigurerats med webbplatsens sidhuvud.
1. I posten för **Sidfot** anger du det sidfotsfragment som förkonfigurerats med webbplatsens sidfot.
1. I posten **Main** anger du en **Container**-modul. I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**.
1. I posten **Container** anger du en **Breadcrumb**-modul. Under **Länkar** i fönstret för modulegenskaper konfigurerar du en länk till startsidan för kontoadministreringen och anger **Mitt konto** som länktext.
1. I posten **Behållare** lägger du till en **InvoicesList**-modul. Under **Rubrik** i egenskapsfönstret för moduler anger du **Fakturor**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.
1. Publicera sidans webbadress (URL).
1. Gå till den landningssida för kontohantering (**Mitt konto**) som du skapade tidigare.
1. I egenskapsfönstret för modulen **Kontopanel för fakturor**, under **Länkar**, konfigurerar du en länk till den listsida för fakturor som du just skapade. 
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

### <a name="create-an-invoice-details-page"></a>Skapa en fakturainformationssida

Om du vill skapa en fakturainformationssida i webbplatsskaparen följer du stegen nedan.

1. Använd mallen **Kontohantering** som du skapade tidigare för att skapa en sida med namnet **Fakturadetaljer**.
1. I posten för **Sidhuvud** anger du det rubrikfragment som förkonfigurerats med webbplatsens sidhuvud.
1. I posten för **Sidfot** anger du det sidfotsfragment som förkonfigurerats med webbplatsens sidfot.
1. I posten **Main** anger du en **Container**-modul. I modulens egenskapsfönster anger du värdet **Bredd** som **Fyll Container**.
1. I posten **Container** anger du en **Breadcrumb**-modul. Under **Länkar** i fönstret för modulegenskaper konfigurerar du en länk till startsidan för kontoadministreringen och anger **Mitt konto** som länktext. Konfigurera sedan en länk till listsidan för fakturor och ange **Fakturalistor** som länktext.
1. I posten **Behållare** lägger du till en **Fakturadetaljer**-modul.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.
1. Publicera sidans webbadress (URL).

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](../starter-kit-overview.md)

[Översikt över redigeringssidan](../authoring-home-overview.md)

[Översikt över mallar och layouter](../templates-layouts-overview.md)

[Arbeta med fragment](../work-with-fragments.md)

[Lägga till en ny webbplatssida](../add-new-page.md)

[Kassamodul](../add-checkout-module.md)

[Innehållsblockmodul](../add-hero-module.md)

[Produktsamling](../product-collection-module-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]