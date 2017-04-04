---
title: "Godkännande av faktura-pilar"
description: "Mobila funktioner i Microsoft Dynamics 365 för operationer kan en affärsanvändare skapa mobila funktioner. Om avancerade scenarier plattformen också utvecklare utökar serverns användningsområden som de önskar. Det mest effektiva sättet att lära sig några nya koncept i mobile ska gå igenom processen med att skapa några scenarier. Det här avsnittet är avsett att ge en praktisk metod för att skapa mobila scenarier genom att leverantören fakturagodkännanden för mobila enheter som ett användningsfall. Det här avsnittet hjälper dig att skapa varianter på scenarier och kan även tillämpas på andra situationer som inte är relaterade till leverantörsfakturor."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 30229c0d24aed0bd927993b9af76b32d9bb073ee
ms.lasthandoff: 03/31/2017


---

# <a name="mobile-invoice-approvals"></a>Godkännande av faktura-pilar

Mobila funktioner i Microsoft Dynamics 365 för operationer kan en affärsanvändare skapa mobila funktioner. Om avancerade scenarier plattformen också utvecklare utökar serverns användningsområden som de önskar. Det mest effektiva sättet att lära sig några nya koncept i mobile ska gå igenom processen med att skapa några scenarier. Det här avsnittet är avsett att ge en praktisk metod för att skapa mobila scenarier genom att leverantören fakturagodkännanden för mobila enheter som ett användningsfall. Det här avsnittet hjälper dig att skapa varianter på scenarier och kan även tillämpas på andra situationer som inte är relaterade till leverantörsfakturor.

<a name="prerequisites"></a>Förutsättningar
-------------

| Förutsättning                                                                                            | beskrivning                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mobila före läsa handboken                                                                                |(/ dynamics365/operationer/dev-itpro/mobile-program / mobile-platform.md)                                                                                                  |
| Dynamics 365 för operationer                                                                             | En miljö med Microsoft Dynamics 365 för operationer version 1611 och Microsoft Dynamics-datorer operationer uppdatering 3 (2016 November)                   |
| Installera snabbkorrigering KB 3204341.                                                                              | Uppgiftsinspelning felaktigt spela in två Stäng kommandon för listrutan dialogrutor detta ingår i Dynamics 365 för operationen plattformsuppdatering 3 (uppdatering 2016 November) |
| Installera snabbkorrigering KB 3207800.                                                                              | Denna snabbkorrigering gör att bifogade filer som ska visas på mobila klienten detta ingår i Dynamics 365 för operationen plattformsuppdatering 3 (November 2016 uppdatering).           |
| Installera snabbkorrigering KB 3208224.                                                                              | Programkoden för mobila leverantör fakturan godkännande programmet detta ingår i Microsoft Dynamics AX application 7.0.1 (maj 2016).                          |
| En Android eller iOS eller en Windows-enhet med mobiltelefonprogrammet för Dynamics 365 för operationer | Sök efter appen i butiken lämpligt program.                                                                                                                     |

## <a name="introduction"></a>Introduktion
Mobila godkännanden för leverantörsfakturor kräver tre snabbkorrigeringar som nämns i avsnittet "Förutsättningar". De här snabbkorrigeringarna innehåller inte en arbetsyta för fakturan godkännande. Om du vill ta reda på vad läses en arbetsyta i samband med mobil, mobila handbok som nämns i avsnittet "Förutsättningar". Arbetsytan fakturan godkännanden skall utformas. 

Alla organisationer orchestrates och definierar sin affärsprocess för leverantörsfakturor på olika sätt. Innan du börjar utforma en mobila upplevelse för godkännande av leverantörens faktura bör du överväga följande aspekter i affärsprocessen. Tanken är att använda dessa datapunkter som möjligt att optimera användarupplevelsen på enheten.

-   Vilka fält från fakturahuvudet användaren vill ha i mobila erfarenheten, och i vilken ordning?
-   Vilka fält från fakturaraderna användaren vill ha i mobila erfarenheten, och i vilken ordning?
-   Hur många rader som finns i en faktura? Regeln 80 20 här och optimera för 80 procent.
-   Användarna vill ha redovisningsfördelningar (faktura kodning) på den mobila enheten under granskning? Om svaret på frågan är Ja kan beakta följande:
    -   Hur många redovisningsfördelningar (utökat pris, moms, tillägg, delningar, och så vidare) som finns för en fakturarad? Återigen, Använd 80 20-regeln.
    -   Fakturorna också har redovisningsfördelningar i fakturahuvudet? Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?

> [!NOTE]
> Det här avsnittet förklaras inte hur du redigera redovisningsfördelningar, eftersom den här funktionen inte stöds för närvarande mobila scenarier.

-   Användarna vill ha bilagor för fakturan på enheten?

Utformningen av mobila upplevelsen för godkännande av faktura varierar beroende på svaren på dessa frågor. Målet är att optimera användarupplevelsen för Affärsprocess i mobile i organisationen. I resten av det här avsnittet beskrivs två varianter av scenario som baseras på olika föregående frågor och svar. 

Som en allmän vägledning när du arbetar med mobila designer, måste du publicera ändringarna förlorat uppdateringarna.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Utforma ett scenario för godkännande av enkel faktura för Contoso
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenarioattribut</th>
<th>Besvara</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vilka fält från fakturahuvudet användaren vill ha i mobila erfarenheten, och i vilken ordning?</td>
<td><ol>
<li>Leverantörsnamn</li>
<li>Fakturatotal</li>
<li>Fakturakonto</li>
<li>Fakturanummer</li>
<li>Fakturadatum</li>
<li>Fakturabeskrivning</li>
<li>Förfallodatum</li>
<li>Fakturavaluta</li>
</ol></td>
</tr>
<tr class="even">
<td>Vilka fält från fakturaraderna användaren vill ha i mobila erfarenheten, och i vilken ordning?</td>
<td><ol>
<li>Anskaffningskategori</li>
<li>Kvantitet</li>
<li>Pris per enhet</li>
<li>Nettobelopp för rad</li>
<li>1099-belopp</li>
</ol></td>
</tr>
<tr class="odd">
<td>Hur många rader som finns i en faktura? Regeln 80 20 här och optimera för 80 procent.</td>
<td>1</td>
</tr>
<tr class="even">
<td>Användarna vill ha redovisningsfördelningar (faktura kodning) på den mobila enheten under granskning?</td>
<td>Ja</td>
</tr>
<tr class="odd">
<td>Hur många redovisningsfördelningar (utökat pris, moms, tillägg och så vidare) som finns för en fakturarad? Återigen, Använd 80 20-regeln.</td>
<td>Utökat pris: 2 moms: 0-tillägg: 0</td>
</tr>
<tr class="even">
<td>Fakturorna också har redovisningsfördelningar i fakturahuvudet? Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?</td>
<td>Används inte</td>
</tr>
<tr class="odd">
<td>Användarna vill ha bilagor för fakturan på enheten?</td>
<td>Ja</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Skapa arbetsytan

1.  Öppna Dynamics 365 för operationer och logga in i en webbläsare.
2.  När du har loggat in kan du lägga till **& mode = mobila** till URL som visas i följande exempel och uppdatera sidan: https://&lt;yoururl&gt;/? cmp = usmf & mi = DefaultDashboard**& läge = mobil**
3.  Klicka på den **inställningar** (växel)-knappen i det övre högra hörnet på sidan och klicka sedan på **mobiltelefonprogrammet**. Designern mobiltelefonprogrammet måste visas precis som uppgiften inspelning ska visas.
4.  Klicka på **Lägg** om du vill skapa en ny arbetsyta. Namn på arbetsytan för det här exemplet **Mina godkännanden**.
5.  Ange en beskrivning.
6.  Välj en färg för arbetsytan. Arbetsytans färg ska användas för övergripande formatmallen för mobila upplevelsen för den här arbetsytan.
7.  Välj en ikon för arbetsytan.
8.  Klicka på **har gjort**
9.  Klicka på **publicera arbetsytan** att spara ändringarna

### <a name="vendor-invoices-assigned-to-me"></a>Leverantörsfakturor som har tilldelats mig

Första sidan mobile som du bör utforma är en lista med fakturor som har tilldelats användare för granskning. När du designar sidan mobil, Använd den **VendMobileInvoiceAssignedToMeListPage** sida i Dynamics 365 för operationer. Innan du slutför den här proceduren kan du kontrollera att minst en leverantörsfaktura som är tilldelad till dig för granskning, och att fakturaraden har två fördelningar. Den här inställningen uppfyller kraven i det här scenariot.

1.  Ersätt modulens namn med menyalternativet i Dynamics 365 för operationer URL, **VendMobileInvoiceAssignedToMeListPage** öppna mobil version av den **pågående leverantörsfakturor som tilldelats mig** listsidan i den **Leverantörsreskontra** modulen. Beroende på hur många fakturor som du har på datorn tilldelas du visas den här sidan de fakturorna. Du kan använda filtret till vänster om du vill hitta en viss faktura. Men kräver vi inte en viss faktura i det här exemplet. Vi behöver bara vissa fakturan som tilldelats dig som kommer att utforma sidan mobile. Nya sidor som är tillgängliga har utformats specifikt för utveckling av mobila scenarier för leverantörsfakturan. Därför måste du använda sidorna. URL bör likna följande URL och när du har angett måste den sida som visas i illustrationen visas: https://&lt;yourURL&gt;/? cmp = usmf & mi =**VendMobileInvoiceAssignedToMeListPage**& mode = mobila [![sidan väntande leverantörsfakturor som har tilldelats mig](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
2.  Klicka på den **inställningar** (växel) knappen i det övre högra hörnet på sidan och klicka sedan på **mobiltelefonprogrammet**
3.  Markera arbetsytan och på **redigera**
4.  Klicka på **sidan Lägg till** du skapar du första sidan mobil.
5.  Ange ett namn, till exempel **fakturor från leverantörer**, och en beskrivning, t.ex **leverantörsfakturor som tilldelats mig för granskning**.
6.  Click **Done**.
7.  I mobila designern klickar du på den **fält** klickar du på **Välj fält**. Kolumnerna på listsidan måste likna illustrationen. [![Kolumnerna på pågående leverantörsfakturor som har tilldelats till mig sida](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
8.  Lägg till kolumnerna som krävs från sidan som visas för användare på sidan mobile. Den ordning som du lägger till är den ordning i vilken fälten visas för användaren. Det enda sättet att ändra ordningen på fälten blir genom att välja alla fält igen. Utifrån kraven i det här scenariot krävs följande åtta fält. Men överväga vissa användare åtta fält för mycket information på en mobil enhet. Därför visas bara de viktigaste fälten i vyn i listan. De återstående fälten visas i Detaljvyn vi utformar senare. Nu ska vi lägga till följande fält. Klicka på plustecknet (**+**) i dessa kolumner om du vill skicka till mobil sida.
    1.  Leverantörsnamn
    2.  Fakturatotal
    3.  Fakturakonto
    4.  Fakturanummer
    5.  Fakturadatum

    När fält läggs måste sidan mobile likna illustrationen. [![När fält läggs](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)
9.  Du måste även lägga till följande kolumner nu så att vi kan aktivera arbetsflödesåtgärder senare.
    1.  Visa slutförd aktivitet
    2.  Visa Delegera aktivitet
    3.  Visa återkalla uppgift
    4.  Visa avvisa ändringar
    5.  Visa slutförandeuppgiften för begäran
    6.  Visa skicka uppgift

10. Klicka på **har gjort** att Avsluta redigeringsläge.
11. Klicka på **tillbaka** och **har gjort** avsluta arbetsytan
12. Klicka på **publicera arbetsytan** att spara arbetet.
13. Aktivera **visa fakturatotalen på pågående fakturor lista** i parameterformuläret för leverantörsreskontra under **fakturan**. Observera att endast genom att aktivera den här parametern fakturasummor beräknas som ska visas på listsidan för leverantörer pågående fakturor. Detta är en ny funktion som en del av bestämda snabbkorrigering 3208224.

### <a name="vendor-invoice-details"></a>Leverantör-Fakturadetaljer

När du designar sidan faktura för mobile, Använd den **VendMobileInvoiceHeaderDetails** sida i Dynamics 365 för operationer. Observera att den här sidan visas de äldsta fakturan (faktura som först skapades) beroende på hur många fakturor som du har på datorn. Du kan använda filtret till vänster om du vill hitta en viss faktura. Men kräver vi inte en viss faktura i det här exemplet. Vi behöver bara vissa fakturadata så att vi kan utforma sidan mobil. [![Arbetsflödessidan](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1.  Ersätt modulens namn med menyalternativet i Dynamics 365 för operationer URL, **VendMobileInvoiceHeaderDetails** så att formuläret öppnas
2.  Öppna designern mobila från den **inställningar** (växel) knappen.
3.  Klicka på den **redigera** du vill starta redigeringsläget i arbetsytan.
4.  Välj den ** fakturor från leverantörer ** du skapade tidigare och sedan på **redigera**.
5.  I den **fält** klickar du på den **rutnät** kolumnrubriken.
6.  Klicka på **egenskaper**&gt;**sidan Lägg till**. **Anmärkning:** när du klickar på de **rutnät** rubrik och lägga till en sida i relation till sida får du automatiskt information.
7.  Ange en sidrubrik som **fakturainformation**, och en beskrivning, t.ex **visa fakturahuvudet och raddetaljer**.
8.  Klicka på **Välj fält**. Lägg märke till att den ordning som du lägger till ordern där fälten visas för användaren. Det enda sättet att ändra ordningen på fälten blir genom att välja alla fält igen.
9.  Från sidhuvudet i baserat på kraven i det här scenariot lägger du till följande fält:
    1.  Leverantörsnamn
    2.  Fakturatotal
    3.  Fakturakonto
    4.  Fakturanummer
    5.  Fakturadatum
    6.  Fakturabeskrivning
    7.  Förfallodatum
    8.  Fakturavaluta

10. Lägg till följande fält i rutnätet rader på sidan:
    1.  Anskaffningskategori
    2.  Kvantitet
    3.  Pris per enhet
    4.  Nettobelopp för rad
    5.  1099-belopp

11. När alla fält från de två föregående stegen har lagts till, klickar du på **har gjort**. Sidan måste likna illustrationen. [![När fält läggs](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)
12. Klicka på **har gjort** att Avsluta redigeringsläge.
13. Klicka på **tillbaka** och **har gjort** avsluta arbetsytan
14. Klicka på **publicera arbetsytan** att spara arbetet

### <a name="workflow-actions"></a>Arbetsflödesåtgärder

Om du vill lägga till arbetsflödesåtgärder, Använd den **VendMobileInvoiceHeaderDetails** sida i Dynamics 365 för operationer. Ersätt namnet på menyalternativet i URL-Adressen, precis som tidigare om du vill öppna sidan. Öppna designern mobila från den **inställningar** (växel) knappen. Så här lägger du till arbetsflödesåtgärder på sidan.

1.  Klicka på den **redigera** du vill starta redigeringsläget i arbetsytan.
2.  Välj den **fakturainformation** du skapade tidigare och sedan på **redigera**.
3.  I den **åtgärder** klickar du på **lägga till**.
4.  Ange en rubrik för åtgärden, till exempel **Godkänn**, och en beskrivning, t.ex **Godkänn fakturan**. Observera att rubriken åtgärd som du anger här blir namnet på åtgärden som visas för användaren i mobila programmet.
5.  Click **Done**.
6.  Klicka på **Välj fält**.
7.  Gå igenom arbetsflödesprocessen den **VendMobileInvoiceHeaderDetails** sidan och utför åtgärden som du vill registrera. Kontrollera att du skriver kommentarer för arbetsflöde under den här processen så att ett kommentarsfält ingår också i mobila upplevelsen.
8.  När arbetsflödesåtgärden körs, klickar du på **har gjort** ska ha slutfört uppgiften väljer fält.
9.  Klicka på **har gjort** att Avsluta redigeringsläge.
10. Klicka på **tillbaka** och **har gjort** avsluta arbetsytan
11. Klicka på **publicera arbetsytan** att spara arbetet
12. Upprepa steg 3 till 11 för att registrera de obligatoriska arbetsflödesåtgärder. Observera att det är ett krav har tilldelats dig fakturor som är i ett tillstånd att tillhandahålla de arbetsflödesåtgärder som du tänker skapa för.
13. Öppna Anteckningar eller Microsoft Visual Studio och klistra in följande kod. Spara filen som en JS-fil. Den här koden gör två saker:
    1.  Extra arbetsflöde relaterade kolumnerna som vi har lagt till tidigare på listsidan för mobila döljs. Vi har lagt till kolumnerna så att programmet har informationen i sammanhanget göra nästa steg.
    2.  Utifrån arbetsflödessteg som visas gäller logik för att visa bara de åtgärderna.

Observera att namnet på sidorna och andra kontroller i JS koden måste överensstämma med arbetsytan.

1.  Funktion huvudsakliga (metadataService, dataService, cacheService, $q) {returnera {appInit: funktion (appMetadata) {/ / Dölj kontroller som måste vara finns men är inte synliga metadataService.configureControl (' min--leverantörsfakturor, 'ShowAccept' {dolda: true}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowApprove' {dolda: true}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowReject' {dolda: true}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowDelegate' {dolda: SANT}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowRequestChange' {dolda: SANT}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowRecall' {dolda: SANT}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowComplete' {dolda: SANT}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowResubmit' { dolda: true}); }, pageInit: funktion (pageMetadata, parametrar) {om (pageMetadata.Name == 'Fakturadetaljer') {/ / Visa/Dölj arbetsflödesåtgärder utifrån arbetsflöde steg metadataService.configureAction (acceptera godkänns {visas: true}), metadataService.configureAction (Godkänn, {visas: true}), metadataService.configureAction (ignorera, {visas: true}), metadataService.configureAction (delegera, {visas: SANT}), metadataService.configureAction (' begär ändring ', {visas: true}), metadataService.configureAction (återkallande, {visas: SANT}), metadataService.configureAction (avslutad, {visas: SANT}), metadataService.configureAction ("Skicka" {visas: SANT}),

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }

2.  Överför kodfilen till arbetsytan genom att välja den **Logic** fliken
3.  Klicka på **har gjort** att Avsluta redigeringsläge.
4.  Klicka på **tillbaka** och **har gjort** avsluta arbetsytan
5.  Klicka på **publicera arbetsytan** att spara arbetet

### <a name="vendor-invoice-attachments"></a>Leverantör, faktura bifogade filer

1.  Klicka på den **inställningar** (växel) knappen i det övre högra hörnet på sidan och klicka sedan på **mobiltelefonprogrammet**
2.  Klicka på den **redigera** du vill starta redigeringsläget i arbetsytan.
3.  Välj den ** fakturainformation ** du skapade tidigare och sedan på **redigera**.
4.  Ange den **dokumenthantering** att **Ja** enligt nedan. **Anmärkning:** om det finns inga krav för att visa bifogade filer på den mobila enheten kan du lämna detta alternativ inställt på **nr**, vilket är standardinställningen.
5.  [![docmanagement](./media/docmanagement-216x300.png)](./media/docmanagement.png)
6.  Klicka på **har gjort** att Avsluta redigeringsläge.
7.  Klicka på **tillbaka** och **har gjort** avsluta arbetsytan
8.  Klicka på **publicera arbetsytan** att spara arbetet

### <a name="vendor-invoice-line-distributions"></a>Leverantörsfakturafördelningar rad

Kraven i det här scenariot bekräfta att endast-radnivå fördelningar och en faktura kommer alltid att bara en rad. Eftersom detta scenario är enkelt, måste användargränssnitt på den mobila enheten vara så enkelt att användaren inte behöver gå ned flera nivåer som ska visa fördelningarna. Leverantörsfakturor i Dynamics 365 för operationer finns alternativet att visa alla fördelningar från fakturahuvudet. Denna erfarenhet är det vi behöver mobila scenariot. Därför använder vi i **VendMobileInvoiceAllDistributionTree** vill designa den här delen av mobila scenariot. 

> [!NOTE] 
> Behovet av att veta hjälper oss att avgöra vilken sida ska användas och hur exakt att optimera mobila upplevelse för användaren när vi utformar scenariot. I det andra fallet utnyttjas en annan sida för att visa fördelningar, eftersom olika krav för scenariot.

1.  Ersätt namnet på menyalternativet som du gjorde första gången i URL. Sidan visas bör likna illustrationen. [![Alla fördelningar sida](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)
2.  Öppna designern mobila från den **inställningar** (växel) knappen.
3.  Klicka på den **redigera** du vill starta redigeringsläget i arbetsytan. **Anmärkning:** visas två nya sidor har skapats automatiskt. Dessa sidor skapas i systemet eftersom du aktiverade dokumenthantering i föregående avsnitt. Du kan ignorera dessa nya sidor.
4.  Klicka på **sidan Lägg till**.
5.  Ange en sidrubrik som **visa redovisning**, och en beskrivning, t.ex **visa redovisning av fakturan**.
6.  Click **Done**.
7.  På den **fält** klickar du på **Välj fält**Välj följande fält från sidan fördelningar och klicka sedan på **har gjort**:
    1.  Belopp
    2.  Valuta
    3.  Huvudbokskonto

> [!NOTE] 
> Vi inte väljer den **beskrivning** kolumn från rutnätet fördelningar eftersom kraven i det här scenariot bekräftat att det utökade priset är endast beloppet som finns för fördelningar. Därför behöver inte användaren någon ett annat fält för att avgöra vilken beloppstyp som avser fördelningen. I nästa scenariot har vi **kan** använder den här informationen eftersom anger krav för scenariot som andra belopptyper har fördelningar (till exempel försäljnings skatteskäl).
8.  Klicka på **har gjort** att Avsluta redigeringsläge.
9.  Klicka på **tillbaka** och **har gjort** avsluta arbetsytan
10. Klicka på **publicera arbetsytan** att spara arbetet

**Anmärkning:** de **visa redovisning** mobilsida är inte kopplad till någon av mobila sidorna som vi har skapat hittills. Eftersom användaren ska kunna navigera till den **visa redovisning** sidan från den **fakturainformation** sida på den mobila enheten måste gärna navigering från den **fakturainformation** sidan till den **visa redovisning** sida. Vi fastställa navigering med hjälp av ytterligare logik via JavaScript.

1.  Öppna JS-fil som du skapade tidigare och lägga till rader som markerats i koden nedan. Den här koden gör två saker:
    1.  Det hjälper till att garantera att användaren inte kan bläddra direkt från arbetsytan till den **visa redovisning** sida.
    2.  Den konstaterar att en navigeringskontroll från den **fakturainformation** sidan till den **visa redovisning** sida.

> [!NOTE] 
> Namnet på sidorna och andra kontroller i JS-koden måste vara densamma från arbetsytan.

1.  Funktion huvudsakliga (metadataService, dataService, cacheService, $q) {returnera {appInit: funktion (appMetadata) {/ / Dölj kontroller som måste vara finns men är inte synliga metadataService.configureControl (' min--leverantörsfakturor, 'ShowAccept' {dolda: true}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowApprove' {dolda: true}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowReject' {dolda: true}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowDelegate' {dolda: SANT}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowRequestChange' {dolda: SANT}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowRecall' {dolda: SANT}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowComplete' {dolda: SANT}), metadataService.configureControl (' min--leverantörsfakturor, 'ShowResubmit' { dolda: true}); Dölja sidor är inte tillgängligt för roten navigering metadataService.hideNavigation('View-accounting'); Länk metadataService.addLink redovisning ('-Fakturadetaljer, ' Visa redovisning ', '-redovisning-nav-kontroll ', "Visa redovisning", SANT); }, pageInit: funktion (pageMetadata, parametrar) {om (pageMetadata.Name == 'Fakturadetaljer') {/ / Visa/Dölj arbetsflödesåtgärder utifrån arbetsflöde steg metadataService.configureAction (acceptera godkänns {visas: true}), metadataService.configureAction (Godkänn, {visas: true}), metadataService.configureAction (ignorera, {visas: true}), metadataService.configureAction (delegera, {visas: SANT}), metadataService.configureAction (' begär ändring ', {visas: true}), metadataService.configureAction (återkallande, {visas: SANT}), metadataService.configureAction (avslutad, {visas: SANT}), metadataService.configureAction ("Skicka" {visas: SANT}),

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }

2.  Överför kodfilen till arbetsytan genom att välja den **logik** att ersätta föregående kod
3.  Klicka på **har gjort** att Avsluta redigeringsläge.
4.  Klicka på **tillbaka** och **har gjort** avsluta arbetsytan
5.  Klicka på **publicera arbetsytan** att spara arbetet

### <a name="validation"></a>Validering

Öppna appen från den mobila enheten och Anslut till Dynamics 365 för operationer instans. Kontrollera att du loggar in till företaget där leverantörsfakturor som har tilldelats dig för granskning. Du ska kunna utföra följande åtgärder:

-   Finns det **Mina godkännanden** arbetsytan.
-   Gå till den **Mina godkännanden** arbetsytan och se den **fakturor från leverantörer** sida.
-   Gå till den **fakturor från leverantörer** och se en lista med fakturor som har tilldelats dig.
-   Gå till en fakturor och visa Fakturadetaljer rubrik- och raddetaljer.
-   På informationssidan visas en länk till bilagor och Använd den här länken för att navigera till listan med bifogade filer och visa de bifogade filerna.
-   På informationssidan visas en länk till den **visa redovisning** sidan och Använd den här länken för att gå till sidan fördelningar och visa fördelningarna.
-   På detaljsidan i **åtgärder** menyn längst ned och utföra arbetsflödesåtgärder som gäller för arbetsflödessteget.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Utforma ett godkännande scenario komplicerad faktura för Fabrikam
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenarioattribut</th>
<th>Besvara</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vilka fält från fakturahuvudet användaren vill ha i mobila erfarenheten, och i vilken ordning?</td>
<td><ol>
<li>Leverantörsnamn</li>
<li>Fakturabelopp</li>
<li>Fakturakonto</li>
<li>Fakturanummer</li>
<li>Fakturadatum</li>
<li>Fakturabeskrivning</li>
<li>Förfallodatum</li>
<li>Fakturavaluta</li>
</ol></td>
</tr>
<tr class="even">
<td>Vilka fält från fakturaraderna användaren vill ha i mobila erfarenheten, och i vilken ordning?</td>
<td><ol>
<li>Anskaffningskategori</li>
<li>Kvantitet</li>
<li>Pris per enhet</li>
<li>Nettobelopp för rad</li>
<li>1099-belopp</li>
</ol></td>
</tr>
<tr class="odd">
<td>Hur många rader som finns i en faktura? Regeln 80 20 här och optimera för 80 procent.</td>
<td>5</td>
</tr>
<tr class="even">
<td>Användarna vill ha redovisningsfördelningar (faktura kodning) på den mobila enheten under granskning?</td>
<td>Ja</td>
</tr>
<tr class="odd">
<td>Hur många redovisningsfördelningar (utökat pris, moms, tillägg och så vidare) som finns för en fakturarad? Återigen, Använd 80 20-regeln.</td>
<td>Utökat pris: 2 moms: tillägg 2: 2</td>
</tr>
<tr class="even">
<td>Fakturorna också har redovisningsfördelningar i fakturahuvudet? Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?</td>
<td>Används inte</td>
</tr>
<tr class="odd">
<td>Användarna vill ha bilagor för fakturan på enheten?</td>
<td>Ja</td>
</tr>
</tbody>
</table>

### <a name="exercise"></a>Övning

Följande ändringar kan göras för scenario 1, baserat på kraven för scenario 2. Använd det här avsnittet som Övning som du kan utföra om syften.

1.  Eftersom flera fakturarader förväntas i scenario 2, hjälper optimera användarupplevelsen på den mobila enheten design följande ändringar:
    1.  Istället för att visa fakturarader på sidan med information (som i scenario 1) kan användare välja att visa rader på en mobil sida.
    2.  Eftersom flera fakturaraden förväntas i det här fallet om den **VendMobileInvoiceAllDistributionTree** sidan används för att utforma sidan fördelningar för mobile (liksom i scenario 1), det kan vara förvirrande för användaren att jämföra fördelningar raderna. Använd därför den **VendMobileInvoiceLineDistributionTree** sidan om du vill designa sidan fördelningar.
    3.  Vi rekommenderar ska fördelningarna visas i samband med en fakturarad i det här scenariot. Kontrollera därför att användaren kan söka i en rad för att visa sidan fördelningar. Använd sidan länken möjligheten för att upprätta detaljerad, precis som du gjorde för sidorna i scenario 1 rubrik och information.

2.  Eftersom flera beloppstyp förväntas vid utdelning i scenario 2 (moms, tillägg och så vidare), kan det vara praktiskt att visa beskrivningen av beloppstyp. (Vi bort informationen i scenario 1.)

## <a name="conclusion"></a>Slutsats
Mobil plattform och programmet funktionerna möjliggör mobil scenarier som är optimerade för användarbas i organisationen. Utifrån exemplen i det här avsnittet finns du prova andra varianter och skapa olika erfarenheter som uppfyller specifika behov.


