<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="omni-auto-charges.md" target-language="sv-SE">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>omni-auto-charges.2f6e37.47829a6fcae37e03510929dc46b942455016df0b.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>47829a6fcae37e03510929dc46b942455016df0b</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\omni-auto-charges.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avancerade automatiska avgifter för flera kanaler</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes capabilities for managing additional order charges for Retail channel orders using advanced auto charges features.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det här avsnittet beskriver funktionerna för hantering av ytterligare avgifter för beställningar i butikskanal med hjälp av funktioner för avancerade automatiska avgifter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avancerade automatiska avgifter för flera kanaler</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>This topic provides information on configuration and deployment of the advanced auto-charges feature which are available in Dynamics 365 for Retail version 10.0.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det här avsnittet innehåller information om konfiguration och distribution av funktionen för avancerade automatiska avgifter som är tillgängliga i Dynamics 365 for Retail version 10.0.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>When the advanced auto-charges features are enabled, orders created in any supported Retail channel (point of sale (POS), call center, and online), can take advantage of the <bpt id="p1">[</bpt>auto-charges<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations defined in the ERP application for both header and line-level related charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När avancerade funktioner för automatiska avgifter är aktiverade stöds order som har skapats i någon Butikskanal (kassa, kundtjänst och online), kan utnyttja den <bpt id="p1">[</bpt>automatisk debitering<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> konfigurationer som fastställs i ERP-programmet för både huvud- och relaterade avgifter på radnivå.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>In releases prior to Dynamics 365 for Retail version 10.0, <bpt id="p1">[</bpt>auto-charge<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations are only accessible by orders created in e-Commerce and call center channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I versioner före Dynamics 365 for Retail version 10.0, är konfigurationer av <bpt id="p1">[</bpt>automatiska avgifter<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> endast tillgängliga för order som har skapats i e-handels- och kundtjänstkanaler.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>In versions 10.0 and later, POS-created orders can leverage the auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I versioner 10.0 och senare kan kassaskapade order utnyttja konfigurationer av automatiska avgifter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>That way, additional miscellaneous charges can systematically be added to sales transactions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">På så sätt kan ytterligare avgifter systematiskt läggas på försäljningstransaktioner.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>When using releases prior to version 10.0, a POS user is prompted to manually enter a shipping fee during the creation of a "ship all" or "ship selected" POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När du använder versioner före version 10.0 uppmanas POS-användare att manuellt ange en leverans avgift när skapas fartygets ”alla” eller ”skicka valda” POS-transaktionen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>While the miscellaneous charges capabilities of the application are utilized in respect to how the charges are written to the order, no systematic calculation is provided – the calculation relies on the user's input to determine the value of the charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">När funktionerna för diverse avgifter i programmet används i förhållande till hur avgifterna skrivs till ordern, ges inte någon systematisk beräkning – beräkningen är beroende av användarens indata för att bestämma värdet på avgifterna.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The charges can only be added as a single "shipping" related charges code and cannot easily be edited or changed in the POS after they are created.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avgifterna endast läggas till som en enda ”leverans”-relaterad kod och enkelt redigeras eller ändras när de har skapats i kassan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The use of manual prompts to add shipping charges is still available in versions 10.0 and later.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Manuella anvisningar för att lägga till leveransavgifter används fortfarande i version 10.0 eller senare.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>If an organization does not enable the <bpt id="p1">**</bpt>Advanced Auto-charges<ept id="p1">**</ept> parameter, the POS prompts for manual entry of charges will remain the same.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om en organisation inte har aktiverat parametern <bpt id="p1">**</bpt>avancerade automatiska avgifter<ept id="p1">**</ept> kommer kassauppmaningar om manuell inmatning av avgifter inte att påverkas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>With the advanced auto-charges feature, POS users can have systematic calculations for any defined miscellaneous charges based on auto-charges setup tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Med funktionen för avancerade automatiska avgifter kan kassaanvändare ha systematiska beräkningar för alla definierade diverse avgifter baserat på inställningstabeller för automatiska avgifter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In addition, users will have the ability to add or edit an unlimited amount of additional charges and fees to any POS sales transaction at the header or line-level (for a cash and carry or customer order).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dessutom kan har användare möjlighet att lägga till eller redigera en obegränsad mängd ytterligare debiteringar och avgifter till en försäljningstransaktion i kassa i rubrik eller radnivå (för en hämtköp eller kundorder).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Enabling advanced auto-charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aktivera avancerade automatiska avgifter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>On the <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Headquarters setup <ph id="ph2">\&gt;</ph> Parameters <ph id="ph3">\&gt;</ph> Retail parameters<ept id="p1">**</ept> page, go to the <bpt id="p2">**</bpt>Customer orders<ept id="p2">**</ept> tab. On the <bpt id="p3">**</bpt>Charges<ept id="p3">**</ept> FastTab, set <bpt id="p4">**</bpt>Use advanced auto-charges<ept id="p4">**</ept> to <bpt id="p5">**</bpt>Yes<ept id="p5">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">På sidan <bpt id="p1">**</bpt>Butik <ph id="ph1">\&gt;</ph> Administrationsinställning <ph id="ph2">\&gt;</ph> Parametrar <ph id="ph3">\&gt;</ph> Butiksparametrar<ept id="p1">**</ept>, gå till fliken <bpt id="p2">**</bpt>kundorder<ept id="p2">**</ept>. På snabbfliken <bpt id="p3">**</bpt>Avgifter<ept id="p3">**</ept>, ange <bpt id="p4">**</bpt>Använd avancerade automatiska avgifter<ept id="p4">**</ept> till <bpt id="p5">**</bpt>Ja<ept id="p5">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Advanced Auto-Charges Parameter</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Parametrar för avancerade automatiska avgifter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>When advanced auto-charges are enabled, users are no longer prompted to manually enter a shipping charge at the POS terminal when creating a ship-all or ship-selected customer order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När avancerad automatiska avgifter aktiveras uppmanas användare inte längre att manuellt ange en fraktkostnad vid kassaterminalen när man skapar en leverera alla eller leverera utvalda kundorder.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>POS order charges are systematically calculated and added to the POS transaction (if a corresponding auto-charges table that matches the criterion of the order being created are found).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kassans orderavgifter beräknas systematiskt och läggs till kassatransaktionen (om det finns en motsvarande tabell för automatiska avgifter som matchar kriteriet om ordern som skapats).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Users can also add or maintain header or line-level charges manually through newly added POS operations that can be added to the POS screen layouts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Användare kan också lägga till eller underhålla sidhuvud eller radnivå tillägg manuellt via tillagda kassaoperationer som kan läggas till kassaskärmens layout.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>When advanced auto-charges are enabled, the existing <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> for <bpt id="p2">**</bpt>Shipping charges code<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> are no longer utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När avancerade automatiska tillägg är aktiverade kommer befintliga <bpt id="p1">**</bpt>butiksparametrar<ept id="p1">**</ept> för <bpt id="p2">**</bpt>leveransavgiftskod<ept id="p2">**</ept> och <bpt id="p3">**</bpt>återbetala leveransavgifter<ept id="p3">**</ept> inte längre användas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>These parameters are only applicable if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>No<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dessa parametrar kan endast användas om parametern <bpt id="p1">**</bpt>Använd avancerade automatiska avgifter<ept id="p1">**</ept> är inställd på <bpt id="p2">**</bpt>Nej<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Before you enable this feature, ensure that you have tested and trained your employees, as this will change the business process flow of how shipping or other charges are calculated and added to POS sales orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Innan du aktiverar den här funktionen, kontrollera att du har testat och utbildad personal, eftersom detta ändrar affärsprocessflödet för hur frakt och andra avgifter beräknas och läggs till försäljningsorder från kassan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Make sure that you understand the impact of the process flow to the creation of transactions from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kontrollera att du förstår effekten av processflödet för att skapa transaktioner från kassan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For call center and e-Commerce orders, the impact of enabling advanced auto-charges is minimal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För kundtjänst och e-handel är effekterna av att aktivera avancerade automatiska tillägg minimal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Call center and e-Commerce applications will continue to have the same behavior they have had historically related to the auto-charges tables to calculate additional order fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kundtjänst och e-handelsprogram fortsätter att ha samma sätt som de tidigare har haft relaterade till register för automatiska avgifter för att beräkna ytterligare avgifter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>Call center channel users will continue to have the ability to manually edit any system calculated auto-charges at the header or line level, or manually add additional miscellaneous charges at the header or line level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Användare av kundtjänstkanal kommer även fortsättningsvis ha möjlighet att manuellt redigera beräknade automatiska avgifter på rubrik- eller radnivå eller lägga till ytterligare tillägg manuellt på rubrik- eller radnivå.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Additional POS operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ytterligare kassaåtgärder</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>For advanced auto-charges to work properly in your POS application environment, new POS operations have been added.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att avancerade automatiska avgifter ska fungera korrekt i din kassaapplikationsmiljö, har nya kassaåtgärder lagts till.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>These operations must be added to your <bpt id="p1">[</bpt>POS screen layouts<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> and deployed to the POS devices as you deploy advanced auto-charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dessa åtgärder måste du lägga till dina <bpt id="p1">[</bpt>kassaskärmlayouter<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> och distribuera till kassaenheter när du distribuerar avancerade automatiska avgifter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>If these operations are not added, users will not be able to manage or maintain miscellaneous charges on the POS transactions and will have no way of adjusting or changing the charges values that are systematically calculated based on auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om dessa åtgärder inte läggs till kan användare inte hantera eller underhålla diverse avgifter för kassatransaktioner och har inget sätt att justera eller ändra tilläggsvärden som systematiskt beräknas utifrån konfigurationer av automatiska avgifter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>At minimum, it is suggested that you deploy the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation to your POS layout.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Vi rekommenderar åtminstone att du distribuerar åtgärden <bpt id="p1">**</bpt>Hantera avgifter<ept id="p1">**</ept> i kassalayouten.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>The new operations are as follows.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Följande nya åtgärder finns.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source><bpt id="p1">**</bpt>142 - Manage charges<ept id="p1">**</ept> – Use this operation to allow POS users to view and edit miscellaneous charges for the POS transaction that were either added manually or systematically through auto-charges calculations.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>142 - Hantera avgifter<ept id="p1">**</ept> - Använd följande åtgärd för att kassaanvändare ska kunna visa och redigera tillägg för kassatransaktionen som är läggs till manuellt eller systematiskt genom beräkningar av avgifter.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source><bpt id="p1">**</bpt>141 - Add header charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a header-level miscellaneous charge to any POS sales transaction (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>141 - Lägg till huvudavgifter<ept id="p1">**</ept> - Använd denna åtgärd för att ge användaren möjlighet att manuellt lägga till en tilläggsavgift på huvudnivå till en försäljningstransaktion i kassan (och välj avgiftskoden som ska användas).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source><bpt id="p1">**</bpt>140 - Add line charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a line level miscellaneous charge to any POS sales transaction line (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>140 - Lägg till radavgifter<ept id="p1">**</ept> - Använd denna åtgärd för att ge användaren möjlighet att manuellt lägga till en tilläggsavgift på radnivå till en försäljningstransaktionsrad i kassan (och välj avgiftskoden som ska användas).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source><bpt id="p1">**</bpt>143 - Recalculate charges<ept id="p1">**</ept> – Use this operation to perform a full re-calculation of the charges for the sales transaction.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>143 - beräkna om avgifter<ept id="p1">**</ept> - Använd följande åtgärd för att utföra en fullständig ny beräkning av avgifterna för försäljningstransaktionen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Any previously user-overwritten auto-charges will be recalculated based on the current cart configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tidigare överskrivna automatiska avgifter för användare beräknas om utifrån den aktuella vagnkonfigurationen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>As with all POS operations, security configurations can be made to require manager approval in order to execute the operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Som med alla kassaoperationer kan säkerhetskonfigurationen kräva godkännande av chef för att utföra operationen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>It is important to note that the above listed POS operations can also be added to the POS layout even if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det är viktigt att komma ihåg de ovan angivna kassaoperationerna kan också läggas till kassalayout även om parametern <bpt id="p1">**</bpt>Använd avancerade automatiska avgifter<ept id="p1">**</ept> inaktiveras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>In this scenario, organizations will still get added benefits of being able to view manually added charges and edit them using the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här scenariot får organisationer fortfarande fördelarna med att kunna visa manuellt tillagda avgifter och redigera dem med hjälp av åtgärden <bpt id="p1">**</bpt>Hantera avgifter<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Users may also use the <bpt id="p1">**</bpt>Add header charges<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Add line charges<ept id="p2">**</ept> operations for POS transactions even when <bpt id="p3">**</bpt>Use advanced auto-charges<ept id="p3">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Användare kan även använda åtgärderna <bpt id="p1">**</bpt>Lägg till huvudavgifter<ept id="p1">**</ept> och <bpt id="p2">**</bpt>Lägg till radavgifter<ept id="p2">**</ept> för kassatransaktioner även om parametern <bpt id="p3">**</bpt>Använd avancerade automatiska avgifter<ept id="p3">**</ept> är inaktiverad.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>The <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation has less functionality if used when <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Åtgärden <bpt id="p1">**</bpt>beräkna om avgifter<ept id="p1">**</ept> har begränsad funktionalitet om den används med <bpt id="p2">**</bpt>Använd avancerade automatiska avgifter<ept id="p2">**</ept> inaktiverad.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>In this sceanrio, nothing would be recalculated and any charges manually added to the transaction would just reset to $0.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I detta scenario kan inget beräknas om och eventuella avgifter som har lagts till manuellt i transaktionen återställs bara till 0,00 $.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Use case examples</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Använd fallexempel</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In this section, sample use cases are presented to help you understand the configuration and usage of auto-charges and miscellaneous charges within the context of Retail channel orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här avsnittet visas exempel på användningsfall som hjälper dig att förstå konfiguration och användning av automatiska avgifter och övriga kostnader i samband med order för butikskanal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>These examples illustrate the behavior of the application when the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter has been enabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">De här exemplen visar hur programmet uppför sig när parametern <bpt id="p1">**</bpt>Använd avancerade automatiska avgifter<ept id="p1">**</ept> har aktiverats.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Auto-charges header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exempel på automatiska avgifter för huvudavgifter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Använd fallstudie</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>A retailer wants to automatically add charges for freight when transactions are created in any Retail channel that require a shipment of products to the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En återförsäljare vill automatiskt lägga till avgifter för frakt när transaktioner skapas i någon butikskanal som kräver en leverans av varor till kunden.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The retailer offers 2 methods of delivery: Ground and Air.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Återförsäljaren erbjuder 2 leveransmetoder: mark och luft.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>If a customer chooses Ground delivery and the order value is less than $100, the retailer wants to charge the customer a freight charge of $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om en kund väljer markleverans och ordervärdet är mindre än $100, vill återförsäljaren debitera kunden en fraktavgift på $10,00.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>If the order is over $100 in value and the customer chooses ground shipping, the customer will not be charged any additional freight fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om kunden väljer markleverans och ordern är över $100 debiteras kunden inte några ytterligare fraktavgifter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>If the customer chooses the Air method of delivery for all orders, regardless of their total value, will be charged a freight fee of $20.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om kunden väljer flygleveranssätt för alla order, oavsett deras totala värde debiteras en avgift för frakt på $20,00.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Installation och konfiguration</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>This scenario requires the configuration of two auto-charges tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta scenario kräver konfiguration av två tabeller för automatiska avgifter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Go to <bpt id="p1">**</bpt>Accounts receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gå till <bpt id="p1">**</bpt>Kundreskontra <ph id="ph1">\&gt;</ph> Ställa in avgifter <ph id="ph2">\&gt;</ph> Automatiska avgifter<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Configure two different header-level auto charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurera två olika automatiska avgifter på huvudnivå.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Configure one for the "Ground mode" of delivery and one for the "Air mode" of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurera en för ”markleverans” och en ”flygleverans”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>For this scenario, configure them to be used for "All customers".</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här scenariot kan du konfigurera de som ska användas för ”alla kunder”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>For the ground delivery charges, in the lines section of the <bpt id="p1">**</bpt>Auto-charges<ept id="p1">**</ept> page, define a charge that will be applied for orders between $.01 and $100 as $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För markleverans, i radavsnittet på sidan <bpt id="p1">**</bpt>automatiska avgifter<ept id="p1">**</ept> kan du definiera ett tillägg som ska användas för order mellan $,01- och $100 som $10,00.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Create another charges line to indicate orders over $100.01 will have no charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skapa en annan avgiftsrad för att ange att order under $100,01 inte har avgifter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exempel på automatiska avgifter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>For the air delivery charges, in the lines section of the auto-charges form, define a charge of $20.00 that will be applied to all orders (between a value of $.01 to $9,999,999).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För luftsleverans, i radavsnittet på formuläret automatiska avgifter kan du definiera ett tillägg på $20,00 som ska användas för alla order (mellan $,01och $9 999 999).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Send the changes to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skicka ändringarna till Retail Server/Channel DB så att kassan kan utnyttja dem genom att köra jobbet <bpt id="p1">**</bpt>1040 distributionsschema<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Försäljningsbearbetning för det här scenariot</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>After the configuration steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have the ground or air delivery methods set at the header level will utilize these charges and automatically apply them to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När du är klar med ovanstående konfiguration och ändringarna har tillämpats för databaskanal, alla kundorder eller försäljningstransaktioner som skapats i kassan, kundtjänst eller e-handelskanaler som har mark- eller flygleverans metoderna i huvudnivå ska använda dessa avgifter och tillämpa dem automatiskt på försäljningen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>At this time the charges will apply to all sales transactions created within the legal entity that utilize these delivery modes, as there is no functionality to designate that an auto-charge configuration will only apply to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vid denna tidpunkt kommer avgifterna att gälla för alla försäljningstransaktioner som skapats inom den juridiska enheten som använder dessa leveranssätt, eftersom det inte finns någon funktionalitet för att ange att en konfiguration av automatiska avgifter endast gäller en specifik försäljningskanal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>For POS and e-Commerce scenarios, because there is no clearly defined "header" on these orders, header-level charges will only apply if all sales lines on the transaction are set to ship with the exact same mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För kassa- och e-handelsscenarier, eftersom det inte finns någon tydligt definierad "huvud" på dessa beställningar gäller avgifter på huvudnivå endast om alla försäljningsrader på transaktionen är inställda att skickas med exakt samma leveranssätt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>If there are "mixed-modes" of fulfillment on the transactions created by POS or e-Commerce, only line-level auto-charges will be considered and applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om ”blandade sätt” för utförande av transaktioner skapas av kassan eller e-handel beaktas och tillämpas endast automatiska avgifter på radnivå.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>In call center scenarios, the user has control over the setting of the delivery mode at the order header, therefore header-level charges will apply for these orders even if some of the sales lines have been configured to use a different mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I kundtjänstscenarier har användaren kontroll över inställningen för leveransläge vid orderhuvudet. Därför gäller avgifter på huvudnivå för dessa order även om några av försäljningsraderna har konfigurerats för att använda ett annat leveranssätt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Header-level charges for call center orders will always be based on the mode of delivery that is defined at the order header level of the sales order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avgifter på huvudnivå för kundtjänstorder kommer alltid att baseras på leveranssättet som definieras vid orderhuvudnivån i försäljningsordern.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Auto-charges line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exempel på automatiska avgifter för radavgifter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Använd fallstudie</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>A retailer wants to add an additional charge to the customer for setup fees when the customer purchases a particular model of computer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En återförsäljare vill lägga till en extra avgift för kunden för installationskostnader när kunden köper en viss modell av datorn.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>This computer requires additional non-optional setup actions that the retailer will perform for the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Den här datorn kräver ytterligare icke valfria inställningar som återförsäljaren utför för kunden.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>The retailer has informed customers that there will be an additional fee for this setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Återförsäljaren har meddelat kunder att en avgift tas för denna inställning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>The retailer prefers to manage the charges related to this fee separately from the product sales price for financial reporting purposes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Återförsäljaren föredrar att hantera avgifter relaterade till denna avgift separat från produktens försäljningspriset för ekonomisk rapportering.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>A setup fee of $19.99 will be charged to the customer when this specific computer is purchased in any retail channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En inställningsavgift på $19,99 debiteras kunden när den specifika datorn köps i någon butikskanal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Installation och konfiguration</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>This scenario requires the configuration of one line-level auto charges table.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta scenario kräver konfiguration av tabell för automatiska avgifter på en radnivå.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>Go to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gå till <bpt id="p1">**</bpt>Kundreskontra <ph id="ph1">\&gt;</ph> Ställa in avgifter <ph id="ph2">\&gt;</ph> Automatiska avgifter<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Set the <bpt id="p1">**</bpt>Level<ept id="p1">**</ept> drop-down menu to <bpt id="p2">**</bpt>Line<ept id="p2">**</ept>, and create a new auto-charges record for all customers and for the specific product or product group where the setup fees will be charged.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ange listrutan <bpt id="p1">**</bpt>nivå<ept id="p1">**</ept> till <bpt id="p2">**</bpt>rad<ept id="p2">**</ept> och skapa en ny post för automatiska avgifter för alla kunder och för en viss produkt eller produktgrupp där inställningsavgifter tas ut.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exempel på automatiska avgifter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skicka avgifter till Retail Server/Channel DB så att kassan kan utnyttja dem genom att köra jobbet <bpt id="p1">**</bpt>1040 distributionsschema<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Försäljningsbearbetning för det här scenariot</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>After the configurations steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have this item on the order will trigger a line-level charge to be systematically added to the order total.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När du är klar med ovanstående konfiguration och ändringarna har tillämpats för databaskanal, alla kundorder eller försäljningstransaktioner som skapats i kassan, kundtjänst eller e-handelskanaler som har denna post i ordern kommer att utlösa en radnivåavgift som systematiskt läggs till i orderantalet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>At this time the charges will apply to any sales line that matches the configuration of the line-level auto charges within the legal entity, as there is no functionality to configure a line-level auto-charge to apply only to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vid denna tidpunkt kommer avgifterna att gälla för alla försäljningsrader som matchar konfigurationen av automatiska avgifter på radnivå inom juridisk enhet, eftersom det inte finns någon funktionalitet för att konfigurera en automatisk avgift på radnivå för att endast vara tillämplig på en viss försäljningskanal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Manual header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exempel på manuella huvudavgifter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>Use case scenario description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beskrivning av att använda fallstudie</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>A retailer is making an exception to typical processes by offering to provide a special home delivery of products to a customers who order products in the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En återförsäljare gör undantag från vanliga processer genom att erbjuda en särskild hemleverans av produkter till kunder som beställer produkter i butiken.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The retailer and the customer have agreed that the customer will pay an additional $25 handling fee for this service.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Återförsäljaren och kunden har kommit överens om att kunden kommer att betala en extra avgift på $25 för den här tjänsten.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>The order-taker needs to add this additional fee to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ordermottagaren behöver lägga till denna avgift i transaktionen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Because the fee is a blanket fee and not related to any single product on the order, a header charge will be utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Eftersom avgiften är avgiftsbelagd och inte hör till en enda produkt i ordern, ska en huvudkostnad användas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Installation och konfiguration</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kontrollera att avgiftskoden som används i det här scenariot har konfigurerats korrekt genom att gå till <bpt id="p1">**</bpt>kundreskontra <ph id="ph1">\&gt;</ph> inställningar av avgifter <ph id="ph2">\&gt;</ph> avgifter<ept id="p1">**</ept> för att definiera en lämplig avgiftskod för scenariot.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>Charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exempel på avgifter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Ange om avgiften ska betraktas som en ”frakt”-relaterad avgift för fraktrelaterade rabatter eller kampanjer, ange <bpt id="p1">**</bpt>leveransavgift<ept id="p1">**</ept> för avgiftskoden till <bpt id="p2">**</bpt>Ja<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>If this charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om denna avgift också kan återbetalas systematiskt under bearbetningen av en returtransaktion i kassaprogram ställer du in <bpt id="p1">**</bpt>Återbetalningsbar<ept id="p1">**</ept> till <bpt id="p2">**</bpt>Ja<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Flaggan <bpt id="p1">**</bpt>Återbetalningsbar<ept id="p1">**</ept> gäller endast när parameter <bpt id="p2">**</bpt>Använd avancerade automatiska avgifter<ept id="p2">**</ept> är inställd på <bpt id="p3">**</bpt>Ja<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skicka avgifter till Retail Server/Channel DB så att kassan kan utnyttja dem genom att köra jobbet <bpt id="p1">**</bpt>1040 distributionsschema<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>The <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 141).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Åtgärden <bpt id="p1">**</bpt>lägg till huvudavgift<ept id="p1">**</ept> måste konfigureras i din <bpt id="p2">[</bpt>kassaskärmlayout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> så att en knapp som är tillgänglig för användaren från kassan kan anropa åtgärden (åtgärd 141).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skärmens layoutändringar måste distribueras till butikskanalen samt via distributionsplanen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Sales processing of manual header charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Försäljningsprocesserna för manuella huvudavgifter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om du vill köra scenariot i kassaprogrammet kommer kassaanvändaren att skapa försäljningstransaktionen som vanligt, lägga till produkter och andra konfigurationer för försäljning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>Prior to collecting payment, the user should execute the <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation, which will prompt the user to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Innan betalningen samlas in ska användaren utföra åtgärden <bpt id="p1">**</bpt>Lägg till huvudavgift<ept id="p1">**</ept> som uppmanar användaren att välja avgiftskod och ange avgiftsvärdet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Once the user completes the process, the charge will be added to the sales order as a header-level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När användaren slutför processen läggs avgiften till försäljningsorder som ett tillägg på huvudnivå.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>This process can be applied in the call center by using the existing <bpt id="p1">**</bpt>Charges<ept id="p1">**</ept> feature found on the <bpt id="p2">**</bpt>Sell<ept id="p2">**</ept> tab on the toolbar.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Proceduren kan tillämpas i kundtjänst genom att använda den befintliga funktionen <bpt id="p1">**</bpt>avgifter<ept id="p1">**</ept> som finns på fliken <bpt id="p2">**</bpt>sälja<ept id="p2">**</ept> i verktygsfältet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>On the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page, the user can add a new charges line to the order header.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">På sidan <bpt id="p1">**</bpt>Underhåll avgifter<ept id="p1">**</ept> kan användaren kan lägga till en ny rad i orderrubriken.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Manual line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exempel på manuella radavgifter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Använd fallstudie</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>A customer has requested that 2 of the 5 items on their sales order be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En kund har begärt att 2 av 5 artiklar på deras försäljningsorder ska slås in.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>The retailer offers this optional service for a fee of $2.00 per item.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Återförsäljaren erbjuder valfria tjänsten till en kostnad av $2,00 per artikel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>The order-taker will need to add these fees to the specific items that need to be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ordermottagaren måste lägga till dessa avgifter till de artiklar som behöver slås in.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Installation och konfiguration</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kontrollera att avgiftskoden som används i det här scenariot har konfigurerats korrekt genom att gå till <bpt id="p1">**</bpt>kundreskontra <ph id="ph1">\&gt;</ph> inställningar av avgifter <ph id="ph2">\&gt;</ph> avgifter<ept id="p1">**</ept> för att definiera en lämplig avgiftskod för scenariot.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set the <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ange om avgiften ska betraktas som en ”frakt”-relaterad avgift för fraktrelaterade rabatter eller kampanjer, ange <bpt id="p1">**</bpt>leveransavgift<ept id="p1">**</ept> för avgiftskoden till <bpt id="p2">**</bpt>Ja<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>If the charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om denna avgift också kan återbetalas systematiskt under bearbetningen av en returtransaktion i kassaprogram ställer du in <bpt id="p1">**</bpt>Återbetalningsbar<ept id="p1">**</ept> till <bpt id="p2">**</bpt>Ja<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Flaggan <bpt id="p1">**</bpt>Återbetalningsbar<ept id="p1">**</ept> gäller endast när parameter <bpt id="p2">**</bpt>Använd avancerade automatiska avgifter<ept id="p2">**</ept> är inställd på <bpt id="p3">**</bpt>Ja<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skicka avgifter till Retail Server/Channel DB så att kassan kan utnyttja dem genom att köra jobbet <bpt id="p1">**</bpt>1040 distributionsschema<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>The <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 140).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Åtgärden <bpt id="p1">**</bpt>lägg till radavgift<ept id="p1">**</ept> måste konfigureras i din <bpt id="p2">[</bpt>kassaskärmlayout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> så att en knapp som är tillgänglig för användaren från kassan kan anropa åtgärden (åtgärd 140).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skärmens layoutändringar måste distribueras till butikskanalen samt via distributionsplanen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>Sales processing of the manual line charge</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Försäljningsprocesserna för manuella radavgifter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om du vill köra scenariot i kassaprogrammet kommer kassaanvändaren att skapa försäljningstransaktionen som vanligt, lägga till produkter och andra konfigurationer för försäljning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>Prior to collecting payment, the user should select the specific line where the charge will apply from the POS item list display and execute the <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Innan man tar betalt måste användaren markera den rad som avgiften tillämpas från kassans visning av artikellista och köra åtgärden <bpt id="p1">**</bpt>lägga till radavgift<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>The user will be prompted to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Användaren uppmanas att välja avgiftskod och ange värdet för avgiften.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>Once the user completes the process, the charge will be linked to the line and added to the order total as a line level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När användaren slutför processen kopplas avgiften till raden och läggs till ordersumman som en avgift på radnivå.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>The user can repeat the process to add additional line charges to other items lines on the transaction if needed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Användaren kan upprepa processen för att lägga till ytterligare radavgifter för andra artikelrader i transaktionen om det behövs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>The same process can be applied in the call center by using the "maintain charges" feature found under the <bpt id="p1">**</bpt>Financials<ept id="p1">**</ept> drop-down menu in the <bpt id="p2">**</bpt>Sales order lines<ept id="p2">**</ept> section on the <bpt id="p3">**</bpt>Sales order<ept id="p3">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Samma tillvägagångssätt kan användas i kundtjänst med funktionen ”Underhåll avgifter” som du hittar under listrutan <bpt id="p1">**</bpt>ekonomi<ept id="p1">**</ept> i avsnittet <bpt id="p2">**</bpt>försäljningsorderrader<ept id="p2">**</ept> på dian <bpt id="p3">**</bpt>försäljningsorder<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>This will open the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page where the user can add a new line specific charge to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Då öppnas sidan <bpt id="p1">**</bpt>Underhåll avgifter<ept id="p1">**</ept> där användaren kan lägga till en ny radspecifik avgift i transaktionen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>Additional features</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ytterligare funktioner</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>Editing charges on a POS sales transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Redigera avgifter i en kassaförsäljningstransaktion</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>The <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation (142) should be added to the <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a user can view and edit or override any system-calculated or manually-created header or line-level charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Åtgärden <bpt id="p1">**</bpt>Hantera tillägg<ept id="p1">**</ept> (142) ska läggas till i <bpt id="p2">[</bpt>kassaskärmlayout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> så att en användare kan visa och redigera eller åsidosätta eventuella systemberäknade eller manuellt skapade avgifter på huvud- eller radnivå.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>If the operation is not added, users will not be able to adjust the value of the charges on the POS transaction, nor will they be able to view the details of the charges such as the type of charges code tied to the charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om operationen inte läggs till kommer användaren inte att kunna justera värdet av avgifterna på kassatransaktionen, och inte heller kan de visa information om avgifter såsom typ av avgiftskod kopplad till avgiften.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>On the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> page in POS, the user can view both header and line-level charges details.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">På sidan <bpt id="p1">**</bpt>Hantera avgifter<ept id="p1">**</ept> i kassan kan användaren visa information om avgifter på både huvud- och radnivå.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>The user can use the <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> function available on this page to make changes to the amount charged to a specific charges line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Användaren kan använda <bpt id="p1">**</bpt>redigera<ept id="p1">**</ept> som är tillgänglig på den här sidan för att ändra det belopp som debiteras en specifik avgiftsrad.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>Once a charges line is overwritten manually, it will not be systematically recalculated unless the user initiates the <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När en avgiftsrad läggs till manuellt räknas den inte om systematiskt om inte användaren initierar åtgärden <bpt id="p1">**</bpt>beräkna om avgifter<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>If the <bpt id="p1">**</bpt>Charge override reason code<ept id="p1">**</ept> has been configured on the <bpt id="p2">**</bpt>Retail parameters<ept id="p2">**</ept> setup page, the user will be prompted to provide a reason code when charges have been modified in the POS application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om <bpt id="p1">**</bpt>Orsakskod för åsidosättning av avgift<ept id="p1">**</ept> har konfigurerats på installationssidan <bpt id="p2">**</bpt>butiksparametrar<ept id="p2">**</ept>, användaren uppmanas att ange en orsakskod när avgifter har ändrats i kassaprogrammet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>If reason codes have been captured for overwritten charges, a new report is also available to review and audit these overrides.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om orsakskoder registrerays för överskrivna avgifter, finns även en ny rapport för att granska dessa åsidosättningar.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>The report can be found in <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge override history<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rapporten finns i <bpt id="p1">**</bpt>butik <ph id="ph1">\&gt;</ph> förfrågningar och rapporter <ph id="ph2">\&gt;</ph> historik för avgiftsåsidosättning<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>Refunding charges on a POS return transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Återbetalning av avgifter för en kassareturtransaktion</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>If the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>, the existing retail parameter for <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> is no longer applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om parametern <bpt id="p1">**</bpt>Använd avancerade automatiska avgifter<ept id="p1">**</ept> är inställd på <bpt id="p2">**</bpt>Ja<ept id="p2">**</ept> kommer befintlig butiksparameter för <bpt id="p3">**</bpt>återbetala leveransavgifter<ept id="p3">**</ept> inte längre gälla.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>To indicate which charges should be systematically refunded to a customer when using advanced auto-charges, ensure the related charges code has been configured as <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om du vill ange vilka avgifter som systematiskt återbetalas till en kund vid användning av avancerade automatiska avgifter, kontrollera att relaterade avgiftskoden har konfigurerats som <bpt id="p1">**</bpt>Återbetalningsbar<ept id="p1">**</ept> på installationssidan <bpt id="p2">**</bpt>avgiftskod<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>Make sure that the settings have been synchronized to your Retail channel databases through distribution schedule processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kontrollera att inställningarna har synkroniserats med databaserna för butikskanal via distributionsplan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Refunding charges on a return order transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Återbetalning av avgifter för en ordertransaktion</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>Charges are not systematically refunded to <bpt id="p1">**</bpt>Return orders<ept id="p1">**</ept> created in Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avgifter återbetalas inte systematiskt till <bpt id="p1">**</bpt>returorder<ept id="p1">**</ept> som skapats i Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>Users are required to select the <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> option when creating the <bpt id="p2">**</bpt>Return order<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Användare måste välja alternativet <bpt id="p1">**</bpt>kopiera avgifter<ept id="p1">**</ept> när de skapar <bpt id="p2">**</bpt>returorder<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is not selected, charges from the original sales transaction will not be automatically refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om <bpt id="p1">**</bpt>kopiera avgifter<ept id="p1">**</ept> inte är markerat kommer avgifter från den ursprungliga försäljningstransaktionen inte att återbetalas automatiskt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is selected, all charges will be copied to the return order and the user can manually edit or remove any charges they do not want to have refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om <bpt id="p1">**</bpt>kopiera avgifter<ept id="p1">**</ept> är markerat kopieras alla avgifter till returordern och användaren kan manuellt redigera eller ta bort ändringar som de inte vill ha tillbaka.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>The call center return order process currently does not acknowledge the <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Returorderprocessen för kundtjänst accepterar för närvarande inte flaggan <bpt id="p1">**</bpt>Återbetalningsbar<ept id="p1">**</ept> på <bpt id="p2">**</bpt>Avgiftskod<ept id="p2">**</ept>-inställningen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>Configuring POS receipts to show charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurera kassainleveranser för att visa debiteringar</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>The following receipt elements have been added to the receipt line and footer to support the advanced auto-charges functionality.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Följande inleverans har lagts till inleveransraden och sidfoten för att stödja funktionen för avancerade automatiska avgifter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source><bpt id="p1">**</bpt>Line Shipping Charges<ept id="p1">**</ept> – This line-level element can be used to recap specific charges codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Leveransavgifter för rad<ept id="p1">**</ept> - Detta element på radnivå kan användas för att sammanfatta koder för särskilda avgifter som har kopplats till försäljningsraden.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>Only charges codes that have been flagged as <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> charges on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page will be displayed here.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Endast avgiftskoder som har flaggats som <bpt id="p1">**</bpt>leverans<ept id="p1">**</ept>-avgifter på sidan <bpt id="p2">**</bpt>avgiftskoder<ept id="p2">**</ept> visas här.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source><bpt id="p1">**</bpt>Line Other Charges<ept id="p1">**</ept> – This line-level element can be used to recap any non-shipping specific charge codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Övriga avgifter för rad<ept id="p1">**</ept> - Detta element på radnivå kan användas för alla icke leveransspecifika avgiftskoder som har kopplats till försäljningsraden.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>These are charges codes where the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page has not been enabled.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Dessa är avgiftskoder där flaggan <bpt id="p1">**</bpt>leverans<ept id="p1">**</ept> på sidan den <bpt id="p2">**</bpt>avgiftskod<ept id="p2">**</ept> inte har aktiverats.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source><bpt id="p1">**</bpt>Order Shipping Charges Details<ept id="p1">**</ept> – This footer-level element displays the descriptions of the charge codes applied to the order that have been flagged as <bpt id="p2">**</bpt>Shipping<ept id="p2">**</ept> charges on the <bpt id="p3">**</bpt>Charges code<ept id="p3">**</ept> setup page.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Leveransavgiftsdetaljer för order<ept id="p1">**</ept> - Detta element på sidfotnivå visar beskrivningar av avgiftskoder som gäller för ordern som har flaggats som <bpt id="p2">**</bpt>leverans<ept id="p2">**</ept> på installationssidan <bpt id="p3">**</bpt>avgiftskod<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source><bpt id="p1">**</bpt>Order Shipping Charges<ept id="p1">**</ept> – This footer-level element shows the dollar value of the shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Leveransavgifter för order<ept id="p1">**</ept> - Detta element på sidfotnivå visar belopp för leveransrelaterade avgifter.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source><bpt id="p1">**</bpt>Order Other Charges Details<ept id="p1">**</ept> – This footer-level element displays the description of the charges codes applied to the order that have not been flagged as shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Övriga leveransavgiftsdetaljer för order<ept id="p1">**</ept> - Detta element på sidfotnivå visar beskrivningar av avgiftskoder som gäller för ordern som inte har flaggats som leveransrelaterade avgifter.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source><bpt id="p1">**</bpt>Order Other Charges<ept id="p1">**</ept> – This footer-level element displays the dollar value of the other charges that are not shipping-related.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Övriga avgifter för order<ept id="p1">**</ept> - Detta element på sidfotnivå visar belopp för andra avgifter som inte är leveransrelaterade.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>It is recommended that the organization also add free text fields to the receipt footer, in order to define the areas where charges will be recapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det rekommenderas att organisationen även lägger till fritextfält på kvittosidfoten för att definiera områden där avgifter ska sammanfattas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>Preventing charges from being calculated until the POS order is completed</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Förhindrar att avgifter beräknas innan kassaordern är klar.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>Some organizations may prefer to wait until the user has finished adding all of the sales lines to the POS transaction before calculating charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vissa organisationer föredrar att vänta tills användaren är klar med att lägga till alla försäljningsrader i kassatransaktionen innan de beräknar avgifter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source>To prevent calculation of charges as items are added to the POS transaction, turn on the <bpt id="p1">**</bpt>Manual charge calculation<ept id="p1">**</ept> parameter in the <bpt id="p2">**</bpt>Functionality profile<ept id="p2">**</ept> used by the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att undvika beräkning av avgifter när artiklar läggs till i kassatransaktionen, aktiverar du parametern <bpt id="p1">**</bpt>Manuell beräkning av avgifter<ept id="p1">**</ept> i den <bpt id="p2">**</bpt>funktionsprofil<ept id="p2">**</ept> som används i butiken.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>Enabling this parameter will require the POS user to use the <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation when they have completed adding the products to the POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att aktivera den här parametern måste kassaanvändaren använda åtgärden <bpt id="p1">**</bpt>beräkna summa<ept id="p1">**</ept> när de är klara med att lägga till produkter i kassatransaktionen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>The <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation will then trigger the calculation of any auto charges for the order header or lines as applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Åtgärden <bpt id="p1">**</bpt>beräkna summa<ept id="p1">**</ept> utlöser sedan beräkning av eventuella automatiska avgifter för orderrubriken eller rader.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>Charges override reports</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Raporrter för avgiftsåsidosättning</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>If users manually override the calculated charges or add a manual charge to the transaction, this data will available for auditing in the <bpt id="p1">**</bpt>Charge Override History<ept id="p1">**</ept> report.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om användare åsidosätter beräknade avgifter eller lägger till manuell avgift i transaktionen, kommer dessa data vara tillgängliga för granskning i rapporten <bpt id="p1">**</bpt>historik för avgiftsåsidosättning<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>The report can be accessed from <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge Override History<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rapporten kan tillgås från <bpt id="p1">**</bpt>butik <ph id="ph1">\&gt;</ph> förfrågningar och rapporter <ph id="ph2">\&gt;</ph> historik för avgiftsåsidosättning<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>It is important to note that the data needed for this report is imported from the channel database into HQ through the "P" distribution schedule jobs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det är viktigt att komma ihåg att de data som krävs för den här rapporten importeras från kanaldatabasen i HQ genom ”P” distribution tidsplanera jobb.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>Therefore, information about overrides just performed in the POS may not be immediately available on this report until this job has uploaded the store transaction data into HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Information om åsidosättningar kan därför endast utföras i kassan och kanske inte är omedelbart tillgängliga i rapporten tills jobbet har överfört butikens transaktionsdata till HQ.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>