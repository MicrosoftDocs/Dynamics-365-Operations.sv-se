---
title: Mobila fakturagodkännanden
description: Det här avsnittet är avsett att ge en praktisk metod för att skapa mobila scenarier i Dynamics 365 for Finance and Operations genom att ta leverantörsfakturagodkännanden för mobila enheter som ett användningsfall.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5a48ea7b0c1faf5726de21a246e3d8b4d98f166a
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1511670"
---
# <a name="mobile-invoice-approvals"></a>Mobila fakturagodkännanden

[!include [banner](../includes/banner.md)]

Med mobila funktioner i Microsoft Dynamics 365 for Finance and Operations kan en affärsanvändare skapa mobila funktioner. För avancerade scenarier gör plattformen också att utvecklare kan utöka användningsområdena som de önskar. Det mest effektiva sättet att lära sig nya koncept på mobilen är att gå igenom processen att skapa några scenarier. Det här avsnittet är avsett att ge en praktisk metod för att skapa mobila scenarier genom att ta leverantörsfakturagodkännanden för mobila enheter som ett användningsfall. Det här avsnittet hjälper dig att skapa varianter på scenarier och kan även tillämpas på andra scenarier som inte är relaterade till leverantörsfakturor.

<a name="prerequisites"></a>Förutsättningar
-------------

| Förutsättning                                                                                            | beskrivning                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mobil handbok - före läsning                                                                                |[Mobilplattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| Dynamics 365 for Finance and Operations                                                                             | En miljö som har Microsoft Dynamics 365 for Operations version 1611 och Microsoft Dynamics for Operations uppdatering 3 (november 2016)                   |
| Installera snabbkorrigering KB 3204341.                                                                              | Uppgiftsinspelaren kan felaktigt spela in två Stäng-kommandon för listrutans dialogrutor. Detta ingår i Dynamics 365 for Operation-plattformsuppdatering 3 (uppdatering november 2016) |
| Installera snabbkorrigering KB 3207800.                                                                              | Denna snabbkorrigering gör att bifogade filer kan visas på mobila klienten. Detta ingår i Dynamics 365 for Operation-plattformsuppdatering 3 (uppdatering november 2016).           |
| Installera snabbkorrigering KB 3208224.                                                                              | Programkoden för godkännandeprogrammet för mobila leverantörsfakturan. Detta ingår i Microsoft Dynamics AX-programmet 7.0.1 (maj 2016).                          |
| En Android-, iOS- eller en Windows-enhet med mobilappen installerad för Finance and Operations | Sök efter appen i lämplig appbutik.                                                                                                                     |

## <a name="introduction"></a>Introduktion
Mobila godkännanden för leverantörsfakturor kräver tre snabbkorrigeringar som nämns i avsnittet "Förutsättningar". De här snabbkorrigeringarna innehåller inte en arbetsyta för fakturagodkännande. Om du vill ta reda på vad en arbetsyta är i samband med mobil, läs mobila handbok som nämns i avsnittet "Förutsättningar". Arbetsytan för fakturagodkännanden måste utformas. 

Alla organisationer orkestrerar och definierar sin affärsprocess för leverantörsfakturor på olika sätt. Innan du börjar utforma en mobil upplevelse för godkännande av leverantörsfakturor bör du överväga följande aspekter i affärsprocessen. Tanken är att använda dessa datapunkter så mycket som möjligt för att optimera användarupplevelsen på enheten.

-   Vilka fält från fakturahuvudet vill användaren ha i mobilupplevelsen, och i vilken ordning?
-   Vilka fält från fakturaraderna vill användaren ha i mobilupplevelsen, och i vilken ordning?
-   Hur många rader finns det i en faktura? Använd 80-20-regeln här och optimera för 80 procent.
-   Vill användarna ha redovisningsfördelningar (fakturakodning) på den mobila enheten vid granskningar? Om svaret på frågan är Ja, beakta följande:
    -   Hur många redovisningsfördelningar (slutligt pris, moms, avgifter, delningar, och så vidare) finns det för en fakturarad? Återigen, använd 80-20-regeln.
    -   Har fakturorna också redovisningsfördelningar i fakturahuvudet? Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?

> [!NOTE]
> Det här avsnittet förklarar inte hur du redigerar redovisningsfördelningar, eftersom den här funktionen inte stöds för närvarande för mobila scenarier.

-   Vill användarna se bilagor för fakturan på enheten?

Utformningen av den mobila upplevelsen för fakturagodkännanden varierar beroende på svaren på dessa frågor. Målet är att optimera användarupplevelsen för affärsprocessen på mobil i organisationen. I resten av det här avsnittet beskrivs två varianter av scenario som baseras på olika svar på föregående frågor. 

Som en allmän vägledning, när du arbetar med mobildesignern, se till att du "publicerar" ändringarna för att inte förlora uppdateringarna.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Utforma ett enkelt scenario för fakturagodkännande för Contoso
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
<td>Vilka fält från fakturahuvudet vill användaren ha i mobilupplevelsen, och i vilken ordning?</td>
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
<td>Vilka fält från fakturaraderna vill användaren ha i mobilupplevelsen, och i vilken ordning?</td>
<td><ol>
<li>Anskaffningskategori</li>
<li>Kvantitet</li>
<li>Pris per enhet</li>
<li>Nettobelopp för rad</li>
<li>1099-belopp</li>
</ol></td>
</tr>
<tr class="odd">
<td>Hur många rader finns det i en faktura? Använd 80-20-regeln här och optimera för 80 procent.</td>
<td>1</td>
</tr>
<tr class="even">
<td>Vill användarna ha redovisningsfördelningar (fakturakodning) på den mobila enheten vid granskningar?</td>
<td>Ja</td>
</tr>
<tr class="odd">
<td>Hur många redovisningsfördelningar (slutligt pris, moms, avgifter, och så vidare) finns det för en fakturarad? Återigen, använd 80-20-regeln.</td>
<td>Slutligt pris: 2 Moms: 0 Avgifter: 0</td>
</tr>
<tr class="even">
<td>Har fakturorna också redovisningsfördelningar i fakturahuvudet? Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?</td>
<td>Används inte</td>
</tr>
<tr class="odd">
<td>Vill användarna se bilagor för fakturan på enheten?</td>
<td>Ja</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Skapa arbetsytan

1.  Öppna Finance and Operations och logga in i en webbläsare.
2.  När du har loggat in kan du lägga till **&mode=mobile** till URL:en som visas i följande exempel, och uppdatera sidan: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**
3.  Klicka på knappen **Inställningar** (kugghjul) i det övre högra hörnet på sidan och klicka sedan på **Mobilapp**. Mobilapps-designern måste visas precis som Uppgiftsinspelare visas.
4.  Klicka på **Lägg till** för att skapa en ny arbetsyta. Namnet på arbetsytan för det här exemplet anger du som **Mina godkännanden**.
5.  Ange en beskrivning.
6.  Välj en färg på arbetsytan. Arbetsytans färg ska användas för övergripande stilen för den mobila upplevelsen för den här arbetsytan.
7.  Välj en ikon för arbetsytan.
8.  Klicka på **Klart**
9.  Klicka på **Publicera arbetsytan** för att spara ändringarna.

### <a name="vendor-invoices-assigned-to-me"></a>Leverantörsfakturor som har tilldelats mig

Den första mobilsidan som du bör utforma är en lista med fakturor som har tilldelats till användaren för granskning. Använd sidan **VendMobileInvoiceAssignedToMeListPage** i Finance and Operations när du designar den här mobilsidan. Innan du slutför den här proceduren, kontrollera att minst en leverantörsfaktura har tilldelats till dig för granskning, och att fakturaraden har två fördelningar. Den här inställningen uppfyller kraven i det här scenariot.

1.  Ersätt menyalternativets namn i URL:en till Finance and Operations med **VendMobileInvoiceAssignedToMeListPage** för att öppna mobilversionen av listsidan **Pågående leverantörsfakturor som tilldelats mig** i modulen **Leverantörsreskontra**. Beroende på hur många fakturor som du har i systemet tilldelade till dig, visas dessa fakturor på den här sidan. Om du vill hitta en specifik faktura kan du använda filtret till vänster. Men i det här exemplet kräver vi inte en viss faktura. Vi behöver bara en faktura som tilldelats dig som gör att du kan utforma mobilsidan. De nya sidor som är tillgängliga har utformats specifikt för utveckling av mobila scenarier för leverantörsfakturan. Därför måste du använda dessa sidor. URL:en bör likna följande URL och när du har angett den måste sidan som visas i illustrationen visas: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Väntande leverantörsfakturor som har tilldelats mig](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
2.  Klicka på knappen **Inställningar** (kugghjul) i det övre högra hörnet på sidan och klicka sedan på **Mobilapp**
3.  Välj din arbetsyta och klicka på **Redigera**
4.  Klicka på **Lägg till sida** för att skapa den första mobilsidan.
5.  Ange ett namn, till exempel **Mina leverantörsfakturor**, och en beskrivning, till exempel **Leverantörsfakturor som tilldelats mig för granskning**.
6.  Klicka på **Klart**.
7.  I mobila designern, på fliken **Fält** klickar du på **Välj fält**. Kolumnerna på listsidan måste likna följande illustration. [![Kolumner på sidan Väntande leverantörsfakturor som har tilldelats mig](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
8.  Lägg till de kolumner som krävs från listsidan som måste visas för användare på mobilsidan. Den ordning som du lägger till i är den ordning i vilken fälten visas för slutanvändaren. Det enda sättet att ändra ordningen på fälten blir genom att välja alla fält igen. Utifrån kraven i det här scenariot krävs följande åtta fält. Men vissa användare kanske anser att åtta fält är för mycket information på en mobil enhet. Därför visar vi bara de viktigaste fälten i vyn med mobillistan. De återstående fälten visas i detaljvyn som vi utformar senare. Nu lägger vi till följande fält. Klicka på plustecknet (**+**) i dessa kolumner för att lägga till på mobilsidan.
    - Leverantörsnamn
    - Fakturatotal
    - Fakturakonto
    - Fakturanummer
    - Fakturadatum

    När fält läggs till måste mobilsidan likna följande illustration. 
    [![Sidan när fält har lagts till](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)
9.  Du måste även lägga till följande kolumner nu, så att vi kan aktivera arbetsflödesåtgärder senare.
    - Visa Slutför uppgift
    - Visa Delegera uppgift
    - Visa Återkalla uppgift
    - Visa Avvisa uppgift
    - Visa Begär slutförandeuppgift
    - Visa Skicka uppgift igen

10. Klicka på **Klart** för att avsluta redigeringsläge.
11. Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan
12. Klicka på **Publicera arbetsytan** för att spara ditt arbete.
13. Aktivera **Visa fakturasumma i listan med pågående leverantörsfakturor** i parameterformuläret för leverantörsreskontra under **Faktura**. Observera att endast genom att aktivera den här parametern beräknas fakturasummor som ska visas på listsidan för pågående leverantörsfakturor. Detta är en ny funktion som en del av förutsättningen snabbkorrigering 3208224.

### <a name="vendor-invoice-details"></a>Detaljer om leverantörsfaktura

Använd sidan **VendMobileInvoiceHeaderDetails** i Finance and Operations när du designar sidan med fakturadetaljer för mobil. Observera att beroende på antalet fakturor som du har i systemet visar den här sidan den äldsta fakturan (faktura som först skapades). Om du vill hitta en specifik faktura kan du använda filtret till vänster. Men i det här exemplet kräver vi inte en viss faktura. Vi behöver bara vissa fakturadata så att vi kan utforma mobilsidan. [![Sida för arbetsflöde](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1. I URL:en för Finance and Operations ersätter du namnet på menyalternativet med **VendMobileInvoiceHeaderDetails** för att öppna formuläret
2. Öppna mobildesignern med knappen **Inställningar** (kugghjul).
3. Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan.
4. Välj sidan **Mina leverantörsfakturor** som du skapade tidigare och klicka sedan på **Redigera**.
5. På fliken **Fält** klickar du på kolumnrubriken **Rutnät**.
6. Klicka på **Egenskaper &gt;Lägg till sida**. **Anmärkning:** När du klickar på rubriken **Rutnät** och lägger till en sida, etableras relationen med detaljsidan automatiskt.
7. Ange en sidrubrik, till exempel **Fakturadetaljer**, och en beskrivning, till exempel **Visa fakturahuvud och raddetaljer**.
8. Klicka på **Välj fält**. Observera att den ordning som du lägger till i är den ordning i vilken fälten visas för slutanvändaren. Det enda sättet att ändra ordningen på fälten blir genom att välja alla fält igen. 
9. Lägg till följande fält från huvudet, baserat på förutsättningarna för det här scenariot:
   - Leverantörsnamn
   - Fakturatotal
   - Fakturakonto
   - Fakturanummer
   - Fakturadatum
   - Fakturabeskrivning
   - Förfallodatum
   - Fakturavaluta

10. Lägg till följande fält från radrutnätet på sidan:
    - Anskaffningskategori
    - Kvantitet
    - Pris per enhet
    - Nettobelopp för rad
    - 1099-belopp

11. När alla fält från de två föregående stegen har lagts till, klickar du på **Klart**. Sidan måste likna följande illustration.
    [![Sidan när fält har lagts till](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)
12. Klicka på **Klart** för att avsluta redigeringsläge.
13. Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan
14. Klicka på **Publicera arbetsytan** för att spara ditt arbete

### <a name="workflow-actions"></a>Arbetsflödesåtgärder

Om du vill lägga till arbetsflödesåtgärder, använd sidan **VendMobileInvoiceHeaderDetails** i Finance and Operations. Ersätt namnet på menyalternativet i URL-adressen precis som tidigare om du vill öppna sidan. Öppna sedan mobildesignern med knappen **Inställningar** (kugghjul). Så här lägger du till arbetsflödesåtgärder på sidan med detaljer. För att de arbetsflödesåtgärder som du tänker utforma för tillgängliga för dig, måste dina tilldelade fakturor ha lämplig status.

#### <a name="record-workflow-actions"></a>Registrera arbetsflödesåtgärder
1.  Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan.
2.  Välj sidan **Fakturadetaljer** som du skapade tidigare och klicka sedan på **Redigera**.
3.  Klicka på **Lägg till åtgärd** på fliken **Åtgärder**.
4.  Ange en rubrik för åtgärden, till exempel **Godkänn**, och en beskrivning, till exempel **Godkänn fakturan**. Observera att rubriken för åtgärden som du anger här blir namnet på åtgärden som visas för användaren i mobilappen.
5.  Klicka på **Klart**.
6.  Klicka på **Välj fält**.
7.  Gå igenom arbetsflödesprocessen på sidan **VendMobileInvoiceHeaderDetails** sidan och slutför åtgärden som du vill registrera. Kontrollera att du skriver kommentarer för arbetsflöde under den här processen så att ett kommentarsfält ingår också i mobila upplevelsen.
8.  När arbetsflödesåtgärden körs, klickar du på **Klart** för att slutföra uppgiften Välj fält.
9.  Klicka på **Klart** för att avsluta redigeringsläge.
10. Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan
11. Klicka på **Publicera arbetsytan** för att spara ditt arbete
12. Upprepa föregående steg för att registrera alla obligatoriska arbetsflödesåtgärder. 

#### <a name="create-a-js-file"></a>Skapa en .js-fil
1. Öppna Anteckningar eller Microsoft Visual Studio och klistra in följande kod. Spara filen som en JS-fil. Koden utför följande:
    - Den döljer de extra arbetsflödesrelaterade kolumner som vi har lade till tidigare på mobillistsidan. Vi har lagt till kolumnerna så att appen har informationen i sammanhang och kan utföra nästa steg.
    - Utifrån vilket arbetsflödessteg som är aktivt, använder den logik för att visa enbart de åtgärderna.

> [!NOTE]
> Namnet på sidorna och andra kontroller i koden måste överensstämma med namnen i arbetsytan.

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

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

2.  Ladda upp kodfilen till arbetsytan genom att välja fliken **Logik**
3.  Klicka på **Klart** för att avsluta redigeringsläge.
4.  Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan
5.  Klicka på **Publicera arbetsytan** för att spara ditt arbete

### <a name="vendor-invoice-attachments"></a>Leverantörsfakturabilagor

1. Klicka på knappen **Inställningar** (kugghjul) i det övre högra hörnet på sidan och klicka sedan på **Mobilapp**
2. Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan.
3. Välj sidan <strong>Fakturadetaljer** som du skapade tidigare och klicka sedan på **Redigera</strong>.
4. Ange alternativet **Dokumenthantering** till **Ja** enligt nedan. **Anmärkning:** Om det inte finns några inga krav på att visa bifogade filer på den mobila enheten kan du lämna detta alternativ inställt på **Nej**, vilket är standardinställningen.
   ![Dokumenthantering](./media/docmanagement-216x300.png)
5. Klicka på **Klart** för att avsluta redigeringsläge.
6. Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan
7. Klicka på **Publicera arbetsytan** för att spara ditt arbete

### <a name="vendor-invoice-line-distributions"></a>Fördelningar av leverantörsfakturarader

Kraven i det här scenariot bekräftar att endast det endast ska finnas fördelningar på radnivå, och att en faktura alltid bara har en rad. Eftersom detta scenario är enkelt, måste användargränssnitt på den mobila enheten vara så enkelt att användaren inte behöver gå ned flera nivåer för att visa fördelningarna. Leverantörsfakturor i Finance and Operations innehåller alternativet att visa alla fördelningar från fakturahuvudet. Denna upplevelse är det vi behöver för det mobila scenariot. Därför använder vi sidan **VendMobileInvoiceAllDistributionTree** för att utforma den här delen av det mobila scenariot. 

> [!NOTE] 
> Att känna till kraven hjälper oss att avgöra vilken sida som ska användas och hur exakt mobila upplevelsen ska optimeras för användaren när vi utformar scenariot. I det andra scenariot utnyttjas en annan sida för att visa fördelningar, eftersom kraven är olika krav för det scenariot.

1.  Ersätt namnet på menyalternativet i URL-adressen precis som du gjorde tidigare. Sidan som visas bör likna illustrationen.
[![Sida med alla distributioner](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)
2.  Öppna mobildesignern med knappen **Inställningar** (kugghjul).
3.  Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan. **Anmärkning:** Du ser att två nya sidor har skapats automatiskt. Dessa sidor skapas i systemet eftersom du aktiverade dokumenthantering i föregående avsnitt. Du kan ignorera dessa nya sidor.
4.  Klicka på **Lägg till sida**.
5.  Ange en sidrubrik som **Visa redovisning**, och en beskrivning, t.ex **Visa redovisning för fakturan**.
6.  Klicka på **Klart**.
7.  På fliken **Fält** klickar du på **Välj fält**. Välj följande fält från fördelningssidan och klicka sedan på **Klart**:
    1.  Belopp
    2.  Valuta
    3.  Huvudbokskonto

    > [!NOTE] 
    > Vi valde inte kolumnen **Beskrivning** i rutnätet för fördelningar, eftersom kraven i det här scenariot har bekräftat att det utökade priset är de enda belopp som det finns fördelningar för. Därför behöver användaren inte något ytterligare fält för att fastställa beloppstypen som fördelningen gäller. Men i nästa scenario **ska** vi använda den här informationen, kraven för det scenariot anger att andra beloppstyper har fördelningar (till exempel moms).
8.  Klicka på **Klart** för att avsluta redigeringsläge.
9.  Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan
10. Klicka på **Publicera arbetsytan** för att spara ditt arbete

> [!NOTE] 
> Mobilsidan **Visa redovisning** är för tillfället inte kopplad till någon av de mobilsidor som vi har utformat hittills. Eftersom användaren ska kunna navigera till sidan **Visa redovisning** sidan från sidan **Fakturadetaljer** på den mobila enheten måste vi tillhandahålla navigering från sidan **Fakturadetaljer** till sidan **Visa redovisning**. Vi fastställer den här navigeringen med hjälp av ytterligare logik via JavaScript.

1.  Öppna den JS-fil som du skapade tidigare och lägg till de rader som markerats i koden nedan. Den här koden gör två saker:
    1.  Det hjälper till att garantera att användaren inte kan bläddra direkt från arbetsytan till sidan **Visa redovisning**.
    2.  Den etablerar en navigeringskontroll från sidan **Fakturadetaljer** till sidan **Visa redovisning**.

> [!NOTE] 
> Namnet på sidorna och andra kontroller i koden måste överensstämma med namnen i arbetsytan.

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

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

2.  Ladda upp kodfilen till arbetsytan genom att välja fliken **Logik** för att skriva över föregående kod
3.  Klicka på **Klart** för att avsluta redigeringsläge.
4.  Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan
5.  Klicka på **Publicera arbetsytan** för att spara ditt arbete

### <a name="validation"></a>Validering

Öppna appen från din mobila enhet och anslut till din Finance and Operations-instans. Kontrollera att du loggar in till företaget där leverantörsfakturor har tilldelats dig för granskning. Du ska kunna utföra följande åtgärder:

-   Se arbetsytan **Mina godkännanden**.
-   Gå nedåt i arbetsytan **Mina godkännanden** och se sidan **Mina leverantörsfakturor**.
-   Gå nedåt i sidan **Mina leverantörsfakturor** och se en lista med fakturor som har tilldelats dig.
-   Gå till en av fakturorna och visa huvud- och raddetaljer för fakturan.
-   På informationssidan visas en länk till bilagor. Använd den här länken för att navigera till listan med bifogade filer och visa de bifogade filerna.
-   På informationssidan visas en länk till sidan **Visa redovisning**. Använd den här länken för att navigera till fördelningssidan och visa fördelningarna.
-   På detaljsidan, klicka på menyn **Åtgärder** längst ned och utför arbetsflödesåtgärder som gäller för arbetsflödessteget.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Utforma ett komplext scenario för fakturagodkännande för Fabrikam
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
<td>Vilka fält från fakturahuvudet vill användaren ha i mobilupplevelsen, och i vilken ordning?</td>
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
<td>Vilka fält från fakturaraderna vill användaren ha i mobilupplevelsen, och i vilken ordning?</td>
<td><ol>
<li>Anskaffningskategori</li>
<li>Kvantitet</li>
<li>Pris per enhet</li>
<li>Nettobelopp för rad</li>
<li>1099-belopp</li>
</ol></td>
</tr>
<tr class="odd">
<td>Hur många rader finns det i en faktura? Använd 80-20-regeln här och optimera för 80 procent.</td>
<td>5</td>
</tr>
<tr class="even">
<td>Vill användarna ha redovisningsfördelningar (fakturakodning) på den mobila enheten vid granskningar?</td>
<td>Ja</td>
</tr>
<tr class="odd">
<td>Hur många redovisningsfördelningar (slutligt pris, moms, avgifter, och så vidare) finns det för en fakturarad? Återigen, använd 80-20-regeln.</td>
<td>Slutligt pris: 2 Moms: 2 Avgifter: 2</td>
</tr>
<tr class="even">
<td>Har fakturorna också redovisningsfördelningar i fakturahuvudet? Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?</td>
<td>Används inte</td>
</tr>
<tr class="odd">
<td>Vill användarna se bilagor för fakturan på enheten?</td>
<td>Ja</td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a>Nästa steg

Följande ändringar kan göras för scenario 1, baserat på kraven för scenario 2. Du kan använda det här avsnittet för att förbättra upplevelsen av mobilappen.

1.  Eftersom flera fakturarader förväntas i scenario 2, hjälper följande ändringar i designen till att optimera användarupplevelsen på den mobila enheten:
    1.  I stället för att visa fakturarader på detaljsidan (som i scenario 1) kan användare välja att visa rader på en separat mobilsida.
    2.  Eftersom flera fakturarader förväntas i det här scenariot, och om sidan **VendMobileInvoiceAllDistributionTree** används för att utforma fördelningssidan för mobil (liksom i scenario 1), kan det vara förvirrande för användaren att korrelera rader till fördelningar. Använd därför sidan **VendMobileInvoiceLineDistributionTree** sidan för att utforma fördelningssidan.
    3.  Vi rekommenderar att fördelningarna visas i samband med en fakturarad i det här scenariot. Kontrollera därför att användaren kan gå nedåt i en rad för att visa fördelningssidan. Använd sidans länkfunktion för att upprätta detaljgranskningen, precis som du gjorde för huvud- och detaljsidorna i scenario 1.

2.  Eftersom flera beloppstyper förväntas för fördelningar i scenario 2 (moms, tillägg och så vidare), kan det vara praktiskt att visa beskrivningen av beloppstypen. (Vi uteslöt den här informationen i scenario 1.)




