<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="optimal-combination-overlapping-discounts.md" target-language="sv-SE">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>optimal-combination-overlapping-discounts.e4f3cd.e327f652855f898e50f1dd853ae20f3a0ff41d9e.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>e327f652855f898e50f1dd853ae20f3a0ff41d9e</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>e2fb0846fcc6298050a0ec82c302e5eb5254e0b5</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/27/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\optimal-combination-overlapping-discounts.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Determine the optimal combination of overlapping discounts</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Fastställa den optimala kombinationen av överlappande rabatter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>When discounts overlap, you must determine the combination of overlapping discounts that will produce the lowest transaction total or the highest total discount.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När rabatterna överlappar måste du fastställ vilken kombination av överlappande rabatter som ger det lägsta transaktionssumman eller den högsta rabattsumman.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103" restype="x-metadata">
          <source>When the discount amount varies according to the price of the products that are purchased, such as in the common 'Buy 1, get 1 X percent off' (BOGO) retail discount, this process becomes an issue of combinatorial optimization.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När rabattbeloppet varierar beroende på priset på de produkter som köps, så som den vanliga butiksrabatten "Köp 1, få 1 X procent rabatt" (BOGO), blir processen en fråga om kombinatorisk optimering.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Determine the optimal combination of overlapping discounts</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Fastställa den optimala kombinationen av överlappande rabatter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>When discounts overlap, you must determine the combination of overlapping discounts that will produce the lowest transaction total or the highest total discount.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När rabatterna överlappar måste du fastställ vilken kombination av överlappande rabatter som ger det lägsta transaktionssumman eller den högsta rabattsumman.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>When the discount amount varies according to the price of the products that are purchased, such as in the common "Buy 1, get 1 X percent off" (BOGO) retail discount, this process becomes an issue of combinatorial optimization.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När rabattbeloppet varierar beroende på priset på de produkter som köps, så som den vanliga butiksrabatten "Köp 1, få 1 X procent rabatt" (BOGO), blir processen en fråga om kombinatorisk optimering.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>This article applies to Microsoft Dynamics AX 2012 R3 with KB 3105973 (released November 2, 2015) or later, and to Microsoft Dynamics 365 for Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Den här artikeln avser Microsoft Dynamics AX 2012 R3 KB 3105973 (utgiven 2 november 2015) eller senare och till Microsoft Dynamics 365 for Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>To determine the combination overlapping discounts to apply in a timely manner, we have introduced a method for applying overlapping discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att fastställa kombinationen av överlappande rabatter som ska tillämpas vid rätt tidpunkt har vi introducerat en metod för att använda överlappande rabatter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>We call this new method <bpt id="p1">**</bpt>marginal value ranking<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Den nya metoden kallas <bpt id="p1">**</bpt>marginalvärderankning<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Marginal value ranking is used when the time that is required in order to evaluate the possible combinations of overlapping discounts exceeds a threshold that is configurable on the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Marginalvärderankning används när den tid som krävs för att utvärdera möjliga kombinationer av överlappande rabatter överskrider ett tröskelvärde som kan konfigureras på sidan <bpt id="p1">**</bpt>Butiksparametrar<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>In the marginal value ranking method, a value is calculated for each overlapping discount by using the discount's value on the shared products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I metoden marginalvärderankning beräknas ett värde för varje överlappande rabatt genom att använda rabattvärdet på de delade produkterna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The overlapped discounts are then applied from the highest relative value to the lowest relative value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Överlappande rabatter tillämpas sedan från det högsta relativa värdet till det lägsta relativa värdet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>For details about the new method, see the "Marginal value" section, later in this article.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mer information om den nya metoden finns i avsnittet "Marginalvärde" nedan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Marginal value ranking isn't used when the discount amounts for a product aren't affected by another product in the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Marginalvärderankning används inte när rabattbeloppen för en produkt inte påverkas av en annan produkt i transaktionen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>For example, this method isn't used for two simple discounts, or for a simple discount and a single product quantity discount.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Denna metod används exempelvis inte för två enkla rabatter, eller för en enkel rabatt och en enda produktkvantitetsrabatt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Discount examples</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exempel på rabatter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>You can create an unlimited number of retail discounts on a common set of products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Du kan skapa ett obegränsat antal butiksrabatter för en gemensam uppsättning produkter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>However, because there is no limit, performance issues can occur when you try to calculate the discounts that should be used on the various products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Men eftersom det inte finns någon gräns kan prestandaproblem uppstå när du försöker att beräkna rabatterna som ska användas för de olika produkterna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>The following examples illustrate this issue in more detail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Följande exempel visar det här problemet i detalj.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>In example 1, we start with two products and two overlapping discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I exempel 1 börjar vi med två produkter och två överlappande rabatter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Then, in example 2, we show how the issue evolves as more products are added.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sedan, i exempel 2, visar vi hur problemet utvecklas när fler produkter läggs till.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Example 1: Two products and two discounts</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exempel 1: Två produkter och två rabatter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>In this example, two products are required in order to qualify for each discount, and the discounts can't be combined.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här exemplet krävs två produkter för att kvalificera sig för varje rabatt och rabatterna kan inte kombineras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>The discounts in this example are <bpt id="p1">**</bpt>Best price<ept id="p1">**</ept> discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rabatterna i det här exemplet är <bpt id="p1">**</bpt>Bästa pris<ept id="p1">**</ept>-rabatter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Both products qualify for both discounts.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Båda produkterna uppfyller kraven för båda rabatterna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Here are the two discounts.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Här följer två rabatter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Example of two Best price discounts</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Exempel på två bästa prisrabatter</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>For any two products, the better of these two discounts depends on the prices of the two products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">För två valfria produkter vilar den bättre av dessa två rabatter på priserna för de två produkterna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>When the price of both products is equal or almost equal, discount 1 is better.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När priset för båda produkterna är nästan lika eller lika, är rabatt 1 bättre.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>When the price of one product is significantly less than the price of the other product, discount 2 is better.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När priset på en produkt är betydligt mindre än priset på den andra produkten, är rabatt 2 bättre.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Here is the mathematical rule for evaluating these two discounts against each other.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Här följer den matematiska regeln för att bedöma dessa två rabatter mot varandra.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Rule for evaluating the discounts</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Regel för utvärdering av rabatterna</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>When the price of product 1 is equal to two-thirds of the price of product 2, the two discounts are equal.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">När priset för produkt 1 är lika med två tredjedelar av priset för produkt 2, väger de två rabatterna lika.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>In this example, the effective discount percentage for discount 1 varies from a few percent (when the prices of the two products are far apart) to a maximum of 25 percent (when the two products have the same price).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här exemplet varierar rabattprocenten för rabatt 1 från några procent (när priserna för de två produkterna ligger långt från varandra) till högst 25 procent (när de två produkterna har samma pris).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>The effective discount percentage for discount 2 is fixed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Den effektiv rabattprocenten för rabatt 2 är fast.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>It's always 20 percent.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Den är alltid 20 procent.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>Because the effective discount percentage for discount 1 has a range that can be more than or less than discount 2, the best discount depends on the prices of the two products that must be discounted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Eftersom den effektiva rabattprocenten för rabatten 1 har ett intervall som kan vara mer än eller mindre än rabatt 2 är den bästa rabatten beroende av priserna för de två produkter som måste rabatteras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>In this example, the calculation is completed quickly, because only two discounts are applied on only two products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här exemplet slutfördes beräkningen snabbt, eftersom endast två rabatter tillämpas på endast två produkter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>There are only two possible combinations: one application of discount 1 or one application of discount 2.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det finns två möjliga kombinationer: ett användning av rabatt 1 eller en användning av rabatt 2.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>There are no permutations to calculate.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det finns inga permutationer att beräkna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>The value of each discount is calculated by using both products, and the best discount is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Värdet för varje rabatt beräknas med hjälp av båda produkterna och bästa rabatten används.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Example 2: Four products and two discounts</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exempel 2: Fyra produkter och två rabatter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Next, we will use four products and the same two discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nu ska använda fyra produkter och samma två rabatter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>All four products qualify for both discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Alla fyra produkterna uppfyller kraven för båda rabatterna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>There are twelve possible combinations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det finns tolv möjliga kombinationer.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>In the end, two discounts will be applied to the transaction in one of three combinations: two applications of discount 1, two applications of discount 2, or one application of discount 1 and one application of discount 2.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I slutändan ska två rabatter användas på transaktionen i någon av tre kombinationer: två användningar av rabatt 1, två användningar av rabatt 2 eller en användning av rabatt 1 och en användning av rabatt 2.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>To illustrate the possible combinations, we will look at two different sets of four products that have different prices:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att illustrera de möjliga kombinationerna ska vi titta på två olika uppsättningar med fyra produkter som har olika priser:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>All four products have the same price, $15.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Alla fyra produkterna har samma pris, $15,00.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>In this case, the best discount combination is two applications of discount 1.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här fallet är den bästa kombinationen två användningar av rabatt 1.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Two products will be full price, and two will be 50 percent off.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Två produkter får fullt pris och två får 50 procent rabatt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>The discounted total for the transaction is $45 (15 + 15 + 7.50 + 7.50), which is $15 (25 percent) off the undiscounted total of $60.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Den rabatterade summan för transaktionen är $45 (15 + 15 + 7,50 + 7,50), vilket är $15 (25 procent) av den orabatterade summan på $60.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>Discount 2 is only $12 (20 percent).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rabatt 2 är bara $12 (20 procent).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>Two products are $20 each, one product is $15, and one product is $5.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Två produkter kostar $20 var, en produkt koster $15 och en produkt kostar $5.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>In this case, the best discount combination is one application of discount 2 and one application of discount 1.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här fallet är den bästa kombinationen en användning av rabatt 2 och en användning av rabatt 1.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>The following tables illustrates the discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Följande tabeller visar rabatterna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>To read the tables, use one product from a row and one product from a column.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att läsa tabellerna, använd en produkt från en rad och en produkt från en kolumn.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>For example, in the table for discount 1, when you combine the two $20 products, you get $10 off.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Till exempel i tabellen för rabatt 1, när du kombinerar de två $20-produkterna, får du $10 rabatt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>In the table for discount 2, when you combine the $15 product and the $5 product, you get $4 off.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">I tabellen för rabatt 2, när du kombinerar $15-produkten och $5-produkten, får du $4 rabatt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Example that uses four products for the same two discounts</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Exempel på användning av fyra produkter för samma två rabatter</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>First, we find the largest discount that is available from any two products by using either discount.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Först letar vi reda på den största möjliga rabatten för två produkter genom att använda någondera av rabatterna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>The two tables show the discount amount for all combinations of the two products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">De två tabellerna visar rabattbeloppet för alla kombinationer av de två produkterna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>The shaded portions of the tables represent either cases where a product is paired with itself, which we can't do, or a reverse pairing of two products that produces the same discount amount and can be ignored.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Den skuggade delen av tabellerna representerar antingen fall där en produkt är ihopparad med sig själv, vilket vi inte kan göra, eller en omvänd ihopparning av två produkter som ger samma rabattbelopp och kan ignoreras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>By looking at the tables, you can see that discount 1 for the two $20 items is the largest discount that is available for either discount on all four products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Genom att titta i tabellerna ser du att rabatt 1 för de två $20-artiklarna är den största möjliga rabatten för någon rabatt på alla fyra produkterna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>(This discount is highlighted in green in the first table.) That leaves only the $15 product and the $5 product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">(Den här rabatten markeras med grönt i den första tabellen.) Kvar finns då $15-produkten och $5-produkten.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>By looking at the two tables again, you can see that, for these two products, discount 1 gives a $2.50 discount, whereas discount 2 gives a $4 discount.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Genom att titta på de två tabellerna igen ser du att rabatt 1 för dessa två produkter ger en rabatt på $2,50, medan rabatt 2 ger en rabatt på $4.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Therefore, we select discount 2.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vi väljer därför rabatt 2.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>The total discount is $14.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Totalrabatten är $14.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>To make this discussion easier to visualize, here are two additional tables that show the effective discount percentage for all possible two-product combinations for both discount 1 and discount 2.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att göra den här diskussionen enklare att visualisera är här två ytterligare tabeller som visar den effektiva rabattprocenten för alla möjliga kombinationer av två produkter för både rabatt 1 och rabatt 2.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>Only half the list of combinations is included, because, for these two discounts, the order in which the two products are put into the discount doesn't matter.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Endast halva listan över kombinationer ingår, eftersom det för dessa två rabatter inte spelar någon roll i vilken ordning de två produkterna tas med i rabatten.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>The highest effective discount (25 percent) is highlighted in green, and the lowest effective discount (10 percent) is highlighted in red.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Den högsta effektiva rabatten (25 procent)markeras med grönt och lägsta effektiva rabatten (10 procent) markeras i rött.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>Effective discount percentage for all two-product combinations for both discounts</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Effektiv rabatt i procent för alla kombinationer med två produkter för båda rabatterna</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>When prices vary, and two or more discount compete, the only way to guarantee the best combination of discounts is to evaluate both discounts and compare them.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">När priserna varierar, och två eller flera rabatter konkurrerar, är det enda sättet att garantera den bästa rabattkombinationen att utvärdera båda rabatter och jämföra dem.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Total possible combinations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Totalt antal möjliga kombinationer</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>This section continues the example from the previous section.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det här avsnittet fortsätter med exemplet i det föregående avsnittet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>We will add more products and another discount, and see how many combinations must be calculated and compared.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vi ska lägga till fler produkter och ytterligare en rabatt och se hur många kombinationer som måste beräknas och jämförs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>The following table shows the number of possible discount combinations as the product quantity increases.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tabellen nedan visar antalet möjliga rabattkombinationer allt eftersom produktkvantiteten ökar.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>The table shows what happens both when there are two overlapping discounts, as in the previous example, and when there are three overlapping discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I tabellen visas vad som händer, både när det finns två överlappande rabatter, som i föregående exempel, och när det finns tre överlappande rabatter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>The number of possible discount combinations that must be evaluated soon exceeds what even a fast computer can calculate and compare quickly enough to be acceptable for retail transactions.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Antalet möjliga rabattkombinationer som måste bedömas överskrider snart vad även en snabb dator kan beräkna och jämföra tillräckligt snabbt för att kunna godtas för butikstransaktioner.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>Number of possible discount combinations as the product quantity increases</source><target logoport:matchpercent="74" state="translated" state-qualifier="fuzzy-match">Antalet möjliga rabattkombinationer allt eftersom produktkvantiteten ökar.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>When even larger quantities or more overlapping discounts are applied, the total number of possible discount combinations quickly goes into the millions, and the time that is required in order to evaluate and select the best possible combination quickly becomes noticeable.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">När ännu större kvantiteter eller fler överlappande rabatter används blir det totala antalet möjliga rabattkombinationer snabbt miljontals, och den tid som krävs för att utvärdera och välja den bästa möjliga kombinationen blir snabbt betydande.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Some optimizations have been done in the retail price engine to reduce the total number of combinations that must be evaluated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vissa optimeringar har gjorts i butiksprismotorn för att minska det totala antalet kombinationer som måste utvärderas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>However, because the number overlapping discounts and the quantities in a transaction aren't limited, a large number of combinations will always have to be evaluated whenever there are overlapping discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Men eftersom antalet överlappande rabatter och kvantiteterna i en transaktion inte är begränsade måste ett stort antal kombinationer alltid utvärderas när det finns överlappande rabatter.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>This issue is the issue that the marginal value ranking method addresses.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Detta är problemet som metoden för marginalvärderankning hanterar.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Marginal value method</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Marginalvärdemetod</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>To resolve the issue of an exponentially increasing number of combinations that must be evaluated, an optimization exists that calculates the value per shared product of each discount on the set of products that two or more discounts can be applied to.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att lösa problemet med ett exponentiellt ökande antal kombinationer som måste utvärderas, finns en optimering som beräknar värdet per delad produkt för varje rabatt i uppsättningen med produkter som två eller flera rabatter kan tillämpas på.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>We refer to this value as the <bpt id="p1">**</bpt>marginal value<ept id="p1">**</ept> of the discount for the shared products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vi kallar detta värde för <bpt id="p1">**</bpt>marginalvärdet<ept id="p1">**</ept> på rabatten för de delade produkterna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>The marginal value is the average per product increase in the total discount amount when the shared products are included in each discount.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Marginalvärdet är den genomsnittliga ökningen per produkt av det totala rabattbeloppet när delade produkter tas med i varje rabatt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>The marginal value is calculated by taking the total discount amount (DTotal), subtracting the discount amount without the shared products (DMinus<ph id="ph1">\\</ph> Shared), and dividing that difference by the number of shared products (ProductsShared).</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Marginalvärdet beräknas genom att det totala rabattbeloppet (DTotal), dra av rabattbeloppet utan de delade produkterna (DMinus<ph id="ph1">\\</ph> Shared), och dividera denna skillnad med antalet delade produkter (ProductsShared).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>Formula for calculating marginal value</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Formel för beräkning av marginalvärde</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>After the marginal value of each discount on a shared set of products is calculated, the discounts are applied to the shared products in order, exhaustively, from highest marginal value to lowest marginal value.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">När marginalvärdet av varje rabatt i en delad uppsättning produkter beräknas, tillämpas rabatterna på de delade produkterna i ordning och fullständigt, från högsta marginalvärde till lägsta marginalvärde.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>For this method, all remaining discount possibilities aren't compared every time after a single instance of a discount is applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För den här metoden jämförs inte alla resterande rabattmöjligheter varje gång när en enda instans av en rabatt har tillämpats.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>Instead, the overlapping discounts are compared one time and then applied in order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I stället jämförs överlappande rabatter en gång och tillämpas sedan i ordning.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>No additional comparisons are done.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inga ytterligare jämförelser görs.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>You can configure the threshold to switch to the marginal value method on the <bpt id="p1">**</bpt>Discount<ept id="p1">**</ept> tab of the <bpt id="p2">**</bpt>Retail parameters<ept id="p2">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Du kan konfigurera tröskeln att byta till marginalvärdesmetoden på fliken <bpt id="p1">**</bpt>Rabatt<ept id="p1">**</ept> på sidan <bpt id="p2">**</bpt>Butiksparametrar<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>The acceptable time to calculate the total discount varies across retail industries.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Den godtagbar tiden att beräkna den totala rabatten varierar mellan butiksbranscher.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>However, this time generally falls in the range of tens of milliseconds to one second.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tiden ligger dock vanligtvis mellan tiotals millisekunder och en sekund.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>