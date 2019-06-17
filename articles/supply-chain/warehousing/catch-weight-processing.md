<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="catch-weight-processing.md" target-language="sv-SE">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>catch-weight-processing.d3ca7d.6e295456838ca0195a472518b5979dfdc7819f74.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>6e295456838ca0195a472518b5979dfdc7819f74</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>19859d8566a8c7840066b2c10c6b08b67f1b83f4</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/04/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\supply-chain\warehousing\catch-weight-processing.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Catch weight product processing with warehouse management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Bearbetning av produkt i faktisk/nominell vikt med lagerstyrning</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes how to use work templates and location directives to determine how and where work is done in the warehouse.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta avsnitt beskriver hur man använder mallar och placering direktiven för att bestämma hur och var arbetet utförs i lagret.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Catch weight product processing with warehouse management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Bearbetning av produkt i faktisk/nominell vikt med lagerstyrning</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Feature exposure</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Funktionen exponering</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>To use warehouse management to process catch weight products, you must use a license configuration key to turn on the functionality.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om du vill använda lagerstyrning för att bearbeta produkt i faktisk/nominell vikt måste du använda en licensnyckelkonfiguration för att aktivera funktionen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>(Go to <bpt id="p1">**</bpt>System administration <ph id="ph1">\&gt;</ph> Setup <ph id="ph2">\&gt;</ph> License configuration<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">(Gå till <bpt id="p1">**</bpt>Systemadministration <ph id="ph1">\&gt;</ph> Inställningar <ph id="ph2">\&gt;</ph> Licenskonfiguration<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Then, on the <bpt id="p1">**</bpt>Configuration keys<ept id="p1">**</ept> tab, expand <bpt id="p2">**</bpt>Trade <ph id="ph1">\&gt;</ph> Warehouse and Transportation management<ept id="p2">**</ept>, and select the check box for <bpt id="p3">**</bpt>Catch weight for warehouse<ept id="p3">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Klicka sedan på fliken <bpt id="p1">**</bpt>konfigurationsnycklar<ept id="p1">**</ept>, expandera <bpt id="p2">**</bpt>handel <ph id="ph1">\&gt;</ph> hantering av lager och transport<ept id="p2">**</ept> och markera kryssrutan för <bpt id="p3">**</bpt>faktisk/nominell vikt för lagerstället<ept id="p3">**</ept>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Both the <bpt id="p1">**</bpt>Warehouse and Transportation management<ept id="p1">**</ept> license configuration key and the <bpt id="p2">**</bpt>Process distribution <ph id="ph1">\&gt;</ph> Catch weight<ept id="p2">**</ept> license configuration keys must also be turned on.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Både <bpt id="p1">**</bpt>hantering av lager och transport<ept id="p1">**</ept> licensnyckeln för konfiguration och <bpt id="p2">**</bpt>Processfördelning <ph id="ph1">\&gt;</ph> faktisk/nominell vikt<ept id="p2">**</ept> måste också aktiveras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>After the license configuration key is turned on, when you create a released product, you can select <bpt id="p1">**</bpt>Catch weight<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Efter att licenskonfigurationens nyckel är inaktiverad, när du skapar en frisläppt produkt, kan du välja <bpt id="p1">**</bpt>faktisk/nominell vikt<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>You can also associate the released product with a storage dimension group that the <bpt id="p1">**</bpt>Use warehouse management processes<ept id="p1">**</ept> parameter is selected for.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Du kan också koppla frisläppt produkt till en lagringsdimension som parametern <bpt id="p1">**</bpt>använda processer för lagerhantering<ept id="p1">**</ept> väljs för.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Before you can use the product in Warehouse management, you must do some basic product-specific setup for catch weight:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Innan du kan använda produkten i lagerstyrning, måste du göra vissa grundläggande produktspecifika inställningar för faktisk/nominell vikt:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>Define the nominal weight conversion between the catch weight unit (box) and the inventory unit (kilogram <ph id="ph1">\[</ph>kg<ph id="ph2">\]</ph>) as part of a unit conversion definition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Definiera konverteringen mellan enheten för faktisk/nominell vikt (låda) och lagerenheten (kilogram <ph id="ph1">\[</ph>kg<ph id="ph2">\]</ph>) som en del av en definition för enhetskonvertering.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Define the minimum and maximum weight tolerances as part of the catch weight unit setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ange minimi- eller maximivikttoleranser som del av inställningen av faktisk/nominell viktenhet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Set up a unit sequence group where the catch weight unit is defined as the lowest stock keeping unit (SKU).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skapa en enhetssekvensgrupp där faktisk/nominell viktenheten definieras som den lägsta lagerhållningsenhet (SKU).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Set up a catch weight item handling policy.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ställ in en policy för hantering av faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>For more information, see <bpt id="p1">[</bpt>Setting up and maintaining catch weight items<ept id="p1">](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mer information finns i <bpt id="p1">[</bpt>ställa in och underhålla artiklar i faktisk/nominell vikt<ept id="p1">](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Transaction adjustments</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Transaktionjusteringar</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Because the weight of inventory when it comes into a warehouse can differ from the weight when the inventory is issued out of the warehouse, the catch weight product processing must adjust the inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Eftersom vikten av lagret när det gäller i ett lagerställe kan skilja sig från vikt när lagret utfärdas från lagerstället, måste bearbetning av produkt med faktisk/nominell vikt justera lagret.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source><bpt id="p1">**</bpt>Example 1<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Exempel 1<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>During a <bpt id="p1">**</bpt>Report as finished<ept id="p1">**</ept> production process, the inbound weight of a license plate that contains eight boxes of a catch weight product is captured as 80.1 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Under produktionsprocessen <bpt id="p1">**</bpt>rapportera som färdig<ept id="p1">**</ept> måste den inkommande vikten av en registreringsskylt som innehåller åtta rutor hos en produkt faktisk/nominell vikt registreras som 80,1 kg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>The license plate is then stored away in the finished goods area, and during the storage period, some weight is lost into the air.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Registreringsskylt lagras direkt i området för färdiga varor och under lagringsperioden, försvinner viss vikt i luften.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Later, as part of a sales order picking process, the weight of the same license plate is captured as 79.8 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vikten av samma registreringsskylt fångas senare som en del av en process, plockning försäljningsorder som 79,8 kg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Therefore, in the system, you now have a weight difference as part of the physical dimension set.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Därför har du i systemet en viktskillnad som en del av fysiska dimensionsuppsättningen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>In this case, the system automatically adjusts the difference by posting a transaction for the missing 0.3 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här fallet justeras skillnaden automatiskt genom att bokföra en transaktion för saknade 0,3 kg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source><bpt id="p1">**</bpt>Example 2<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Exempel 2<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>In its definition, a product is set up to tolerate a minimum weight of 8 kg and a maximum weight of 12 kg for the <bpt id="p1">**</bpt>Box<ept id="p1">**</ept> catch weight unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I dess definition ställs en produkt in för att klara en lägsta vikt på 8 kg och en maximal vikt på 12 kg för enhet för faktisk/nominell vikt <bpt id="p1">**</bpt>låda<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>You have two boxes of the product, and they have a registered weight of 16 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Du har två lådor av produkten och de har 16 kg registrerad vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>If a warehouse worker picks and weighs one of the boxes, and the weight is captured as 9 kg, the remaining box will weigh 7 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om lagerarbetare plockar väger en av lådorna och vikt registreras som 9 kg, väger återstående fält 7 kg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>However, because 7 kg is below the minimum weight, the system does an automatic adjustment to increase the weight of the on-hand inventory by 1 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Men eftersom 7 kg är lägre än lägsta vikten, gör systemet en automatisk justering för att öka vikten på lagerbehållningen med 1 kg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>To set up the accounts that these adjustments are posted to, go to <bpt id="p1">**</bpt>Cost management <ph id="ph1">\&gt;</ph> Ledger integration policies setup <ph id="ph2">\&gt;</ph> Posting<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om du vill ställa in kontona justeringarna bokförs på Gå till <bpt id="p1">**</bpt>kostnadshantering <ph id="ph1">\&gt;</ph> Ställ in policyer för redovisningsintegrering <ph id="ph2">\&gt;</ph> bokföring<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Then, on the <bpt id="p1">**</bpt>Inventory<ept id="p1">**</ept> tab, define the following accounts:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Klicka sedan på fliken <bpt id="p1">**</bpt>lager<ept id="p1">**</ept>, ange följande konton:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Catch weight loss account</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Förlustkonto för faktisk/nominell vikt</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Catch weight profit account</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vinstkonto för faktisk/nominell vikt</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>Catch weight item handling policy</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Hanteringspolicy för artiklar i faktisk/nominell vikt</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>The catch weight item handling policy defines two primary warehouse management flows for the items: when the weight of the items is captured, and how it's captured.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Hanteringspolicy för artikel med faktisk/nominell vikt definierar två primära flöden för lagerställehantering för artiklar: när vikten på artiklarna registreras och hur den hämtas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>You can define when the weight is captured for sales and transfer order processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Du kan definiera när vikt registreras för orderbehandling för försäljning och överföring.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>The weight can be captured during either of the following processes:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vikten kan hämtas under någon av följande processer:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source><bpt id="p1">**</bpt>Picking<ept id="p1">**</ept> – The weight is captured during the initial pick work lines of order work.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Plockning<ept id="p1">**</ept> – vikten registreras under första plockningsraderna för orderarbete.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source><bpt id="p1">**</bpt>Packing<ept id="p1">**</ept> – The weight is captured during manual packing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Packning<ept id="p1">**</ept> – vikten registreras under manuell packning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>(You must send the items to a packing station.)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">(Du måste skicka artiklar till en förpackningsstation.)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>If the actual weight is captured at the packing station during the container packing processes, warehouse workers won't be prompted to capture the weight during picking work.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om den faktiska vikten registreras in på förpackningsstationen under packning av behållar ombeds lagerarbetare att inte hämta vikten vid plockningsarbete.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Instead, the average weight of the physical inventory will be used as the weight of the picked inventory that goes to the packing area.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I stället används genomsnittlig vikt för fysiskt lager som vikt för det plockade lagret som leder till packningsområdet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>For internal warehouse management processes like counting and adjustment corrections it is possible to define if the weight should be captured or not.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För interna lagerhanteringsprocesser som räkning och justeringskorrigeringar är det möjligt att definiera om vikten ska registreras eller inte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>If not captured the nominal weight will be used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om inte registrerad ska nominell vikt användas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>You can also define how the weight is captured.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Du kan definiera hur vikt registreras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>In one of the two main flows, catch weight tags are tracked and used to capture the weight.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I den ena av två huvudsakliga flöden fångstvikt taggar spåras och används för att hämta vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In the other flow, catch weight tags aren't tracked.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det andra flödet spåras inte faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source><bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> – The item uses catch weight tags.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Ja<ept id="p1">**</ept> - artikel används i faktisk/nominell vikt taggar.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Each tag number represents one catch weight unit (box), and a weight and other information are associated with the tag.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Varje taggnummer motsvarar en enhet för faktisk/nominell vikt (låda) och en vikt och annan information som är associerad med taggen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>For outbound processes, the weight that is associated with the tag is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vikten som är associerad med taggen används för utgående processer.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source><bpt id="p1">**</bpt>No<ept id="p1">**</ept> – The item doesn't use catch weight tags.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Nej<ept id="p1">**</ept> – artikeln använder inte nominella vikttaggar.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The inbound and outbound weighing processes are based on the actual weight that is captured during each process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inkommande och utgående vägningsprocesser baseras på den faktiska vikten som registreras under varje process.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>The process of tracking catch weight tags can be used for items that won't change weight during the storage period.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Processen för att spåra faktisk/nominell vikt kan användas för artiklar där vikten inte förändras under lagringsperiodens.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>The weight will be captured only during the inbound warehouse process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vikten registreras bara i processer för ankommande lager.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>During the outbound process, the catch weight tags will just be scanned, and the weights that are associated with the tags will be used for the outbound transactional processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Under den utgående processen kommer taggar för faktisk/nominell vikt bara att skannas och vikterna som är associerade med taggarna kommer att användas för utgående transaktionsbehandling.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>How to capture catch weight</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Så här registrerar du faktisk/nominell vikt</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>When catch weight tag tracking is used, a tag must always be created for every catch weigh unit that is received, and every tag must always be associated with a weight.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När spårning av taggar för faktisk/nominell vikt används måste taggen alltid skapas för varje faktisk/nominell viktenhet som tas emot och varje tagg måste alltid associeras med en vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>For example, <bpt id="p1">**</bpt>Box<ept id="p1">**</ept> is the catch weight unit, and you receive one pallet of eight boxes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Till exempel <bpt id="p1">**</bpt>Låda<ept id="p1">**</ept> är faktisk/nominell viktenheten och du får en lastpall med åtta lådor.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>In this case, eight unique catch weight tags must be created, and a weight must be associated with each tag.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här fallet måste åtta unika taggar för faktisk/nominell vikt skapas och en vikt måste vara associerad med varje tagg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Depending on the inbound catch weight tag, either the weight of all eight boxes can be captured, and the average weight can then be distributed to each box, or a unique weight can be captured for each box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beroende på taggen för inkommande faktisk/nominell vikt måste antingen vikten för alla åtta lådor registreras och den genomsnittliga vikten som sedan kan distribueras till varje låda eller en unik vikt registreras in för varje låda.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>When catch weight tag tracking isn't used, the weight can be captured for each dimension set (for example, for each license plate and tracking dimension).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När spårning av tagg för faktisk/nominell vikt inte används registreras vikten för varje dimensionsuppsättning (till exempel för varje registreringsskylt och spårningsdimension).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Alternatively, the weight can be captured based on an aggregated level, such as five license plates (pallets).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Du kan också registrera vikten in baserat på aggregerad nivå, t.ex. fem registreringsskyltar (lastpallar).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>For the methods for capturing outbound weight, you can define whether the weighing is done for each catch weight unit (that is, per box), or whether the weight is captured based on the quantity that will be picked (for example, three boxes).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För metoder för att registrera utgående vikt, kan du ange om vägning utförs för varje faktisk/nominell viktenhet (det vill säga varje låda), eller om vikten registreras baserat på den kvantitet som plockas (t.ex. tre lådor).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Note that for the production line picking and internal movement processes, the average weight will be used if the <bpt id="p1">**</bpt>Not captured<ept id="p1">**</ept> option is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Observera att för plocknings- och interna förflyttningsprocessen ska genomsnittsvikten användas om alternativet <bpt id="p1">**</bpt>inte registrerad<ept id="p1">**</ept> används.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>To restrict the warehouse management picking processes from capturing weights resulting in catch weight profit/loss adjustments, the Outbound weight variance method can be used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att begränsa att lagerstyrningens plockningsprocesser samlar in vikter som resulterar i för justeringar av vinst/förlust för faktisk/nominell vikt kan utgående viktavvikelsemetod användas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Supported scenarios</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Stödda scenarier</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Not all workflows support catch weight product processing with warehouse management.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Alla arbetsflöden stöder inte bearbetning av produkt i faktisk/nominell vikt med lagerstyrning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>The following restrictions currently apply.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Följande begränsningar gäller för tillfället.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>Configuring catch weight products for warehouse management processes</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Bearbetning av produkt i faktisk/nominell vikt med lagerstyrningsprocesser</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>For catch weight products, the storage dimension group for items can't be changed (so that warehouse management processes can be used for them).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För produkter med faktisk/nominell vikt kan inte lagringsdimensionsgruppen för artiklar ändras (så att lagerprocess hantering kan användas för dem).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>Only formula processing is supported for catch weight products (not bill of materials).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Endast formelbearbetning stöds för produkter med faktisk/nominell viktfaktisk/nominell vikt (inte strukturlista).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>Catch weight products can't be associated with a tracking dimension group by using the Owner dimension.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Produkter med faktisk/nominell vikt kan inte associeras med en spårningsdimensionsgrupp med dimensionsägare.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Catch weight products can't be used as services.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Produkter med faktisk/nominell vikt kan inte användas som tjänster.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Catch weight products can be used as "stocked products" only as part the item model group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Produkter med faktisk/nominell vikt kan endast användas som ”produkter som finns i lager” som del av artikelmodellgruppen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Catch weight products can't be used together with the functionality for tracking "Active in sales process."</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Produker med faktisk/nominell vikt kan inte användas tillsammans med funktionen för att spåra ”Aktiv i försäljningsprocessen”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>Catch weight products can't be used together with the functionality for capturing serial numbers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Produker med faktisk/nominell vikt kan inte användas tillsammans med funktionen för att registrera serienummer.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>Therefore, products can't be transferred from a "blank" to a serial number as part of the picking/packing process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Därför kan inte produkter föras över från ”tom” till ett serienummer som en del av plockning/packningsprocessen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>Catch weight products can't be used together with the functionality for registering serials before consumption.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Produker med faktisk/nominell vikt kan inte användas tillsammans med funktionen för att registrera serienummer före förbrukning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>Catch weight products that are variant-enabled can't be used together with the functionality for converting variant units of measure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Produkter med faktisk/nominell vikt som är variantaktiverade kan inte användas tillsammans med funktionen för att konvertera en variant av måttenhet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Catch weight products can't be marked as a retail "product kit."</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En produkt med faktisk/nominell vikt kan inte markeras som produktpaket.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Catch weight products can be used only with a unit sequence group that has catch weight handling units, and that has the catch weight unit as the lowest sequence.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Produkt med faktisk/nominell vikt kan bara användas med en enhetssekvensgrupp med faktisk/nominell vikthanteringsenheter och som har som lägst sekvens av faktisk/nominell viktenhet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>For catch weight products, the inventory unit can be converted to the catch weight unit only if the conversion produces a nominal quantity that is more than 1.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För produkter med faktisk/nominell vikt får lagerenheten endast omvandlas till faktisk/nominell viktenhet om konvertering ger en nominell kvantitet som är mer än 1.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>The setup of bar codes for catch weight products doesn't support a variable weight setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inställningen av streckkoder för produkter med faktisk/nominell vikt stöder inte en variabel inställning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Order processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Orderbehandling</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>The creation of advance ship notice (ASN/packing structures) doesn't support weight information.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skapandet av leveransavisering (ASN/förpackningsstruktur) stöder inte information om vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>The order quantity must be maintained based on the catch weight unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Orderkvantiteten måste underhållas utifrån faktisk/nominell viktenheten.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Inbound warehouse processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Bearbetning av ingående lagerställe</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>Receiving license plates requires that weights be assigned during registration, because weight information isn't supported as part of the advance ship notice.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ta emot registreringsskyltar kräver att vikter tilldelas under registreringen, eftersom viktinformation inte stöds som en del av leveransaviseringen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>When catch weight tag processes are used, the tag number must be manually assigned per catch weight unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Processer för taggar för faktisk/nominell vikt när taggnummer måste tilldelas manuellt per faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Inventory and warehouse operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Operationer för lager och lagerställen</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>Manual creation of quarantine orders isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skapa karantänorder manuellt stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>Manual movement of inventory that is related to work isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Manuell lagerförflyttning relaterad till arbete stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>Consolidation of license plates isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Konsolidering av licensskyltar stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>License plate loading to initialize warehouse stock isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Inläsningen av registreringsskylt initierar lagerställe stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Batch balancing processes aren't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Batchbalanseringsprocesser stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Handling of negative physical inventory isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Hantering av fysiskt negativt lager stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Inventory marking can't be used for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lagermarkering kan inte användas för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>Outbound warehouse processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Bearbetning av utgående lagerställe</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>The functionality for cluster picking isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Funktionen för plockning av kluster stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>Pick and pack warehouse processing isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Lagerbearbetning för plocka och packa stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>For catch weight products, work that is defined in a work template can be run automatically.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Produkter med faktisk/nominell vikt som definieras i en arbetsmall kan köras automatiskt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>The functionality for reversing work isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Funktionen för återföringsarbete stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>For catch weight products, manual packing station processing where work is created after containers are closed isn't supported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För produkter med faktisk/nominell vikt stöds inte manuell stationsbearbetning där arbete skapas när behållare stängs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>The functionality for pcs-by-pcs scanning isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Funktionen för skanning styckvis stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Production processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Produktionsprocess</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>For catch weight products, only batch orders for formula products are supported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För produkter med faktisk/nominell vikt stöds endast batchorder för formelprodukter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>Kanban functionality isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kanban-funktionen stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>For catch weight products, serial numbers can't be registered before consumption.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Serienummer kan inte registreras före förbrukning för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>The functionality for reversing license plates isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Funktionen för återföring av registreringsskylt stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>For catch weight products, reporting as finished cannot be registered by serial number.</source><target logoport:matchpercent="94" state="translated" state-qualifier="fuzzy-match">Produkter med faktisk/nominell vikt kan inte rapporteras som färdig registreras efter serienummer.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Transportation management processing</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Transporthanteringsprocesser</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Load building workbench processing isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Workbench för lastuppbyggnad stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>Transport request lines aren't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rader för transportförfrågan stöds inte för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>Other restrictions and behaviors for catch weight product processing with warehouse management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Andra begränsningar och beteenden för processer med produkter med faktisk/nominell vikt med lagerstyrning</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>During picking processes where the user isn't prompted to identify tracking dimensions, the weight assignment is done based on the average weight.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vid plockningsprocesser där användaren inte ombeds att identifiera spårningsdimensioner sker viktfördelningen utifrån den genomsnittliga vikten.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>This behavior occurs when, for example, a combination of tracking dimensions is used in the same location and, after a user processes picking, only one tracking dimension value is left in the location.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta beteende uppstår när exempelvis en kombination av spårningsdimensioner används på samma plats och efter att en användare bearbetar plockning lämnas endast en spårningsdimension kvar på platsen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>When inventory is reserved for a catch weight product that is configured for warehouse management processes, the reservation is done based on the minimum weight that is defined, even if this quantity is the on-hand last handling quantity.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När lagret reserveras för en produkt med faktisk/nominell vikt som är konfigurerad för lagerhanteringsprocesser görs bokningen baserat på den minsta vikten som definieras, även om den här kvantiteten är den sista hanteringskvantiteten.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>This behavior differs from the behavior for items that aren't configured for warehouse management processes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta beteende skiljer sig från funktionen för artiklar som inte är konfigurerade för hantering av lagerprocesser.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>Processes that use the weight as part of capacity calculations (wave thresholds, work maximum breaks, container maximums, location load capacities, and so on) don't use the actual weight of the inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Processer som använder vikten som en del av kapacitetsberäkningar (vågtröskelvärden, arbetets maximala raster, maximal kapacitet för behållare, lastningskapacitet för platsen och så vidare) använder inte lagrets faktiska vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>Instead, the processes are based on the physical handling weight that is defined for the product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I stället baseras processer på vikten av fysisk hantering som är definierad för produkten.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>In general, Retail functionality isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I allmänhet stöds inte butiksfunktionen för produkter med faktisk/nominell vikt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>Catch weight tags</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Taggar för faktisk/nominell vikt</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>Currently, the functionality for catch weight tags is supported only as part of the following scenarios:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Funktionerna för taggar för faktisk/nominell vikt stöds för närvarande bara som en del av följande scenarier:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>When processing purchase order warehouse app receiving.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När bearbetning av inköpsorder för inleverans via lagerapp.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>When processing load receiving via warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När bearbetning av mottagande av last via lagerapp.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>For license plate receiving that is related to a purchase order load, weight assignment is requested during the receiving process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För inleverans av registreringsskylt relaterad till inköpsorderns last, begärs vikttilldelning under inleveransen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>By contrast, for transfer order receiving, the weight from the shipment data for the transfer order is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Däremot för inleverans av överföringsorder används vikt från försändelsedata för överföringsordern.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>For transfer order item and line receiving that comes from a non-warehouse management process warehouse.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För överföringsorder och radmottagning som kommer från en hanteringsprocess för icke-lagerställe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>The processing of sales return order receiving can record catch weight tags, but the processing won't be validated if the tags are the same tags that were originally shipped for a particular sales order line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Behandlingen av inleverans av försäljningsreturorder kan registrera taggar för faktisk/nominell vikt, men bearbetningen kommer inte att valideras om taggarna är samma taggar som ursprungligen skickades för en viss försäljningsorderrad.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>When processing a inventory status changed by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När bearbetning av lagerstatus ändras via appen lagerställe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>When a warehouse transfer is done by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När lagerställeöverföring görs via appen lagerställe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>When processing adjustment in and out via the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vid bearbetning av justering in och ut via appen lagerställe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>When picking work is processed for sales and transfer orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När plockningsarbete bearbetas för försäljnings- och överföringsorder.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>(Note that catch weight tags can't be recorded for production component picking.)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">(Observera att taggar för faktisk/nominell vikt inte kan registreras för plockning av produktionskomponent).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>When picked quantities are reduced from load lines, regardless of whether containers are used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När plockade kvantiteter minskas från lastrader, oavsett om behållare används.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>When products are packed into containers at a packing station.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När produkter som är förpackade i behållare på en förpackningsstation.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>When containers are reopened.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När behållare öppnas på nytt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>When formula products are reported as finished by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När formelprodukter rapporteras som färdiga via appen lagerställe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>When transport loads are processed by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När transporten läses in bearbetas via appen lagerställe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>A catch weight tag can either be created using a warehousing app process, manually created in the form, or creating using a data entity process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En kod för faktisk/nominell vikt kan skapas antingen med en lagerstyrningsapprocess, skapas manuellt i formuläret eller skapas med en dataentitetsprocess.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>If a catch weight tag gets associated with an inbound source document line, such as purchase order line, the tag will be registered.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om en kod för nominell vikt blir associerad med en inkommande källdokumentrad, till exempel inköpsorderrad, kommer koden att registreras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>If the line is used for outbound processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om raden används för utgående bearbetning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>The tag will be updated as shipped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Koden uppdateras som levererad.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>