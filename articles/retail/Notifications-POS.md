<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="Notifications-POS.md" target-language="sv-SE">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>Notifications-POS.74d2b9.6c813cfea9b570e8dfd5dbe7f3ca1f4ba8594420.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>6c813cfea9b570e8dfd5dbe7f3ca1f4ba8594420</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\Notifications-POS.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Show order notifications in the point of sale (POS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Visa ordermeddelanden i kassan (POS)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes how to enable order notifications in the point of sale and the notification framework.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det här avsnittet beskriver hur du aktiverar ordermeddelanden i kassan och ramverket för meddelanden.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Show order notifications in the point of sale (POS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Visa ordermeddelanden i kassan (POS)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>In the modern retail environment, store associates are assigned various tasks, such as helping customers, entering transactions, doing stock counts, and receiving orders in the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I dagens moderna butiksmiljö tilldelas butikens personal olika uppgifter, till exempel att hjälpa kunder, registrera transaktioner, lagerinventeringar och ta emot order i butiken.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The point of sale (POS) client provides a single application where associates can perform all these tasks and many others.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kassaklienten ger en enda applikation där medarbetare kan utföra alla dessa uppgifter och många andra.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>Because various tasks must be performed during the day, associates might have to be notified when something requires their attention.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Eftersom olika aktiviteter måste utföras under dagen kan personalen behöva meddelas när något kräver deras uppmärksamhet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>The notification framework in the POS helps by letting retailers configure role-based notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ramverket för meddelanden i kassan hjälper till genom att låta återförsäljarna konfigurera rollbaserade meddelanden.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>In Microsoft Dynamics 365 for Retail with application update 5, these notifications can be configured only for POS operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I Microsoft Dynamics 365 for Retail med programuppdatering 5, kan dessa meddelanden konfigureras för kassaoperationer.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Currently, the system can show notifications only for order fulfillment operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Systemet kan för närvarande endast visa meddelanden för orderuppföljningsåtgärder.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>However, because the framework is designed to be extensible, developers will eventually be able to write a notification handler for any operation and show the notifications for that operation in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Men eftersom ramverket är utformat till att vara utbyggbart kommer utvecklare så småningom kunna skriva en meddelandehanterare för alla åtgärder och visa meddelanden för den åtgärden i kassan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Enable notifications for order fulfillment operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aktivera meddelanden för utförande av orderuppfyllelse</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>To enable notifications for order fulfillment operations, follow these steps.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om du vill aktivera meddelanden för utförande av orderuppfyllelse, se följande steg:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Channel setup<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>POS setup<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>POS<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Operations<ept id="p5">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Navigera till <bpt id="p1">**</bpt>Butik<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Kanalinställningar<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Kassainställningar<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>Kassa<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Åtgärder<ept id="p5">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Search for the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> operation, and select the <bpt id="p2">**</bpt>Enable notifications<ept id="p2">**</ept> check box for it to specify that the notification framework should listen to the handler for this operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sök efter åtgärden <bpt id="p1">**</bpt>Orderuppfyllelse<ept id="p1">**</ept> och markera kryssrutan <bpt id="p2">**</bpt>Aktivera meddelanden<ept id="p2">**</ept> för att ange att ramverket för meddelanden ska lyssna på hanteraren för den här åtgärden.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>If the handler is implemented, notifications for this operation will then be shown in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om hanteraren implementeras visas meddelanden för den här åtgärden i kassan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Employees<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Workers<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph>, under Retail tab, open the POS permissions associated with the worker.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gå till <bpt id="p1">**</bpt>Butik<ept id="p1">**</ept><ph id="ph1">&amp;gt;</ph><bpt id="p2">**</bpt>Medarbetare<ept id="p2">**</ept><ph id="ph2">&amp;gt;</ph><bpt id="p3">**</bpt>Medarbetare<ept id="p3">**</ept><ph id="ph3">&amp;gt;</ph>, under fliken Butik, öppna de kassabehörigheter som är kopplade till medarbetaren.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Expand the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> FastTab, add the <bpt id="p2">**</bpt>Order fulfillment<ept id="p2">**</ept> operation, and set the <bpt id="p3">**</bpt>Display order<ept id="p3">**</ept> field to <bpt id="p4">**</bpt>1<ept id="p4">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Expandera snabbfliken <bpt id="p1">**</bpt>meddelanden<ept id="p1">**</ept>, lägg till åtgärden <bpt id="p2">**</bpt>orderuppfyllande<ept id="p2">**</ept> och ange fältet <bpt id="p3">**</bpt>visningsordning<ept id="p3">**</ept> till <bpt id="p4">**</bpt>1<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>If more than one notification is configured, this field is used to arrange the notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om fler än ett meddelande har konfigurerats används det här fältet för att ordna meddelanden.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Notifications that have a lower <bpt id="p1">**</bpt>Display order<ept id="p1">**</ept> value appear above notifications that have a higher value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Meddelanden som har ett lägre värde för <bpt id="p1">**</bpt>visningsordning<ept id="p1">**</ept> visas ovanför de meddelanden som har ett högre värde.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>Notifications that have a <bpt id="p1">**</bpt>Display order<ept id="p1">**</ept> value of <bpt id="p2">**</bpt>1<ept id="p2">**</ept> are at the top.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Meddelanden som har ett värde för <bpt id="p1">**</bpt>visningsordning<ept id="p1">**</ept> av <bpt id="p2">**</bpt>1<ept id="p2">**</ept> visas överst.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Notifications are shown only for operations that are added on the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> FastTab, and you can add operations there only if the <bpt id="p2">**</bpt>Enable notifications<ept id="p2">**</ept> check box for those operations has been selected on the <bpt id="p3">**</bpt>POS operations<ept id="p3">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Meddelandena visas endast för åtgärder som läggs till på snabbfliken <bpt id="p1">**</bpt>meddelanden<ept id="p1">**</ept> och du kan bara lägga till åtgärder där om kryssrutan <bpt id="p2">**</bpt>Aktivera meddelanden<ept id="p2">**</ept> för dessa åtgärder är markerad på sidan <bpt id="p3">**</bpt>Kassaåtgärder<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Additionally, notifications for an operation are shown to workers only if the operation is added to the POS permissions for those workers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dessutom visas meddelanden för en åtgärd för medarbetare endast om åtgärden läggs till i kassabehörigheterna för dessa medarbetare.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Notifications can be overridden at the user level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Meddelanden kan åsidosättas på användarnivå.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Open the worker's record, select <bpt id="p1">**</bpt>POS permissions<ept id="p1">**</ept>, and then edit the user's notification subscription.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Öppna medarbetarens post, markera <bpt id="p1">**</bpt>Kassabehörigheter<ept id="p1">**</ept> och redigera sedan användarens meddelandeabonnemang.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Channel setup<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>POS setup<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>POS profiles<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Functionality profiles<ept id="p5">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gå till <bpt id="p1">**</bpt>Butik<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Kanalinställningar<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Kassainställningar<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>Kassaprofiler<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Funktionsprofiler<ept id="p5">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>In the <bpt id="p1">**</bpt>Notification interval<ept id="p1">**</ept> field, specify how often notifications should be pulled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I fältet <bpt id="p1">**</bpt>meddelandeintervall<ept id="p1">**</ept>, anger du hur ofta meddelanden ska dras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>For some notifications, the POS must make real-time calls to the back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För vissa meddelanden måste kassan ringa samtal i realtid till backoffice-programmet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>These calls consume the compute capacity of your back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dessa samtal tar upp datorkapacitet i backoffice-programmets.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Therefore, when you set the notification interval, you should consider both your business requirements and the impact of real-time calls to the back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Därför när du anger meddelandeintervallet bör du både beakta ditt företags behov och effekten av samtal i realtid till backoffice-programmet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>A value of <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (zero) turns off notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Värdet <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (noll) stänger av meddelandefunktionen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Retail IT<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Distribution schedule<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gå till <bpt id="p1">**</bpt>Butik<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Butik-IT<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Distributionsschema<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Select the <bpt id="p1">**</bpt>1060<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Staff<ept id="p2">**</ept>) schedule to synchronize notification subscription settings, and then select <bpt id="p3">**</bpt>Run now<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Välj schemat <bpt id="p1">**</bpt>1060<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Personal<ept id="p2">**</ept>) för att synkronisera inställningar av meddelandeabonnemang och välj sedan <bpt id="p3">**</bpt>Kör nu<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Next, select the <bpt id="p1">**</bpt>1070<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Channel configuration<ept id="p2">**</ept>) schedule to synchronize the permission interval, and then select <bpt id="p3">**</bpt>Run now<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Välj sedan schemat <bpt id="p1">**</bpt>1070<ept id="p1">**</ept> (<bpt id="p2">**</bpt>kanalkonfiguration<ept id="p2">**</ept>) för att synkronisera behörighetsintervallet och välj sedan <bpt id="p3">**</bpt>Kör nu<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>View notifications in the POS</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Visa meddelanden i kassan</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>After you complete the preceding steps, the workers will be able to view the notifications in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När du har slutfört föregående steg ska medarbetare kunna visa meddelanden i kassan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>To view notifications, press the notification icon in the top right corner of the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att visa meddelanden, tryck på meddelandeikonen i det övre högra hörnet av kassan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>A notification center appears and shows notifications for the order fulfillment operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ett meddelandecenter visas och visar meddelanden för utförandet av orderuppfyllelse.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>The notification center should show the following groups in the order fulfillment operation:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Meddelancecentret ska visa följande grupper inom utförandet av orderuppfyllelse:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source><bpt id="p1">**</bpt>Store pickup<ept id="p1">**</ept> – This group shows the count of orders that have a delivery mode of <bpt id="p2">**</bpt>Pickup<ept id="p2">**</ept>, and that are scheduled for pickup from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Upphämtning i butik<ept id="p1">**</ept> Den här gruppen visar antalet order som har leveransläget <bpt id="p2">**</bpt>upphämtning<ept id="p2">**</ept> och upphämtning kommer från den aktuella butiken.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>You can press the number on the group to open the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Du kan trycka på numret i gruppen så öppnas sidan <bpt id="p1">**</bpt>orderuppfyllelse<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>In this case, the page will be filtered so that it shows only the active orders that are set up for pickup from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här fallet filtreras sidan så att den endast visar de aktiva order som har ställts in för upphämtning från den aktuella butiken.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source><bpt id="p1">**</bpt>Ship from store<ept id="p1">**</ept> – This group shows the count of orders that have the delivery mode of <bpt id="p2">**</bpt>Shipping<ept id="p2">**</ept>, and that are scheduled for shipment from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Leverera från butik<ept id="p1">**</ept> Den här gruppen visar antalet order som har leveransläget <bpt id="p2">**</bpt>Leverans<ept id="p2">**</ept> och leverans är planerad från den aktuella butiken.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>You can press the number on the group to open the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Du kan trycka på numret i gruppen så öppnas sidan <bpt id="p1">**</bpt>orderuppfyllelse<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>In this case, the page will be filtered so that it shows only the active orders that are set up for shipment from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I det här fallet filtreras sidan så att den endast visar de aktiva order som har ställts in för försändelse från den aktuella butiken.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>When new orders are assigned to the store for fulfillment, the notification icon changes to indicate that there are new notifications, and the count for the appropriate groups is updated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">När nya order tilldelats butiken för uppfyllelse kommer meddelandeikonen att ändras för att indikera att det finns nya meddelanden och antalet för lämpliga grupper uppdateras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Even though the groups are refreshed at regular intervals however, POS users can manually refresh the groups at any time by selecting the <bpt id="p1">**</bpt>Refresh<ept id="p1">**</ept> button next to the group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Även om grupperna uppdateras med jämna mellanrum kan kassaanvändare uppdatera grupperna manuellt när som helst genom att välja knappen <bpt id="p1">**</bpt>uppdatera<ept id="p1">**</ept> bredvid gruppen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>Lastly, if a group has a new item, that the current worker hasn't viewed, then the group shows a burst symbol to indicate new content.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Slutligen, om en grupp har en ny artikel som den aktuella medarbetaren inte har sett visar gruppen en explosionsikon som indikerar nytt innehåll.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>Enable live content on POS buttons</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aktivera levande innehåll på kassaknappar</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>POS buttons can now show a count to help workers easily determine which tasks require their immediate attention.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kassaknapparna kan nu visa ett antal för att hjälpa medarbetarna att bestämma vilka aktiviteter som kräver deras omedelbara uppmärksamhet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>To show this number on a POS button, you must complete the notification setup that is described earlier in this topic (that is, you must enable notifications for an operation, set up a notification interval, and update the POS permission group for the worker).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">För att visa detta nummer på en kassaknapp måste du slutföra de meddelandeinställningar som beskrivs tidigare i det här avsnittet (det vill säga du måste aktivera meddelanden för en åtgärd, konfigurera intervall för ett meddelande och uppdatera kassabehörighetsgrupp för medarbetaren).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Additionally, you must open the button grid designer, view the button's properties, and select the <bpt id="p1">**</bpt>Enable live content<ept id="p1">**</ept> check box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dessutom måste du öppna knappsatsen för designern, visa knappens egenskaper och markera kryssrutan <bpt id="p1">**</bpt>Aktivera levande innehåll<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>In the <bpt id="p1">**</bpt>Content alignment<ept id="p1">**</ept> field, you can select whether the count appears in the upper-right corner of the button (<bpt id="p2">**</bpt>Top right<ept id="p2">**</ept>) or in the center (<bpt id="p3">**</bpt>Center<ept id="p3">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I fältet <bpt id="p1">**</bpt>Innehållsjustering<ept id="p1">**</ept> kan du välja om numret ska visas i det övre högra hörnet på knappen (<bpt id="p2">**</bpt>Högst upp till höger<ept id="p2">**</ept>) eller i mitten (<bpt id="p3">**</bpt>Mitten<ept id="p3">**</ept>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>The live content can be enabled for operations only if the <bpt id="p1">**</bpt>Enable notifications<ept id="p1">**</ept> check box has been selected for them on the <bpt id="p2">**</bpt>POS operations<ept id="p2">**</ept> page, as described earlier in this topic.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Det levande innehållet kan endast aktiveras för åtgärder om kryssrutan <bpt id="p1">**</bpt>Aktivera meddelanden<ept id="p1">**</ept> har markerats för dem på sidan <bpt id="p2">**</bpt>Kassaåtgärder<ept id="p2">**</ept> som beskrivs tidigare i detta avsnitt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>The following illustration shows the live content settings in the button grid designer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Följande bild visar inställningarna för levande innehåll i knappsatsen för designern,</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source><bpt id="p1">![</bpt>Live content settings in the button grid designer<ept id="p1">]</ept><bpt id="p2">(./media/ButtonGridDesigner.png "</bpt>Live content settings in the button grid designer<ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Inställningar för levande innehåll i knappsatsen för designern<ept id="p1">]</ept><bpt id="p2">(./media/ButtonGridDesigner.png "</bpt>Inställningar för levande innehåll i knappsatsen för designern<ept id="p2">")</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>To show the notification count on a button, you need to ensure that the correct screen layout is being updated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om du vill visa meddelanderäkningen på en knapp måste du kontrollera att rätt skärmlayout håller på att uppdateras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>To determine the screen layout that is being used by the POS, select the <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> icon in upper-right corner and note the <bpt id="p2">**</bpt>Screen layout ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Layout resolution<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Om du vill ta reda på vilken skärmlayout som används i POS väljer du ikonen <bpt id="p1">**</bpt>Inställningar<ept id="p1">**</ept> i övre högra hörnet och noterar <bpt id="p2">**</bpt>Skärmlayout-ID<ept id="p2">**</ept> och <bpt id="p3">**</bpt>Layoutupplösning.<ept id="p3">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Now using Edge browser, go to the <bpt id="p1">**</bpt>Screen layout<ept id="p1">**</ept> page in Dynamics 365 for Finance and Operations, find the <bpt id="p2">**</bpt>Screen layout ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Layout resolution<ept id="p3">**</ept> identified above and select the <bpt id="p4">**</bpt>Enable live content<ept id="p4">**</ept> check box.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Nu använder du Edge-webbläsaren, gå till sidan <bpt id="p1">**</bpt>skärmlayout<ept id="p1">**</ept> i Dynamics 365 for Finance and Operations, leta reda på <bpt id="p2">**</bpt>bildskärms-ID<ept id="p2">**</ept> och <bpt id="p3">**</bpt>Layoutupplösning<ept id="p3">**</ept> som identifieras ovan och markera kryssrutan <bpt id="p4">**</bpt>Aktivera live-innehåll<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Go to <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Retail IT <ph id="ph2">\&gt;</ph> Distribution schedule<ept id="p1">**</ept> and run the 1090 (Registers) job to synchronize layout changes.</source><target logoport:matchpercent="0" state="translated">Gå <bpt id="p1">**</bpt>Butik <ph id="ph1">\&gt;</ph> Butikens IT <ph id="ph2">\&gt;</ph> Distributionsschema<ept id="p1">**</ept> och kör 1090-jobbet (journaler) för att synkronisera layoutändringar.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source><bpt id="p1">![</bpt>Find the screen layout used by POS<ept id="p1">]</ept><bpt id="p2">(./media/Choose_screen_layout.png "</bpt>Find the screen layout <ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Hitta den skärmlayout som används av kassan<ept id="p1">]</ept><bpt id="p2">(./media/Choose_screen_layout.png "</bpt>Hitta skärmlayouten <ept id="p2">")</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>The following illustration shows the effect of selecting <bpt id="p1">**</bpt>Top right<ept id="p1">**</ept> versus <bpt id="p2">**</bpt>Center<ept id="p2">**</ept> in the <bpt id="p3">**</bpt>Content alignment<ept id="p3">**</ept> field for buttons of various sizes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Följande bild visar effekterna av att välja <bpt id="p1">**</bpt>Högst upp till höger<ept id="p1">**</ept> jämfört med <bpt id="p2">**</bpt>Mitten<ept id="p2">**</ept> i fältet <bpt id="p3">**</bpt>Innehållsjustering<ept id="p3">**</ept> för knappar med olika storlekar.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source><bpt id="p1">![</bpt>Live content on POS buttons<ept id="p1">]</ept><bpt id="p2">(./media/ButtonsWithLiveContent.png "</bpt>Live content on POS buttons<ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Levande innehåll på kassaknappar<ept id="p1">]</ept><bpt id="p2">(./media/ButtonsWithLiveContent.png "</bpt>Levande innehåll på kassaknappar<ept id="p2">")</ept></target></trans-unit>
      </group>
    </body>
  </file>
</xliff>