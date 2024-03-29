---
title: Översikt över elektronisk rapportering (ER)
description: Det här ämnet ger en översikt till verktyget Elektronisk rapportering. Det beskriver viktiga begrepp, scenarier som stöds och format som är en del av lösningen.
author: kfend
ms.date: 11/02/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58941,  ""intro-internal
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.form: ERWorkspace
ms.openlocfilehash: e94846dd565abb6de2c1f07532d285e28307e9a2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269704"
---
# <a name="electronic-reporting-er-overview"></a>Översikt över elektronisk rapportering (ER)

[!include [banner](../includes/banner.md)]

Den här artikeln ger en översikt över verktyget Elektronisk rapportering (ER). Den innehåller information om huvudkoncepten, scenarier som ER stöder och en lista över format som har utformats och lanserats som en del av lösningen.

ER är ett konfigurerbart verktyg som hjälper dig att skapa och underhålla elektronisk rapportering och betalningar. Det baseras på följande tre koncept:

- Konfiguration i stället för kodning:

    - Konfiguration kan utföras av en företagsanvändare och ingen utvecklare krävs.
    - Datamodellen definieras i affärsvillkor.
    - Visuella redigerare används för att skapa alla komponenter i ER-konfigurationen.
    - Det språk som används vid datatransformeringen liknar det språk som används Microsoft Excel.

- En konfiguration för flera Dynamics 365 Finance versioner:

    - Hantera en domänspecifik datamodell som är definierad i affärsvillkor.
    - Frisläppningsdetaljer för tillämpad program i frisläppningsberoende datamodellmappningar.
    - Underhåll en formatkonfiguration för flera versioner av den aktuella versionen, baserat på datamodellen.

- Enkel eller automatisk uppgradering:

    - Versioner och ER-konfigurationer stöds.
    - Microsoft Dynamics Lifecycle Services-biblioteket (LCS) resursbiblioteket kan användas som databas för ER-konfigurationer för versionutbyte.
    - Lokaliseringar som baseras på ursprungliga ER-konfigurationer kan införas som underordnade versioner.
    - Ett ER-konfigurationsträd finns som ett verktyg för att kontrollera versioners beroenden.
    - Skillnader i localization, eller deltakonfigurationen, registreras för att aktivera automatisk uppgradering till en ny version av den ursprungliga ER-konfigurationen.
    - Det är enkelt att lösa konflikter som upptäcks vid automatisk uppgradering av lokaliseringsversioner.

ER låter dig definiera elektroniska formatstrukturer och sedan beskriva hur strukturerna ska fyllas i genom att använda data och algoritmer. Du kan använda ett receptspråk som liknar Excel-språket för datatransformeringen. För att göra mappningen i databasen till format mer hanterbar, återanvändningsbar och oberoende av formatändringar, införas ett mellanliggande datamodellbegrepp. Med detta begrepp kan implementeringsdetaljer döljas från formatmappningen och en enskild datamodell kan återanvändas för flera formatmappningar.

ER är ett verktyg du kan använda för att konfigurera format för såväl inkommande som utgående elektroniska dokument i enlighet med de rättsliga kraven i olika länder/regioner. Med hjälp av ER kan du hantera dessa format under deras livscykel. Du kan exempelvis tillämpa nya lagkrav och skapa affärsdokument i de format som krävs för elektroniskt informationsutbyte med myndigheter, banker och andra parter.

ER-motorn riktar sig till företagsanvändare, i stället för till utvecklare. Eftersom du kan konfigurera formaten istället för koden blir processerna för att skapa och ändra format på elektroniska dokument snabbare och enklare.

ER stöder för närvarande formaten TEXT, XML, JSON, PDF, Microsoft Word, Microsoft Excel och OPENXML kalkylblad.

## <a name="capabilities"></a>Funktioner

ER-motorn har följande funktioner:

- Den representerar ett enskilt delat verktyg för elektronisk rapportering inom olika domäner och ersätter fler än 20 olika motorer som används för någon form av elektronisk rapportering för Ekonomi och drift.
- Den skapar ett rapportformat utanför den aktuella implementeringen. Formatet är med andra ord tillämpligt för olika versioner.
- Den har stöd för att skapa ett anpassat format som är baserat på ett originalformat. Det innehåller även funktioner för automatisk uppdatering av det anpassade formatet när ursprungsformatet ändras på grund av nya lokaliserings-/anpassningskrav.
- Det kommer att vara det primära standardverktyget för att stödja lokaliseringskrav vid elektronisk rapportering – både för Microsoft samt för Microsofts partner.
- Den stöder funktionen för att distribuera format till partner och kunder via Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Viktiga begrepp

### <a name="main-data-flow"></a>Huvuddataflöde

[![ER-huvuddataflöde.](./media/ger-main-data-flow.jpg)](./media/ger-main-data-flow.jpg)

### <a name="component"></a>Komponent

ER stöder följande typer av komponenter:

- Datamodell
- Modellmappning
- Format
- Metadata

Mer information finns i [Komponenter för elektronisk rapportering](er-overview-components.md).

### <a name="configuration"></a><a name="Configuration"></a>Konfiguration

En ER-konfiguration är omslaget (wrappern) för en viss ER-komponent. Komponenten kan antingen vara en datamodellskomponent eller en formatkomponent. En konfiguration kan omfatta olika versioner av en ER-komponent. Varje konfiguration markeras som ägda av en viss konfigurationsleverantör. **Utkast**-versionen av en komponent i en konfiguration kan redigeras om ägaren av en konfiguration har valts som en aktiv leverantör i ER-inställningarna i programmet.

Varje modellkonfiguration innehåller en datamodellskomponent. En ny formatkonfiguration har sitt ursprung i (kan härledas från) en specifik datamodellskonfiguration. Formatkonfigurationen som skapas anges i konfigurationsträdet som underordnad till den ursprungliga datamodellskonfigurationen.

Formatkonfigurationen som skapas innehåller en formatkomponent. Datamodellkomponenten i den ursprungliga modellkonfigurationen infogas automatiskt i formatkomponenten för den underordnade formatkonfigurationen som en standarddatakälla.

En ER-konfiguration delas av programföretag.

### <a name="provider"></a><a name="Provider"></a>Leverantör

ER-leverantören är partens identifierare som används för att indikera författare (ägare) av varje ER-konfiguration. Med hjälp av ER kan du hantera listan över konfigurationsleverantörer. Formatkonfigurationer som släpps för elektroniska dokument som en del av Ekonomi och drift-lösningen markeras som ägda av konfigurationsleverantören **Microsoft**.

För information om hur du registrerar en ny ER-leverantör, kör uppgiftsguiden **ER skapa en konfigurationstjänst och markera den som aktiv** (ingår i affärsprocessen **7.5.4.3 Införskaffa/utveckla IT-tjänst/-lösningskomponenter (10677)**).

### <a name="repository"></a><a name="Repository"></a>Databas

En ER-databas lagrar ER-konfigurationer. Följande typer av ER-databaser stöds för närvarande: 

- Delat LCS-bibliotek
- LCS-projekt
- Filsystem
- RCS
- Operations-resurser
- Global databas

En databas för **delat LCS-bibliotek** ger dig listan över konfigurationer i det delade tillgångsbiblioteket i Lifecycle Services (LCS). Den här typen av ER-databas kan endast registreras för Microsoft-leverantören. Från det delade LCS-tillgångsbiblioteket kan du importera de senaste versionerna av ER-konfigurationer till den aktuella instansen.

En **LCS-projekt**-databas ger åtkomst till listan över konfigurationerna för ett visst LCS-projekt (tillgångsbibliotek för LCS-projekt) som valdes när databasen registrerades. ER låter dig överföra delade konfigurationer från den befintliga instansen till en specifik databas för **LCS-projekt**. Du kan även importera konfigurationer från en **LCS-projekt**-databas till den befintliga instansen av dina appar för ekonomi och drift.

En **Filsystem**-datalager ger åtkomst till listan över konfigurationer som finns som XML-filer i en viss mapp i det lokala filsystemet på maskinen där AOS-tjänsten finns. Önskad mapp väljs vid registreringssteget för datalagret. Du kan även importera konfigurationer från ett **Filsystem**-datalager till den befintliga instansen. 

Observera att den här databasen är tillgänglig i följande miljöer:

- Molnstyrda miljöer distribueras i utvecklingssyften (innehåller testmodeller av bifogade paket)
- Lokalt distribuerade miljöer (lokala)

Mer information finns i [Importera konfigurationer för elektronisk rapportering (ER)](./electronic-reporting-import-ger-configurations.md).

En **RCS**-databasen ger åtkomst till listan över konfigurationerna för en viss instans som valdes i [Regulatory Configuration Service (RCS)](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) som valdes i registreringssteget för datalagret. ER låter dig importera slutförda eller delade konfigurationer från valda RCS-instansen till den aktuella instansen så att du kan använda dem för elektronisk rapportering.

Mer information finns i [Importera konfigurationer för elektronisk rapportering från RCS](./rcs-download-configurations.md).

En **Global databas** ger åtkomst till listan över konfigurationer i den globala databasen i [Regulatory Configuration Services](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration). Den här typen av ER-databas kan endast registreras för Microsoft-leverantören. Från den globala databasen kan du importera de senaste versionerna av ER-konfigurationer till den aktuella instansen.

För mer information, se [Importera e-rapporteringskonfigurationer från global databas från Regulatory Configuration Services](./er-download-configurations-global-repo.md).

En databas för **Verksamhetsresurser** ger åtkomst till listan över konfigurationer som Microsoft frisläpper som en del av programlösningen i egenskap av ER-konfigurationsleverantör. Dessa konfigurationer kan importeras till den aktuella instansen och användas för elektronisk rapportering eller spela upp exempeluppgiftsguider. De kan också användas för ytterligare lokaliseringar och anpassningar. Observera att de senaste versionerna från Microsoft ER-konfigurationer måste importeras från det delade LCS-tillgångsbiblioteket med motsvarande ER-databas.

Obligatoriska datalager för **LCS-projekt**, **Filsystem** och **Regulatory Configuration Services (RCS)** kan registreras separat för respektive konfigurationsleverantör av den aktuella instansen. Varje databas kan reserveras för en viss konfigurationsleverantör.

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

Spela upp ER-uppgiftsguiden för **Skapa en konfiguration för rapporter i OPENXML-format** (del av affärsprocessen **7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)**) för att bekanta dig med detaljerna i det här scenariot. Som ett led i uppgiftsguiden för att importera en mall använder du Excel-filen [Mall för betalningsrapport (SampleVendPaymWsReport.xlsx)](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx) som en mall.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Skapa en konfiguration för att skapa elektroniska dokument i ett Word-dokumentformat

ER-formatdesignern kan användas för att skapa ett elektroniskt dokument i ett Word-dokumentformat. Följande illustration visar ett exempel på den här typen av format. Notera att detta format återanvänder den befintliga ER-konfigurationen som ursprungligen skapades för att skapa rapportutdata i OPENXML-format.

Kör ER-uppgiftsguiden för Designa en konfiguration för att skapa rapporter i Microsoft WORD-format (ingår i affärsprocessen 7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677) för att bekanta dig med detaljerna i det här scenariot). Använd följande Word-filer som mallar för ER-formatet som ett led i uppgiftsguidesteget för att importera en mall:

- [Mall för betalningsrapport (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Bunden mall för betalningsrapport (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Skapa en konfiguration för att importera data från inkommande elektroniska dokument

ER-formatdesignern kan användas för att beskriva ett elektroniskt dokument som har planerats för dataimport i antingen text- eller XML-format. Det designade formatet används för att tolka ett inkommande dokument. Mappningsdesignern för ER-format kan användas för att definiera elementbindningen för det utformade formatet för datamodellen. 

Kör uppgiftsguiden Skapa erforderlig ER för att importera data från en extern fil (ingår affärsprocessen 7.5.4.3 Anskaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677) för att bekanta dig med detaljerna i det här scenariot). Använd följande filer för att köra den här guiden:

- [Konfiguration av ER-datamodell (1099model.xml)](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)
- [ER-formatkonfiguration (1099model.xml)](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)
- [Exempel på det inkommande dokumentet i XML-format (1099entries.xml)](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)
- [Exempel på arbetsboken för att hantera data för inkommande dokument (1099entries.xlsx)](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx)

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

## <a name="list-of-er-configurations-that-have-been-released-in-finance"></a><a name="list-of-configurations"></a>Lista över ER-konfigurationer som har frisläppts i Finance

Listan över ER-konfigurationer för Finance uppdateras regelbundet. Öppna den [globala databasen](er-download-configurations-global-repo.md) för att granska listan över ER-konfigurationer som för närvarande stöds. På snabbfliken **Information om annullering** kan du granska information om konfigurationer som har upphört att gälla eller som inte längre används. 

![Innehållet i den globala databasen på sidan Konfigurationsdatabas.](./media/er-overview-03.gif)

## <a name="additional-resources"></a>Ytterligare resurser

- [Komponenter för elektronisk rapportering](er-overview-components.md)
- [Skapa konfigurationer för elektronisk rapportering (ER)](electronic-reporting-configuration.md)
- [Hantera livscykeln för konfiguration av elektronisk rapportering (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

