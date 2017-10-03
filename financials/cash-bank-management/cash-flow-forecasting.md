---
title: "Kassaflödesprognoser"
description: "Det här avsnittet innehåller en översikt över kassaflödeprognosprocess. Dessutom beskrivs hur kassaflödesprognos är integrerad med andra moduler i systemet."
author: saraschi
manager: AnnBe
ms.date: 05/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: sarasch
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 3abf4b151b177095b71d44e9a6c9fd8541eaa64e
ms.openlocfilehash: a8ccd99431178c3cb4e73e7cd199de8e0845d716
ms.contentlocale: sv-se
ms.lasthandoff: 06/14/2017

---

# <a name="cash-flow-forecasting"></a>Kassaflödesprognoser

[!include[banner](../includes/banner.md)]

Du kan använda verktygen för kassaflödesprognostisering för att analysera kommande kassaflöde för att uppskatta företagets framtida behov av kontanter. Om du vill ha en prognos av kassaflödet måste du göra följande:

- Identifiera och ordna alla likviditetskonton. Lividitetskonton är företagets kassakonton eller kassaliknande konton.
- Konfigurera uppförandet av prognoserna för transaktioner som påverkar företagets likviditetskonton.

När du har slutfört uppgifterna kan du beräkna och analysera prognoser över kassaflöde och kommande valutabehov.

## <a name="cash-flow-forecasting-integration"></a>Integrering av kassaflödesprognos

Kassaflödesprognos kan integreras med Redovisning, Leverantörsreskontra, Kundreskontra, Budgetering och lagerhantering. Prognosprocessen använder transaktionsinformation som registreras i systemet och beräkningsprocessen ger prognoser över förväntad kontantpåverkan på varje transaktion. Följande typer av transaktioner tas med när kassaflödet beräknas:

- **Försäljningsorder** – Försäljningsorder som ännu inte fakturerats och som leder till fysiska eller ekonomiska försäljningar.
- **Inköpsorder** – Inköpsorder som ännu inte fakturerats och som leder till fysiska eller ekonomiska inköp.
- **Kundreskontra** – Öppna kundtransaktioner (obetalda fakturor).
- **Leverantörsreskontra** – Öppna leverantörstransaktioner (obetalda fakturor).
- **Redovisningstransaktioner** – transaktioner där det har angetts att en framtida bokföring kommer att inträffa.
- **Budgetregisterposter** – budgetregisterposter som har valts för kassaflödesprognoser.
- **Efterfrågeprognoser** – lagerprognosmodellrader som valts för kassaflödesprognoser.
- **Leveransprognoser** – lagerprognosmodellrader som valts för kassaflödesprognoser.

Även om det inte finns någon direkt integration med projekthantering och redovisning, finns det flera sätt att inkludera projekttransaktioner i kassaflödesprognosen. Bokförda projektfakturor ingår som en del av öppna kundtransaktioner i prognosen. Projekt som initierats av försäljnings- och inköpsorder ingår i prognosen som öppna order när de registreras i systemet. Du kan också överföra projektprognoser till en redovisningsbudgetmodell. Den här redovisningsbudgetmodellen inkluderas sedan i kassaflödesprognosen som en del av budgetregisterposterna.

## <a name="configuration"></a>Inställningar

Om du vill konfigurera kassaflödeprognosprocess använder du sidan **kassaflödesprognosinställningar**. På den här sidan anger du likviditetskonton för att spåra och standardprognosbeteendet för varje område.

### <a name="general-ledger"></a>Huvudbok

Du måste först definiera likviditetskonton du vill spåra för kassaflödesprognos. Normalt är dessa likviditetskonton huvudkonton som är kopplade till bankkonton som ska ta emot och betala kontant. På sidan **kassaflödesprognosinställningar** på fliken **redovisning** väljer du huvudkontona som ska tas med i prognoser. Om ett bankkonto har kopplats till huvudkontot på sidan **bankkonto** visas den i fältet **bankkonto**.

Du kan skapa en beroende kassaflödesprognos för ett huvudkonto som innehåller transaktioner som är direkt relaterade till transaktioner på ett annat huvudkonto. Varje rad som du lägger till i avsnittet **i Beroende konton** skapar ett belopp för kassaflödesprognos på ett beroende huvudkonto. Detta belopp är en procentandel av kassaflödesbeloppen på det primära huvudkontot som du har valt.

Först anger du fältet **huvudkonto** till det primära huvudkontot där transaktioner förväntas inträffa från början. Ange fältet **beroende huvudkonto** till det konto som påverkas av den ursprungliga transaktionen mot det primära huvudkontot. Ange lämpliga värden för de andra fälten på raden. Du kan ändra värdet i fältet **Procent** så att det avspeglar hur det primära huvudkontot påverkar det beroende huvudkontot. För en försäljnings- eller inköpsprognos ska du välja ett värde för **Betalningsvillkor** som är typiskt för de flesta kunderna eller leverantörerna. Ange fältet **bokföringstyp** till den förväntade bokföringstypen som är relaterad till kassaflödesprognosen.

### <a name="accounts-payable"></a>Leverantörsreskontra

Du kan beräkna prognosen för inköp med inställningsalternativen på fliken **Leverantörsreskontra** på sidan **kassaflödesprognosinställningar**. Innan du kan konfigurera kassaflödesprognos för leverantörsreskontra måste du konfigurera betalningsvillkor, leverantörsgrupper och bokföringsprofiler för leverantörer.

I avsnittet **Standardvärden för inköpsprognos** kan du välja standardinköpsbeteenden för kassaflödesprognos. Tre fält bestämmer tiden för kontantpåverkan: **Tiden mellan leveransdatum och fakturadatum**, **betalningsvillkor**, och **Tiden mellan fakturans förfallodatum och betalningsdatum**. Prognosen använder endast standardinställningen för fältet **betalningsvillkor** om ett värde inte anges på transaktionen. Använd ett betalningsvillkor som beskriver de vanligaste antalet dagar för varje del av processen.

Fältet **likviditetskonton för betalningar** anger du det likviditetskonto som oftast används vid betalning. Använd fältet **Procent av beloppet som ska fördelas till kassaflödesprognos** för att ange om procent av beloppen ska användas vid prognoser. Lämna fältet tomt om de fullständiga transaktionsbeloppen ska användas vid prognoser.

Du kan åsidosätta standardinställningen för fältet **Tiden mellan fakturans förfallodatum och betalningsdatum** för befintliga leverantörsgrupper. Prognosen använder standardvärdet från avsnittet **Standardvärden för inköpsprognos** om inte ett annat värde har angetts för den leverantörsgrupp som är kopplad till leverantören på transaktionen. Om du vill åsidosätta standardvärdet markerar du en leverantörsgrupp och anger det nya värdet för fältet **inköpstid**.

Du kan åsidosätta standardinställningen för fältet **Likviditetskonto** för specifika leverantörsbokföringsprofiler. Prognosen använder standardvärdet från avsnittet **Standardvärden för inköpsprognos** om inte ett annat likviditetskonto har angetts för den bokföringsprofilen som är kopplad till leverantören på transaktionen. Välj en bokföringsprofil och ange det likviditetskonto som ska påverkas om du vill åsidosätta standardvärdet.

### <a name="accounts-receivable"></a>Kundreskontra

Du kan beräkna prognosen för försäljning med inställningsalternativen på fliken **Kundreskontra** på sidan **kassaflödesprognosinställningar**. Innan du kan konfigurera kassaflödesprognos för Kundreskontra måste du konfigurera betalningsvillkor, kundgrupper och bokföringsprofiler för kunder.

I avsnittet **Standardvärden för försäljningsprognos** kan du välja standardförsäljningsbeteenden för kassaflödesprognos. Tre fält bestämmer tiden för kontantpåverkan: **Tiden mellan leveransdatum och fakturadatum**, **betalningsvillkor**, och **Tiden mellan fakturans förfallodatum och betalningsdatum**. Prognosen använder endast standardinställningen för fältet **betalningsvillkor** om ett värde inte anges på transaktionen. Använd ett betalningsvillkor som beskriver de vanligaste antalet dagar för varje del av processen. 

Fältet **likviditetskonton för betalningar** anger du det likviditetskonto som oftast används vid betalning. Använd fältet **Procent av beloppet som ska fördelas till kassaflödesprognos** för att ange om procent av beloppen ska användas vid prognoser. Lämna fältet tomt om de fullständiga transaktionsbeloppen ska användas vid prognoser.

Du kan åsidosätta standardinställningen för fältet **Tiden mellan fakturans förfallodatum och betalningsdatum** för befintliga kundgrupper. Prognosen använder standardvärdet från avsnittet **Standardvärden för försäljningsprognos** om inte ett annat värde har angetts för den kundgrupp som är kopplad till kunden på transaktionen. Om du vill åsidosätta standardvärdet markerar du en kundgrupp och anger det nya värdet för fältet **försäljningstid**.

Du kan åsidosätta standardinställningen för fältet **Likviditetskonto** för specifika kundbokföringsprofiler. Prognosen använder standardvärdet från avsnittet **Standardvärden för försäljningsprognos** om inte ett annat likviditetskonto har angetts för den bokföringsprofilen som är kopplad till kunden på transaktionen. Välj en bokföringsprofil och ange det likviditetskonto som ska påverkas om du vill åsidosätta standardvärdet.

### <a name="budgeting"></a>Budgetering

Du kan ta med budgetar som skapas från budgetmodeller i kassaflödesprognoser. På fliken **budget** på sidan **kassaflödesprognosinställningar** markerar du budgetmodellerna som ska inkluderas i prognosen. Som standard ingår nya budgetregisterposter i prognoser när budgetmodellen har aktiverats för kassaflödesprognos. Inkludering i kassaflödesprognos kan åsidosättas på enskilda budgetregisterposter.

### <a name="inventory-management"></a>Lagerhantering

Lagerleverans och efterfråganprognoser kan inkluderas i kassaflödesprognoser. På fliken **Lagerhantering** på sidan **kassaflödesprognosinställningar** markerar du den prognosmodellen som ska inkluderas i kassaflödesprognosen. Inkludering i kassaflödesprognos kan åsidosättas på enskilda prognosrader för tillgång och efterfrågan.

### <a name="calculation"></a>Beräkning

Innan du kan visa kassaflödesprognosanalyser måste du köra kassaflödesberäkningsprocessen. Beräkningsprocessen kommer att projicera framtida kassaflödesefekter av transaktioner som har registrerats.

Beräkna kassaflödesprognosen genom att använda sdian **beräkna kassaflödesprognoser**. Du kan beräkna antingen fullständig kassaflödesprognos eller en stegvis kassaflödesprognos. 

- Om du vill rensa alla kassaflödesprognostransaktioner och omberäkna anger du fältet **Beräkningsmetod för kassaflödesprognos** till **totala**. Vi rekommenderar att du använder den här metoden om du inte har uppdaterat kassaflödesprognoserna på länge. 
- Om du vill uppdatera befintlig information om kassaflöden för nya transaktioner anger du bara fältet **Beräkningsmetod för kassaflödesprognos** till **Ny**. Här visas datumet då kassaflödesberäkningen senast kördes.

Du kan också använda batchbearbetning för din kassaflödesprognos. För att garantera att prognosanalysen uppdateras regelbundet, anger du en återkommande batchprocess för beräkning av kassaflödesprognos.

### <a name="reporting"></a>Rapportering

När du har berälnat kassaflödesprognosen måste du uppdatera den kopplade entitetsinformationen för analytisk rapportering. På sidan **Enhetslagring** anger du mätningen **LedgerCovLiquidityMeasurement aggregera** och klickar sedan på **uppdatera**.

Det finns två arbetsytor som innehåller data med kassaflödesprognoser. En arbetsyta innehåller data för alla företag och den gamla arbetsytan innehåller endast data för det aktuella företaget.

Åtkomst till arbetsytan för alla företag styrs via programbehörigheten **Visa kassaflödet för arbetsytan för alla företag**. Som standard är arbetsytan **Kassaöversikt – alla företag** tillgänglig för följande roller:

- Verkställande direktör
- Ekonomichef
- Ekonomicontroller

Åtkomst till arbetsytan för det aktuella företaget styrs via programbehörigheten **Visa kassaflödet för arbetsytan för aktuellt företag**. Som standard är arbetsytan **Kassaöversikt – aktuellt företag** tillgänglig för följande roller:

- Redovisare
- Redovisningschef
- Redovisningsansvarig
- Leverantörsreskontrachef
- Kundreskontrachef

Arbetsytan **kassaöversikt – alla företag** visar kassaflödesanalys i systemvalutan. Systemvalutan och systemvalutakurstypen som används för analysen definieras på sidan **systemparametrar**. Den här arbetsytan visar en översikt över kassaflödesprognos och bankkontosaldon för alla företag. Ett diagram över kassainflöden och kassautflöden ger en översikt över framtida kassaflödesrörelser och saldon i systemvalutan tillsammans med detaljerad information om de prognostiserade transaktionerna. Du kan också se prognostiserade valutasaldon.

Arbetsytan **kassaöversikt – aktuellt företag** visar kassaflödesprognosanalyser i företagets definierade redovisningsvaluta. Redovisningsvalutan som används för analysen definieras på sidan **redovisning**. Den här arbetsytan visar en översikt över kassaflödesprognos och bankkontosaldon för det aktuella företaget. Ett diagram över kassainflöden och kassautflöden ger en översikt över framtida kassaflödesrörelser och saldon i redovisningsvalutan tillsammans med detaljerad information om de prognostiserade transaktionerna. Du kan också se prognostiserade valutasaldon.

Mer information om kassaflödesprognosanalys finns i kassaöversikt Power BI-innehåll.

Dessutom kan du visa kassaflödesprognoser för specifika konton, order och artiklar på följande sidor:

- **Råbalans**: Välj **kassaflödesprognoser** om du vill visa framtida kassaflöden för det valda huvudkontot.
- **Alla försäljningsorder**: På fliken **faktura** väljer du **kassaflödesprognoser** för att visa prognostiserad kassaeffekten av den valda försäljningsordern.
- **Alla inköpsorder**: På fliken **faktura** väljer du **kassaflödesprognoser** för att visa prognostiserad kassaeffekten av den valda inköpsordern.
- **Leveransprognos**: Välj **kassaflödesprognoser** för att visa framtida kassaflöden som är kopplade till den valda artikelleveransprognosen.
- **Efterfrågeprognos**: Välj **kassaflödesprognoser** för att visa framtida kassaflöden som är kopplade till den valda efterfrågeprognos per artikel.


