---
title: Översikt över elektronisk rapportering (ER)
description: Det här ämnet ger en översikt till verktyget Elektronisk rapportering (ER). Den innehåller information om huvudkoncepten, scenarier som ER stöder och en lista över format som har utformats och lanserats som en del av lösningen.
author: NickSelin
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7cd3e2ac729bdb3ecc8e7bfacb060e433b185f09
ms.sourcegitcommit: 3a06d3b38d9de2afc22839e5a794829405068024
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2020
ms.locfileid: "2933942"
---
# <a name="electronic-reporting-er-overview"></a>Översikt över elektronisk rapportering (ER)

[!include [banner](../includes/banner.md)]

Det här ämnet ger en översikt till verktyget Elektronisk rapportering (ER). Den innehåller information om huvudkoncepten, scenarier som ER stöder och en lista över format som har utformats och lanserats som en del av lösningen.

ER är ett verktyg du kan använda för att konfigurera format för såväl inkommande som utgående elektroniska dokument i enlighet med de rättsliga kraven i olika länder/regioner. Med hjälp av ER kan du hantera dessa format under deras livscykel. Du kan exempelvis tillämpa nya lagkrav och skapa affärsdokument i de format som krävs för elektroniskt informationsutbyte med myndigheter, banker och andra parter.

ER-motorn riktar sig till företagsanvändare, i stället för till utvecklare. Eftersom du kan konfigurera formaten istället för koden blir processerna för att skapa och ändra format på elektroniska dokument snabbare och enklare.

ER stöder för närvarande formaten TEXT, XML, Microsoft Word-dokument och OPENXML-kalkylblad. Ett tilläggsgränssnitt kan dock ge stöd för ytterligare format.

## <a name="capabilities"></a>Funktioner
ER-motorn har följande funktioner:

- Den representerar ett enskilt verktyg som kan användas för elektronisk rapportering i olika domäner och ersätter fler än 20 olika motorer som används för någon form av elektronisk rapportering för Finance and Operations.
- Den skapar ett rapportformat utanför den aktuella implementeringen. Formatet är med andra ord tillämpligt för olika versioner.
- Den har stöd för att skapa ett anpassat format som är baserat på ett originalformat. Det innehåller även funktioner för automatisk uppdatering av det anpassade formatet när ursprungsformatet ändras på grund av nya lokaliserings-/anpassningskrav.
- Det kommer att vara det primära standardverktyget för att stödja lokaliseringskrav vid elektronisk rapportering – både för Microsoft samt för Microsofts partners.
- Den stöder funktionen för att distribuera format till partners och kunder via Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Viktiga begrepp
### <a name="components"></a>Komponenter

ER stöder två typer av komponenter: **Datamodell** och **Format**.

#### <a name="data-model-and-model-mapping-components"></a>Komponenter för datamodell och datamodellmappning

En datamodellskomponent är en abstrakt representation av en datastruktur. Den används för att beskriva domänen för ett visst affärsområde tillräckligt detaljerat för att uppfylla rapporteringskraven för domänen. En datamodellkomponent för omfattar följande delar:

- <a name="DataModelComponent"></a>En datamodell som en uppsättning domänspecifika affärsenheter och en hierarkiskt strukturerad definition av relationer mellan dem.
- <a name="ModelMappingComponent"></a>En modellmappning som länkar valda programdatakällor till enskilda element i en datamodell som vid körning specificerar dataflödet och reglerna för population av affärsdata till datamodellkomponenten.

En affärsenhet av datamodellen representeras som en behållare (post). Affärsenhetsegenskaper återges som dataobjekt (fält). Varje dataobjekt har ett unikt namn, en unik etikett, en unik beskrivning och ett unikt värde. Värdet på respektive dataobjekt kan vara utformat så att det tolkas som en sträng, ett heltal, ett realtal, ett datum, en uppräkning, ett booleskt värde och så vidare. Dessutom kan det vara en annan post eller lista över poster.

En enskild datamodellskomponent kan innehålla flera hierarkier av domänspecifika affärsenheter. Den kan också innehålla modellmappningar som har stöd för ett rapportspecifikt dataflöde vid körning. Hierarkierna särskiljs av en enda post som har valts som rot för modellmappningen. Datamodellen för betalningsdomänområdet kan exempelvis stödja följande mappningar:

- Företag \> Leverantör -\> Betalningstransaktioner i AP-domänen
- Kund \> Företag -\> Betalningstransaktioner i AR-domänen

Observera att affärsenheter såsom företags- och betalningstransaktioner skapas en gång. Olika mappningar återanvänder sedan dem.

En modellmappning som har stöd för utgående elektroniska dokument har följande funktioner:

- Den kan använda olika datatyper som datakällor för en datamodell. Den kan exempelvis använda tabeller, datatabeller, metoder eller fasttext.
- Den har stöd för användardefinierade indataparametrar som kan definieras som datakällor för datamodeller när vissa data måste specificeras vid körning.
- Den stöder transformeringen av data till erforderliga grupper. Dessutom kan du filtrera, sortera och summera data, samt lägga till logiska, beräknade fält som utformas via formler som liknar Microsoft Excel-formler. Mer information finns i [Formeldesigner i elektronisk rapportering (ER)](general-electronic-reporting-formula-designer.md).


En modellmappning som har stöd för inkommande elektroniska dokument har följande funktioner:

- Olika uppdateringsbara dataelement används som mål. Dessa dataelement inkluderar tabeller, dataenheter och vyer. Datan kan uppdateras med data från inkommande elektroniska dokument. Flera mål kan användas i en enda modellmappning.
- Den har stöd för användardefinierade indataparametrar som kan definieras som datakällor för datamodeller när vissa data måste specificeras vid körning.

En datamodellskomponent har utformats för respektive företagsdomän som ska användas som en enhetlig datakälla för rapportering som isolerar rapporterna från den fysiska implementeringen av datakällor för Finance and Operations. Den representerar domänspecifika affärsbegrepp och -funktioner i ett formulär som utgör ett rapporteringsformulärs ursprungliga konstruktion och vidare underhåll effektivare.

#### <a name="FormatComponentOutbound"></a>Formatkomponenter för utgående elektroniska dokument

En formatkomponent är schemat för de rapporteringsutdata som skapas vid körning. Ett schema består av följande element:

- Ett format som definierar strukturen och innehållet i det utgående elektroniska dokument som skapas vid körning.
- Datakällor som en uppsättning parametrar för användarindata och en domänspecifik datamodell som använder en vald modellmappning.
- En formatmappning som en uppsättning bindningar av formatdatakällor som har vissa element i ett format som vid körning specificerar dataflödet och reglerna för formatets utdatagenerering.
- En formatvalidering som en uppsättning konfigurerbara regler som kontrollerar rapportgenereringen vid körning beroende på löpande kontext. Det kan exempelvis finnas en regel som stoppar utgående generering av en viss leverantörs betalningar, och som skapar ett undantag när specifika attribut för den valda leverantören saknas, till exempel bankkontonummer.

En formatkomponent har stöd för följande funktioner:

- Skapa rapporteringsutdata som enskilda filer i olika format, till exempel text, XML Microsoft Word-dokument eller kalkylblad.
- Skapa flera filer separat och även packa filerna i zip-filer.

En formatkomponent låter dig bifoga vissa filer som kan användas i rapporteringsutdatan:

- Excel-arbetsböcker som innehåller ett kalkylblad som kan användas som en mall för utdata i OPENXML-kalkylbladsformat
- Word-filer som innehåller ett dokument som kan användas som en mall för utdata i Microsoft Word-dokumentformat
- Andra filer som kan ingå i formatets utdata som fördefinierade filer.

Följande bild visar hur datan flödar för dessa format.

[![Dataflöde för utgående formatkomponenter](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Du måste identifiera mappningen av formatkonfigurationen för att kunna köra en enskild ER formatkonfiguration och skapa utgående elektroniska dokument.

#### <a name="FormatComponentInbound"></a>Formatkomponenter för inkommande elektroniska dokument
En formatkomponent är schemat för de inkommande dokument som importeras vid körning. Ett schema består av följande element:

- Ett format som definierar strukturen och innehållet i de inkommande elektroniska dokument som innehåller data som importeras vid körning. En formatkomponent används för att tolka ett inkommande dokument i olika format, till exempel text och XML.
- En formatmappning som binder enskilda formatelement till element i en domänspecifik datamodell. Vid körning anger elementen i datamodellen dataflödet och reglerna för import av data från ett inkommande dokument, och spara sedan datan i en datamodell.
- En formatvalidering som en uppsättning konfigurerbara regler som kontrollerar dataimporten vid körning, beroende på körningskontexten. Det kan exempelvis finnas en regel som stoppar dataimporten av ett bankutdrag med en viss leverantörs betalningar, och som skapar ett undantag när attributen för en specifik leverantör saknas, till exempel ID-koden för leverantören.

Följande bild visar hur datan flödar för dessa format.

[![Dataflöde för inkommande formatkomponenter](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Om du vill köra en enskild ER formatkonfiguration för att importera data från ett inkommande elektroniskt dokument måste du identifiera önskad mappning för en formatkonfiguration, samt även integreringspunkten för en modellmappning. Du kan använda samma modellmappning och mål tillsammans med olika format för olika typer av inkommande dokument.

#### <a name="component-versioning"></a>Komponentversionsnumrering

Versionsnumrering stöds för ER-komponenter. Följande arbetsflöde tillhandahålls för att hantera ändringar i ER-komponenter:

1. Den version som ursprungligen skapades är markerad som en **Utkast**-version. Den här versionen kan redigeras och är tillgänglig för provkörningar.
2. **Utkast**-versionen kan konverteras till en **Slutförd** version. Den här versionen kan användas i lokala rapporteringsprocesser.
3. Den **Slutförda** versionen kan konverteras till en **Delad** version. Denna version publiceras på LCS och kan användas inom globala rapporteringsprocesser.
4. **Delad**-versionen kan konverteras till en **Avslutad** version. Den här versionen kan sedan tas bort.

Versioner som har statusen **Slutförd** eller **Delad** är tillgängliga för annan dataöverföring. Följande åtgärder kan utföras på en komponent som har dessa statusvärden:

- Komponenten kan serialiseras i XML-format och exporteras från en XML-fil.
- Komponenten kan omserialiseras från en XML-fil och importeras till programmet som en ny version av en ER-komponent.

#### <a name="component-date-effectivity"></a>Komponent giltighetsdatum

ER-komponentversionerna har giltighetsdatum. Du kan ange **Gäller från**-datumet för en ER-komponent för att ange från och med vilket datum komponenten ska aktiveras för rapporteringsprocesser. Programmets sessionsdatum används för att definiera om en komponent är giltig för körning. Den senaste versionen används för rapporteringsprocesser om fler än en version är giltig för ett visst datum.

#### <a name="component-access"></a>Åtkomsten till komponenter

Åtkomsten till ER-formatkomponenter beror på inställningen för ISO-lands-/regionskod. När den här inställningen är tom för en vald version av en formatkonfiguration kan formatkomponenten nås från vilket företag som helst vid körning. När inställningen innehåller ISO-lands-/regionskoder är formatkomponenten endast tillgänglig från de företag som har en primäradress som är definierad för en av en formatkomponents ISO-lands-/regionskoder.

Olika versioner av en dataformatkomponent kan ha olika inställningar för ISO-lands-/regionskoder.

#### <a name="Configuration"></a>Konfiguration

En ER-konfiguration är omslaget (wrappern) för en viss ER-komponent. Komponenten kan antingen vara en datamodellskomponent eller en formatkomponent. En konfiguration kan omfatta olika versioner av en ER-komponent. Varje konfiguration markeras som ägda av en viss konfigurationsleverantör. **Utkast**-versionen av en komponent i en konfiguration kan redigeras om ägaren av en konfiguration har valts som en aktiv leverantör i ER-inställningarna i programmet.

Varje modellkonfiguration innehåller en datamodellskomponent. En ny formatkonfiguration har sitt ursprung i (kan härledas från) en specifik datamodellskonfiguration. Formatkonfigurationen som skapas anges i konfigurationsträdet som underordnad till den ursprungliga datamodellskonfigurationen.

Formatkonfigurationen som skapas innehåller en formatkomponent. Datamodellkomponenten i den ursprungliga modellkonfigurationen infogas automatiskt i formatkomponenten för den underordnade formatkonfigurationen som en standarddatakälla.

En ER-konfiguration delas av programföretag.

#### <a name="Provider"></a>Leverantör

ER-leverantören är partens identifierare som används för att indikera författare (ägare) av varje ER-konfiguration. Med hjälp av ER kan du hantera listan över konfigurationsleverantörer. Formatkonfigurationer som släpps för elektroniska dokument som en del av Finance and Operations-lösningen markeras som ägda av **Microsoft**-konfigurationsleverantören.

För information om hur du registrerar en ny ER-leverantör, kör uppgiftsguiden **ER skapa en konfigurationstjänst och markera den som aktiv** (ingår i affärsprocessen **7.5.4.3 Införskaffa/utveckla IT-tjänst/-lösningskomponenter (10677)**).

#### <a name="Repository"></a>Databas

En ER-databas lagrar ER-konfigurationer. Följande typer av ER-databaser stöds för närvarande: 

- Delat LCS-bibliotek
- LCS-projekt
- Filsystem:
- Lagstadgad konfigurationstjänst (RCS)
- Verksamhetsresurser


En databas för **delat LCS-bibliotek** ger dig listan över konfigurationer i det delade tillgångsbiblioteket i Lifecycle Services (LCS). Den här typen av ER-databas kan endast registreras för Microsoft-leverantören. Från det delade LCS-tillgångsbiblioteket kan du importera de senaste versionerna av ER-konfigurationer till den aktuella instansen.

En **LCS-projekt**-databas ger åtkomst till listan över konfigurationerna för ett visst LCS-projekt (tillgångsbibliotek för LCS-projekt) som valdes i registreringssteget för databasen. ER låter dig överföra delade konfigurationer från den befintliga instansen till en specifik databas för **LCS-projekt**. Du kan även importera konfigurationer från en **LCS-projekt**-databas till den befintliga Finance and Operations-instansen.

En **Filsystem**-datalager ger åtkomst till listan över konfigurationer som finns som XML-filer i en viss mapp i det lokala filsystemet på maskinen där AOS-tjänsten finns. Önskad mapp väljs vid registreringssteget för datalagret. Du kan även importera konfigurationer från ett **Filsystem**-datalager till den befintliga instansen. 

Observera att den här databasen är tillgänglig i följande miljöer:

- Molnstyrda miljöer distribueras i utvecklingssyften (innehåller testmodeller av bifogade paket)
- Lokalt distribuerade miljöer (lokala)

Mer information finns i [Importera konfigurationer för elektronisk rapportering (ER)](./electronic-reporting-import-ger-configurations.md).

Ett **RCS-instans**-datalager ger åtkomst till listan över konfigurationerna för en viss RCS-instans som valdes i registreringssteget för datalagret. ER låter dig importera slutförda eller delade konfigurationer från valda RCS-instansen till den aktuella instansen så att du kan använda dem för elektronisk rapportering.

För mer information, se [Importera e-rapporteringskonfigurationer från Regulatory Configuration Services (RCS)](./rcs-download-configurations.md).

En databas för **Verksamhetsresurser** ger åtkomst till listan över konfigurationer som Microsoft frisläpper som en del av programlösningen i egenskap av ER-konfigurationsleverantör. Dessa konfigurationer kan importeras till den aktuella instansen och användas för elektronisk rapportering eller spela upp exempeluppgiftsguider. De kan också användas för ytterligare lokaliseringar och anpassningar. Observera att de senaste versionerna från Microsoft ER-konfigurationer måste importeras från det delade LCS-tillgångsbiblioteket med motsvarande ER-databas.

Obligatoriska datalager för **LCS-projekt**, **Filsystem** och **Lagstadgade konfigurationstjänster (RCS)** kan registreras separat för respektive konfigurationsleverantör av den aktuella instansen. Varje databas kan reserveras för en viss konfigurationsleverantör.

## <a name="supported-scenarios"></a>Stödda scenarier
### <a name="building-a-data-model"></a>Bygga en datamodell

ER erbjuder en modelldesigner som kan användas för att bygga en datamodell för en viss affärsdomän. Alla domänspecifika företagsenheter och relationerna mellan dem kan presenteras i en datamodell som en hierarkisk struktur. 

Spela upp ER-uppgiftsguiden **Skapa domänspecifik datamodell** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="translating-data-model-content"></a>Översätta datamodellens innehåll

Datamodellens innehåll (etiketter och beskrivningar) kan översättas till andra språk som programmet har stöd för. Du kanske vill översätta datamodellens innehåll av följande skäl:

- Vid designtillfället för att göra innehållet mer begripligt för formatdesigners som talar andra språk och som ska använda datamodellen för datamappning av formatkomponenter.
- Vid körning för att göra innehållet mer användarvänligt genom att använda prompter och hjälp för körningsparametrar, samt konfigurerade valideringsmeddelanden (fel och varningar) på det språk som för tillfället inloggade användarna föredrar.

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Konfigurera mappningar för datamodeller för utgående dokument

ER har en modellmappningsdesigner som låter användarna mappa datamodeller som de har utformat för specifika programdatakällor. Baserat på mappningen importeras datan vid körning från markerade datakällor till datamodellen. Datamodellen används sedan som en abstrakt datakälla för ER format som skapar utgående elektroniska dokument. 

Spela upp ER-uppgiftsguiderna **Definiera modellmappning och välja datakällor** och **Mappa datamodell till valda datakällor** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Konfigurera mappningar för datamodeller för inkommande dokument
ER har en modellmappningsdesigner som låter användarna mappa datamodeller som de har utformat för specifika mål. Exempelvis kan datamodeller mappas till uppdateringsbara datakomponenter (tabeller, dataenheter och vyer). Baserat på mappningen uppdateras vid körning med data från datamodellen. Som abstrakt lagring av ER formatet fylls datamodellen med data som importeras från ett inkommande elektroniskt dokument. 

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Spara en skapad modellkomponent som en modellkonfiguration

ER kan spara en skapad datamodell tillsammans med tillhörande datamappningar som en modellkonfiguration för den aktuella instansen. Följande illustration visar ett exempel på den här typen av datamodellkonfiguration (betalningsmodellskonfiguration).

Spela upp ER-uppgiftsguiden för **Mappa datamodell till valda datakällor** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Skapa ett format som använder en datamodell som bas

ER stöder en formatdesigner som kan användas för att skapa formatet för ett visst elektroniskt dokument för en vald affärsdomän genom att välja modellkomponenten som bas. Med hjälp av samma ER-formatdesigner kan du mappa formatet du skapar till en vald domäns datamodellmappning som en datakälla. 

Spela upp ER-uppgiftsguiden för **Skapa domänspecifika format** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Skapa en konfiguration för att skapa elektroniska dokument i OPENXML-kalkylbladsformat

ER-formatdesignern kan användas för att skapa ett elektroniskt dokument i OPENXML-kalkylbladsformat. 

Spela upp ER-uppgiftsguiden för **Skapa en konfiguration för rapporter i OPENXML-format** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot. Som ett led i uppgiftsguiden för att importera en mall använder du Excel-filen [Mall för betalningsrapport (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202) som en mall.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Skapa en konfiguration för att skapa elektroniska dokument i ett Word-dokumentformat
ER-formatdesignern kan användas för att skapa ett elektroniskt dokument i ett Word-dokumentformat. Följande illustration visar ett exempel på den här typen av format. Notera att detta format återanvänder den befintliga ER-konfigurationen som ursprungligen skapades för att skapa rapportutdata i OPENXML-format.

Kör ER-uppgiftsguiden för Designa en konfiguration för att skapa rapporter i Microsoft WORD-format (ingår i affärsprocessen 7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677) för att bekanta dig med detaljerna i det här scenariot. Använd följande Word-filer som mallar för ER-formatet som ett led i uppgiftsguidesteget för att importera en mall:

- [Mall för betalningsrapport (SampleVendPaymDocReport.docx)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Bunden mall för betalningsrapport (SampleVendPaymDocReportBounded.docx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Skapa en konfiguration för att importera data från inkommande elektroniska dokument
ER-formatdesignern kan användas för att beskriva ett elektroniskt dokument som har planerats för dataimport i antingen text- eller XML-format. Det designade formatet används för att tolka ett inkommande dokument. Mappningsdesignern för ER-format kan användas för att definiera elementbindningen för det utformade formatet för datamodellen. 

Kör uppgiftsguiden Skapa erforderlig ER för att importera data från en extern fil (ingår affärsprocessen 7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677) för att bekanta dig med detaljerna i det här scenariot. Använd följande filer för att köra den här guiden:

- [Konfiguration av ER-datamodell (1099model.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [ER-formatkonfiguration (1099model.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Exempel på det inkommande dokumentet i XML-format (1099entries.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Exempel på arbetsboken för att hantera data för inkommande dokument (1099entries.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Spara en skapad formatkomponent i en formatkonfiguration

Det går att spara ett skapat format i ER, tillsammans med konfigurerade datamappningar, som en formatkonfiguration av den aktuella instansen. I föregående illustration visas ett exempel på denna typ av konfiguration för format (**BACS (UK)**, som är underordnad konfigurationen för **Betalningsmodell**). Spela upp ER-uppgiftsguiden för **Skapa domänspecifika format** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="configuring-finance-to-start-to-use-a-created-format-internally"></a>Konfigurera Finance för att börja använda skapade format internt

Programmet kan konfigureras för att börja använda skapade format för att generera elektroniska rapporter. Hänvisningen till den skapade formatkonfigurationen ska definieras i inställningarna för en viss domän. Om du exempelvis vill börja använda en ER-formatkonfiguration för elektroniska leverantörsbetalningar i BACS-format ska du referera till formatkonfigurationen i specifika betalningsmetoder.

Spela upp ER-uppgiftsguiden **Använda format för att skapa elektroniska dokument för betalningar** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i detta scenario.

## <a name="handling-er-components"></a>Hantera ER-komponenter
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publicera en ER-komponent i LCS så att den kan användas externt (lokalisering)

Ägaren av en skapad komponent (modell eller format) kan använda ER för att publicera den färdiga versionen av en komponent i LCS. Det krävs en databas av typen **LCS-projekt** för den aktuella ER-konfigurationsleverantören. När statusen för den slutgiltiga versionen av en komponent ändras från **AVSLUTAD** till **DELAD** publiceras den versionen i LCS. När en komponent har publicerats i LCS blir ägaren av komponenten ansvarig för att uppdatera komponenten. Om formatkomponenten exempelvis utformas för att skapa ett rättsligt obligatoriskt elektroniskt dokument (t.ex. i enlighet med lokaliseringsscenario) förmodas det att formatet uppdateras så att det överensstämmer med lagändringar och att leverantören publicerar nya versioner av komponenten när nya lagkrav uppstår. Spela upp ER-uppgiftsguiden för **Överför en konfiguration i Lifecycle Services** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importera en ER-komponent från LCS och använda den internt

Med hjälp av ER kan du importera ER-komponenter från LCS till den aktuella instansen. Det krävs en databas av typen **LCS-projekt** för detta. När en ER-komponent har importerats från LCS till den aktuella instansen blir ägaren av instansen en konsument av den tjänst som tillhandahålls av ägaren (författaren) till den importerade komponenten. Om formatkomponenten exempelvis har utformats för att generera specifika elektroniska dokument från programmet i ett lands- eller regionsspecifikt format (lokaliseringsscenario) förmodas tjänstkonsumenten hämta alla uppdateringar som görs i det formatet så att det uppfyller alla rättsliga krav. Spela upp ER-uppgiftsguiden för **Importera en konfiguration från Lifecycle Services** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Att bygga ett format att välja ett annat format som bas (anpassning)

Med hjälp av ER kan du skapa (härleda) en ny komponent från den aktuella versionen av en komponent (bas) som importerats från LCS. En användare vill kanske härleda ett nytt format för att införa vissa särskilda krav för ett elektroniskt dokument (t.ex. ett extra fält eller en omfattande beskrivning) så att det stöder ett anpassningsscenario. Spela upp ER-uppgiftsguiden **Uppdatera format genom att tillämpa en ny grundversion av det** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i detta scenario.

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Uppgradering av ett format att välja en ny version av format (ändra basåren)

Med hjälp av ER kan du införa ändringar av den senaste versionen av baskomponenten automatiskt i den aktuella utkastversionen av den härledda komponenten. Den här processen kallas för *ombasering*. En ny regeländring som infördes i den senaste versionen av formatet som importerades från LCS kan exempelvis sammanfogas automatiskt i den anpassade versionen av detta format för elektroniska dokument. Ändringar som inte kan sammanfogas automatiskt anses vara konflikter. Konflikterna presenteras för manuell lösning i designerverktyget för lämplig komponent. Spela upp ER-uppgiftsguiden **Uppdatera format genom att tillämpa en ny grundversion av det** (del av affärsprocessen **7.5.5.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10683)**) för att bekanta dig med detaljerna i detta scenario.

## <a name="list-of-er-configurations-that-are-delivered-in-the-finance-application"></a>Lista över ER-konfigurationer som levereras i Finance-programmet

| Konfigurationer för domänspecifik datamodell: rubrik | Domän                | Konfigurationer för datamodellsberoende format: rubrik | Beskrivning                                                        |
|--------------------------------------------------|-----------------------|---------------------------------------------------|--------------------------------------------------------------------|
| Verifieringsfilsmodell                                 | Ekonomisk granskning       |                                                   |                                                                    |
|                                                  |                       | Verifieringsfil (NL)                                   | Verifieringsfilformat för Nederländerna                                  |
| BAS-modell                                        | Momsrapportering         |                                                   |                                                                    |
|                                                  |                       | BAS (AU)                                          | BAS-format för Australien                                           |
| Modell för konstruktionsbranschschema               | Momsrapportering         |                                                   |                                                                    |
|                                                  |                       | CIS Månatlig avkastning (UK)                           | CIS-format för månatlig avkastning för Storbritannien                   |
| Kravbrevsmodell                          | Elektronisk fakturering  |                                                   |                                                                    |
|                                                  |                       | OIOUBL-kravbrev (DK)                     | OIOUBL-kravbrevsformat för Danmark                        |
| Elektronisk huvudbokskontomodell (MX)          | Momsrapportering         |                                                   |                                                                    |
|                                                  |                       | Hjälpredovisning XML (MX)                         | Extra redovisningstransaktioner per kontorapportformat för Mexiko |
|                                                  |                       | Kontoplan XML (MX)                         | Format för kontoplanrapport för Mexiko                          |
|                                                  |                       | Journaler XML (MX)                                 | Format för journaltransaktionsrapport för Mexiko                      |
|                                                  |                       | Råbalans XML (MX)                            | Format för råbalansrapport för Mexiko                             |
| ELSTER-modell                                     | Momsrapportering         |                                                   |                                                                    |
|                                                  |                       | Elster (DE)                                       | Elster-format för Tyskland                                          |
| Modell för EU-försäljningslista                              | Handelsrapportering       |                                                   |                                                                    |
|                                                  |                       | EU-försäljningslista (DE)                                | EU-försäljningslista i TXT-format för Tyskland                               |
|                                                  |                       | EU-försäljningslista (DK)                                | EU-försäljningslista i TXT-format för Danmark                               |
|                                                  |                       | EU-försäljningslista (FR)                                | EU-försäljningslista i XML-format för Frankrike                                |
|                                                  |                       | EU-försäljningslista (NL)                                | EU-försäljningslista i XML-format för Nederländerna                           |
|                                                  |                       | EU-försäljningslista TXT                            | EU-försäljningslista i TXT-format för Storbritannien                    |
|                                                  |                       | EU-försäljningslista XML (UK)                            | EU-försäljningslista i XML-format för Storbritannien                    |
|                                                  |                       | Rapport med EU-försäljningslista efter kolumner                   | Rapport med EU-försäljningslista efter kolumner                                    |
|                                                  |                       | Rapport med EU-försäljningslista efter rader                      | Rapport med EU-försäljningslista efter rader                                       |
| FEC-redovisningsmodell (FR)                        | Momsrapportering         |                                                   |                                                                    |
|                                                  |                       | FEC-redovisningsdata XML (FR)                      | FEC-redovisningsdataexport i XML-format för Frankrike                   |
| Tysk verifieringsfil                                | Ekonomisk granskning       |                                                   |                                                                    |
|                                                  |                       | Tysk verifieringsfilsutdata                          | Verifieringsfilsutdata för Tyskland och Österrike                          |
| Intrastat-modell                                  | Handelsrapportering       |                                                   |                                                                    |
|                                                  |                       | Intrastat (DE)                                    | Intrastat-format för Tyskland                                       |
|                                                  |                       | Intrastat (DK)                                    | Intrastat-format för Danmark                                       |
|                                                  |                       | Intrastat-INTRACOM (FR)                           | Intrastat INTRACOM-format för Frankrike                               |
|                                                  |                       | Intrastat SAISUNIC (FR)                           | Intrastat SAISUNIC-format för Frankrike                               |
|                                                  |                       | Intrastat (NL)                                    | Intrastat-format för Nederländerna                               |
|                                                  |                       | Intrastat (UK)                                    | Intrastat-format för Storbritannien                            |
|                                                  |                       | Intrastat-rapport                                  | Intrastat-Excel-kontrollrapport                                     |
| Kundfakturamodell                           | Elektronisk fakturering  |                                                   |                                                                    |
|                                                  |                       | Kreditfaktura för OIOUBL-projekt (DK)                   | Kreditfakturaformat för OIOUBL-projekt för Danmark                      |
|                                                  |                       | OIOUBL-projektfaktura (DK)                       | Fakturaformat för OIOUBL-projekt för Danmark                          |
|                                                  |                       | OIOUBL-försäljningskreditfaktura (DK)                     | Format för OIOUBL-försäljningskreditfaktura för Danmark                        |
|                                                  |                       | OIOUBL-försäljningsfaktura (DK)                         | Format för OIOUBL-försäljningsfaktura för Danmark                            |
| OB-deklarationsmodell                             | Momsrapportering         |                                                   |                                                                    |
|                                                  |                       | OB-deklarationsnummer (NL)                               | OB-deklarationsformat för Nederländerna                          |
| Betalningsmodell                                    | Betalningar              |                                                   |                                                                    |
|                                                  |                       | Betalningsservice (DK)                             | Betalningsserviceformat för Danmark                        |
|                                                  |                       | Växelremissa (FR)                  | Växelremissaformat för Frankrike                      |
|                                                  |                       | BTL91 (NL)                                        | BTL91-leverantörsbetalningsformat för Nederländerna                    |
|                                                  |                       | CFONB Prelevements (FR)                           | Format för CFONB-autogirobetalning för Frankrike                       |
|                                                  |                       | CFONB Virements (FR)                              | Format för CFONB lokal leverantörsbetalning för Frankrike                    |
|                                                  |                       | Nordea-leverantör (DK)                                | Format för Nordea Corporate Netbank-leverantörsbetalning för Danmark         |
|                                                  |                       | ANZ-direktkrediteringstjänst (AU)                    | Format för ANZ-direktkrediteringstjänst för Australien                 |
|                                                  |                       | CBA-direktkrediteringstjänst (AU)                    | Format för CBA-direktkrediteringstjänst för Australien                 |
|                                                  |                       | NAB-direktkrediteringstjänst (AU)                    | Format för NAB-direktkrediteringstjänst för Australien                 |
|                                                  |                       | STG-direktkrediteringstjänst (AU)                    | Format för STG-direktkrediteringstjänst för Australien                 |
|                                                  |                       | WBC-direktinmatningssystem (AU)                      | Format för WBC-direktinmatningssystem för Australien                   |
|                                                  |                       | DirectLink (NZ)                                   | Format för DirectLink för Nya Zeeland                              |
|                                                  |                       | JBA-betalningsfil (JP)                             | JBA-betalningsformat för Japan                                       |
|                                                  |                       | ISO20022-kreditöverföring                          | Format för SEPA-kreditöverföring för Europa                             |
|                                                  |                       | ISO20022-kreditöverföring (FR)                     | Format för SEPA-kreditöverföring för Frankrike                             |
|                                                  |                       | ISO20022-kreditöverföring (DE)                     | Format för SEPA-kreditöverföring för Tyskland                            |
|                                                  |                       | ISO20022-kreditöverföring (NL)                     | Format för SEPA-kreditöverföring för Nederländerna                    |
|                                                  |                       | ISO20022-direktdebitering                             | Format för SEPA-direktdebitering för Europa                                |
|                                                  |                       | ISO20022-direktdebitering (FR)                        | Format för SEPA-direktdebitering för Frankrike                                |
|                                                  |                       | ISO20022-direktdebitering (DE)                        | Format för SEPA-direktdebitering för Tyskland                               |
|                                                  |                       | ISO20022-direktdebitering (NL)                        | Format för SEPA-direktdebitering för Nederländerna                       |
|                                                  |                       | BACS (UK)                                         | Format för BACS-leverantörsbetalning för Storbritannien                  |
| Återfört tillägg                                   | Momsrapportering         |                                                   |                                                                    |
|                                                  |                       | Återför tilläggsförsäljningslista                         | Format för återföring av tilläggsförsäljningslista                                   |
| Nedeländsk XBRL-integreringsmodell                     | XBRL-rapportering        |                                                   |                                                                    |
|                                                  |                       | Semansys XBRL (NL)                                | Exportformat för Semansys XBRL för Nederländerna                    |
| GAF-modell (MY)                                   | Ekonomisk granskning       |                                                   |                                                                    |
|                                                  |                       | GAF-fil (MY)                                     | GAF-format för Malaysia                                         |
| Åldersfördelningsrapport för leverantörer (CN)                         | Leverantörsdataanalys |                                                   |                                                                    |
|                                                  |                       | Format för åldersfördelningsrapport (CN)                   | Format för åldersfördelningsrapport för Kina                               |
| Modell för leverantörsfakturadeklaration                 | Leverantörsdataanalys |                                                   |                                                                    |
|                                                  |                       | Leverantörsfakturadeklaration (IS)                   | Format för leverantörsfakturadeklaration för Island                      |
|                                                  |                       | Rapport över leverantörsfakturadeklaration (IS)            | Rapport över leverantörsfakturadeklaration för Island                      |

## <a name="additional-resources"></a>Ytterligare resurser

- [Skapa en konfiguration för elektronisk rapportering (ER)](electronic-reporting-configuration.md)
- [Hantera livscykeln för konfiguration av elektronisk rapportering (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)
