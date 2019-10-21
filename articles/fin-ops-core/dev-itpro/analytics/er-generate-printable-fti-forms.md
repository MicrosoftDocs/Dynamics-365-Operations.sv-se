---
title: Framställ utskrivbara FTI-formulär
description: I det här avsnittet beskrivs hur du använder ramverket för elektronisk rapportering (ER) för att skapa utskrivbara fritextfakturaformulär (FTI) som Microsoft Office-dokument.
author: NickSelin
manager: AnnBe
ms.date: 07/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 731b6a61bd78388f3db0a7007478e3a5e9629a49
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181437"
---
# <a name="generate-printable-fti-forms"></a>Skapa utskrivbara FTI-formulär

[!include[banner](../includes/banner.md)]

Ramverket för elektronisk rapportering (ER) låter dig skapa utskrivbara fritextfakturaformulär (FTI) som Microsoft Office-dokument. Det här avsnittet innehåller information om hur du skapar egna konfigurationer, samt information om tillgängliga konfigurationsmallar.

## <a name="overview"></a>Översikt

Förutom den redan befintliga möjligheten att skapa utskrivbara formulär genom att använda Microsoft SQL Server Server Reporting Services (SSRS) kan du nu också använda ER-ramverket. Du kan hantera utskrivbara FTI-formulär i Microsoft Office Excel och Word. Du kan också ändra layout, dataflöde och formatering för att uppfylla särskilda krav utan att göra ändringar i koden.

> [!NOTE]
> Om du vill börja med en översikt över befintliga ER-konfigurationer för det här exemplet på en utskrivbar FTI-formulärslösning, kan du gå direkt till avsnittet **Hämta exempel på ER-konfigurationer i syfte att skapa utskrivbara FTI-formulär** senare i det här avsnittet.

## <a name="create-customized-configurations-for-fti-printable-forms"></a>Skapa anpassade konfigurationer för utskrivbara FTI-formulär
Som en del av en anpassad lösning för utskrivbara FTI-formulär måste du skapa en uppsättning ER-konfigurationer.

### <a name="configure-the-er-data-model"></a>Konfigurera ER-datamodellen
Programmet måste innehålla den ER-datamodellkonfiguration som innehåller en datamodell som beskriver företagsdomänen för kundfakturering. Som ett krav måste vara namnet på datamodellen vara **Kundfakturering**. För information om hur du utformar ER-datamodeller, se [Designa en domänspecifik datamodell för elektronisk rapportering (ER)](tasks/er-design-domain-specific-data-model-2016-11.md).

### <a name="configure-the-er-model-mapping"></a>Konfigurera mappningen för ER-datamodellen
Ditt program måste innehålla ER-modellmappningen för datamodellen Kundfakturering. Modellmappningen kan vara antingen ER-datamodellkonfigurationen eller konfigurationen för ER-modellmappningen. Namnet på modellmappningens rotbeskrivning måste emellertid vara **Fritextfaktura**.

Mappningen måste innehålla följande datakällor:

- Typ av datakälla: **Tabellposter**

    - Den här datakällan måste heta **KundfakturaJour**.
    - Den måste referera till programtabellen KundFakturaJour.
    - Den används vid körning i syfte att skicka en lista över fakturor som har markerats för utskrift från programmet till ER-modellmappningen.

- Typ av datakälla: **Objekt**

    - Den här datakällan måste heta **UtskrHantUtskriInstInfo**.
    - Den måste referera till programklassen **UtskrHantUtskriInstInfo**.
    - Den används vid körning för att skicka mappningsinformation om inställningarna för utskriftshantering för det ER-format som körs från programmet till ER-modellen.

Information om programintegration med ER-ramverket finns i klassen **ERUtskrHantRapportformatPrenumerant** (integreringsmodellen för ER-programsviten) i programmets källkod.

För mer information om utformningen av ER-modellmappningarna, se [Definiera modellmappning och välj datakällor för elektronisk rapporter (ER)](tasks/er-define-model-mapping-select-data-sources-2016-11.md).

### <a name="configure-the-er-format"></a>Konfigurera ER-formatet
I din programinstans behöver du den ER-formatkonfiguration som ska användas för att generera FTI-formulär. 

> [!NOTE]
> Denna formatkonfiguration måste skapas för datamodellen Kundfakturering och måste använda den modellmappning som har rotbeskrivningen **Fritextfaktura**.

Information om hur du konfigurerar-ER format finns i [Skapa en formatkonfiguration för elektronisk rapportering (ER)](tasks/er-format-configuration-2016-11.md). Information om hur du utformar ER-format för att skapa rapporter i OpenXML-format finns i [Designa en konfiguration för att generera rapporter i OpenXML-format för elektronisk rapportering (ER)](tasks/er-design-reports-openxml-2016-11.md).

## <a name="configure-print-management"></a>Konfigurera utskriftshantering
Om du vill generera FTI-formulär genom att använda ER-ramverket kan du tilldela ER-format på samma sätt som du tilldelar SSRS-rapporter. Om du vill associera ER_format med samtliga FTI för kundreskontra, gå till **Kundreskontra** \> **Inställningar** \> **Formulär** \> **Formulärinställningar** \> **Allmänt** \> **Utskriftshantering** \> **Fritextfaktura** \> **Original**. Följ dessa steg om du vill koppla ER-formatet till en viss kund eller faktura.

1. Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.
2. Välj den FTI som du vill associera med formatet ER och öppna sidan **Inställningar för utskriftshantering**.
3. Välj den dokumentnivå som ska specificera räckvidden av fakturor för bearbetning.
4. Välj ER-format för den angivna dokumentnivån.

![Skriv ut hanteringsinställningar](media/FTIbyGER-PMSetting.png)

> [!NOTE]
> Endast ER-format som använder rotbeskrivningen **Fritextfaktura** med datamodellen **Kundfaktura** syns i fältet **Sökning av rapportformat** för valt format.

## <a name="generate-fti-forms"></a>Generera FTI-formulär
FTI-formulär skapas i ER-ramverket på samma sätt som SSRS-rapporter.

Om du vill skapa FTI-formulär väljer du fakturor genom antingen intervall eller markering. 

![Fakturaval](media/FTIbyGER-InvoiceSelection.png)

![Fakturagranskning](media/FTIbyGER-InvoiceExcelPreview.png)

När du använder ER-format för att skriva ut FTI-formulär på det här sättet används förvalda ER-fildestinationer. Du kan inte ändra destinationen. Mer information om hur du konfigurerar ER-destinationer för ER-format finns i [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md).

Du kan även generera FTI-formulär när du bokför en FTI genom att aktivera **Skriv ut faktura**och avaktivera **Använd destinationer för utskriftshantering**.

> [!NOTE]
> När du använder ER-format för att skriva ut FTI-formulär på det här sättet används förvalda ER-fildestinationer. Du kan ändra standardmålet vid körning om målet redan har konfigurerats. Du måste ha följande säkerhetsprivilegier för att ändra målet:
>
> - **Namn:** ERFormatDestinationKörningBehåll
> - **Etikett:** Behåll formatmål för elektronisk rapportering vid körning

![Destination för elektronisk rapportering](media/FTIbyGER-ERFileDestinationSetting.png)

![Formatmål för elektronisk rapportering](media/FTIbyGER-ERFileDestinationUsage.png)

ER-ramverket stöder för närvarande följande mål för skapade dokument:

- **Hämtad fil** – Skapade formulär görs tillgängliga som hämtningar som du kan spara via webbläsaren.
- **Skärm** – Microsoft Office 365 Excel används för att förhandsgranska skapade FTI-formulär i Excel-format.
- **SharePoint-mapp** – Skapade formulär lagras baserat på inställningarna för ramverket för dokumenthantering.
- **Programarkiv** – Skapade formulär lagras om bilagor till poster med körningsloggar i Microsoft Azure-lagringen.
- **E-post** – Skapade formulär skickas som e-postbilagor.

> [!NOTE]
> Du kan inte skicka de FTI-formulär som skapas direkt till skrivaren, detta eftersom direkt utskrift som använder flödesagenten för Dynamics- skrivare inte stöds för närvarande.

## <a name="download-sample-er-configurations-to-generate-printable-fti-forms"></a>Hämta exempel på ER-konfigurationer för att skapa utskrivbara FTI-formulär
Du kan hämta exempel på ER-konfigurationer och använda dessa som mall för din FTI-lösning. Konfigurationerna lagras i det delade resursbiblioteket i Microsoft Dynamics Lifecycle Services (LCS). Konfigurationerna inkluderar:

- Konfigurationen **Faktureringsmodell för kund** innehåller erforderlig datamodell och modellmappning.
- Konfigurationen **FTI-rapport för kund (GER)** innehåller provformatet.

> [!NOTE]
> Dessa konfigurationer har skapats som exempel för att förklara möjliga scenarier. Framtiden för dessa konfigurationer är beroende av resultatet av denna utvärdering och eventuell feedback som tas emot.

### <a name="features-that-are-implemented-in-the-sample-er-format"></a>Funktioner som implementeras i ER-provformat
I exempelkonfigurationen för ER-format användes en Excel-fil som mall för att skapa FTI-formulär.

![Formatdesigner](media/FTIbyGER-ERFormat.png)

Detta provformat för ER stöder för närvarande följande funktioner för att skapa FTI-formulär:

- FTI-formulär skapas för såväl ursprungliga fakturor som har bokförts som för ursprungliga fakturor som ännu inte har bokförts. Korrigerade fakturor och kreditfakturor stöds inte.
- FTI-formulär skapas på samma språk som finns i fakturan. Formatet för värden och datum i de skapade formulären baseras på inställningarna för användarens klientspråk.
- Skapade fakturor visar meddelanden om otillgängliga data om det inte finns några rader på de fakturor som bearbetas.
- Sidhuvudena i skapade fakturor baseras på det pappersformat som har valts för FTI-formuläret på sidan **Parametrar för kundreskontra**. Företagsinformation visas i sidhuvudet på det skapade fakturaformuläret endast om pappersformatet är tomt.
- Skapade fakturaformulär anger momsregistreringsnummer för företag och kund när lämpligt alternativ har valts för FTI-formuläret på sidan **Parametrar för kundreskontra**.
- Avsnitten för skapade fakturarader och fakturabelopp anger standardfakturans finansiella information i registreringsvalutan för fakturan.
- Avsnittet för skapade fakturabelopp kan ange finansiell information i valutan euro samt i fakturans registreringsvaluta när alternativet **Skriv ut belopp i valutan euro** har aktiverats på sidan **Parametrar för kundreskontra**.
- Skapade fakturaformulär anger vilka kommentarer för processfaktura som finns tillgängliga baserat på sidan **Parametrar för kundreskontra**. Kommentarer inkluderas för både hela fakturan och respektive fakturarad.
- Skapade faktureringsformulären inkluderar kommentarer för kundens FTI-formulär och den bearbetade fakturans språk när de har konfigurerats i kommentarslistan för formulär.
- Beroende på inställningarna för utskriftshantering inkluderar skapade fakturor en anpassad sidfotstext när detta har konfigurerats för fakturaspråk, ER-format samt FTI-dokumentets omfattning.
- Beloppavsnittet för skapade faktureringsformulär innehåller all information om kassarabatt som är tillgänglig.
- Avsnittet för betalningsschema för skapade faktureringsformulär innehåller all tillgänglig information om betalningsschema.
- Markeringsavsnittet för skapade faktureringsformulär innehåller alla avgiftstransaktioner som är tillgängliga.
- Skapade faktureringsformulär innehåller momsinformation baserad på inställningen **Momsspecifikation** på sidan **Parametrar för kundreskontra**. Det här avsnittet kan ange momsinformation i antingen enbart fakturans registreringsvaluta eller i fakturans registreringsvaluta och företagets redovisningsvaluta samtidigt.
- Genererade fakturaformulär anger information om direktdebiteringsmeddelanden. De anger exempelvis när betalningsmetoden med obligatoriskt fullmakts-ID för direktdebitering har valts för fakturan, när den bearbetade fakturan har registrerats i valutan euro, samt när fullmakts-ID för direktdebitering har angetts för fakturan.
- Skapade fakturor anger eventuell information om förskottsbetalning som finns för bokförda fakturor.
- Skapade faktureringsformulär kan skickas som ett e-postmeddelande till en fakturakund. Lämpligt ER-filmål ska konfigureras för det ER-format som används.

### <a name="countryregion-specific-features"></a>Lands-/regionsspecifika funktioner 
Följande lands-/regionspecifika funktioner ingår i provformatet för ER för att visa hur specifika krav kan hanteras i ER-konfigurationer.

#### <a name="norway"></a>Norge
Företagets registreringsterm anges i sidhuvudet på det skapade fakturaformuläret när fakturan bearbetas för en juridisk person som konfigurerats på följande sätt:

- Kontexten för land/region för Norge används.
- Parametern för **Skriv ut företagsregistret** är aktiv för säljdokument.

#### <a name="spain"></a>Spanien
Termen **Specialordning för kontant redovisningsmetod** anges i sidhuvudet på skapat fakturaformulär när fakturan bearbetas för en juridisk person som konfigurerats på följande sätt:

- Kontexten för land/region för Spanien används.
- Specialordningen för kontant redovisningsmetod aktiveras på fakturans bearbetningsdatum.

När kassarabattinformation som exempelvis kassarabattbelopp och fakturaradens nettobelopp är tillgängliga, visas de i avsnittet för fakturabelopp i framställd faktura när denna har bearbetats för en juridisk person som konfigureras på följande sätt:

- Kontexten för land/region för Spanien används.
- **Kontant rabatt tillämpas i fakturan** aktiveras via fakturaalternativet (**Parametrar för redovisning** \> **Momsavsnitt**).

#### <a name="italy"></a>Italien
Markeringen för varurabatt inkluderas på den skapade fakturans fakturarader när denna bearbetas för en juridisk person som konfigureras med lands-/regionkontext för Italien.

#### <a name="finland"></a>Finland
Förutom till det genererade fakturaformuläret kan giroöverföringsblanketter skapas på följande sätt:

- För den juridiska person som använder lands-/regionkontext för Finland och som har minst ett bankkonto markerat som **Girokonto** och **Streckkod för bank**. 
- För en faktura som har markerats på korrekt sätt för associerad **Finsk** betalningsbilaga.

![Giroblankett](media/FTIbyGER-GiroSlip.PNG)

> [!NOTE]
> ER-provformatet har konfigurerats för att skapa gireringsblanketter i separata kalkylblad som tillval.

> [!NOTE]
> Du måste först installera det teckensnitt som används för att skapa streckkoden på den lokala dator där det skapade fakturaformuläret i Excel-format ska förhandsgranskas.

### <a name="use-the-sample-er-format-to-configure-email-destinations"></a>Använd ER-provformatet för att konfigurera e-postmål
Använd följande element för ER-provformatet för att konfigurera e-postmål:

- E-postadressen för en kundkontakt kan nås via följande ER-uttryck: **model.InvoiceBase.Contact.ElectronicMail**.
- Ämnestexten för e-post kan nås via följande ER-uttryck **Emailing.TxtToUse.Subject**.
- Brödtexten för e-post kan nås via följande ER-uttryck **Emailing.TxtToUse.Body**.

![Destinationsinställningar](media/FTIbyGER-ERFileDestinationSettingEmail.png)

Standardtexten i e-postens ämne och brödtext definieras i provformatet för ER. Språket beror på formatets etiketter. Denna standardtext används för e-post om ingen anpassad e-postmall för en organisation med fördefinierat ID **ERFTITMP** har lagts till.

> [!NOTE]
> E-postmall-ID **ERFTITMP** har angetts i provformatet för ER. Detta går att ändra vid behov i ett nytt ER-format som skapas ur detta provformat.

Om organisationens e-postmall med de fördefinierat **ERFTITMP**-ID har lagts till för den juridiska person som du bearbetar fakturan för, kommer mallen för e-postens ämnesrad och brödtext att användas för att skapa e-postmeddelandet. 

![Organisationens e-postmallar](media/FTIbyGER-EmailTemplate.png)

![Överför e-postmall](media/FTIbyGER-EmailTemplateBody.png)

ER-uttrycket **Emailing.TxtToUse.Subject** för ER-provformatet konfigureras i syfte att ersätta eventuella förekomster av platshållare %1 med det faktura-ID som bearbetas.

Uttrycket **Emailing.TxtToUse.Body** för provformatet konfigureras för följande ersättningar för platshållare:

- %1” ersätts med namnet på kundens kontaktperson.
- ”%2” ersätts med namnet på företaget.
- ”%3” ersätts med namnet på kunden.
- ”%4” ersätts med namnet på företagets kontaktperson.
- ”%5” ersätts med jobbtiteln på företagets kontaktperson.
- ”%6” ersätts med e-postadressen till företagets kontaktperson.

![E-postadress](media/FTIbyGER-Email.PNG)

## <a name="additional-resources"></a>Ytterligare resurser
[Översikt över elektronisk rapportering](general-electronic-reporting.md)
