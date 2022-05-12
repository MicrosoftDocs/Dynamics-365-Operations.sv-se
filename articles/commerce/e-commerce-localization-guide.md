---
title: Dynamics 365 Commerce lokaliseringsguide för näthandel
description: I det här avsnittet beskrivs hur du lokaliserar en Microsoft Dynamics 365 Commerce näthandelsplats till flera språk och konfigurerar webbplatsen så att den stöder flera kanaler.
author: bicyclingfool
ms.date: 04/29/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1e9d91036ceeb9161dc8ee903532b2cf3ca435e2
ms.sourcegitcommit: 26c726bd0b00935e3d2c31fdc5a3b2ae03a8a2b0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2022
ms.locfileid: "8661533"
---
# <a name="dynamics-365-commerce-e-commerce-localization-guide"></a>Dynamics 365 Commerce lokaliseringsguide för näthandel

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lokaliserar en Microsoft Dynamics 365 Commerce e-handelsplats till fler språk och konfigurerar webbplats så att den stöder flera kanaler, samt omfattar begreppen och terminologin som hör till processen.

Funktionerna för e-handel i Dynamics 365 Commerce har utformats för att möjliggöra onlineerfarenheter som kan skräddarsys efter specifika länder och språk, men samtidigt tillåta maximal återanvändning av mallar, sidor, innehåll och media. Du kan också skapa en grundläggande webbplats och sedan expandera till nya marknader genom att lägga till stöd för fler länder och språk över tid.

## <a name="definitions"></a>Definitioner

**Språkvariant, språkvariant-ID**: En språkvariant (även kallad språkvariant-ID) definierar ett språk som är associerat med ett land eller en region. Till exempel är språkvariant-ID "fr-ca" associerad med kanadensiska franska.

**Basspråk**: Det språk som du utvecklar innehållet på webbplatsen på innan du exporterar det för lokalisering.

**Kanal, onlinebutik**: En kanal (även kallad onlinebutik) definierar betalningsmetoder, prisgrupper, produkthierarkier, sortiment och produkter för en e-handelsbutik online.

## <a name="concepts"></a>Begrepp

### <a name="url-driven-experience"></a>URL-driven erfarenhet

Dynamics 365 Commerce e-handelssidor ger unika marknadsförda och lokaliserade erfarenheter för kunder via kanaler och språkidentifierare. Kanaler definierar unika produkter, kategorier, valutor och betalningsmetoder för en marknad, och språkidentifierare avgör språket för innehållet som kunderna ser. På en e-handelsplats används URL-adresser för att skilja mellan marknadsförda och lokaliserade erfarenheter. Webbadresser för dessa unika kanal- och lokalupplevelser definieras för en webbplats på **Webbplatsinställningar \> Kanaler** i Dynamics 365 Commerce webbplatsskaparen.

I webbplatsskaparen är en URL en kombination av en domän och en sökväg som definierar startpunkten för en unik kombination av kanal och språk. I följande exempel definierar en fiktiv onlinebutik som kallas Fabrikam Inc. fyra unika kombinationer av en kanal och ett språk och mappar varje kombination till en unik URL som fyller innehållet för kunderna.

| Domän                     |  Sökväg      | Kanal       |   Nationella inställningar     |
|------------------------|--------|--------------------------------|--------|
| `https://fabrikam.com` | /      | Fabrikam utökar onlinebutik | sv-se  |
| `https://fabrikam.com` | /es    | Fabrikam utökar onlinebutik | es     |
| `https://fabrikam.ca`  | /      | Contoso onlinebutik    | fr-ca  |
| `https://fabrikam.ca`  | /en-ca | Contoso onlinebutik    | en-ca  |

#### <a name="domain"></a>Domän

Domäner upprättas när du ställer in din e-handelsplats i Microsoft Dynamics Lifecycle Services (LCS). När din e-handelsmiljö har öppnats kan du lägga till fler domäner genom att öppna en servicebegäran. För mer information om hur du konfigurerar domäner för din e-handelswebbplats, se [Domäner i Dynamics 365 Commerce](domains-commerce.md).

#### <a name="path"></a>Sökväg

- En sökväg är en godtycklig sträng som, tillsammans med domänen, kopplas till en unik kombination av kanal och språk. I föregående exempel matchar strängen som sökvägen används till det språk-ID som sökvägen kopplas till. Du kan emellertid använda ett annat sätt.
- En kombination av en kanal och ett språk kan mappas till en domän och en tom sökväg ("/"). I föregående exempel får kunder som besöker `https://fabrikam.ca/` produkter och sortiment för den kanadensiska marknaden i kanadensiska franska.
- Du kan inte skapa dubblettkombinationer av en domän och en sökväg genom att använda webbplatsverktyg för e-handel. Du kan emellertid mappa dubblettkombinationer för en kanal och ett språk till en annan kombination av en domän och en sökväg.

#### <a name="channel"></a>Kanal

- Kanaler (även kända som onlinebutiker) definierar betalningsmetoder, prisgrupper, produkthierarkier, sortiment och produkter för en e-handelsbutik online.
- Kanaler definieras, konfigureras och publiceras i Dynamics 365 Commerce administration.
- Webbplatsskaparen kan identifiera onlinebutiker som har konfigurerats i Commerce-administration och är tillgängliga för mappning till en webbplats.

Mer information om kanaler, se [Översikt över kanaler](channels-overview.md). Mer information om hur du ställer in en onlinekanal finns i [Ställa in en onlinekanal](channel-setup-online.md).

#### <a name="locale"></a>Nationella inställningar

- Detta är den verkliga identifieraren som används när du lämnar över XLIFF-filer (XML Localization Interchange File Format) för lokalisering. Språken definieras och publiceras för varje kanal i Commerce-administration. Information om hur du konfigurerar språk och kanaler i webbplatsskaparen finns i nästa avsnitt.
- Samma språk kan kopplas till flera kanaler. På det här sättet kan ett gemensamt språk ges på flera marknader.

## <a name="configure-languages-and-channels-for-your-e-commerce-site"></a>Konfigurera språk och kanaler för din e-handelsplats

Alla Dynamics 365 Commerce e-handelssajter är konfigurerade att använda en enda onlinekanal och ett enda språk, oavsett om du börjar med Fabrikams demosida eller skapar en ny webbplats från början.

I den här konfigurationen utvecklar kunder och partner vanligtvis alla tillgångar som ska användas mellan länder och språk. Dessa tillgångar inkluderar mallar, sidor, fragment, innehåll och media. Allt webbplatsinnehåll utvecklas på det första språket du valde för din webbplats, eller om du använder Fabrikams demosida kommer webbplatsinnehållet att utvecklas på engelska.

![Medföljande Dynamics 365 Commerce näthandelsplats](media/loc-guide-1.png)

> [!NOTE]
> Du kan konfigurera Fabrikam-demoplatsen för ytterligare ett språk så att innehållsutveckling kan göras på det språket. Information om hur du lägger till ett nytt språk på en webbplats och en kanal finns i avsnittet [Konfigurera ytterligare ett språk för webbplatsen](#configure-an-additional-language-for-your-site) längre fram i det här avsnittet.

Men innehållshanteringssystemet (CMS) och sidmodellen för Dynamics 365 Commerce e-handelsplatser har utformats för att möjliggöra expansion till nya marknader och språk. Därför kan du via en enskild e-handelsplats hantera tillgångarna för en onlinebutik som sträcker sig över flera marknader och språk.

![Dynamics 365 Commerce e-handelsplats som omfattar flera marknader och språk](media/loc-guide-2.png)

### <a name="configure-an-additional-language-for-your-site"></a>Konfigurera ett ytterligare språk för webbplatsen

Konfigureringsprocessen för ett nytt språk för en e-handelsplats har tre steg.

#### <a name="step-1-add-the-language-to-your-channel-online-store-in-commerce-headquarters"></a>Steg 1: Lägg till språket i din kanal (onlinebutik) i Commerce-administration

1. Gå till den kanal där du vill lägga till det nya språket i Commerce-administration. För att hitta listan över kanaler som du har konfigurerat i Commerce-administration, gå till **Butik och handel \> Kanaler \> Onlinebutiker**.
1. Öppna onlinebutiken som är mappad till din webbplats genom att välja värdet för dess **Butikskanal-ID**. Du kan verifiera onlinebutiken som är mappad till din webbplats genom att öppna **Kanaler** webbplatsinställningssida i Commerce-webbplatsbyggaren och titta på namnet på onlinebutiken i kolumnen **Kanaler**. 
1. På snabbfliken **Språk** väljer du **Lägg till**. I fältet **Språk**, välj kod för språkvariant för det nya språket. Välj sedan **Spara**.
1. Gå till **Butik och handel \> Butik och handel IT \> Distributionsschema** och kör jobbet **1070 kanalkonfiguration**. När jobbet har körts kan du gå vidare till steg 2 och lägga till språket i en kanal för webbplatsen i webbplatsskaparen.

![Snabbfliken Språk för en onlinebutik i Commerce-administration](media/loc-guide-3.png)

#### <a name="step-2-add-the-language-to-a-channel-in-site-builder"></a>Steg 2: Lägg till språket i en kanal i webbplatsskaparen

Om du vill lägga till ett språk i en kanal i webbplatsskaparen följer du stegen nedan.

1. Öppna din webbplats i Commerce-webbplatsbyggaren och öppna sedan sidan **Kanaler** i webbplatsinställningar.
1. Välj namnet på den kanal som du vill lägga till språket på.
1. Välj **Lägg till en språkvariant** i höger fönster.
1. I dialogrutan **Lägg till språkvariant** under **Lägg till språkvariant** välj språkvariant för språket som du tidigare lagt till i kanalen i Commerce-administration.
1. Välj domän och sökväg som kunderna vill begära att visa din webbplats i den här kanalen och på det här språket.
1. Om du vill att språket ska vara standardspråk för visning, skapande och uppdatering av webbplatsskaparens sidor och fragment markerar du kryssrutan **Använd som standardspråk för redigeringskanal**. 
    > [!NOTE]
    > Den här inställningen påverkar endast webbplatsskaparen. Det påverkar inte den publicerade webbplatserfarenheten för dina kunder.
1. Välj **OK**.
1. Välj **Spara och publicera**.

#### <a name="step-3-localize-your-site-content"></a>Steg 3: Lokalisera innehållet på webbplatsen

När du återgår till vyn **Sida** i Commerce webbplatsskaparen blir det nya språket tillgängligt i kanalen och språkväljaren i det övre högra hörnet. Du kan nu skapa lokaliserade versioner av sidorna på ditt basspråk.

Processen för att lokalisera innehållet på dina sidor och fragment behandlas i avsnittet [Lokalisera innehåll på näthandelsplatser](#localize-e-commerce-site-content) senare i detta ämne.

### <a name="configure-a-new-channel-for-your-site"></a>Konfigurera en ny kanal för webbplatsen

Dynamics 365 Commerce näthandelsplatser kan tjäna på erfarenheter som har definierats i flera onlinekanaler som är konfigurerade i Commerce-administration. En webbplats använder flera kanaler för att visa kunderna en unik konfiguration av betalningsmetoder, prisgrupper, produkthierarkier, sortiment och en uppsättning produkter. En kanal används vanligtvis för att konfigurera dimensionerna så att de passar de behov och inställningar som krävs för den erfarenhet som förknippas med enskilda länder. Det här är emellertid ett affärsbeslut som kunden fattar. Det är inget krav.

De förutsättningar och uppgifter som är associerade med att ställa in en kanal (onlinebutik) omfattas av dokumentet. Mer information om hur du ställer in en onlinekanal finns i Commerce-administration finns i [Grundläggande kanalinställningar](channels-overview.md#channel-setup-basics). Information om vilka steg och krav som gäller för onlinekanaler finns i [Ställa in en onlinekanal](channel-setup-online.md).

Om du vill lägga till en kanal till din webbplats i webbplatsskaparen följer du stegen nedan.

1. I Commerce-webbplatsbyggaren, gå till **Webbplatsinställningar \> Kanaler**. 
1. Välj **Lägg till en kanal**.
1. I dialogrutan **Lägg till en kanal**, under **Kanal** välj den kanal du vill lägga till. 
    > [!NOTE]
    > Du kan bara lägga till kanaler som inte redan har lagts till på webbplatsen.
1. Välj standardspråk för kanalen. Om du lägger till nya språk i kanalen kan du ändra standardspråket till ett av dem.
1. Ange domänen och sökvägen som ska utgöra URL-adressen som används för innehåll och erfarenheter i den här kombinationen av en kanal och ett språk.
1. Välj **OK**.
1. Välj **Spara och publicera**.

## <a name="localize-e-commerce-site-content"></a>Lokalisera innehållet på webbplatsen för e-handel

### <a name="xliff-basics"></a>XLIFF-grunder

XLIFF är ett filformat av branschstandard som används för att skicka lokaliserbart innehåll mellan verktyg för innehållshantering. Commerce-webbplatsbyggaren använder filformatet XLIFF för att exportera sida,fragment och bildmetadatainnehåll så att det kan lokaliseras och återimporteras.

Microsoft Dynamics kunderna arbetar vanligtvis med lokaliseringsleverantörer från tredje part, till exempel [Translated.com](https://translated.com/welcome) för att översätta sina XLIFF-filer till de språk de behöver.

### <a name="localize-assets-in-site-builder"></a>Lokalisera tillgångar i webbplatsskaparen

Följande tillgångar för näthandelsplats kan lokaliseras i webbplatsskaparen:

- Sidor
- Fragment
- Medietillgångar
- Moduler

Alla nya sidor, fragment och medietillgångar skapas i samband med kanalen och språket som för närvarande väljs i kanalen och i språkväljaren. Detta språk är vanligtvis ditt "basspråk", under förutsättning att du inte har konfigurerat fler språk eller kanaler. På webbplatser där flera kanaler och språk är konfigurerade, definieras "basspråket" av kanalen och språket du har angett som standard på sidan **Kanaler** i webbplatsinställningar.

Stegen för att lokalisera innehåll för sidor, fragment och medietillgångar liknar varandra. Undantag och skillnader kommer att påpekas i de avsnitt som följer. Stegen för att lokalisera modulinnehåll skiljer sig dock åt. Mer information finns i avsnittet [Lokalisera moduler](#localize-modules) senare i det här avsnittet.

#### <a name="step-1-export-an-xliff-file"></a>Steg 1: Exportera en XLIFF-fil

För att exportera en XLIFF-fil för en sida, ett fragment eller en bild i webbplatsskaparen följer du stegen nedan.

1. Öppna tillgången som du vill exportera grundspråksinnehåll för så att det kan lokaliseras.
1. I kommandofältet, välj **Lokalisering \> Exportera XLIFF**.
    > [!NOTE]
    > Alternativet **Lokalisering** visas bara när tillgången är i läget **Redigera**.

En XLIFF-fil med namnet **\<assetname\>.xlf** kommer att laddas ner till din webbläsares nedladdningsmapp. Denna XLIFF-fil är specifik för den tillgång du lokaliserar. Du exporterar en XLIFF-fil för varje tillgång som du vill lokalisera.

#### <a name="step-2-localize-the-xliff-file"></a>Steg 2: Lokalisera XLIFF-filen

I de flesta fall arbetar du med en lokaliseringsleverantör för att översätta dina XLIFF-filer. Om du lokaliserar tillgångar internt eller bara vill testa lokaliseringsprocessen måste du dock göra följande ändringar i en XLIFF-fil:

- Lägg till ett målspråksattribut i /xliff/fil elementet och ställ in värdet på det språkvariant-ID som du lokaliserar till. 
    > [!NOTE]
    > Detta språk-ID måste matcha språk-ID:t från sidan **Kanaler** i webbplatsinställningarna.
- Lägg till ett målelement för varje //källelement där textvärdet är den lokaliserade versionen av innehållet i källelementet.

Mer information om schemat som styr XLIFF-filer finns i [XLIFF 1.2 Specifikation](http://docs.oasis-open.org/xliff/xliff-core/xliff-core.html).

> [!NOTE]
> Om du vill lokalisera en tillgång till flera språk måste du skapa en lokaliserad XLIFF-fil för vart och ett av dessa språk.

#### <a name="step-3-import-the-localized-xliff-file"></a>Steg 3: Importera den lokaliserade XLIFF-filen

Följ de här stegen om du vill importera en XLIFF-fil för en tillgång.

1. Öppna den tillgång som du vill importera en XLIFF-fil för i Commerce-webbplatsbyggaren.
1. I kanal- och språkväljaren i det övre högra hörnet väljer du kanalen och språket som du importerar lokaliserat innehåll för.
1. I kommandofältet, välj **Lokalisering \> Importera XLIFF**. Bläddra sedan till och välj den lokaliserade XLIFF-filen för vald tillgång och språk.

När XLIFF-filen har importerats skapas en "variant" av sidan, fragmentet eller tillgången. Från och med den punkten kommer alla ändringar som görs i den lokaliserade varianten endast att påverka den varianten. De kommer inte att påverka den bastillgång som varianten härletts från. Ändringar av bastillgången påverkar heller inte tillgångens variant. 

Vad gäller sidor kan du dock göra ändringar mellan varianter genom att ändra den mall eller layout som dessa sidor är bundna till. Ändringar i ett fragment påverkar på samma sätt alla sidor som har ett beroende på den varianten.

### <a name="images"></a>Bilder

Bilder kan bara återges på en sida eller i en modulvariant om innehållsmetadata som hör till dessa bilder lokaliseras. För närvarande är följande metadata i en medietillgång localizable:

- Alternativ text
- Beskrivning
- Titel

För närvarande kan du inte lokalisera den binära för en digital tillgång, till exempel en bild eller en video. Produktgruppen Dynamics 365 Commerce arbetar just nu med den här kapaciteten.

### <a name="localize-modules"></a>Lokalisera moduler

Strängar som återges som en del av modulen (till exempel "Föregående" och "Nästa" i en modul) lokaliseras separat från modulinnehållet. Instruktioner finns i [Lokalisera en modul](e-commerce-extensibility/localize-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Ordlista för sidmodell](page-elements-overview.md)

[Aktivera delning mellan kanaler](cross-channel-sharing.md)

[Lokalisera en modul](e-commerce-extensibility/localize-module.md)

[Definitionsfil för modul](e-commerce-extensibility/module-definition-file.md)

[Lokalisera resurser för Commerce-tillägg och etikettfiler](dev-itpro/extension-resource-localization.md)

[Globalisera moduler med hjälp av klassen CultureInfoFormatter](e-commerce-extensibility/globalize-modules.md)

[Appinställningar: teman](e-commerce-extensibility/app-settings.md#themes-section)
