---
title: "Översikt över elektronisk rapportering"
description: "I den här artikeln finns en översikt över verktyget Elektronisk rapportering (ER). Den innehåller information om huvudkoncepten, scenarier som ER stöder och en lista över format som har utformats och lanserats som en del av lösningen."
author: kfend
manager: AnnBe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: cebd1b6f041e18c2e016142aba7447bf813f570b
ms.openlocfilehash: f6327b339441f2f1f6d4e557e45d085685245a08
ms.contentlocale: sv-se
ms.lasthandoff: 06/19/2017


---

# <a name="electronic-reporting-overview"></a>Översikt över elektronisk rapportering

[!include[banner](../includes/banner.md)]


Det här ämnet ger en översikt till verktyget Elektronisk rapportering (ER). Den innehåller information om huvudkoncepten, scenarier som ER stöder och en lista över format som har utformats och lanserats som en del av lösningen.

Elektronisk rapportering (ER) är ett verktyg du kan använda för att konfigurera format för såväl inkommande som utgående elektroniska dokument i enlighet med de rättsliga kraven i olika länder/regioner. Med hjälp av ER kan du hantera dessa format under deras livscykel. Du kan exempelvis tillämpa nya lagkrav och generera affärsdokument i de format som krävs för elektroniskt informationsutbyte med myndigheter, banker och andra parter.

ER-motorn riktar sig till företagsanvändare, i stället för till utvecklare. Eftersom du kan konfigurera formaten istället för koden blir processerna för att skapa och ändra format på elektroniska dokument snabbare och enklare.

ER stöder för närvarande formaten TEXT, XML, Microsoft Word-dokument samt OPENXML-kalkylblad. Ett tilläggsgränssnitt kan dock ge stöd för ytterligare format.

## <a name="capabilities"></a>Funktioner
ER-motorn har följande funktioner:

- Det representerar ett enskilt, delat verktyg som kan användas för elektronisk rapportering i olika domäner och ersätter fler än 20 olika motorer som används för någon form av elektronisk rapportering för Microsoft Dynamics 365 for Operations.
- Den skapar ett rapportformat utanför den aktuella Dynamics 365 for Operations-implementeringen. Formatet är med andra ord tillämpligt för olika versioner av Dynamics 365 for Operations.
- Den har stöd för att skapa ett anpassat format som är baserat på ett originalformat. Det innehåller även funktioner för automatisk uppdatering av det anpassade formatet när ursprungsformatet ändras på grund av nya lokaliserings-/anpassningskrav.
- Det kommer att vara det primära standardverktyget för att stödja lokaliseringskrav vid elektronisk rapportering – både för Microsoft samt för Microsofts partners.
- Den stöder funktionen för att distribuera format till partners och kunder via Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Viktiga begrepp
### <a name="components"></a>Komponenter

ER stöder två typer av komponenter: **Datamodell** och **Format**.

#### <a name="data-model-components"></a>Datamodellkomponenter

En datamodellskomponent är en abstrakt representation av en datastruktur. Den används för att beskriva domänen för ett visst affärsområde tillräckligt detaljerat för att uppfylla rapporteringskraven för domänen. En datamodellkomponent för omfattar följande delar:

- En datamodell som en uppsättning domänspecifika affärsenheter och en hierarkiskt strukturerad definition av relationer mellan dem.
- En modellmappning som länkar valda Dynamics 365 for Operations-datakällor till enskilda element i en datamodell som vid körning specificerar dataflödet och reglerna för population av affärsdata till datamodellkomponenten.
En affärsenhet av datamodellen representeras som en behållare (post). Affärsenhetsegenskaper återges som dataobjekt (fält). Varje dataobjekt har ett unikt namn, en unik etikett, en unik beskrivning och ett unikt värde. Värdet på respektive dataobjekt kan vara utformat så att det tolkas som en sträng, ett heltal, ett realtal, ett datum, en uppräkning, ett booleskt värde och så vidare. Dessutom kan det vara en annan post eller lista över poster.

En enskild datamodellskomponent kan innehålla flera hierarkier av domänspecifika affärsenheter. Den kan också innehålla modellmappningar som har stöd för ett rapportspecifikt dataflöde vid körning. Hierarkierna särskiljs av en enda post som har valts som rot för modellmappningen. Datamodellen för betalningsdomänområdet kan exempelvis stödja följande mappningar:

- Företag > Leverantör > Betalningstransaktioner i AP-domänen
- Kund > Företag > Betalningstransaktioner i AR-domänen

Observera att affärsenheter såsom företags- och betalningstransaktioner skapas en gång. Olika mappningar återanvänder sedan dem.

En modellmappning som har stöd för utgående elektroniska dokument har följande funktioner:

- Den kan använda olika typer av Dynamics 365 for Operations-datatyper som datakällor för en datamodell. Den kan exempelvis använda tabeller, datatabeller, metoder eller fasttext.
- Den har stöd för användardefinierade indataparametrar som kan definieras som datakällor för datamodeller när vissa data måste specificeras vid körning.
- Den stöder transformeringen av Dynamics 365 for Operations-data till erforderliga grupper. Dessutom kan du filtrera, sortera och summera data, samt lägga till logiska, beräknade fält som utformas via formler som liknar Microsoft Excel-formler, vilket visas i följande illustration. Mer information finns i [Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)).

[![Formeldesigner](./media/ER-overview-01.png)](./media/ER-overview-01.png) 

En modellmappning som har stöd för inkommande elektroniska dokument har följande funktioner:

- Den kan använda olika uppdaterbara dataelement för Dynamics 365 for Operations som mål. Dessa dataelement inkluderar tabeller, dataenheter och vyer. Datan kan uppdateras med data från inkommande elektroniska dokument. Flera mål kan användas i en enda modellmappning.
- Den har stöd för användardefinierade indataparametrar som kan definieras som datakällor för datamodeller när vissa data måste specificeras vid körning.
En datamodellskomponent har utformats för respektive företagsdomän som ska användas som en enhetlig datakälla för rapportering som isolerar rapporterna från den fysiska implementeringen av datakällor för Dynamics 365 for Operations. Den representerar domänspecifika affärsbegrepp och -funktioner i ett formulär som utgör ett rapporteringsformulärs ursprungliga konstruktion och vidare underhåll effektivare.

#### <a name="format-components-for-outgoing-electronic-documents"></a>Formatkomponenter för utgående elektroniska dokument

En formatkomponent är schemat för de rapporteringsutdata som genereras vid körning. Ett schema består av följande element:

- Ett format som definierar strukturen och innehållet i det utgående elektroniska dokument som genereras vid körning.
- Datakällor som en uppsättning parametrar för användarindata och en domänspecifik datamodell som använder en vald modellmappning.
- En formatmappning som en uppsättning bindningar av formatdatakällor som har vissa element i ett format som vid körning specificerar dataflödet och reglerna för formatets utdatagenerering.
- En formatvalidering som en uppsättning konfigurerbara regler som kontrollerar rapportgenereringen vid körning beroende på löpande kontext. Det kan exempelvis finnas en regel som stoppar utgående generering av en viss leverantörs betalningar, och som genererar ett undantag när specifika attribut för den valda leverantören saknas, till exempel bankkontonummer.

En formatkomponent har stöd för följande funktioner:

- Skapa rapporteringsutdata som enskilda filer i olika format, till exempel text, XML, Microsoft Word-dokument eller kalkylblad.
- Skapa flera filer separat och även packa filerna i zip-filer.

En formatkomponent låter dig bifoga vissa filer som kan användas i rapporteringsutdatan:

- Excel-arbetsböcker som innehåller ett kalkylblad som kan användas som en mall för utdata i OPENXML-kalkylbladsformat
- Word-filer som innehåller ett dokument som kan användas som en mall för utdata i Microsoft Word-dokumentformat
- andra filer som kan ingå i formatets utdata som fördefinierade filer.

Följande bild visar hur datan flödar för dessa format.

[![Dataflöde för utgående formatkomponenter](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Du måste identifiera mappningen av formatkonfigurationen för att kunna köra en enskild ER formatkonfiguration och generera utgående elektroniska dokument.

#### <a name="format-components-for-incoming-electronic-documents"></a>Formatkomponenter för inkommande elektroniska dokument
En formatkomponent är schemat för de inkommande dokument som importeras vid körning. Ett schema består av följande element:

- Ett format som definierar strukturen och innehållet i de inkommande elektroniska dokument som innehåller data som importeras vid körning. En formatkomponent används för att tolka ett inkommande dokument i olika format, till exempel text och XML.
- En formatmappning som binder enskilda formatelement till element i en domänspecifik datamodell. Vid körning anger elementen i datamodellen dataflödet och reglerna för import av data från ett inkommande dokument, och spara sedan datan i en datamodell.
- En formatvalidering som en uppsättning konfigurerbara regler som kontrollerar dataimporten vid körning, beroende på körningskontexten. Det kan exempelvis finnas en regel som stoppar dataimporten av ett bankutdrag med en viss leverantörs betalningar, och som genererar ett undantag när attributen för en specifik leverantör saknas, till exempel ID-koden för leverantören.

Följande bild visar hur datan flödar för dessa format.

[![Dataflöde för inkommande formatkomponenter](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Om du vill köra en enskild ER formatkonfiguration för att importera data från ett inkommande elektroniskt dokument måste du identifiera önskad mappning för en formatkonfiguration, samt även integreringspunkten för en modellmappning. Du kan använda samma modellmappning och destinationer tillsammans med olika format för olika typer av inkommande dokument.

#### <a name="component-versioning"></a>Komponentversionsnumrering

Versionsnumrering stöds för ER-komponenter. Följande arbetsflöde tillhandahålls för att hantera ändringar i ER-komponenter:

1. Den version som ursprungligen skapades är markerad som en **Utkast**-version. Den här versionen kan redigeras och är tillgänglig för provkörningar.
2. **Utkast**-versionen kan konverteras till en **Slutförd** version. Den här versionen kan användas i lokala rapporteringsprocesser.
3. Den **Slutförda** versionen kan konverteras till en **Delad** version. Denna version publiceras på LCS och kan användas inom globala rapporteringsprocesser.
4. **Delad**-versionen kan konverteras till en **Avslutad** version. Den här versionen kan sedan tas bort.

Versioner som har statusen **Slutförd** eller **Delad** är tillgängliga för annan dataöverföring. Följande åtgärder kan utföras på en komponent som har dessa statusvärden:

- Komponenten kan serialiseras i XML-format och exporteras från Dynamics 365 for Operations som en XML-fil.
- Komponenten kan omserialiseras från en XML-fil och importeras till Dynamics 365 for Operations som en ny version av en ER-komponent.

#### <a name="component-date-effectivity"></a>Komponent giltighetsdatum

ER-komponentversionerna har giltighetsdatum. Du kan ange **Gäller från**-datumet för en ER-komponent för att ange från och med vilket datum komponenten ska aktiveras för rapporteringsprocesser. Dynamics 365 for Operations-sessionsdatumet används för att definiera huruvida en komponent är giltig för utförande. Den senaste versionen används för rapporteringsprocesser om fler än en version är giltig för ett visst datum.

#### <a name="component-access"></a>Åtkomsten till komponenter

Åtkomsten till ER-formatkomponenter beror på inställningen för ISO-lands-/regionskod. När den här inställningen lämnas tom för en vald version av en formatkonfiguration, kan en formatkomponent nås från vilket Dynamics 365 for Operations-företag som helst vid körning. När inställningen innehåller ISO-koder för lands-/regionskoder är formatkomponenten endast tillgänglig från Dynamics 365 for Operations-företag som har en primäradress som har definierats för en av en formatkomponents ISO-kod för land/region.

Olika versioner av en dataformatkomponent kan ha olika inställningar för ISO-lands-/regionskoder.

#### <a name="configuration"></a>Konfiguration

En ER-konfiguration är omslaget (wrappern) för en viss ER-komponent. Komponenten kan antingen vara en datamodellskomponent eller en formatkomponent. En konfiguration kan omfatta olika versioner av en ER-komponent. Varje konfiguration markeras som ägda av en viss konfigurationsleverantör. **Utkast**-versionen av en komponent i en konfiguration kan redigeras om ägaren till konfigurationen har valts som en aktiv leverantör i ER-inställningarna i Dynamics 365 for Operations.

Varje modellkonfiguration innehåller en datamodellskomponent. En ny formatkonfiguration har sitt ursprung i (kan härledas från) en specifik datamodellskonfiguration. Formatkonfigurationen som skapas anges i konfigurationsträdet som underordnad till den ursprungliga datamodellskonfigurationen.

Formatkonfigurationen som skapas innehåller en formatkomponent. Datamodellkomponenten i den ursprungliga modellkonfigurationen infogas automatiskt i formatkomponenten för den underordnade formatkonfigurationen som en standarddatakälla.

En ER-konfiguration delas av Dynamics 365 for Operations-företag.

#### <a name="provider"></a>Leverantör

ER-leverantören är partens identifierare som används för att indikera författare (ägare) av varje ER-konfiguration. Med hjälp av ER kan du hantera listan över konfigurationsleverantörer. Formatkonfigurationer som släpps för elektroniska dokument som en del av Dynamics 365 for Operations-lösningen markeras som ägda av **Microsoft**-konfigurationsleverantören.

För information om hur du registrerar en ny ER-leverantör, kör uppgiftsguiden **ER skapa en konfigurationstjänst och markera den som aktiv** (ingår i affärsprocessen **7.5.4.3 Införskaffa/utveckla IT-tjänst/-lösningskomponenter (10677)**).

#### <a name="repository"></a>Databas

En ER-databas lagrar ER-konfigurationer. Två typer av ER-databaser stöds för närvarande: **Verksamhetsresurser** och **LCS-projekt**.

En databas för **Verksamhetsresurser** ger åtkomst till listan över konfigurationer som Microsoft frisläpper som en del av Dynamics 365 for Operations-lösningen i egenskap av ER-konfigurationsleverantör. Dessa konfigurationer kan importeras till den aktuella instansen av Dynamics 365 for Operations och användas för elektronisk rapportering. De kan också användas för ytterligare lokaliseringar och anpassningar.

En **LCS-projekt**-databas ger åtkomst till listan över konfigurationerna för ett visst LCS-projekt (tillgångsbibliotek för LCS-projekt) som valdes i registreringssteget för databasen. ER låter dig överföra delade konfigurationer från den befintliga Dynamics 365 for Operations-instansen till en specifik databas för **LCS-projekt**. Du kan även importera konfigurationer från en **LCS-projekt**-databas till den befintliga Dynamics 365 for Operations-instansen.

Obligatoriska **LCS-projekt**-databaser kan registreras separat för respektive konfigurationsleverantör av den aktuella Dynamics 365 for Operations-instansen. Varje databas kan reserveras för en viss konfigurationsleverantör.

## <a name="supported-scenarios"></a>Stödda scenarier
### <a name="building-a-data-model"></a>Bygga en datamodell

ER erbjuder en modelldesigner som kan användas för att bygga en datamodell för en viss affärsdomän. Alla domänspecifika företagsenheter och relationerna mellan dem kan presenteras i en datamodell som en hierarkisk struktur. Följande illustration visar ett exempel på den här typen av datamodell (för betalningsdomän). 

[![Datamodell för betalningsdomän](./media/ER-overview-04.png)](./media/ER-overview-04.png)

Spela upp ER-uppgiftsguiden **Skapa domänspecifik datamodell** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="translating-data-model-content"></a>Översätta datamodellens innehåll

Datamodellens innehåll (etiketter och beskrivningar) kan översättas till andra språk som stöds av Finance and Operations. Du kanske vill översätta datamodellens innehåll av följande skäl:

-   Vid designtillfället för att göra innehållet mer begripligt för formatdesigners som talar andra språk och som ska använda datamodellen för datamappning av formatkomponenter.
-   Vid körning för att göra innehållet mer användarvänligt genom att använda prompter och hjälp för körningsparametrar, samt konfigurerade valideringsmeddelanden (fel och varningar) på det språk som för tillfället inloggade användarna föredrar.

Följande illustration visar ett exempel där datamodellens innehåll översatts från engelska till japanska. 

[![Datamodellens innehåll på engelska](./media/ER-overview-05.png)](./media/ER-overview-05.png)

[![Datamodellens innehåll översatt till japanska](./media/ER-overview-06.png)](./media/ER-overview-06.png)


### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Konfigurera mappningar för datamodeller för utgående dokument

ER har en modellmappningsdesigner som låter användarna mappa datamodeller som de har utformat för specifika Finance and Operations-datakällor. Baserat på mappningen importeras datan vid körning från markerade datakällor till datamodellen. Datamodellen används sedan som en abstrakt datakälla för ER format som genererar utgående elektroniska dokument. Följande illustration visar ett exempel på en sådan datamodellmappning (modellmappning av **SEPA-kreditöverföring** i datamodellen för betalningsdomänen). 

[![Exempel på mappning av en datamodell](./media/ER-overview-07.png)](./media/ER-overview-07.png)

Spela upp ER-uppgiftsguiderna **Definiera modellmappning och välja datakällor** och **Mappa datamodell till valda datakällor** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Konfigurera mappningar för datamodeller för inkommande dokument
ER har en modellmappningsdesigner som låter användarna mappa datamodeller som de har utformat för specifika destinationer. Exempelvis kan datamodeller mappas till uppdateringsbara datakomponenter för Dynamics 365 for Operations (tabeller, dataenheter och vyer). Baserat på mappningen uppdateras Dynamics 365 for Operations vid körning med data från datamodellen. Som abstrakt lagring av ER formatet fylls datamodellen med data som importeras från ett inkommande elektroniskt dokument. Följande illustration visar ett exempel på den här typen av datamodellmappning. I det här exemplet används modellmappningen **Importera mappning för NETS** för betalningsdomänens datamodell för import av bankutdrag i bankformatet NETS för Norge.

[![Importera mappning för exemplet NETS-datamodell](./media/ER-overview-08.png)](./media/ER-overview-08.png)

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Spara en skapad modellkomponent som en modellkonfiguration

ER kan lagra en skapad datamodell tillsammans med tillhörande datamappningar som en modellkonfiguration för den aktuella Finance and Operations-instansen. Följande illustration visar ett exempel på den här typen av datamodellkonfiguration (betalningsmodellskonfiguration). 

Spela upp ER-uppgiftsguiden för **Mappa datamodell till valda datakällor** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Skapa ett format som använder en datamodell som bas

ER stöder en formatdesigner som kan användas för att skapa formatet för ett visst elektroniskt dokument för en vald affärsdomän genom att välja modellkomponenten som bas. Med hjälp av samma ER-formatdesigner kan du mappa formatet du skapar till en vald domäns datamodellmappning som en datakälla. I följande illustration visas ett exempel på den här typen av format (formatkonfigurationen som stöder **BACS**-betalningsformatet för Storbritannien). 

[![Exempel på ett format som använder en datamodell som bas](./media/ER-overview-09.png)](./media/ER-overview-09.png)

Spela upp ER-uppgiftsguiden för **Skapa domänspecifika format** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Skapa en konfiguration för att generera elektroniska dokument i OPENXML-kalkylbladsformat

ER-formatdesignern kan användas för att skapa ett elektroniskt dokument i OPENXML-kalkylbladsformat. I följande illustration visas ett exempel på denna typ av format (en formatkonfiguration för att generera OPENXML-kalkylblad med information om den valda betalningsjournalen).

[![Pic-ER-format-Excel](./media/ER-overview-10.png)](./media/ER-overview-10.png)

Spela upp ER-uppgiftsguiden för **Skapa en konfiguration för rapporter i OPENXML-format** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot. Som ett led i uppgiftsguiden för att importera en mall använder du Excel-filen [Mall för betalningsrapport (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202) som en mall.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Skapa en konfiguration för att generera elektroniska dokument i ett Word-dokumentformat
ER-formatdesignern kan användas för att skapa ett elektroniskt dokument i ett Word-dokumentformat. Följande illustration visar ett exempel på den här typen av format. Notera att detta format återanvänder den befintliga ER-konfigurationen som ursprungligen skapades för att generera rapportutdata i OPENXML-format.

[![Pic-ER-format-Word](./media/ER-overview-11.png)](./media/ER-overview-11.png)

Kör ER-uppgiftsguiden för Designa en konfiguration för att generera rapporter i Microsoft WORD-format (ingår i affärsprocessen 7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)) för att bekanta dig med detaljerna i det här scenariot. Använd följande Word-filer som mallar för ER-formatet som ett led i uppgiftsguidesteget för att importera en mall:

- [Mall för betalningsrapport (SampleVendPaymDocReport.docx)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Bunden mall för betalningsrapport (SampleVendPaymDocReportBounded.docx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Skapa en konfiguration för att importera data från inkommande elektroniska dokument  
ER-formatdesignern kan användas för att beskriva ett elektroniskt dokument som har planerats för dataimport i antingen text- eller XML-format. Det designade formatet används för att tolka ett inkommande dokument. Mappningsdesignern för ER-format kan användas för att definiera elementbindningen för det utformade formatet för datamodellen. Följande illustrationer visar ett exempel på den här typen av format och formatmappning. I det här exemplet importeras NETS-bankutdrag som innehåller information om leverantörsbetalningen i textformat.

[![ER-formatdesigner](./media/ER-overview-12.png)](./media/ER-overview-12.png)

[![ER-modell-mappningsdesigner](./media/ER-overview-13.png)](./media/ER-overview-13.png)

Kör uppgiftsguiden Skapa erforderlig ER för att importera data från en extern fil (ingår affärsprocessen 7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)) för att bekanta dig med detaljerna i det här scenariot. Använd följande filer för att köra den här guiden:

- [Konfiguration av ER-datamodell (1099model.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [ER-formatkonfiguration (1099model.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Exempel på det inkommande dokumentet i XML-format (1099entries.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Exempel på arbetsboken för att hantera data för inkommande dokument (1099entries.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Spara en skapad formatkomponent i en formatkonfiguration

ER kan spara ett utformat format tillsammans med de konfigurerade datamappningarna som en formatkonfiguration för den aktuella Finance and Operations-instansen. I föregående illustration visas ett exempel på denna typ av konfiguration för format (**BACS (UK)**, som är underordnad konfigurationen för **Betalningsmodell**). Spela upp ER-uppgiftsguiden för **Skapa domänspecifika format** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="configuring-finance-and-operations-to-start-to-use-a-created-format-internally"></a>Konfigurera Finance and Operations för att börja använda skapade format internt

Finance and Operations kan konfigureras för att börja använda ett skapat format för att generera elektroniska rapporter. Hänvisningen till den skapade formatkonfigurationen ska definieras i inställningarna för en viss domän. Om du exempelvis vill börja använda en ER-formatkonfiguration för elektroniska leverantörsbetalningar i BACS-format ska du referera till formatkonfigurationen i specifika betalningsmetoder, så som visas i följande illustrationer: 

[![Formatkonfigurationen BACS (Storbritannien)](./media/ER-overview-14.png)](./media/ER-overview-14.png)

[![Referera till BACS-formatet (Storbritannien) i en betalningsmetod](./media/ER-overview-15.png)](./media/ER-overview-15.png)

Spela upp ER-uppgiftsguiden **Använda format för att generera elektroniska dokument för betalningar** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i detta scenario.

## <a name="handling-er-components"></a>Hantera ER-komponenter
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publicera en ER-komponent i LCS så att den kan användas externt (lokalisering)

Ägaren av en skapad komponent (modell eller format) kan använda ER för att publicera den färdiga versionen av en komponent i LCS. Det krävs en databas av typen **LCS-projekt** för den aktuella ER-konfigurationsleverantören. När statusen för den slutgiltiga versionen av en komponent ändras från **AVSLUTAD** till **DELAD** publiceras den versionen i LCS. När en komponent har publicerats i LCS blir ägaren av komponenten ansvarig för att uppdatera komponenten. Om formatkomponenten exempelvis utformas för att generera ett rättsligt obligatoriskt elektroniskt dokument (t.ex. i enlighet med lokaliseringsscenario) förmodas det att formatet uppdateras så att det överensstämmer med lagändringar och att leverantören publicerar nya versioner av komponenten när nya lagkrav uppstår. Spela upp ER-uppgiftsguiden för **Överför en konfiguration i Lifecycle Services** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importera en ER-komponent från LCS och använda den internt

Med hjälp av ER kan du importera ER-komponenter från LCS till den aktuella Finance and Operations-instansen. Det krävs en databas av typen **LCS-projekt** för detta. När en ER-komponent har importerats från LCS till den aktuella Finance and Operations-instansen blir ägaren av instansen en konsument av den tjänst som tillhandahålls av ägaren (författaren) till den importerade komponenten. Om formatkomponenten exempelvis har utformats för att generera specifika elektroniska dokument från Finance and Operations i ett lands- eller regionsspecifikt format (lokaliseringsscenario), förmodas tjänstkonsumenten kunna hämta alla uppdateringar som görs i det formatet så att det uppfyller alla rättsliga krav. Spela upp ER-uppgiftsguiden för **Importera en konfiguration från Lifecycle Services** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Att bygga ett format att välja ett annat format som bas (anpassning)

Med hjälp av ER kan du skapa (härleda) en ny komponent från den aktuella versionen av en komponent (bas) som importerats från LCS. En användare vill kanske härleda ett nytt format för att införa vissa särskilda krav för ett elektroniskt dokument (t.ex. ett extra fält eller en omfattande beskrivning) så att det stöder ett anpassningsscenario. Spela upp ER-uppgiftsguiden **Uppdatera format genom att tillämpa en ny grundversion av det** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i detta scenario.

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Uppgradering av ett format att välja en ny version av format (ändra basåren)

Med hjälp av ER kan du införa ändringar av den senaste versionen av baskomponenten automatiskt i den aktuella utkastversionen av den härledda komponenten. Den här processen kallas för *ombasering*. En ny regeländring som infördes i den senaste versionen av formatet som importerades från LCS kan exempelvis sammanfogas automatiskt i den anpassade versionen av detta format för elektroniska dokument. Ändringar som inte kan sammanfogas automatiskt anses vara konflikter. Konflikterna presenteras för manuell lösning i designerverktyget för lämplig komponent. Spela upp ER-uppgiftsguiden **Uppdatera format genom att tillämpa en ny grundversion av det** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i detta scenario.

## <a name="list-of-er-configurations-that-are-delivered-in-the-finance-and-operations-solution"></a>Lista över ER-konfigurationer som levereras i Finance and Operations-lösningen
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



<a name="see-also"></a>Se även
--------

[Krav för lokalisering – Skapa en konfiguration för elektronisk rapportering](electronic-reporting-configuration.md)

[Hantera livscykeln för konfigurering av elektronisk rapportering](general-electronic-reporting-manage-configuration-lifecycle.md)




