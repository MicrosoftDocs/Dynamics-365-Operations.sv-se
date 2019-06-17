<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="hardware-sizing-on-premises-environments.md" target-language="sv-SE">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>hardware-sizing-on-premises-environments.e242d0.4832a056a99e0f7521e022982b7db7b16d7064a3.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>4832a056a99e0f7521e022982b7db7b16d7064a3</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>574d4dda83dcab94728a3d35fc53ee7e2b90feb0</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/22/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\fin-and-ops\get-started\hardware-sizing-on-premises-environments.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Hardware sizing requirements for on-premises environments</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Krav för beräkning av maskinvara för lokala miljöer</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic lists the hardware sizing requirements for an on-premises environment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta ämne listar krav för beräkning av maskinvara för lokala miljöer</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Hardware sizing requirements for on-premises environments</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Krav för beräkning av maskinvara för lokala miljöer</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Before you begin the hardware and infrastructure sizing process for an on-premises environment, familiarize yourself with the <bpt id="p1">[</bpt>System requirements<ept id="p1">](system-requirements.md)</ept> and <bpt id="p2">[</bpt>Setup and deployment instructions<ept id="p2">](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md)</ept> to gain a solid understanding off the underlying infrastructure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Innan du påbörjar beräkningsprocessen för maskinvara och infrastruktur för en lokal miljö bör du bekanta dig med <bpt id="p1">[</bpt>systemkrav<ept id="p1">](system-requirements.md)</ept> och <bpt id="p2">[</bpt>instruktioner för installation och distribution<ept id="p2">](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md)</ept> för att få en djupare förståelse av underliggande infrastruktur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>Pay close attention to the system setup best practices for optimum performance.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Var mycket uppmärksam på systeminställningarnas bästa metod för optimal prestanda.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>After you have reviewed the documentation, you can start the process of estimating your transactional and concurrent user volume and sizing your environment based on the average core throughput.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När du har granskat dokumentationen startar du processen för uppskattning av transaktionell och samtidig användarvolym och beräknar din miljö baserat på genomsnittlig grundläggande genomflödesberäkning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Factors that affect sizing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Faktorer som påverkar beräkning</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>All the factors shown in the following illustration contribute to sizing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">De faktorer som visas i följande illustration bidrar till beräkning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>The more detailed information that is collected, the more precisely you can determine sizing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ju mer detaljerad information som samlas in, desto mer exakt kan du bestämma beräkning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Hardware sizing, without supporting data, is likely to be inaccurate.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Maskinvaruberäknning utan stöddata blir sannorlikt felaktig.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The absolute minimum requirement for necessary data is the peak transaction line load per hour.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Absolut minimikravet för nödvändiga data är topptransaktionslinjens belastning per timme.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Hardware sizing for on-premises environments<ept id="p1">](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Beräkna maskinvara för lokala miljöer<ept id="p1">](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Viewed from left to right, the first and most important factor needed to accurately estimate sizing is a transaction profile or a transaction characterization.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sett från vänster till höger, är den första och viktigaste faktorn som krävs för att uppskatta beräkning en transaktionsprofil eller transaktionsbeskrivning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>It's important to always find the peak transactional volume per hour.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det är viktigt att alltid hitta den högsta transaktionella volymen per timme.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>If there are multiple peak periods, then these periods need to be accurately defined.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om det finns flera topperioder, måste dessa perioder fastställas noggrant.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>As you understand the load that impacts your infrastructure, you also need to understand more detail about these factors:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När du förstår den belastning som påverkar din infrastruktur måste du också ta reda mer om dessa faktorer:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source><bpt id="p1">**</bpt>Transactions<ept id="p1">**</ept> – Typically transactions have certain peaks throughout the day/week.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Transaktioner<ept id="p1">**</ept> - Transaktioner har normalt vissa toppar under dagen/veckan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>This mostly depends on the transaction type.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta beror oftast på transaktionstypen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Time and expense entries usually show peaks once per week, whereas Sales order entries often come in bulk via integration or trickle in during the day.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tids- och kostnadsposterna visar vanligtvis toppar en gång i veckan och försäljningsorderposter levereras ofta i bulk via integrering eller droppar in under dagen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source><bpt id="p1">**</bpt>Number of concurrent users<ept id="p1">**</ept> – The number of concurrent users is the second most important sizing factor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Antalet samtidiga användare<ept id="p1">**</ept> – Antalet samtidiga användare är den näst viktigaste beräkningsfaktorn.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>You cannot reliably get sizing estimates based on the number of concurrent users, so if this is the only data you have available, estimate an approximate number, and then revisit this when you have more data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Du kan inte tillförlitligt få beräkningsuppskattningar utifrån antalet samtidiga användare, så om detta är de enda data som finns, beräknar du ett ungefärligt nummer och ångrar detta om det finns mer data.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>An accurate concurrent user definition means that:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En exakt samtidig användardefinition innebär:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Named users are not concurrent users.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Namngivna användare är inte samtidiga användare.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Concurrent users are always a subset of named users.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Samtidiga användare är alltid en uppsättning namngivna användare.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Peak workload defines the maximum concurrency for sizing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Högsta belastning definierar högsta samtidighet för beräkning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Criteria for concurrent users is that the user meets all the following criteria:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kriterier för samtidiga användare är att användaren uppfyller följande kriterier:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Logged on.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Har loggat in.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>Working transactions/inquiries at the time of counting.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Arbetar med transaktioner/förfrågningar vid tidpunkten för inventering.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Not an idle session.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inte en inaktiv session.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source><bpt id="p1">**</bpt>Data composition<ept id="p1">**</ept> – This is mostly about how your system will be set up and configured.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Datasammansättning<ept id="p1">**</ept> – Detta är om hur datorn ställs in och konfigureras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>For example, how many legal entities you will have, how many items, how many BOM levels, and how complex your security setup will be.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Till exempel hur många juridiska personer som du har, hur många artiklar, hur många olika strukturlistenivåer och hur komplexa dina säkerhetsinställningar kommer att vara.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Each of those factors may have a small impact on performance, so these factors can be offset by using smart choices when it comes to infrastructure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Var och en av de faktorer som kan påverka lite på prestanda, så att dessa faktorer kan avräknas genom att använda avancerade alternativ när det gäller infrastruktur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source><bpt id="p1">**</bpt>Extensions<ept id="p1">**</ept> – Customizations can be simple or complex.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Tillägg<ept id="p1">**</ept> – Anpassningar kan vara enkel eller komplex.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>The number of customizations and the nature of complexity and usage has a varied impact on the size of the infrastructure needed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Antalet anpassningar och komplexitet och användningen har olika påverkan på beräkningen av den infrastruktur som behövs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>For complex customizations, it's advised to conduct performance evaluations to ensure that they are not only tested for efficiency but also help understand the infrastructure needs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För komplexa anpassningar är det tillrådligt att genomföra en utvärdering av prestanda så att de inte bara testats för effektivitet utan också att förstå infrastrukturen som behövs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>This is even more critical when the extensions are not coded according to best practices for performance and scalability.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta är ännu mer viktigt när tillägg inte är kodade enligt bästa praxis för prestanda och skalbarhet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source><bpt id="p1">**</bpt>Reporting and analytics<ept id="p1">**</ept> – These factors typically include running heavy queries against the various databases in the Finance and Operations database systems.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Rapportering och analyser<ept id="p1">**</ept> – Dessa faktorer inkluderar normalt körning av tunga frågor mot olika databaser i Finance and Operations-databassystem.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Understanding and reducing the frequency when expensive reports run will help you understand the impact of them.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Förstå och minska frekvensen när dyra rapporter körs som hjälper dig att förstå vilken inverkan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source><bpt id="p1">**</bpt>Third-party solutions<ept id="p1">**</ept> – These solutions, like ISVs, have the same implications and recommendations as extensions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Tredjepartslösningar<ept id="p1">**</ept> – Dessa lösningar som t.ex. ISV, har samma konsekvenser och rekommendationer som tillägg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Sizing your Finance and Operations environment</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beräkna Finance and Operation-miljön</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>To understand your sizing requirements, you need to know the peak volume of transactions that you need to process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att förstå dina beräkningskrav måste du veta högsta transaktionsvolymen du måste bearbeta.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Most auxiliary systems, like Management Reporter or SSRS, are less mission critical.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">De kompletterande system som Management Reporter eller SSRS, är mindre verksamhetskritiska.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>As a result, this document focuses mostly on AOS and SQL Server.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta innebär att detta dokument innehåller typiska oftast AOS och SQL Server.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>In general, the compute tiers scale out and should be set up in an N+1 fashion, meaning if you estimate three AOS, add a fourth AOS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I allmänhet beräknas nivåer skala ut och ska ställas in på N+1-sätt, vilket innebär att om du uppskattar tre AOS, lägger du till ett fjärde AOS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>The database tier should be set up in an Always On highly-available setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Databasskiktet ska ställas in i en alltid på hög tillgänglighetsinställning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>SQL Server (OLTP)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">SQL Server (OLTP)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>Sizing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beräkning</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>3K to 15K transaction lines per hour per core on DB server.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">3K till 15K transaktionsrader per timme per kärna på databasserver.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Typical AOS-to-SQL core ratio 3:1 for the primary SQL Server.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Typiska AOS-SQL-kärnförhållandet mellan 3:1 för den primära SQL-servern.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Additional cores are required based on the chosen high availability configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ytterligare kärnor krävs utifrån den valda konfigurationen med hög tillgänglighet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Processing database-heavy operations may regress this to 2:1.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Behandling av databastunga åtgärder kan gå tillbaka till detta 2:1.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The following factors influence variations:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Följande faktorer påverkar varianter:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>Parameter settings in use.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Parameterinställningarna används.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>Levels of extensions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tilläggsnivåer.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>Usage of additional functionality, such as database log and alerts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Användning av flera funktioner, som t.ex. logg och varningar.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Extreme database logging will further reduce throughput per hour per core below 3K lines.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Extrema databainloggning kommer att ytterligare minska per timme per kärna under 3K rader.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>Complexity of data composition – A simple chart of accounts versus a detailed fine-grained chart of accounts has implications on throughput (as an example).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Komplex datasammansättning – en enkel kontoplanen jämfört med mer detaljerad kontoplan har konsekvenser på genomflödet (exempelvis).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Transaction characterization.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beskrivning av transaktionen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>2 GB to 16 GB memory for each core.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">2 GB till 16 GB minne, för varje kärna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Auxiliary databases on DB server such as Management reporter and SSRS databases.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Extra databaser på en databasserver som t.ex. Management reporter och SSRS-databaser.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>Temp DB = 15% of DB size, with as many files as physical processors.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Temp DB = 15 % av storleken på DB, med så många filer som fysiska processorer.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>SAN size and throughput based on total concurrent transaction volume/usage.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">SAN-storlek och genomflöde baserat på total samtidig transaktionsvolym/användning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>High availability</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Hög tillgänglighet</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>We recommend always utilizing SQL Server in either a cluster or mirroring setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vi rekommenderar alltid att använda SQL Server i antingen ett kluster eller speglingsinställning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>The second SQL node should have the same number of cores as the primary node.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Den sekundära SQL-noden ska ha samma antal kärnor som den primära noden.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Active Directory Federation Services (AD FS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Active Directory Federation Services (AD FS)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>For AD FS sizing, see the <bpt id="p1">[</bpt>AD FS Server Capacity documentation<ept id="p1">](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För beräkning av AD FS, se <bpt id="p1">[</bpt>AD FS serverkapacitetdokumentation<ept id="p1">](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>A <bpt id="p1">[</bpt>sizing spreadsheet<ept id="p1">](https://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx)</ept> is available for planning the number of instances in your deployment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ett <bpt id="p1">[</bpt>beräkningskalkylblad<ept id="p1">](https://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx)</ept> är tillgänglig för att planera antalet instanser i distributionen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>AOS (Online and batch)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AOS (Online och batch)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>Sizing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beräkning</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>Sizing by transaction volume/usage</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beräkning efter transaktionsvolym/användning</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>2K to 6K lines per core</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">2K till 6K rader per kärna</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>16 GB per instance</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">16 GB per instans</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Standard box – 4 to 24 cores</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Standardruta – 4 till 24 kärnor</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>10 to 15 Enterprise users per core</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">10 till 15 företagsanvändare per kärna</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>15 to 25 Activity users per core</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">15 till 25 aktivitetsanvändare per kärna</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>25 to 50 Team members per core</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">25 till 50 gruppmedlemmar per kärna</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>Batch</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Batch</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>1 to 4 batch threads per core</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">1 till 4 batchtrådar per kärna</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Size based on batch window characterization</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beräkning baserad på batchfönsterkarakterisering</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Note that the AOS, Data Management, and Batch are on the same role in the Service Fabric.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Observera att AOS, datahantering och batch är på samma roll i Service Fabric.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>You need to size for these three workloads combined, and not separate these like in Microsoft Dynamics AX 2012.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Du behöver beräkna dessa arbetsbelastningar kombinerat, och inte dela dem som i Microsoft Dynamics AX 2012.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>The same variability factors for SQL Server apply here.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Samma variantfaktorer för SQL Server gäller här.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>High availability</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Hög tillgänglighet</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Ensure that you have at least 1 to 2 more AOS available than you estimate.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kontrollera att du har minst 1 till 2 fler AOS tillgängliga än du uppskattar.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Ensure that you have at least 3 to 4 virtual hosts available.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kontrollera att du har minst 3 till 4 virtuella värdar tillgängliga.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Management reporter</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Management Reporter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>In most cases, unless used extensively, the recommended minimum requirements using two nodes should work well.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I de flesta fall, om de inte används mycket, ska de rekommenderade minimikraven med två noder fungerar bra.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>Only in cases where there is heavy use will you need more than two nodes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I de fall där det inte används mycket behöver du fler än två noder.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Please scale as needed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ange skala efter behov.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>SQL Server Reporting Services</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">SQL Server Reporting Services </target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>For the general availability release, only one SSRS node can be deployed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En SSRS-nod kan användas för normal tillgänglighet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>Monitor your SSRS node while testing and increase the number of cores available for SSRS on a need basis.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Övervaka din SSRS-nod medan du testar och ökar antalet kärnor tillgängliga för SSRS på grundval av behov.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>Make sure that you have a preconfigured secondary node available on a virtual host that is different than the SSRS VM.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kontrollera att du har en tillgänglig förkonfigurerad sekundär nod på en virtuell värd som är en annan än SSRS VM.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>This is important if there is an issue with the virtual machine that hosts SSRS or the virtual host.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta är viktigt om det finns ett problem med den virtuella datorn som är värd för SSRS eller den virtuella värden.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>If this the case, they would need to be replaced.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om så är fallet behöver du byta ut dem.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Environment Orchestrator</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Orchestrator-miljö</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>The Orchestrator service is the service that manages your deployment and the related communication with LCS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Orchestrator-tjänsten är en tjänst som hanterar distributionen och relaterad kommunikation med LCS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>This service is deployed as the primary Service Fabric service and requires at least three VMs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Denna tjänst används som primär Service Fabric-tjänst och kräver minst tre virtuella maskiner.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>This service is co-located with the Service Fabric orchestration services.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Denna tjänst är samlokaliserad med Service Fabric-orchestrationtjänsterna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>This and should be sized to the peak load of the cluster.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta bör beräknas till toppbelastning för klustret.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>For more information, see <bpt id="p1">[</bpt>Service Fabric cluster capacity planning considerations<ept id="p1">](/azure/service-fabric/service-fabric-cluster-capacity)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mer information finns i <bpt id="p1">[</bpt>Kapacitetsplanering för Service Fabric-kluster<ept id="p1">](/azure/service-fabric/service-fabric-cluster-capacity)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>Virtualization and oversubscription</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Virtualisering och överabonnemang</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>Mission critical services like the AOS should be hosted on Virtual hosts that have dedicated resources – cores, memory, and disk.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Missionskritiska tjänster som AOS bör finnas på virtuella värdar som har dedikerade resurser - kärnor, minne och disk.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>