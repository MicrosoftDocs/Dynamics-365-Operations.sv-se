<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="trace-execution-er-troubleshoot-perf.md" target-language="sv-SE">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>trace-execution-er-troubleshoot-perf.773b92.aa71db2752889bc905c22bab1cf2fa46d7ee07c7.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>aa71db2752889bc905c22bab1cf2fa46d7ee07c7</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>67d00b95952faf0db580d341249d4e50be59119c</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/15/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\dev-itpro\analytics\trace-execution-er-troubleshoot-perf.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Trace execution of ER format to troubleshoot performance issues</source><target logoport:matchpercent="51" state="translated" state-qualifier="fuzzy-match">Spåringskörning av ER-format för att hjälpa dig att felsöka prestandaproblem.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic provides information about how to use the performance trace feature in Electronic reporting (ER) to troubleshoot performance issues.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Det här avsnittet innehåller information om hur du använder funktionen för prestandaspårning i elektronisk rapportering (ER) för att felsöka prestandaproblem.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Trace the execution of ER formats to troubleshoot performance issues</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Spåra körning av ER-format för att felsöka prestanda problem</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>As part of the process of designing Electronic reporting (ER) configurations to generate electronic documents, you define the method that is used to get data out of Microsoft Dynamics 365 for Finance and Operations and enter it in the output that is generated.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Som en del i processen att utforma konfiguration av elektroniska rapporter (ER) för att generera elektroniska dokument, definierar du den metod som används för att hämta data från Microsoft Dynamics 365 for Finance and Operations och anger den i genererad utdata.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The ER performance trace feature helps significantly reduce the time and cost that are involved in collecting the details of ER format execution and using them to troubleshoot performance issues.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Funktionen för ER-prestationsspårning hjälper till att avsevärt minska både tid och kostnad när det gäller att samla in information om ER-formatkörning och använda den för att felsöka prestandaproblem.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>This tutorial provides guidelines about how to take performance traces for executed ER formats in Finance and Operations, and how to use the information from these traces to help improve performance.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">I den här självstudien finns riktlinjer för hur du utför prestandaspårning för körda ER-format i Finance and Operations och hur du använder informationen från dessa spårningar för att förbättra prestanda.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Prerequisites</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Förutsättningar</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>To complete the examples in this tutorial, you must have the following access:</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">För att slutföra exemplet i den här självstudien måste du ha följande åtkomst:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Access to Finance and Operations for one of the following roles:</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Gå till Finance and Operation för någon av följande roller:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Electronic reporting developer</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Utvecklare för elektronisk rapportering</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Electronic reporting functional consultant</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Konsult för funktionen för elektronisk rapportering</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>System administrator</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Systemadministratör</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Access to the instance of Regulatory Configuration Services (RCS) that has been provisioned for the same tenant as Finance and Operations, for one of the following roles:</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Åtkomst till den instans av Regulatory Configuration Services (RCS) som har etablerats för samma innehavare som Finance and Operations för en av följande roller:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Electronic reporting developer</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Utvecklare för elektronisk rapportering</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Electronic reporting functional consultant</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">Konsult för funktionen för elektronisk rapportering</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>System administrator</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Systemadministratör</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>You must also download and locally store the following files.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Du måste också hämta följande filer och lagra dem lokalt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>File</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Fil</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Content</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Innehåll</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>Performance trace model.version.1</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Prestandaspårningsmodell.version. 1</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source><bpt id="p1">[</bpt>Sample ER data model configuration<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">[</bpt>Konfiguration av exempel på ER-datamodell.<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Performance trace metadata.version.1</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Prestandaspårningsmetadata.version.1</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source><bpt id="p1">[</bpt>Sample ER metadata configuration<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">[</bpt>Konfiguration av exempel på ER-metadata.<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Performance trace mapping.version.1.1</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Prestandaspårningsmappning.version.1.1</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source><bpt id="p1">[</bpt>Sample ER model mapping configuration<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">[</bpt>Konfiguration av exempel på ER-modellmappning<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Performance trace format.version.1.1</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Prestandaspårningsformat.version.1.1</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source><bpt id="p1">[</bpt>Sample ER format configuration<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">[</bpt>Konfiguration av exempel på ER-format.<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>Configure ER parameters</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Konfigurera ER-parametrar</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Each ER performance trace that is generated in Finance and Operations is stored as an attachment of the execution log record.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Varje ER-prestandaspårning som skapas i Finance and Operations lagras som en bilaga till körningsloggposten.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>The Document management (DM) framework of Finance and Operations is used to manage these attachments.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Dokumenthanteringsramverket (DM) för Finance and Operations används för att hantera dessa bilagor.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>You must configure ER parameters in advance, to specify the DM document type that should be used to attach performance traces.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Du måste konfigurera återställningsparametrar i förväg för att kunna ange vilken typ av DM-dokument som ska användas för att koppla prestandaspårningar.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>In Finance and Operation, in the <bpt id="p1">**</bpt>Electronic reporting<ept id="p1">**</ept> workspace, select <bpt id="p2">**</bpt>Electronic reporting parameters<ept id="p2">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">I Finance and Operations, i arbetsytan <bpt id="p1">**</bpt>elektronisk rapportering<ept id="p1">**</ept> väljer du <bpt id="p2">**</bpt>parametrar för elektronisk rapportering<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Then, on the <bpt id="p1">**</bpt>Electronic reporting parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Attachments<ept id="p2">**</ept> tab, in the <bpt id="p3">**</bpt>Others<ept id="p3">**</ept> field, select the DM document type to use for performance traces.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Välj sedan sidan <bpt id="p1">**</bpt>parametrar för elektronisk rapportering<ept id="p1">**</ept> på fliken <bpt id="p2">**</bpt>bilagor<ept id="p2">**</ept> i fältet <bpt id="p3">**</bpt>övriga<ept id="p3">**</ept> och sedan den DM-dokumenttyp som du ska använda för prestandaspårning.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>Electronic reporting parameters page in Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Sidan parametrar för elektronisk rapportering i Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>To be available in the <bpt id="p1">**</bpt>Others<ept id="p1">**</ept> lookup field, a DM document type must be configured in the following manner on the <bpt id="p2">**</bpt>Document types<ept id="p2">**</ept> page (<bpt id="p3">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Document management <ph id="ph2">\&gt;</ph> Document types<ept id="p3">**</ept>):</source><target logoport:matchpercent="0" state="translated">För att vara tillgänglig i sökfältet <bpt id="p1">**</bpt>Övriga<ept id="p1">**</ept> måste en DM-dokumenttyp konfigureras på följande sätt på sidan <bpt id="p2">**</bpt>Dokumenttyper<ept id="p2">**</ept> (<bpt id="p3">**</bpt>Organisationsadministration <ph id="ph1">\&gt;</ph> Dokumenthantering <ph id="ph2">\&gt;</ph> Dokumenttyper<ept id="p3">**</ept>):</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source><bpt id="p1">**</bpt>Class:<ept id="p1">**</ept> Attach file</source><target logoport:matchpercent="0" state="translated"><bpt id="p1">**</bpt>Klass:<ept id="p1">**</ept> Bifoga fil</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source><bpt id="p1">**</bpt>Group:<ept id="p1">**</ept> File</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Grupp:<ept id="p1">**</ept> fil</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Document types page in Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Sidan dokumenttyper i Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>The selected document type must be available in every company of the current Finance and Operations instance, because DM attachments are company-specific.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Den valda dokumenttypen måste vara tillgänglig i alla företag i den aktuella Finance and Operations-instansen eftersom DM-bilagor är företagsspecifika.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Configure RCS parameters</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Konfigurera RCS-parametrar</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>ER performance traces that are generated in Finance and Operations will be imported into RCS for analysis by using the ER format designer and the ER mapping designer.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">ER-prestandaspårningar som skapas i Finance and Operations importeras till RCS för analys med hjälp av ERformatdesigner och ER-mappningsdesigner.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Because ER performance traces are stored as attachments of the execution log record that is related to the ER format, you must configure RCS parameters in advance, to specify the DM document type that should be used to attach performance traces.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Eftersom ER-prestandaspårning lagras som bilagor till körningsloggposten som är relaterad till ER-formatet, måste du konfigurera RCS-parametrar i förväg för att ange den DM-dokumenttyp som ska användas för att koppla prestandaspårningar.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>In the instance of RCS that has been provisioned for your company, in the <bpt id="p1">**</bpt>Electronic reporting<ept id="p1">**</ept> workspace, select <bpt id="p2">**</bpt>Electronic reporting parameters<ept id="p2">**</ept>.</source><target logoport:matchpercent="0" state="translated">elektronisk I instansen av RCS som har etablerats för ditt företag, i arbetsytan <bpt id="p1">**</bpt>elektronisk rapportering<ept id="p1">**</ept> väljer du <bpt id="p2">**</bpt>elektronisk rapportering<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Then, on the <bpt id="p1">**</bpt>Electronic reporting parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Attachments<ept id="p2">**</ept> tab, in the <bpt id="p3">**</bpt>Others<ept id="p3">**</ept> field, select the DM document type to use for performance traces.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Välj sedan sidan <bpt id="p1">**</bpt>parametrar för elektronisk rapportering<ept id="p1">**</ept> på fliken <bpt id="p2">**</bpt>bilagor<ept id="p2">**</ept> i fältet <bpt id="p3">**</bpt>övriga<ept id="p3">**</ept> och sedan den DM-dokumenttyp som du ska använda för prestandaspårning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>Electronic reporting parameters page in RCS</source><target logoport:matchpercent="90" state="translated" state-qualifier="fuzzy-match">Sida för parametrar för elektronisk rapportering i RCS</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>To be available in the <bpt id="p1">**</bpt>Others<ept id="p1">**</ept> lookup field, a DM document type must be configured in the following manner on the <bpt id="p2">**</bpt>Document types<ept id="p2">**</ept> page (<bpt id="p3">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Document management <ph id="ph2">\&gt;</ph> Document types<ept id="p3">**</ept>):</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">För att vara tillgänglig i sökfältet <bpt id="p1">**</bpt>Övriga<ept id="p1">**</ept> måste en DM-dokumenttyp konfigureras på följande sätt på sidan <bpt id="p2">**</bpt>Dokumenttyper<ept id="p2">**</ept> (<bpt id="p3">**</bpt>Organisationsadministration <ph id="ph1">\&gt;</ph> Dokumenthantering <ph id="ph2">\&gt;</ph> Dokumenttyper<ept id="p3">**</ept>):</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source><bpt id="p1">**</bpt>Class:<ept id="p1">**</ept> Attach file</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match"><bpt id="p1">**</bpt>Klass:<ept id="p1">**</ept> Bifoga fil</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source><bpt id="p1">**</bpt>Group:<ept id="p1">**</ept> File</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match"><bpt id="p1">**</bpt>Grupp:<ept id="p1">**</ept> fil</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Design an ER solution</source><target logoport:matchpercent="68" state="translated" state-qualifier="fuzzy-match">Designa en ER-lösning</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Assume that you've started to design a new ER solution to generate a new report that presents vendor transactions.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Anta att du har börjat designa en ny ER-lösning för att skapa en ny rapport som visar leverantörstransaktioner.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Currently, you can find the transactions for a selected vendor on the <bpt id="p1">**</bpt>Vendor transactions<ept id="p1">**</ept> page (go to <bpt id="p2">**</bpt>Account payable <ph id="ph1">\&gt;</ph> Vendors <ph id="ph2">\&gt;</ph> All vendors<ept id="p2">**</ept>, select a vendor, and then, on the Action Pane, on the <bpt id="p3">**</bpt>Vendor<ept id="p3">**</ept> tab, in the <bpt id="p4">**</bpt>Transactions<ept id="p4">**</ept> group, select <bpt id="p5">**</bpt>Transactions<ept id="p5">**</ept>).</source><target logoport:matchpercent="0" state="translated">För närvarande kan du hitta transaktionerna för en vald leverantör på sidan <bpt id="p1">**</bpt>leverantörstransaktioner<ept id="p1">**</ept> (gå till <bpt id="p2">**</bpt>leverantörsreskontra<ph id="ph1">\&gt;</ph> leverantörer <ph id="ph2">\&gt;</ph> alla leverantörer<ept id="p2">**</ept>, välj en leverantörer och sedan i åtgärdspanelen på fliken <bpt id="p3">**</bpt>leverantörer<ept id="p3">**</ept> i gruppen <bpt id="p4">**</bpt>transaktioner<ept id="p4">**</ept> väljer du <bpt id="p5">**</bpt>transaktioner<ept id="p5">**</ept>).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>However, you want to have all vendor transaction at the same time in one electronic document in XML format.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Du vill dock ha alla leverantörstransaktioner samtidigt i ett elektroniskt dokument i XML-format.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>This solution will consist of several ER configurations that contain the required data model, metadata, model mapping, and format components.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Den här lösningen består av flera ER-konfigurationer som innehåller den nödvändiga datamodellen, metadata, modellmappning och formatkomponenter.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>Sign in to the instance of RCS that has been provisioned for your company.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Logga in på den instans av RCS som har etablerats för ditt företag.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>In this tutorial, you will create and modify configurations for the <bpt id="p1">**</bpt>Litware, Inc.<ept id="p1">**</ept> sample company.</source><target logoport:matchpercent="80" state="translated" state-qualifier="fuzzy-match">I den här självstudien ska du skapa och ändra konfigurationer för exempelföretaget <bpt id="p1">**</bpt>Litware, Inc<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Therefore, make sure that this configuration provider has been added to RCS and selected as active.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Kontrollera därför att denna konfigurationsleverantör har lagts till i RCS och valts som aktiv.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>For instructions, see the <bpt id="p1">[</bpt>Create configuration providers and mark them as active<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11)</ept> procedure.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Instruktioner finns i proceduren <bpt id="p1">[</bpt>skapa konfigurationsleverantörer och markera dem som aktiva<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11)</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>In the <bpt id="p1">**</bpt>Electronic reporting<ept id="p1">**</ept> workspace, select the <bpt id="p2">**</bpt>Reporting configurations<ept id="p2">**</ept> tile.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">På arbetsytan <bpt id="p1">**</bpt>Elektronisk rapportering<ept id="p1">**</ept> väljer du panelen <bpt id="p2">**</bpt>Rapporteringskonfiguration<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, import the ER configurations that you downloaded as a prerequisite into RCS, in the following order: data model, metadata, model mapping, format.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">På sidan <bpt id="p1">**</bpt>konfigurationer<ept id="p1">**</ept> importerar du de ER-konfigurationer som du hämtade som en förutsättning i RCS i följande ordning: datamodell, metadata, modellmappning, format.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>For each configuration, follow these steps:</source><target logoport:matchpercent="85" state="translated" state-qualifier="fuzzy-match">Följ dessa steg för varje konfiguration:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>On the Action Pane, select <bpt id="p1">**</bpt>Exchange <ph id="ph1">\&gt;</ph> Load from XML file<ept id="p1">**</ept>.</source><target logoport:matchpercent="0" state="translated">På Åtgärdsfönster väljer du <bpt id="p1">**</bpt>växla <ph id="ph1">\&gt;</ph> läs in från XML-fil<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Select <bpt id="p1">**</bpt>Browse<ept id="p1">**</ept> to select the appropriate file for the required ER configuration in XML format.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Välj <bpt id="p1">**</bpt>bläddra<ept id="p1">**</ept> om du vill välja en fil för den nödvändiga ER-konfigurationen i XML-format.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Select <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Välj <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Configurations page in RCS</source><target logoport:matchpercent="84" state="translated" state-qualifier="fuzzy-match">Sidan Konfigurationer i RCS</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>Run the ER solution to trace execution</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Kör ER-lösning för att spåra körning</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Assume that you've finished designing the first version of the ER solution.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Anta att du har skapat den första versionen av ER-lösningen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>You now want to test it in your Finance and Operations instance and analyze execution performance.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Du vill nu testa den i Finance and Operations-instansen och analysera körningsprestanda.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source><bpt id="p1">&lt;a id='import-configuration'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Import an ER configuration from RCS into Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">&lt;a id='import-configuration'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Importera en ER-konfiguration från RCS till Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>Sign in to your Finance and Operations instance.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Logga in på din instans av Finance and Operations.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>For this tutorial, you will import configurations from your RCS instance (where you design your ER components) into your Finance and Operations instance (where you test and finally use them).</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">För den här självstudien ska du importera konfigurationer från din RCS-instans (där du utformar dina ER-komponenter) till Finance and Operations-instansen (där du testar och slutligen använder dem.)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>Therefore, you must make sure that all the required artifacts have been prepared.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Därför måste du se till att alla nödvändiga artefakter har förberetts.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>For instructions, see the <bpt id="p1">[</bpt>Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)<ept id="p1">](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations)</ept> procedure.</source><target logoport:matchpercent="83" state="translated" state-qualifier="fuzzy-match">För mer information, se proceduren <bpt id="p1">[</bpt>Importera e-rapporteringskonfigurationer från Regulatory Configuration Services (RCS)<ept id="p1">](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations)</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Follow these steps to import the configurations from RCS into Finance and Operations:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Följ dessa steg för att importera konfigurationerna från RCS till Finance and Operations:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>In the <bpt id="p1">**</bpt>Electronic reporting<ept id="p1">**</ept> workspace, on the tile for the <bpt id="p2">**</bpt>Litware, Inc.<ept id="p2">**</ept> configuration provider, select <bpt id="p3">**</bpt>Repositories<ept id="p3">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">I arbetsytan <bpt id="p1">**</bpt>elektronisk rapportering<ept id="p1">**</ept> på panelen för konfigurationsleverantören <bpt id="p2">**</bpt>Litware, Inc.<ept id="p2">**</ept> väljer du <bpt id="p3">**</bpt>Databaser<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>On the <bpt id="p1">**</bpt>Configuration repository<ept id="p1">**</ept> page, select the repository of the <bpt id="p2">**</bpt>RCS<ept id="p2">**</ept> type, and then select <bpt id="p3">**</bpt>Open<ept id="p3">**</ept>.</source><target logoport:matchpercent="73" state="translated" state-qualifier="fuzzy-match">På sidan <bpt id="p1">**</bpt>Konfigurationsdatabaser<ept id="p1">**</ept> väljer du i rutnätet den befintliga databasen för <bpt id="p2">**</bpt>RCS<ept id="p2">**</ept>-typ och väljer sedan <bpt id="p3">**</bpt>Öppna<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> FastTab, select the <bpt id="p2">**</bpt>Performance trace format<ept id="p2">**</ept> configuration.</source><target logoport:matchpercent="0" state="translated">På snabbfliken <bpt id="p1">**</bpt>konfigurationer<ept id="p1">**</ept> väljer du konfigurationen <bpt id="p2">**</bpt>Prestandaspårningsformat<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>On the <bpt id="p1">**</bpt>Versions<ept id="p1">**</ept> FastTab, select version <bpt id="p2">**</bpt>1.1<ept id="p2">**</ept> of the selected configuration, and then select <bpt id="p3">**</bpt>Import<ept id="p3">**</ept>.</source><target logoport:matchpercent="74" state="translated" state-qualifier="fuzzy-match">I snabbfliken <bpt id="p1">**</bpt>Versioner<ept id="p1">**</ept> väljer du version <bpt id="p2">**</bpt>1.1.<ept id="p2">**</ept> för vald konfiguration och sedan <bpt id="p3">**</bpt>Importera<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>Configuration repository page in Finance and Operations</source><target logoport:matchpercent="68" state="translated" state-qualifier="fuzzy-match">Sidan Konfigurationsdatabaser i Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>The corresponding versions of the data model and model mapping configurations are automatically imported as prerequisites for the imported ER format configuration.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Motsvarande versioner av datamodell- och modellmappningskonfigurationer importeras automatiskt som förutsättningar för den importerade ER-formatkonfigurationen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Turn on the ER performance trace</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Aktivera ER-prestandaspårning</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>In Finance and Operations, go to <bpt id="p1">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Electronic reporting <ph id="ph2">\&gt;</ph> Configurations<ept id="p1">**</ept>.</source><target logoport:matchpercent="0" state="translated">I Finance and Operations, gå till <bpt id="p1">**</bpt>Organisationsadministration <ph id="ph1">\&gt;</ph> Elektronisk rapportering <ph id="ph2">\&gt;</ph> Konfigurationer<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, on the Action Pane, on the <bpt id="p2">**</bpt>Configurations<ept id="p2">**</ept> tab, in the <bpt id="p3">**</bpt>Advanced settings<ept id="p3">**</ept> group, select <bpt id="p4">**</bpt>User parameters<ept id="p4">**</ept>.</source><target logoport:matchpercent="72" state="translated" state-qualifier="fuzzy-match">På sidan <bpt id="p1">**</bpt>Konfigurationer<ept id="p1">**</ept> i åtgärdsfönstret, på fliken <bpt id="p2">**</bpt>Konfigurationer<ept id="p2">**</ept> i gruppen <bpt id="p3">**</bpt>Avancerad inställningar<ept id="p3">**</ept> markerar du <bpt id="p4">**</bpt>Använd parametrar<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>In the <bpt id="p1">**</bpt>User parameters<ept id="p1">**</ept> dialog box, in the <bpt id="p2">**</bpt>Execution tracing<ept id="p2">**</ept> section, follow these steps:</source><target logoport:matchpercent="0" state="translated">I dialogrutan <bpt id="p1">**</bpt>Användarparametrar<ept id="p1">**</ept> i avsnittet <bpt id="p2">**</bpt>körningsspårning<ept id="p2">**</ept> gör fäljande steg:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>In the <bpt id="p1">**</bpt>Execution trace format<ept id="p1">**</ept> field, select <bpt id="p2">**</bpt>Debug trace format<ept id="p2">**</ept> to start to collect the details of ER format execution.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">I fältet <bpt id="p1">**</bpt>körningsspårningsformat<ept id="p1">**</ept> väljer du <bpt id="p2">**</bpt>felsökningsspårningsformat<ept id="p2">**</ept> för att börja samla in information om ER-formatkörning.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>When this value is selected, the performance trace will collect information about the time that is spent on the following actions:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">När det här värdet väljs samlar prestandaspårningen in information om den tid som har ägnats åt följande åtgärder:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Running each data source in the model mapping that is called to get data</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Kör varje datakälla i modellmappningen som anropas för att hämta data</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Processing each format item to enter data in the output that is generated</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Behandla varje formatobjekt för att ange data i de utdata som genereras</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>You use the <bpt id="p1">**</bpt>Execution trace format<ept id="p1">**</ept> field to specify the format of the generated performance trace that the execution details are stored in for ER format and mapping elements.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Du använder fältet <bpt id="p1">**</bpt>körningsspårningsformat<ept id="p1">**</ept> om du vill ange formatet för den genererade prestandaspårning som körningsinformationen lagras i för ER-format och mappningselement.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>By selecting <bpt id="p1">**</bpt>Debug trace format<ept id="p1">**</ept> as the value, you will be able to analyze the content of the trace in ER Operation designer, and see the ER format or mapping elements that are mentioned in the trace.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Om du väljer <bpt id="p1">**</bpt>felsökningsspårningsformat<ept id="p1">**</ept> som värde kan du analysera innehållet i spårningen i ER-åtgärdsdesignern och se ER-format eller mappningselement som nämns i spårningen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Set the following options to <bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> to collect specific details of the execution of the ER model mapping and ER format components:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ange följande alternativ till <bpt id="p1">**</bpt>ja<ept id="p1">**</ept> för att samla in specifik information om körningen av komponenterna ER-modellmappning och ER-format:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source><bpt id="p1">**</bpt>Collect query statistics<ept id="p1">**</ept> – When this option is turned on, the performance trace will collect the following information:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Samla in frestatistik<ept id="p1">**</ept> – när det här alternativet är aktiverat samlar prestandaspårningen in följande information:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>The number of database calls that were made by data sources</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Antalet databasanrop som har gjorts av datakällor</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The number of duplicate calls to the database</source><target logoport:matchpercent="86" state="translated" state-qualifier="fuzzy-match">Antalet dubblettanrop till databasen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>Details of the SQL statements that were used to make database calls</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Information om SQL-satserna som användes för att göra databasanrop</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source><bpt id="p1">**</bpt>Trace access of caching<ept id="p1">**</ept> – When this option is turned on, the performance trace will collect information about the ER model mapping's cache usage.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Spåra åtkomst av cachelagring<ept id="p1">**</ept> – när det här alternativet är aktiverat samlar prestandaspårningen in information om vad som gäller för ER-modell mappningens cache-användning.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source><bpt id="p1">**</bpt>Trace data access<ept id="p1">**</ept> – When this option is turned on, the performance trace will collect information about the number of calls to the database for executed data sources of the record list type.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Spåra dataåtkomst<ept id="p1">**</ept> – när det här alternativet är aktiverat samlar prestandaspårningen in information om antalet anrop till databasen för körda datakällor av postlisttypen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source><bpt id="p1">**</bpt>Trace list enumeration<ept id="p1">**</ept> – When this option is turned on, the performance trace will collect information about the number of records that are requested from data sources of the record list type.</source><target logoport:matchpercent="79" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Spåra listuppräkning<ept id="p1">**</ept> – när det här alternativet är aktiverat samlar prestandaspårningen in information om antalet poster som begärs från datakällor av postlisttypen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>The parameters in the <bpt id="p1">**</bpt>User parameters<ept id="p1">**</ept> dialog box are specific to the user and the current company.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Parametrarna i dialogrutan <bpt id="p1">**</bpt>användarparametrar<ept id="p1">**</ept> är specifika för användaren och det aktuella företaget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>User parameters dialog box in Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Dialogrutan användarparametrar i Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source><bpt id="p1">&lt;a id='run-format'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Run the ER format</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">&lt;a id='run-format'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Kör ER-format</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>In Finance and Operations, select the <bpt id="p1">**</bpt>DEMF<ept id="p1">**</ept> company.</source><target logoport:matchpercent="0" state="translated">I Finance and Operations, välj företaget <bpt id="p1">**</bpt>DEMF<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Go to <bpt id="p1">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Electronic reporting <ph id="ph2">\&gt;</ph> Configurations<ept id="p1">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Gå till <bpt id="p1">**</bpt>Organisationsadministration  <ph id="ph1">\&gt;</ph> Elektronisk rapportering <ph id="ph2">\&gt;</ph> Konfigurationer<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, in the configuration tree, select the <bpt id="p2">**</bpt>Performance trace format<ept id="p2">**</ept> item.</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">På sidan <bpt id="p1">**</bpt>konfigurationer<ept id="p1">**</ept> i konfigurationsträdet väljer du artikeln <bpt id="p2">**</bpt>Prestandaspårningsformat<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>On the Action Pane, select <bpt id="p1">**</bpt>Run<ept id="p1">**</ept>.</source><target logoport:matchpercent="86" state="translated" state-qualifier="fuzzy-match">Klicka på <bpt id="p1">**</bpt>Kör<ept id="p1">**</ept> i åtgärdsfönstret.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Notice that the file that is generated presents information about 265 transactions for six vendors.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Observera att filen som genereras visar information om 265 transaktioner för sex leverantörer.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>Review the execution trace</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Granska körningsspårningen</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source><bpt id="p1">&lt;a id='export-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Export the generated trace from Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">&lt;a id='export-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Exportera den genererade spårningen från Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Performance traces are decoupled from the source ER format and can be serialized to an external zip file.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Prestandaspårningen kopplas från källans ER-format och kan serialiseras till en extern ZIP-fil.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>In Finance and Operations, go to <bpt id="p1">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Electronic reporting <ph id="ph2">\&gt;</ph> Configuration debug logs<ept id="p1">**</ept>.</source><target logoport:matchpercent="88" state="translated" state-qualifier="fuzzy-match">I Finance and Operations, gå till <bpt id="p1">**</bpt>Organisationsadministration <ph id="ph1">\&gt;</ph> Elektronisk rapportering <ph id="ph2">\&gt;</ph> Konfiguration av felsökningsloggar<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>On the <bpt id="p1">**</bpt>Electronic reporting run logs<ept id="p1">**</ept> page, in the left pane, in the <bpt id="p2">**</bpt>Configuration name<ept id="p2">**</ept> field, select <bpt id="p3">**</bpt>Performance trace format<ept id="p3">**</ept> to find the log records that have been generated by the execution of the <bpt id="p4">**</bpt>Performance trace format<ept id="p4">**</ept> configuration.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">På sidan <bpt id="p1">**</bpt>elektronisk rapportering kör loggar<ept id="p1">**</ept> i det vänstra fönstret i <bpt id="p2">**</bpt>konfigurationsnamn<ept id="p2">**</ept> väljer du <bpt id="p3">**</bpt>prestandaspårningsformat<ept id="p3">**</ept> i för att hitta de loggposter som har genererats vid körning av konfigurationen <bpt id="p4">**</bpt>Prestandaspårningsformat<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Select the <bpt id="p1">**</bpt>Attachments<ept id="p1">**</ept> button (the paper clip symbol) in the upper-right corner of the page, or press <bpt id="p2">**</bpt>Ctrl+Shift+A<ept id="p2">**</ept>.</source><target logoport:matchpercent="0" state="translated">Välj knappen <bpt id="p1">**</bpt>Bilagor<ept id="p1">**</ept> (gemsymbolen) längst upp till höger på sidan eller tryck på <bpt id="p2">**</bpt>Ctrl+Shift+A<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Attachments button on the Electronic reporting run logs page in Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Knappen Bilagor på sidan elektronisk rapportering körningsloggarna i Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>On the <bpt id="p1">**</bpt>Attachments for Electronic reporting run logs<ept id="p1">**</ept> page, on the Action Pane, select <bpt id="p2">**</bpt>Open<ept id="p2">**</ept> to get the performance trace as a zip file and store it locally.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">På sidan <bpt id="p1">**</bpt>bilagor för elektroniska rapportering körningsloggar<ept id="p1">**</ept> i åtgärdsfönstret väljer du <bpt id="p2">**</bpt>öppna<ept id="p2">**</ept> för att få prestandaspårningen som en zip-fil och spara den lokalt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>Attachments for Electronic reporting run logs page in Finance and Operations</source><target logoport:matchpercent="85" state="translated" state-qualifier="fuzzy-match">Bilagor för elektronisk rapportering körningsloggarna i Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>The trace that is generated has a reference to the source ER report via a unique report identifier in <bpt id="p1">**</bpt>GUID<ept id="p1">**</ept> format only.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Spårningen som genereras har en referens till källans ER-rapport via en unik rapportidentifierare i <bpt id="p1">**</bpt>GUID<ept id="p1">**</ept>-format.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>The version numbering of the format isn't considered.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Versionsnumret för formatet beaktas inte.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>Notice that the association between the performance trace that has been generated for the executed ER format and the ER model mapping is based on the root descriptor that was used and the common data model.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Observera att associationen mellan resultatspårningen som har genererats för det körda ER-formatet och ER-modellmappningen baseras på den rotbeskrivare som användes och den gemensamma datamodellen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>The version numbering of the format and model mapping isn't considered.</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">Versionsnumret för formatet ochmmdellmappning beaktas inte.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>The setting of the <bpt id="p1">**</bpt>Default for model mapping<ept id="p1">**</ept> flag for the model mapping also isn't considered.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Inställningen av flaggan <bpt id="p1">**</bpt>Standard för modellmappning<ept id="p1">**</ept> för modellmappningen beaktas inte heller.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source><bpt id="p1">&lt;a id='import-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Import the generated trace into RCS</source><target logoport:matchpercent="80" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">&lt;a id='import-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Importera genererad spårning till RCS.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>In RCS, in the <bpt id="p1">**</bpt>Electronic reporting<ept id="p1">**</ept> workspace, select the <bpt id="p2">**</bpt>Reporting configurations<ept id="p2">**</ept> tile.</source><target logoport:matchpercent="94" state="translated" state-qualifier="fuzzy-match">I RCS på arbetsytan <bpt id="p1">**</bpt>Elektronisk rapportering<ept id="p1">**</ept> väljer du panelen <bpt id="p2">**</bpt>Rapporteringskonfiguration<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, in the configuration tree, expand the <bpt id="p2">**</bpt>Performance trace model<ept id="p2">**</ept> item, and select the <bpt id="p3">**</bpt>Performance trace format<ept id="p3">**</ept> item.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">På sidan <bpt id="p1">**</bpt>konfigurationer<ept id="p1">**</ept> i konfigurationsträdet, expandera artikeln <bpt id="p2">**</bpt>Prestandaspårningsmodell<ept id="p2">**</ept> och väljer artikeln <bpt id="p3">**</bpt>Prestandaspårningsformat<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>On the Action Pane, select <bpt id="p1">**</bpt>Designer<ept id="p1">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Klicka på <bpt id="p1">**</bpt>Designer<ept id="p1">**</ept> i åtgärdsfönstret.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>On the <bpt id="p1">**</bpt>Format designer<ept id="p1">**</ept> page, on the Action Pane, select <bpt id="p2">**</bpt>Performance trace<ept id="p2">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">På snabbfliken <bpt id="p1">**</bpt>Formatdesigner<ept id="p1">**</ept> på åtgärdsfönstret väljer du <bpt id="p2">**</bpt>Prestandaspårningsformat<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>In the <bpt id="p1">**</bpt>Performance trace result settings<ept id="p1">**</ept> dialog box, select <bpt id="p2">**</bpt>Import performance trace<ept id="p2">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">I dialogrutan <bpt id="p1">**</bpt>Inställning av prestandaspårningsresultat<ept id="p1">**</ept> väljer du <bpt id="p2">**</bpt>Importera prestandaspårning<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>Select <bpt id="p1">**</bpt>Browse<ept id="p1">**</ept> to select the zip file that you exported from Finance and Operations earlier.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Välj <bpt id="p1">**</bpt>bläddra<ept id="p1">**</ept> om du vill välja den zip-fil som du exporterade från Finance and Operations tidigare.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>Select <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Välj <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>Performance trace result settings dialog box in RCS</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Dialogrutan inställningar av prestandaspårningsresultat i RCS</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>Use the performance trace for analysis in RCS – Format execution</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Använd prestandaspårning för analys i RCS – formatkörning</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>In RCS, on the <bpt id="p1">**</bpt>Format designer<ept id="p1">**</ept> page, select <bpt id="p2">**</bpt>Expand/collapse<ept id="p2">**</ept> to expand the content of all format items.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">I RCS, på sidan <bpt id="p1">**</bpt>Formatdesigner<ept id="p1">**</ept> välj <bpt id="p2">**</bpt>Visa/Dölj<ept id="p2">**</ept> för att expandera innehållet i alla formatobjekt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>Notice that additional information is shown for some items of the current format:</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Lägg märke till att ytterligare information visas för vissa artiklar i det aktuella formatet:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>The actual time that was spent entering data in the generated output by using the format item</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Den faktiska tid som användes för att mata in data i det genererade utmatninget med hjälp av formaobjekt</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>The same time expressed as a percentage of the total time that was spent generating the whole output</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Samma tid uttryckt i procent av den totala tid som användes för att generera hela utdata</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>Format designer page in RCS</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Formatdesignersida i RCS</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>Close <bpt id="p1">**</bpt>Format designer<ept id="p1">**</ept> page.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Stäng sidan <bpt id="p1">**</bpt>Formatdesigner<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source><bpt id="p1">&lt;a id='use-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Use the performance trace for analysis in RCS – Model mapping</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">&lt;a id='use-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Använd prestandaspårning för analys i RCS – modellmappning</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>In RCS, on the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, in the configuration tree, select the <bpt id="p2">**</bpt>Performance trace mapping<ept id="p2">**</ept> item.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">I RCS på sidan <bpt id="p1">**</bpt>konfigurationer<ept id="p1">**</ept> i konfigurationsträdet väljer du artikeln <bpt id="p2">**</bpt>Prestandaspårningsmappning<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>On the Action Pane, select <bpt id="p1">**</bpt>Designer<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">Klicka på <bpt id="p1">**</bpt>Designer<ept id="p1">**</ept> i åtgärdsfönstret.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>Select <bpt id="p1">**</bpt>Designer<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Välj <bpt id="p1">**</bpt>Designer<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>On the <bpt id="p1">**</bpt>Model mapping designer<ept id="p1">**</ept> page, on the Action Pane, select <bpt id="p2">**</bpt>Performance trace<ept id="p2">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">På snabbfliken <bpt id="p1">**</bpt>Modellmappningsdesigner<ept id="p1">**</ept> på åtgärdsfönstret väljer du <bpt id="p2">**</bpt>Prestandaspårningsformat<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>Select the trace that you imported earlier.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Välj spårningen som du importerade tidigare.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>Select <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Välj <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>Notice that new information becomes available for some data source items of the current model mapping:</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Lägg märke till att ny information blir tillgänglig för vissa datakällobjekt i den aktuella modellmappningen:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>The actual time that was spent getting data by using the data source</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Den faktiska tid som användes för att hämta data genom att använda datakällan</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>The same time expressed as a percentage of the total time that was spent running the whole model mapping</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Samma tid uttryckt i procent av den totala tid som användes för att köra hela modellmappningen</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Notice that ER informs you that the current model mapping duplicates database requests while the VendTable/<ph id="ph1">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum data source is run.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Observera att du informerar dig om att den aktuella modellmappningen duplicerar databas begäranden när datakällan VendTable/<ph id="ph1">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum körs.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>This duplication occurs because the list of vendor transactions is called two times for each iterated vendor record:</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Den här dubbletten sker eftersom listan med leverantörstransaktioner anropas två gånger för varje förslagen leverantörspost:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>One call is made to enter details of each transaction in the data model, based on configured bindings.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ett anrop görs för att ange information om varje transaktion i datamodellen, baserat på konfigurerade bindningar.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>One call is made to enter the calculated number of transactions per vendor in the data model.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ett samtal görs för att ange det beräknade antalet transaktioner per leverantör i datamodellen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>Message about duplicate database requests on the Model mapping designer page in RCS</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Meddelande om dubbla databasbegäranden på sidan modellmappningsdesigner i RCS</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>The value <bpt id="p1">**</bpt><ph id="ph1">\[</ph>Q:530<ph id="ph2">\]</ph><ept id="p1">**</ept> indicates that the VendTrans table was called 530 times to return a record from that table to the VendTable/<ph id="ph3">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph4">\_</ph>AccountNum data source.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Värdet <bpt id="p1">**</bpt><ph id="ph1">\[</ph>Q:530<ph id="ph2">\]</ph><ept id="p1">**</ept> anger att VendTrans-registret har anropats 530 gånger för att returnera en post från registret till datakällan VendTable/<ph id="ph3">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph4">\_</ph>AccountNum.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>The value <bpt id="p1">**</bpt><ph id="ph1">\[</ph>530<ph id="ph2">\]</ph><ept id="p1">**</ept> indicates that the VendTable/<ph id="ph3">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph4">\_</ph>AccountNum data source was called 530 times to return a record from that data source and enter the details from it in the data model.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Värdet <bpt id="p1">**</bpt><ph id="ph1">\[</ph>530<ph id="ph2">\]</ph><ept id="p1">**</ept> anger att datakällan VendTable/<ph id="ph3">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph4">\_</ph>AccountNum har anropats 530 gånger för att returnera en post från den datakällan och ange informationen från den i datamodellen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>We recommend that you use caching for the VendTable/<ph id="ph1">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum data source, to reduce the number of calls that are made to get the details for 265 transactions and help improve the performance of the model mapping.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Vi rekommenderar att du använder cache för datakällan VendTable/<ph id="ph1">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum för att minska antalet anrop som görs för att få information om 265-transaktioner och förbättra modellmappningens prestanda.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source>It can also be useful to reduce the number of calls that are made to the LedgerTransTypeList data source.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Det kan också vara användbart om du vill minska antalet anrop som görs till datakällan LedgerTransTypeList.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>This data source is used to associate each value of the <bpt id="p1">**</bpt>LedgerTransType<ept id="p1">**</ept> enumeration with its label.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Denna datakälla används för att koppla varje värde i <bpt id="p1">**</bpt>LedgerTransType<ept id="p1">**</ept>-uppräkningen till dess etikett.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source>By using this data source, you can find an appropriate label and enter it in the data model for each vendor transaction.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Genom att använda den här datakällan kan du hitta en lämplig etikett och ange den i datamodellen för varje leverantörstransaktion.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>The current number of calls to this data source (9,027) is quite high for 265 transactions.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Det aktuella antalet anrop till den här datakällan (9 027) är ganska högt för 265 transaktioner.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source>Model mapping designer page in RCS, showing 9,027 calls to the data source</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Sidan modellmappningsdesigner i RCS, visar 9 027 anrop till datakällan</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source>Improve the model mapping based on information from the execution trace</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Förbättra modellmappningen utifrån information från körningsspårningen</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source>Modify the logic of the model mapping</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">Ändra logiken för modellmappningen</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source>Follow these steps to use caching, to help prevent duplicate calls to the database:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Gör så här om du vill använda cache för att förhindra att anrop till databasen dupliceras:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>In RCS, on the <bpt id="p1">**</bpt>Model mapping designer<ept id="p1">**</ept> page, in the <bpt id="p2">**</bpt>Data sources<ept id="p2">**</ept> pane, select the <bpt id="p3">**</bpt>VendTable<ept id="p3">**</ept> item.</source><target logoport:matchpercent="0" state="translated">I RCS, på sidan <bpt id="p1">**</bpt>Modellmappingsdesigner<ept id="p1">**</ept> i fönstret <bpt id="p2">**</bpt>Datakällor<ept id="p2">**</ept> väljer du objektet <bpt id="p3">**</bpt>VendTable<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>Select <bpt id="p1">**</bpt>Cache<ept id="p1">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Välj <bpt id="p1">**</bpt>cache<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>Expand the <bpt id="p1">**</bpt>VendTable<ept id="p1">**</ept> item, expand the list of one-to-many relations for the VendTable data source (the <bpt id="p2">**</bpt><ph id="ph1">\&lt;</ph>Relations<ept id="p2">**</ept> item), and select the <bpt id="p3">**</bpt>VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum<ept id="p3">**</ept> item.</source><target logoport:matchpercent="0" state="translated">Expandera objektet <bpt id="p1">**</bpt>VendTable<ept id="p1">**</ept>  expandera listan med 1:n-relationer för VendTable-datakälla (<bpt id="p2">**</bpt><ph id="ph1">\&lt;</ph>Relationer<ept id="p2">**</ept> objekt) och välj objektet <bpt id="p3">**</bpt>VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source>Select <bpt id="p1">**</bpt>Cache<ept id="p1">**</ept>.</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Välj <bpt id="p1">**</bpt>cache<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>Caching setup to help prevent duplicate calls</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cachelagring för att förhindra dubbla anrop</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>Follow these steps to bring the LedgerTransTypeList data source into the scope of the VendTable data source:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Följ dessa steg för att hämta datakällan LedgerTransTypeList till omfattningen för datakällan VendTable:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>In the <bpt id="p1">**</bpt>Data source types<ept id="p1">**</ept> pane, expand the <bpt id="p2">**</bpt>Functions<ept id="p2">**</ept> item, and select the <bpt id="p3">**</bpt>Calculated field<ept id="p3">**</ept> item.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">I fönstret <bpt id="p1">**</bpt>datakälltyper<ept id="p1">**</ept> expanderar du objektet <bpt id="p2">**</bpt>funktioner<ept id="p2">**</ept> och markerar objektet <bpt id="p3">**</bpt>beräknade fält<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>In the <bpt id="p1">**</bpt>Data sources<ept id="p1">**</ept> pane, select the <bpt id="p2">**</bpt>VendTable<ept id="p2">**</ept> item.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Markera objektet <bpt id="p1">**</bpt>VendTable<ept id="p1">**</ept> i fönstret <bpt id="p2">**</bpt>datakällor<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>Select <bpt id="p1">**</bpt>Add<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Markera <bpt id="p1">**</bpt>Lägg till<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>In the <bpt id="p1">**</bpt>Name<ept id="p1">**</ept> field, enter <bpt id="p2">**</bpt><ph id="ph1">\$</ph>TransType<ept id="p2">**</ept>.</source><target logoport:matchpercent="83" state="translated" state-qualifier="fuzzy-match">Skriv <bpt id="p1">**</bpt><ph id="ph1">\$</ph>TransType<ept id="p1">**</ept> i fältet <bpt id="p2">**</bpt>Namn<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>Select <bpt id="p1">**</bpt>Edit formula<ept id="p1">**</ept>.</source><target logoport:matchpercent="74" state="translated" state-qualifier="fuzzy-match">Välj <bpt id="p1">**</bpt>Redigera recept<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="273">
          <source>In the <bpt id="p1">**</bpt>Formula<ept id="p1">**</ept> field, enter <bpt id="p2">**</bpt>LedgerTransTypeList<ept id="p2">**</ept>.</source><target logoport:matchpercent="0" state="translated">I fältet <bpt id="p1">**</bpt>Recept<ept id="p1">**</ept> ange <bpt id="p2">**</bpt>LedgerTransTypeList<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="274">
          <source>Select <bpt id="p1">**</bpt>Save<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Välj <bpt id="p1">**</bpt>Spara<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="275">
          <source>Close the <bpt id="p1">**</bpt>Formula editor<ept id="p1">**</ept> page.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Stäng sidan <bpt id="p1">**</bpt>receptredigering<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="276">
          <source>Click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Klicka på <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="277">
          <source>Follow these steps to do caching of the <bpt id="p1">**</bpt><ph id="ph1">\$</ph>TransType<ept id="p1">**</ept> field:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Gör följande om du vill göra cachelagring av fältet <bpt id="p1">**</bpt><ph id="ph1">\$</ph>TransType<ept id="p1">**</ept>:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="278">
          <source>Select the <bpt id="p1">**</bpt>LedgerTransTypeList<ept id="p1">**</ept> item.</source><target logoport:matchpercent="0" state="translated">Välj bjektet <bpt id="p1">**</bpt>LedgerTransTypeList<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="279">
          <source>Select <bpt id="p1">**</bpt>Cache<ept id="p1">**</ept>.</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Välj <bpt id="p1">**</bpt>cache<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="280">
          <source>Select the <bpt id="p1">**</bpt>VendTable.<ph id="ph1">\$</ph>TransType<ept id="p1">**</ept> item.</source><target logoport:matchpercent="0" state="translated">Välj objektet <bpt id="p1">**</bpt>VendTable.<ph id="ph1">\$</ph>TransType<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="281">
          <source>Select <bpt id="p1">**</bpt>Cache<ept id="p1">**</ept>.</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Välj <bpt id="p1">**</bpt>cache<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="282">
          <source>Caching setup for the $TransType field</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cachelagra inställningar för fältet $TransType</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="283">
          <source>Follow these steps to change the <bpt id="p1">**</bpt><ph id="ph1">\$</ph>TransTypeRecord<ept id="p1">**</ept> field so that it starts to use the cached <bpt id="p2">**</bpt><ph id="ph2">\$</ph>TransType<ept id="p2">**</ept> field:</source><target logoport:matchpercent="0" state="translated">Följ dessa steg för att ändra <bpt id="p1">**</bpt><ph id="ph1">\$</ph>TransTypeRecord<ept id="p1">**</ept> så att det börjar använda cachelagrade fältet <bpt id="p2">**</bpt><ph id="ph2">\$</ph>TransType<ept id="p2">**</ept>:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="284">
          <source>In the <bpt id="p1">**</bpt>Data sources<ept id="p1">**</ept> pane, expand the <bpt id="p2">**</bpt>VendTable<ept id="p2">**</ept> item, expand the <bpt id="p3">**</bpt><ph id="ph1">\&lt;</ph>Relations<ept id="p3">**</ept> item, expand the <bpt id="p4">**</bpt>VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum<ept id="p4">**</ept> item, and select the <bpt id="p5">**</bpt>VendTable. VendTrans.VendTable<ph id="ph3">\_</ph>AccountNum.<ph id="ph4">\$</ph>TransTypeRecord<ept id="p5">**</ept> item.</source><target logoport:matchpercent="0" state="translated">I fönstret <bpt id="p1">**</bpt>Datakällor<ept id="p1">**</ept>, expandera objektet <bpt id="p2">**</bpt>VendTable<ept id="p2">**</ept> expandera objektet <bpt id="p3">**</bpt><ph id="ph1">\&lt;</ph>Relations<ept id="p3">**</ept> expandera objektet <bpt id="p4">**</bpt>VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum<ept id="p4">**</ept> och välj sedan  <bpt id="p5">**</bpt>VendTable. VendTrans.VendTable<ph id="ph3">\_</ph>AccountNum.<ph id="ph4">\$</ph>TransTypeRecord<ept id="p5">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="285">
          <source>Select <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Välj <bpt id="p1">**</bpt>Redigera<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="286">
          <source>Select <bpt id="p1">**</bpt>Edit formula<ept id="p1">**</ept>.</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Välj <bpt id="p1">**</bpt>Redigera recept<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="287">
          <source>In the <bpt id="p1">**</bpt>Formula<ept id="p1">**</ept> field, find the following expression:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">I fältet <bpt id="p1">**</bpt>formel<ept id="p1">**</ept> hittar du följande uttryck:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="288">
          <source>FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = <ph id="ph1">\@</ph>.TransType))</source><target logoport:matchpercent="0" state="translated">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = <ph id="ph1">\@</ph>.TransType))</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="289">
          <source>In the <bpt id="p1">**</bpt>Formula<ept id="p1">**</ept> field, enter the following expression:</source><target logoport:matchpercent="86" state="translated" state-qualifier="fuzzy-match">I fältet <bpt id="p1">**</bpt>formel<ept id="p1">**</ept> anger du följande uttryck:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="290">
          <source>FIRSTORNULL (WHERE (VendTable.'<ph id="ph1">\$</ph>TransType', VendTable.'<ph id="ph2">\$</ph>TransType'.Enum = <ph id="ph3">\@</ph>.TransType)).</source><target logoport:matchpercent="0" state="translated">FIRSTORNULL (WHERE (VendTable.'<ph id="ph1">\$</ph>TransType', VendTable.'<ph id="ph2">\$</ph>TransType'.Enum = <ph id="ph3">\@</ph>.TransType)).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="291">
          <source>Select <bpt id="p1">**</bpt>Save<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Välj <bpt id="p1">**</bpt>Spara<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="292">
          <source>Close the <bpt id="p1">**</bpt>Formula editor<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Stäng sidan <bpt id="p1">**</bpt>receptredigering<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="293">
          <source>Select <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Välj <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="294">
          <source>Select <bpt id="p1">**</bpt>Save<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Välj <bpt id="p1">**</bpt>Spara<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="295">
          <source>Close the <bpt id="p1">**</bpt>Model mapping designer<ept id="p1">**</ept> page.</source><target logoport:matchpercent="0" state="translated">Stäng sidan <bpt id="p1">**</bpt>modellmappningsdesigner<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="296">
          <source>Close the <bpt id="p1">**</bpt>Model mappings<ept id="p1">**</ept> page.</source><target logoport:matchpercent="73" state="translated" state-qualifier="fuzzy-match">Stäng sidan <bpt id="p1">**</bpt>modellmappningar<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="297">
          <source>Complete the modified version of the ER model mapping</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Slutför den ändrade versionen av ER-modellmappningen</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="298">
          <source>In RCS, on the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Versions<ept id="p2">**</ept> FastTab, select version <bpt id="p3">**</bpt>1.2<ept id="p3">**</ept> of the <bpt id="p4">**</bpt>Performance trace mapping<ept id="p4">**</ept> configuration.</source><target logoport:matchpercent="0" state="translated">I RCS, på sidan <bpt id="p1">**</bpt>Konfigurationer<ept id="p1">**</ept> på snabbfliken <bpt id="p2">**</bpt>Versioner<ept id="p2">**</ept> FastTab, välj version <bpt id="p3">**</bpt>1.2<ept id="p3">**</ept> av konfigurationen <bpt id="p4">**</bpt>prestandaspårningsmappning<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="299">
          <source>Select <bpt id="p1">**</bpt>Change status<ept id="p1">**</ept>.</source><target logoport:matchpercent="0" state="translated">Välj <bpt id="p1">**</bpt>Ändra status<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="300">
          <source>Select <bpt id="p1">**</bpt>Complete<ept id="p1">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Välj <bpt id="p1">**</bpt>Slutför<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="301">
          <source>Import the modified ER model mapping configuration from RCS into Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Importera den modifierade ER-modellmappningskonfigurationen från RCS till Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="302">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Import an ER configuration from RCS into Finance and Operations<ept id="p1">](#import-configuration)</ept> section earlier in this topic to import version 1.2 of the <bpt id="p2">**</bpt>Performance trace mapping<ept id="p2">**</ept> configuration into Finance and Operations.</source><target logoport:matchpercent="0" state="translated">Upprepa stegen i avsnittet <bpt id="p1">[</bpt>Importera en ER-konfiguration från RCS till Finance and Operations<ept id="p1">](#import-configuration)</ept> tidigare i det här avsnittet om du vill importera version 1.2 av konfigurationen <bpt id="p2">**</bpt>Prestandaspårningsmappning<ept id="p2">**</ept> i Finance and Operations.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="303">
          <source>Run the modified ER solution to trace execution</source><target logoport:matchpercent="86" state="translated" state-qualifier="fuzzy-match">Kör modifierad ER-lösning för att spåra körning</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="304">
          <source>Run the ER format</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Kör ER-format</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="305">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Run the ER format<ept id="p1">](#run-format)</ept> section earlier in this topic to generate a new performance trace.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Upprepa stegen i avsnittet <bpt id="p1">[</bpt>kör ER-format<ept id="p1">](#run-format)</ept> tidigare i det här avsnittet om du vill generera en ny prestandaspårning.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="306">
          <source>Review the execution trace</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Granska körningsspårningen</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="307">
          <source>Export the generated trace from Finance and Operations</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Exportera den genererade spårningen från Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="308">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Export the generated trace from Finance and Operations<ept id="p1">](#export-trace)</ept> section earlier in this topic to save a new performance trace locally.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Upprepa stegen i avsnittet <bpt id="p1">[</bpt>exportera den genererade spårningen från Finance and Operations<ept id="p1">](#export-trace)</ept> tidigare i det här avsnittet om du vill spara en ny prestandaspårning lokalt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="309">
          <source>Import the generated trace into RCS</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Importera genererad spårning till RCS.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="310">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Import the generated trace into RCS<ept id="p1">](#import-trace)</ept> section earlier in this topic to import the new performance trace into RCS.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">tiUpprepa stegen i avsnittet <bpt id="p1">[</bpt>importera den genererade spårningen till RCS<ept id="p1">](#import-trace)</ept> tidigare i det här avsnittet om du vill importera den nya prestandaspårningen till RCS.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="311">
          <source>Use the performance trace for analysis in RCS – Model mapping</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Använd prestandaspårning för analys i RCS – modellmappning</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="312">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Use the performance trace for analysis in RCS – Model mapping<ept id="p1">](#use-trace)</ept> section earlier in this topic to analyze the latest performance trace.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Upprepa stegen i avsnittet <bpt id="p1">[</bpt>Använd prestandaspårning för analys i RCS – modellmappning<ept id="p1">](#use-trace)</ept> tidigare i det här avsnittet om du vill analysera den senaste prestandaspårningen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="313">
          <source>Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Observera att justeringarna som du har gjort av modellmappningen har eliminerat dubbla frågor till databasen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="314">
          <source>The number of calls to database tables and data sources for this model mapping has been also reduced.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Antalet anrop till databasregister och datakällor för den här modellmappningen har också minskats.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="315">
          <source>Therefore, the performance of the whole ER solution has improved.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Därför har hela ER-lösningens prestanda förbättrats.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="316">
          <source>Trace information for the VendTable data source on the Model mapping designer page in RCS</source><target logoport:matchpercent="74" state="translated" state-qualifier="fuzzy-match">Spårningsinformation för datamodellen VendTable på sidan för modellmappningsdesigner i RCS</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="317">
          <source>In the trace information, the value <bpt id="p1">**</bpt><ph id="ph1">\[</ph>12<ph id="ph2">\]</ph><ept id="p1">**</ept> for the VendTable data source indicates that this data source was called 12 times.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">I spårningsinformationen indikerar värdet <bpt id="p1">**</bpt><ph id="ph1">\[</ph>12<ph id="ph2">\]</ph><ept id="p1">**</ept> för VendTable-datakällan att denna datakälla har anropats 12 gånger.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="318">
          <source>The value <bpt id="p1">**</bpt><ph id="ph1">\[</ph>Q:6<ph id="ph2">\]</ph><ept id="p1">**</ept> indicates that six calls were translated to database calls to the VendTable table.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Värdet <bpt id="p1">**</bpt><ph id="ph1">\[</ph>Q:6<ph id="ph2">\]</ph><ept id="p1">**</ept> anger att sex anrop översattes till databasanrop till VendTable-registret.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="319">
          <source>The value <bpt id="p1">**</bpt><ph id="ph1">\[</ph>C:6<ph id="ph2">\]</ph><ept id="p1">**</ept> indicates that the records that were fetched from the database were cached, and six other calls were processed by using the cache.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Värdet <bpt id="p1">**</bpt><ph id="ph1">\[</ph>C:6<ph id="ph2">\]</ph><ept id="p1">**</ept> indikerar att posterna som hämtades från databasen cachelagrades, och sex andra anrop bearbetades med hjälp av cachen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="320">
          <source>Notice that the number of calls to the LedgerTransTypeList data source has been reduced from 9,027 to 240.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Observera att antalet anrop till datakällan LedgerTransTypeList har minskats från 9 027 till 240.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="321">
          <source>Trace information for the LedgerTransTypeList data source on the Model mapping designer page in RCS</source><target logoport:matchpercent="91" state="translated" state-qualifier="fuzzy-match">Spårningsinformation för datamodellen LedgerTransTypeList på sidan för modellmappningsdesigner i RCS</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="322">
          <source>Review the execution trace in Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Granska körningsspårningen i Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="323">
          <source>In addition to RCS, some versions of Finance and Operations might offer capabilities for an ER framework designer experience.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Förutom RCS kan vissa versioner av Finance and Operations erbjuda funktioner för en ER-ramverk designerupplevelse.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="324">
          <source>These versions of Finance and Operations have an <bpt id="p1">**</bpt>Enable design mode<ept id="p1">**</ept> option that can be turned on.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Dessa versioner av Finance and Operations har alternativet <bpt id="p1">**</bpt>aktivera designläge<ept id="p1">**</ept> som kan aktiveras.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="325">
          <source>You can find this option on the <bpt id="p1">**</bpt>General<ept id="p1">**</ept> tab of the <bpt id="p2">**</bpt>Electronic reporting parameters<ept id="p2">**</ept> page, which you can open from the <bpt id="p3">**</bpt>Electronic reporting<ept id="p3">**</ept> workspace.</source><target logoport:matchpercent="0" state="translated">Du hittar det här alternativet på fliken <bpt id="p1">**</bpt>Allmänt<ept id="p1">**</ept> på sidan <bpt id="p2">**</bpt>parametrar elektronisk rapportering<ept id="p2">**</ept> som du öppnar från arbetsytan <bpt id="p3">**</bpt>elektronisk rapportering<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="326">
          <source>Enable design mode option on the Electronic reporting parameters page in Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Aktivera designlägesalternativet på sidan parametrar för elektronisk rapportering i Finance and Operations</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="327">
          <source>If you use one of these versions of Finance and Operations, you can analyze the details of generated performance traces directly in Finance and Operations.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Om du använder någon av dessa versioner av Finance and Operations kan du analysera detaljerna för genererade resultat spårningar direkt i Finance and Operations.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="328">
          <source>You don't have to export them from Finance and Operation and import them into RCS.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Du behöver inte exportera dem från Finance and Operations och importera dem till RCS.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="329">
          <source>Review the execution trace by using external tools</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Granska körningsspårningen med hjälp av externa verktyg</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="330">
          <source>Configure user parameters</source><target logoport:matchpercent="87" state="translated" state-qualifier="fuzzy-match">Konfigurera användarparametrar</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="331">
          <source>In Finance and Operations, go to <bpt id="p1">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Electronic reporting <ph id="ph2">\&gt;</ph> Configurations<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">I Finance and Operations, gå till <bpt id="p1">**</bpt>Organisationsadministration <ph id="ph1">\&gt;</ph> Elektronisk rapportering <ph id="ph2">\&gt;</ph> Konfigurationer<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="332">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, on the Action Pane, on the <bpt id="p2">**</bpt>Configurations<ept id="p2">**</ept> tab, in the <bpt id="p3">**</bpt>Advanced settings<ept id="p3">**</ept> group, select <bpt id="p4">**</bpt>User parameters<ept id="p4">**</ept>.</source>
        <target logoport:matchpercent="72" state="translated" state-qualifier="leveraged-inherited">På sidan <bpt id="p1">**</bpt>Konfigurationer<ept id="p1">**</ept> i åtgärdsfönstret, på fliken <bpt id="p2">**</bpt>Konfigurationer<ept id="p2">**</ept> i gruppen <bpt id="p3">**</bpt>Avancerad inställningar<ept id="p3">**</ept> markerar du <bpt id="p4">**</bpt>Använd parametrar<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="333">
          <source>In the <bpt id="p1">**</bpt>User parameters<ept id="p1">**</ept> dialog box, in the <bpt id="p2">**</bpt>Execution tracing<ept id="p2">**</ept> section, in the <bpt id="p3">**</bpt>Execution trace format<ept id="p3">**</ept> field, select <bpt id="p4">**</bpt>PerfView XML<ept id="p4">**</ept>.</source><target logoport:matchpercent="0" state="translated">I dialogrutan <bpt id="p1">**</bpt>Användarparametrar<ept id="p1">**</ept> i avsnittet <bpt id="p2">**</bpt>Körningsspårning<ept id="p2">**</ept> i fältet <bpt id="p3">**</bpt>Körnngsspårningsformat<ept id="p3">**</ept>, välj <bpt id="p4">**</bpt>PerfView XML<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="334">
          <source>Run the ER format</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">Kör ER-format</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="335">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Run the ER format<ept id="p1">](#run-format)</ept> section earlier in this topic to generate a new performance trace.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Upprepa stegen i avsnittet <bpt id="p1">[</bpt>kör ER-format<ept id="p1">](#run-format)</ept> tidigare i det här avsnittet om du vill generera en ny prestandaspårning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="336">
          <source>Notice that the web browser offers a zip file for download.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Observera att en zip-fil kan hämtas i webbläsaren.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="337">
          <source>This file contains the performance trace in PerfView format.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Den här filen innehåller prestandaspårningen i PerfView-format.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="338">
          <source>You can then use the PerfView performance analysis tool to analyze the details of ER format execution.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Du kan sedan använda prestandaanalysverktyget PerfView för att analysera information om ER-formatkörning.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>