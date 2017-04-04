---
title: "Översikt över elektronisk rapportering"
description: "I den här artikeln finns en översikt över verktyget Elektronisk rapportering (ER). Den innehåller information om huvudkoncepten, scenarier som ER stöder och en lista över format som har utformats och lanserats som en del av lösningen."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: b3e8174d07c9b9fd4210486c369c640fe07c49eb
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-overview"></a>Översikt över elektronisk rapportering

I den här artikeln finns en översikt över verktyget Elektronisk rapportering (ER). Den innehåller information om huvudkoncepten, scenarier som ER stöder och en lista över format som har utformats och lanserats som en del av lösningen.

Elektronisk rapportering (ER) är ett verktyg du kan använda för att konfigurera format för elektroniska dokument i enlighet med de rättsliga kraven i olika länder/regioner. Med hjälp av ER kan du hantera dessa format under deras livscykel. Du kan exempelvis tillämpa nya lagkrav och generera affärsdokument i de format som krävs för elektroniskt informationsutbyte med myndigheter, banker och andra parter. ER-motorn riktar sig till företagsanvändare, i stället för till utvecklare. Eftersom du kan konfigurera formaten, men inte koden, är processerna för att skapa och ändra format på elektroniska dokument snabbare och enklare. ER stöder för närvarande formaten TEXT, XML och OPENXML-kalkylblad. Ett tilläggsgränssnitt kan dock ge stöd för fler format.

## <a name="capabilities"></a>Funktioner
ER-motorn har följande funktioner:

-   Den representerar ett enskilt vanliga verktyg för elektronisk rapportering i olika domäner och ersätter mer än 20 olika sökmotorer som utför någon typ av elektronisk rapportering till Microsoft Dynamics 365 för operationer.
-   Gör ett rapportformat isolerade från aktuellt Dynamics 365 för genomförande av åtgärder. (D.v.s. formatet gäller för olika versioner av Dynamics 365 för operationer.)
-   Den har stöd för att skapa ett anpassat format som är baserat på ett originalformat. Den innehåller funktioner för automatisk uppdatering av det anpassade formatet när ändringar av ursprungsformatet införs på grund av att nya lokaliserings-/anpassningskrav uppstår.
-   Det kommer att vara det primära standardverktyget för att stödja lokaliseringskrav vid elektronisk rapportering – både för Microsoft samt för Microsofts partners.
-   Den stöder funktionen för att distribuera format till partners och kunder via Microsoft Dynamics Lifecycle Services (LCS).

## <a name="concepts"></a>Begrepp
### <a name="components"></a>Komponenter

ER stöder två typer av komponenter: **Datamodell **och **Format **.

#### <a name="data-model-components"></a>Datamodellkomponenter

En datamodellkomponent är en abstrakt representation av en datastruktur och används för att beskriva ett specifikt arbetsdomänområde tillräckligt detaljerat för att uppfylla rapporteringskraven för respektive domän. En datamodellkomponent för omfattar följande delar:

-   En datamodell som en uppsättning domänspecifika affärsenheter och en hierarkiskt strukturerad definition av relationer mellan dem
-   En modell mappning att länkar markerade Dynamics 365 för operationer datakällor i enskilda delar av en datamodell anger vid körning dataflödet och reglerna för business datapopulationen till en värdemodell komponent.

En affärsenhet av datamodellen representeras som en behållare (post). Affärsenhetsegenskaper återges som dataobjekt (fält). Varje dataobjekt har unikt namn, etikett, beskrivning och värde. Värdet på varje dataobjekt kan vara utformat så att det tolkas som en sträng, ett heltal, ett realtal, ett datum, en uppräkningstyp, ett booleskt värde och så vidare. Dessutom kan det vara en annan post eller lista över poster. En enskild datamodellkomponent kan innehålla flera hierarkier av domänspecifika affärsenheter och även modellmappningar som stöder ett visst rapportspecifikt dataflöde vid körning. Hierarkierna särskiljs av en enda post som har valts som rot för modellmappningen. Datamodellen för betalningsdomänområdet kan exempelvis stödja följande mappningar:

-   Företag -&gt; leverantör -&gt; betalningstransaktioner på AP-domän
-   Kund -&gt; företag -&gt; betalningstransaktioner på domänen AR

Observera att affärsenheter (såsom företags- och betalningstransaktioner) skapas en gång. Olika mappningar återanvänder sedan dem. En modellmappning har följande funktioner:

-   Den kan använda olika Dynamics 365 för operationer datatyper som datakällor för en datamodell. Den kan exempelvis använda tabeller, datatabeller, metoder eller fasttext.
-   Den har stöd för användardefinierade indataparametrar som kan definieras som datakällor för datamodeller när vissa data måste specificeras vid körning.
-   Transformering av Dynamics 365 stöd för operationer i obligatoriska grupper, filtrera, sortera och summera data och även bifoga med logiska beräknade fält som via Microsoft Excel-formler (Mer information finns i [formeldesigner elektronisk rapportering av](general-electronic-reporting-formula-designer.md)).

[![Excel-liknande formeln editor](./media/pic-formula-1024x615.png)](./media/pic-formula.png) en komponent för data-modellen har utformats för business domänerna som ska användas som datakälla för rapportering av enhetliga som isolerar rapportering av fysiska genomförandet av Dynamics 365 för operationer datakällor och representerar domän-specifika begrepp och funktioner i ett formulär som gör en rapporteringsformulär första utformningen och ytterligare Underhåll mer effektivt.

#### <a name="format-components"></a>Formatkomponenter

En formatkomponent är schemat för de rapporteringsutdata som genereras vid körning. Ett schema består av följande element:

-   ett format som definierar strukturen och innehållet i det elektroniska rapporteringsdokumentet som genereras vid körning
-   datakällor som en uppsättning användardefinierade indataparametrar och en domänspecifik datamodell som använder en vald modellmappning
-   en formatmappning som en uppsättning bindningar av formatdatakällor som har vissa element i ett format som vid körning specificerar dataflödet och reglerna för formatets utdatagenerering
-   en formatvalidering som en uppsättning konfigureringsbara regler som styr genereringen av rapporten vid körning, beroende på körsammanhanget (till exempel en regel som stoppar utdatagenerering av en leverantörsbetalningar och kastar ett undantag när särskilda attribut för den valda leverantören saknas, till exempel bankkontonummer).

En formatkomponent har stöd för följande funktioner:

-   skapa rapporteringsutdata som enskilda filer i olika format såsom text, XML eller kalkylblad
-   skapa flera filer separat och även packa filerna i zip-filer.

En formatkomponent innehåller en funktion för att bifoga vissa filer som kan användas i rapporteringsutdata:

-   Excel-arbetsböcker som innehåller ett kalkylblad som kan användas som en mall för utdata i OPENXML-kalkylbladsformat
-   andra filer som kan ingå i formatets utdata som fördefinierade filer.

#### <a name="component-versioning"></a>Komponentversionsnumrering

Versionsnumrering stöds för ER-komponenter. Följande arbetsflöde tillhandahålls för att hantera ändringar i ER-komponenter:

-   Den version som ursprungligen skapades är markerad som en **UTKAST**-version. Den här versionen kan redigeras och är tillgänglig för provkörningar.
-   En **UTKAST**-version kan konverteras till en **SLUTFÖRD**-version. Den här versionen kan användas i lokala rapporteringsprocesser.
-   Den **SLUTFÖRD** version kan konverteras till ett **delade** version. Den här versionen publiceras på LCS och kan användas i global rapportering processer.
-   En **DELAD** version kan konverteras till en **AVSLUTAD** version. Den här versionen kan sedan tas bort.

Versioner som har antingen ** ** SLUTFÖRD eller **delade** status som är tillgängliga för andra dataöverföring. Det går att utföra följande åtgärder på en komponent som har dessa statusvärden:

-   De kan serialiseras i XML-format och exporteras från Dynamics 365 för åtgärder som en fil i XML-format.
-   De kan reserialized från en XML-fil och importeras till Dynamics 365 för åtgärder som en ny version av en komponent för ER.

#### <a name="component-date-effectivity"></a>Komponent giltighetsdatum

ER-komponentversionerna har giltighetsdatum. **Gäller från**-datumet kan definieras för en ER-komponent för att ange från och med vilket datum komponenten ska aktiveras för rapporteringsprocesser. Dynamics 365 för operationer sessionsdatum används för att bestämma om en komponent är giltig för körning. Den senaste versionen används för rapporteringsprocesser om fler än en version är giltig för ett visst datum.

#### <a name="component-access"></a>Åtkomsten till komponenter

Åtkomsten till ER-formatkomponenter beror på inställningen för ISO-lands-/regionskod. När den här inställningen är tomt för en vald version av en formatkonfigurationen kan en del format nås från alla Dynamics 365 för operationer företag vid körning. När den här inställningen innehåller ISO-koder för land/region, är en komponent i formatet bara tillgängligt från Dynamics 365 för operationer företag som har en primär adress som har definierats för något av formatet komponentens ISO-koder för land/region. Olika versioner av en dataformatkomponent kan ha olika inställningar för ISO-lands-/regionskoder.

#### <a name="configuration"></a>Konfiguration

En ER-konfiguration är omslag för en viss ER-komponent: antingen **Datamodell** eller **Format**. En konfiguration kan omfatta olika versioner av en viss ER-komponent. Varje konfiguration markeras som ägs av en viss konfiguration tillhandahåller. Den **utkast** version av en komponent i en konfiguration kan redigeras när du har valt äger konfigurationen som en aktiv provider i ER inställningarna i Dynamics 365 för operationer. Varje modellkonfiguration innehåller en **Datamodell**-komponent. En ny formatkonfiguration har sitt ursprung i (kan härledas från) en specifik datamodellskonfiguration. Formatkonfigurationen som skapas presenteras i konfigurationsträdet som underordnad till den ursprungliga datamodellskonfigurationen. Formatkonfigurationen som skapas innehåller en **Format**-komponent. **Datamodell**-komponenten i den ursprungliga modellkonfigurationen infogas automatiskt i **Format**-komponenten för den underordnade formatkonfigurationen som en standarddatakälla. En konfiguration av ER delas för Dynamics 365 för operationer företag.

#### <a name="provider"></a>Leverantör

ER-leverantören är partens identifierare som används för att indikera författare (ägare) av varje ER-konfiguration. Med hjälp av ER kan du hantera listan över konfigurationsleverantörer. Formatera konfigurationer som skall övergå till elektroniska dokument som en del av Dynamics 365 lösning för operationer som markeras som ägs av den **Microsoft** konfigurationstjänst.

#### <a name="repository"></a>Databas

En ER-databas lagrar ER-konfigurationer. Följande typer av ER databaser stöds: **operationsresurser** och **LCS projektet**. En ** operationer resurser ** databasen hittar du listan över konfigurationer som tillhandahålls av Microsoft som en ER konfigurationstjänst tillhör Dynamics 365 för operationer. Dessa konfigurationer kan importeras till aktuellt Dynamics 365 för operationer och används för elektronisk rapportering. De kan också användas för ytterligare lokaliseringar/anpassningar. En **LCS-projekt**-databas ger åtkomst till listan över konfigurationerna för ett visst LCS-projekt (tillgångsbibliotek för LCS-projekt) som valdes i registreringssteget för databasen. ER kan du överföra delade konfigurationer från aktuellt Dynamics 365 för operationer instans till en särskild **LCS projektet** databasen. Du kan också importera konfiguration från en viss **LCS projekt** till aktuellt Dynamics 365 operationer för databasen. Nödvändig **LCS projektet** databaser kan registreras separat för varje provider för konfiguration av aktuellt Dynamics 365 för operationer instans. Varje databas kan reserveras för en viss konfigurationsleverantör.

## <a name="supported-scenarios"></a>Stödda scenarier
### <a name="building-a-data-model"></a>Bygga en datamodell

ER erbjuder en modelldesigner som kan användas för att bygga en datamodell för en viss affärsdomän. Alla domänspecifika företagsenheter och relationerna mellan dem kan presenteras i en datamodell som en hierarkisk struktur. Följande illustration visar ett exempel på den här typen av datamodell (för betalningsdomän). [![Exempel på en datamodell](./media/pic-data-model-1024x550.png)](./media/pic-data-model.png) för att bekanta dig med information om det här scenariot, spela den **ER Design domänmodell specifika data** aktivitet guide (ingår i den **7.5.4.3 hämta/ta fram IT service/komponenter (10677)** affärsprocess).

### <a name="translating-data-model-content"></a>Översätta datamodellens innehåll

Modellen datainnehållet (beskrivningar och etiketter) kan översättas till andra språk som stöds i Dynamics 365 för operationer. Du kanske vill översätta datamodellens innehåll av följande skäl:

-   om du vid designtillfället vill göra innehållet mer begripligt för designers som talar andra språk och som ska använda en datamodell för datamappning av formatkomponenter
-   Vid körtid att göra vad mer användarvänligt genom att visa en prompt och för körning parametrar och verifieringsmeddelanden (fel och varningar) också är konfigurerad på det språk som den inloggade Dynamics 365 för operationer användare föredrar

Följande illustration visar ett exempel på hur datamodellens innehåll kan översättas från engelska till japanska. [![Innehåll på engelska för modellering av data](./media/pic-translate-en-1024x495.png)](./media/pic-translate-en.png)[![modell Data översätts till japanska innehåll](./media/pic-translate-ja-1024x495.png)](./media/pic-translate-ja.png)

### <a name="configuring-data-model-mappings"></a>Konfigurera datamodellmappningar

ER ger en modell mappning designer där användaren rör specifika Dynamics 365 för operationer datakällor datamodeller som de har skapats. Följande illustration visar ett exempel på en sådan datamodellmappning (modellmappning av **SEPA-kreditöverföring** i datamodellen för betalningsdomänen). [![Exempel på en datamappning modell ](./media/pic-model-mapping-1024x551.png)](./media/pic-model-mapping.png)för att bekanta dig med information om det här scenariot, spela den **modell ER definierar datakällor mappning och väljer** och **ER karta datamodellen till markerade datakällor** aktiviteter stödlinjerna (ingår i den **7.5.4.3 hämta/ta fram IT service/komponenter (10677)** affärsprocess).

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Spara en skapad modellkomponent som en modellkonfiguration

En datamodell utformad tillsammans med tillhörande datamappningar lagra ER som en konfiguration av aktuellt Dynamics 365 för operationer instans. Följande illustration visar ett exempel på den här typen av datamodellkonfiguration (betalningsmodellskonfiguration). [![Exempel på en konfiguration av data ](./media/pic-model-configuration-1024x585.png)](./media/pic-model-configuration.png)om du vill bekanta dig med information om det här scenariot, spela den **ER karta datamodellen till markerade datakällor** aktivitet guide (ingår i den **7.5.4.3 hämta/ta fram IT service/komponenter (10677)** affärsprocess).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Skapa ett format som använder en datamodell som bas

ER stöder en formatdesigner som kan användas för att skapa formatet på ett visst elektroniskt dokument för en vald affärsdomän genom att välja modellkomponenten som bas. Med hjälp av samma ER-formatdesigner kan du mappa formatet du skapar till en vald domäns datamodellmappning som en datakälla. I följande illustration visas ett exempel på den här typen av format (formatkonfigurationen som stöder **BACS**-betalningsformatet för Storbritannien). [![Exempel på ett format med en datamodell som bas](./media/pic-format-1024x690.png)](./media/pic-format.png) om du vill bekanta dig med information om det här scenariot, spela den **ER Design domän specifikt format** aktivitet guide (ingår i den **7.5.4.3 hämta/ta fram IT service/komponenter (10677)** affärsprocess).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Skapa en konfiguration för att generera elektroniska dokument i OPENXML-kalkylbladsformat

Formatdesigner för ER kan användas för att skapa ett visst elektroniskt dokument i OPENXML-kalkylbladsformat. Följande bild visar ett exempel på denna typ av format (en formatkonfigurationen att generera OPENXML-kalkylblad med information om den valda betalningsjournalen):[![Pic-ER format-Excel](./media/pic-er-format-excel.jpg)](./media/pic-er-format-excel.jpg) om du vill bekanta dig med information om det här scenariot, spela den **ER skapa en konfiguration för rapporter i OPENXML-format** aktivitet guide (ingår i den **7.5.4.3 hämta/ta fram IT service/komponenter (10677)** affärsprocess). Använda Hänvisad under Excel-fil som en mall av formatet utformning ER för att slutföra ett steg i ett format mall import av handboken uppgift: [mall för betalningsrapport (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Spara en skapad formatkomponent i en formatkonfiguration

ER lagra ett designade format tillsammans med konfigurerade datamappningar som en formatkonfigurationen av aktuellt Dynamics 365 för operationer instans. I föregående illustration visas ett exempel på denna typ av konfiguration för format (**BACS (UK)**, som är underordnad konfigurationen för **Betalningsmodell**). Spela upp ER-uppgiftsguiden för **Skapa domänspecifika format** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="configuring-dynamics-365-for-operations-to-start-to-use-a-created-format-internally"></a>Konfigurera Dynamics 365 att använda ett format som skapade internt

Dynamics 365 för operationer kan konfigureras så att de börjar använda formatet skapade elektroniska rapporter ska skapas. Hänvisningen till den skapade formatkonfigurationen ska definieras i inställningarna för en viss domän. Exempelvis om du vill börja använda en ER formatkonfigurationen för elektroniska leverantörsbetalningar BACS format ska formatkonfigurationen refereras till i specifika betalningsmetoder, enligt bilderna nedan: 

[![Formatkonfigurationen BACS (UK)](media/ger-bacs-uk-format-configuration.png) 

[![Referera till formatet i en betalningsmetod BACS (UK)](media/ger-bacs-uk-format-method.png) 

Spela upp ER-uppgiftsguiden **Använda format för att generera elektroniska dokument för betalningar** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i detta scenario.

## <a name="handling-er-components"></a>Hantera ER-komponenter
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publicera en ER-komponent i LCS så att den kan användas externt (lokalisering)

Ägaren av en skapad komponent (modell eller format) kan använda ER för att publicera den färdiga versionen av en komponent i LCS. Det krävs en databas av typen **LCS-projekt** för den aktuella ER-konfigurationsleverantören. När statusen för den slutgiltiga versionen av en komponent ändras från **AVSLUTAD** till **DELAD** publiceras den versionen i LCS. När en komponent har publicerats i LCS blir ägaren av komponenten ansvarig för att uppdatera komponenten. Om formatkomponenten exempelvis utformas för att generera ett rättsligt obligatoriskt elektroniskt dokument (t.ex. i enlighet med lokaliseringsscenario) förmodas det att formatet uppdateras så att det överensstämmer med lagändringar och att leverantören publicerar nya versioner av komponenten när nya lagkrav uppstår. Spela upp ER-uppgiftsguiden för **Överför en konfiguration i Lifecycle Services** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importera en ER-komponent från LCS och använda den internt

ER kan du importera ER komponenter från LCS till aktuellt Dynamics 365 för operationer instans. Det krävs en databas av typen **LCS-projekt ** för detta. När komponenten ER importerades från LCS till aktuellt Dynamics 365 för operationer instans blir ägare till instansen som en konsument av tjänsten som tillhandahålls av ägaren (författaren) för importerade komponenten. Till exempel om en komponent i formatet är utformad att generera ett visst elektroniska dokument från Dynamics 365 för operationer i formatet för lands-/ regionspecifika (lokalisering scenariot), förutsätts att tjänsten konsumenten få några uppdateringar som görs i detta format, så att den uppfyller de krav i lagstiftningen. Spela upp ER-uppgiftsguiden för **Importera en konfiguration från Lifecycle Services** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot.

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Att bygga ett format att välja ett annat format som bas (anpassning)

Med hjälp av ER kan du skapa (härleda) en ny komponent från den aktuella versionen av en komponent (bas) som importerats från LCS. En användare vill kanske härleda ett nytt format för att införa vissa särskilda krav för ett elektroniskt dokument (t.ex. ett extra fält eller en omfattande beskrivning) så att det stöder ett anpassningsscenario. Spela upp ER-uppgiftsguiden **Uppdatera format genom att tillämpa en ny grundversion av det** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i detta scenario.

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Uppgradering av ett format att välja en ny version av format (ändra basåren)

Med hjälp av ER kan du införa ändringar av den senaste versionen av baskomponenten automatiskt i den aktuella utkastversionen av den härledda komponenten. Den här processen kallas för *ombasering*. En ny regeländring som infördes i den senaste versionen av formatet som importerades från LCS kan exempelvis sammanfogas automatiskt i den anpassade versionen av detta format för elektroniska dokument. Ändringar som inte kan sammanfogas automatiskt anses vara konflikter. Konflikterna presenteras för manuell lösning i designerverktyget för lämplig komponent. Spela upp ER-uppgiftsguiden **Uppdatera format genom att tillämpa en ny grundversion av det** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i detta scenario.

## <a name="list-of-er-configurations-that-are-delivered-in-the-dynamics-365-for-operations-solution"></a>Lista över ER konfigurationer som levereras i Dynamics 365 för operationer
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


