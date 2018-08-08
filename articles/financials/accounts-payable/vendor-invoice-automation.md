---
title: "Automation av leverantörsfaktura"
description: "Det här avsnittet beskriver de funktioner som är tillgängliga för slutpunkt till slutpunkt-automatisering av leverantörsfakturor, även fakturor som innehåller bilagor."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendEditInvoiceHeaderStagingListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 551f3d5fc52fac725fcc9fedc37dc1c85fac5a26
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---
# <a name="vendor-invoice-automation"></a>Automation av leverantörsfaktura

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver de funktioner som är tillgängliga för slutpunkt till slutpunkt-automatisering av leverantörsfakturor, även fakturor som innehåller bilagor.

Organisationer som vill förenkla sina processer för leverantörsreskontra (AP) identifierar ofta behandlingen av fakturan som ett av det viktigaste behandlingsområdet att effektivisera. I många fall kan dessa organisationer avlasta behandlingen av pappersfakturor till en tredjeparts tjänstleverantör av optisk teckenläsning (OCR). De får sedan metadata för en maskinläsbar faktura tillsammans med en skannad bild av varje faktura. Som en hjälp för automatiseringen byggs sedan en ”slut”-lösning för att möjliggöra förbrukning av dessa artefakter i faktureringssystemet. Microsoft Dynamics 365 for Finance and Operations möjliggör nu ”slut”-automatisering via en färdig lösning för automatisering av fakturan.

## <a name="solution-context"></a>Kontexten för lösningen

Lösningen för automatiseringen av fakturor innebär ett standardgränssnitt som kan acceptera fakturametadata för fakturahuvudet och fakturaraderna och även bifogade filer som är kopplade till fakturan. Alla externa system som genererar artefakter som överensstämmer med det här gränssnittet kan skicka flödet till Finance and Operations för automatisk bearbetning av fakturor och bifogade filer.

Följande bild visar ett exempelscenario på integrering där Contoso samarbetar med en OCR-tjänstleverantör för behandling av leverantörsfakturor. Contosos leverantörer skickar fakturor till tjänstleverantören via e-post. Via OCR-bearbetningen genererar tjänstleverantören fakturans metadata (rubrik och/eller rader) och en skannad bild av fakturan. Ett integreringsskikt omvandlar sedan dessa artefakter så att Finance and Operations kan förbruka dem.

![Exempel på integreringsscenario](media/vendor_invoice_automation_01.png)

Det finns flera variationer av föregående scenario som är möjliga om fakturintegrering krävs. Migrering av data är ett annat användningsfall där detta gränssnitt kan användas för att skapa fakturor och bilagor i Finance and Operations.

### <a name="solution-components"></a>Lösningens komponenter

Lösningens fotspår består av följande komponenter:

+ Dataenheter för fakturahuvudet, fakturarader och fakturera bilagor
+ Undantagsbehandling av fakturor
+ En sida-vid-sida-bilagevisning på fakturor

Resten av det här avsnittet innehåller detaljerade beskrivningar av dessa komponenter.

## <a name="data-entities"></a>Datatabeller

Ett datapaket är den arbetsenhet som måste skickas till Finance and Operations, så att fakturahuvuden, fakturarader och fakturans bilagor kan skapas. Följande dataenheter används för artefakter som ingår i datapaketet:

+ Leverantörsfakturahuvud
+ Leverantörsfakturarad
+ Dokumentbilaga till leverantörsfaktura

Dokumentbilagor till leverantörsfakturan är en ny dataenhet som introduceras som en del av den här funktionen. Rubrikenheten för leverantörsfakturan har ändrats så att den stöder bilagor. Radenheten för leverantörsfakturan har inte ändrats för den här funktionen.

Det här avsnittet ger inte en detaljerad definition av ett datapaket. Det ges inte heller någon beskrivning av hur du skapar datapaket. Den här informationen finns i [Ramverk för dataenheter och -paket](../../dev-itpro/data-entities/data-entities-data-packages.md).

Om du snabbt vill generera testdata som inkluderar fakturor och bilagor ska du följa dessa steg.

1. Logga in på din instans av Finance and Operations.
1. Gå till **Leverantörsreskontra** > **Fakturor** > **Väntande leverantörsfakturor**.
1. Skapa fakturor som har rader och bilagor.

    > [!NOTE]
    > Bilagorna måste vara rubrikbilagor. För närvarande stöder inte dokumentbilageenheten för leverantörsfakturan radbilagor.

1. Öppna arbetsytan **Datahantering**.
1. Skapa ett exportjobb som innehåller leverantörsfakturans rubrik, leverantörsfakturaraden och leverantörsfakturans dokumentbilageenhet.
1. Exportera data.
1. Hämta exporterade data som ett paket. Du kan nu använda paketet för att importera data till målinstanser för testningsändamål.

### <a name="determining-the-legal-entity-for-an-invoice"></a>Fastställa juridisk person för en faktura

Fakturor som importeras med datapaket kan associeras med den juridiska person de tillhör på två sätt:

+ Importjobbet som bearbetar fakturan importerar den till samma företag som jobbet planerades för i arbetsytan **Datahantering**. Med andra ord fastställer företaget som utför jobbet vilket företag fakturan tillhör.
+ När datapaket som innehåller fakturor skickas till Finance and Operations kan anroparen (det vill säga integreringsprogrammet som körs utanför Finance and Operations) explicit ange företagets ID i HTTP-förfrågan. I det här fallet åsidosätts företagssammanhanget i Finance and Operations som jobbet körs i och fakturorna importeras till det företag som skickades via en HTTP-begäran.

> [!NOTE]
> Detta beteende är standard för datahantering. Det förklaras här, i samband med fakturor, för fullständighet.

## <a name="exception-processing"></a>Behandling av undantag

I fall där leverantörsfakturor kommer till Finance and Operations via integrering måste det finnas ett enkelt sätt för ansvariga för leverantörsreskontra att behandla undantag och felaktiga fakturor och att skapa väntande fakturor med utgångspunkt från felaktiga fakturor. Behandlingen av detta undantag för leverantörsfakturor ingår nu i Finance and Operations.

### <a name="exceptions-list-page"></a>Sida med lista över undantag

Den nya sidan med lista över undantag finns på **Leverantörsreskontra** > **Fakturor** > **Importfel** > **Leverantörsfakturor som inte importerades**. Den här sidan visar alla rubrikposter för leverantörsfakturan från mellanlagringsregistret för leverantörsfakturans rubrikdatapost. Observera att du kan visa samma poster från arbetsytan **Datahantering**, där du även kan utföra samma åtgärder som ingår i funktionen för hantering av undantag. Användargränssnittet för funktionen för hantering av undantag är dock optimerad för en funktionell användare.

![Sida med lista över undantag](media/vendor_invoice_automation_02.png)

Den här sidan innehåller följande fält som kommer in via flödet:

+ **Företag** – företaget som fakturan tillhör
+ **Felmeddelande** – felmeddelandet som ramverket för datahantering utfärdar för att förklara varför fakturan inte kunde skapas
+ **Nummer** – fakturanumret
+ **Fakturakonto**
+ **Namn** – leverantörens namn
+ **Leverantörskonto**
+ **Inköpsorder** – numret på inköpsordern (IO) för fakturan
+ **Bokföringsdatum**
+ **Fakturadatum**
+ **Fakturabeskrivning**
+ **Valuta**
+ **Logg**
+ **Radreferens** – identifierare som kommer från det externa systemet

    > [!NOTE]
    > Radreferensen är inte fakturans ID.

Den här listsidan har även ett förhandsgranskningsfönster som kan användas på följande sätt:

+ Visa hela felmeddelandet så att du inte behöver utöka kolumnen **Felmeddelande** i rutnätet.
+ Visa hela listan över bifogade filer för fakturan, om bilagor medföljde fakturan.

Listsidan stöder följande åtgärder:

+ **Redigera** – öppna undantagsposten i redigeringsläge, så att du kan lösa problemen.
+ **Alternativ** – åtkomst till standardalternativ som är tillgängliga på listsidor. Du kan använda alternativet **Lägg till arbetsyta** för att fästa listsidan med undantag på din arbetsyta som en lista eller panel.

### <a name="exception-details-page"></a>Informationssida för undantag

När du startar redigeringsläget visas informationssidan för undantag för fakturan med fel. Om det inte finns bilagor visas fakturan och standardbilagan sida vid sida på informationssidan för undantag.

![Informationssida för undantag](media/vendor_invoice_automation_03.png)

I föregående illustration fanns det inga rader för leverantörsfakturarubrik som kom in. Radavsnittet är därför tomt.

Informationssidan för undantag stöder följande åtgärd:

+ **Skapa väntande faktura** – när du har åtgärdat felen på fakturan som en del av behandlingen av ett undantag kan du klicka på den här knappen om du vill skapa en väntande faktura. Väntande fakturor skapas i bakgrunden (som en asynkron åtgärd).

### <a name="shared-service-vs-organization-based-exception-processing"></a>Delad tjänst i förhållande till organisationsbaserad hantering av undantag

Sidan med en lista över undantag stöder standardsäkerhetskonstruktioner som arbetsytan **Datahantering** stöder för behandling av mellanlagringsposter. Importen av fakturan kan skyddas på följande sätt:

+ Efter användarroll
+ Efter användare
+ Efter juridisk person

![Importjobb som skyddas av användarroll och juridisk person](media/vendor_invoice_automation_04.png)

Om skydd konfigureras för importen av fakturan, godkänner sidan med listan över undantag dessa inställningar. Användarna kommer enbart att kunna visa de undantagsposter för fakturan som den här inställningen tillåter.

Exempelvis har Contoso beslutat att bearbeta fakturaundantag efter juridisk person. Därför konfigureras skyddet för importen av fakturan så att en användare som är en juridisk person A ser undantag för fakturan i juridisk person A, medan en användare som är juridisk person B enbart ser fakturaundantag i den juridiska personen B. Denna inställning möjliggör ansvarsfördelning för hantering av undantag för fakturan.

Contoso kan även bestämma sig för att inte tillämpa något skydd, så att samma användare kan bearbeta fakturaundantag för alla juridiska personer. Denna inställning möjliggör ett scenario med delade tjänster för hantering av fakturaundantag.

## <a name="side-by-side-attachment-viewer"></a>Visningsprogram för sida-vid-sida-bilaga

För att du snabbt ska kunna visa bilagor till leverantörsfakturor innehåller följande sidor, som används i faktureringsprocessen, nu ett visningsprogram för bilagor:

+ **Hantering av undantag**
+ **Väntande leverantörsfakturor** sida (även tillgänglig i processen för granskning av fakturan)
+ **Fakturajournal** sida för förfrågan (för bokförda fakturor)

Här är huvudfunktionerna i visningsprogrammet för bilagor:

+ Visa alla bilagstyper som stöds av Dokumenthantering (filer, bilder, URL-adresser och anteckningar).
+ Visa flersidiga TIFF-filer.
+ Utföra följande åtgärder på bildfiler:
  + Markera delar av bilden.
  + Blockera delar av bilden.
  + Lägga till anteckningar till bilden.
  + Zooma in eller ut i bilden.
  + Panorera bilden.
  + Ångra och göra om åtgärder.
  + Anpassa bilden till storlek.

> [!NOTE]
> Dessa åtgärder är bara tillgängliga för bildfiler (JPEG, TIFF, PNG och så vidare). Alla ändringar som du gör i en bild med hjälp av dessa åtgärder sparas i bildfilen. För närvarande inkluderar visningsprogrammet för bilagor inte versionshantering eller granskning av funktioner.

### <a name="default-attachment"></a>Standardbilaga

Om en leverantörsfaktura har fler än en bilaga kan du ställa in ett av dokumenten som standardbilaga på sidan **Bilagor**. Alternativet **Standardbilaga** är ett nytt alternativ som har lagts till som en del av den här funktionen. Det här alternativet visas också i dataenheten för leverantörsfakturans dokumentbilaga. Standardbilagan kan därför ställas in via integrering.

Endast ett dokument kan anges som standardbilaga. När du har angett ett dokument som standardbilaga visas det automatiskt i visningsprogrammet för bilagor när fakturan öppnas. Om du inte anger ett dokument som standardbilaga visar visningsprogrammet för bilagor automatiskt vilken bilaga som helst när fakturan öppnas.

### <a name="showhide-invoice-attachments"></a>Visa/dölj fakturabilagor

Med hjälp av en ny knapp på förfrågningssidan **Bearbetning av undantag**, **Väntande faktura** och **Fakturajournal** kan du visa eller dölja visningsprogrammet för bilagor.

### <a name="security"></a>Säkerhet

Följande åtgärder i visningsprogrammet för bilagor styrs via rollbaserad säkerhet:

+ Markera
+ Spärra
+ Anteckning

### <a name="pending-vendor-invoices-page"></a>Sida för väntande leverantörsfakturor

Följande behörigheter tillåter skrivskyddad åtkomst eller läs/skriv-åtkomst till visningsprogrammet för bilagor för att markera, blockera och anteckna åtgärder:

+ **Underhålla bilden på leverantörsfakturan** – denna behörighet ger läs/skriv-behörighet.
+ **Visa bilden på leverantörsfakturan** – denna behörighet ger enbart läsbehörighet.

Följande arbetsuppgifter ger skrivskyddad åtkomst eller läs/skriv-åtkomst till visningsprogrammet för bilagor för dessa åtgärder:

+ **Underhålla leverantörsfakturor** – behörighet för bilden på leverantörsfakturan tilldelas denna uppgift.
+ **Fråga om status på leverantörsfaktura** – behörighet för att visa bilden på leverantörsfakturan tilldelas denna uppgift.

Följande roller ger skrivskyddad åtkomst eller läs/skriv-åtkomst till visningsprogrammet för bilagor för dessa åtgärder:

+ **Ansvarig för leverantörsreskontra** och **Chef för leverantörsreskontra** – underhålla leverantörsfakturor har tilldelats dessa roller.
+ **Ansvarig för leverantörsreskontra**, **Chef för leverantörsreskontra**, **Ansvarig för centraliserade leverantörsreskontrabetalningar** och **Ansvarig för leverantörsreskontrabetalningar** – uppgiften Fråga om status på leverantörsfaktura har tilldelats dessa roller.

### <a name="invoice-exception-details-page"></a>Informationssida för fakturaundantag

Följande behörigheter tillåter skrivskyddad åtkomst eller läs/skriv-åtkomst till visningsprogrammet för bilagor för att markera, blockera och anteckna åtgärder.

> [!NOTE]
> Rollerna som nämns i det här avsnittet tillåter skrivskyddad åtkomst till bilderna på fakturan i visningsprogrammet för bilagor. Om en roll även måste ha skrivbehörighet för bilderna kan du bevilja skrivåtkomst till rollen med hjälp av den behörighet och den uppgift som beskrivs här.

+ **Underhålla bild av enhet för leverantörsfakturarubrik** – denna behörighet ger full åtkomst till fakturabilderna i visningsprogrammet för bilagor.
+ **Visa bild av enhet för leverantörsfakturarubrik** – denna behörighet ger skrivskyddad åtkomst till fakturabilderna i visningsprogrammet för bilagor.

Följande arbetsuppgifter ger skrivskyddad åtkomst till visningsprogrammet för bilagor för dessa åtgärder:

+ **Underhålla leverantörsfakturor** – behörighet för att underhålla bilden på leverantörsfakturan är tilldelad denna uppgift.

Följande roller ger skrivskyddad åtkomst till visningsprogrammet för bilagor för dessa åtgärder:

+ **Ansvarig för leverantörsreskontra** och **Chef för leverantörsreskontra** – underhålla leverantörsfakturor har tilldelats dessa roller.

Som standard, om användarrollen ger redigeringsrättigheter på valfri sida, har användaren även redigeringsrättigheter i visningsprogrammet för bilagor för att markera, blockera och anteckna åtgärder. Om scenarier där en viss roll bör ha redigeringsrättigheter på sidan men inte i visningsprogrammet för bilagor kan behörighet i ovanstående lista användas i detta användningsfall.

