---
title: Översikt över budgetplanering
description: Det här ämnet beskriver budgetplanering. Det här avsnittet kan hjälpa dig konfigurera budgetplanering och hur du ställer in budgetplaneringsprocessen.
author: panolte
ms.date: 01/11/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "17251"
- intro-internal
ms.assetid: a2e06633-a800-4840-a962-88fed8462104
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 391f62f42e482f79420bbe1bbd4cec4930790229
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982075"
---
# <a name="budget-planning-overview"></a>Översikt över budgetplanering

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver budgetplanering. Det här avsnittet kan hjälpa dig konfigurera budgetplanering och hur du ställer in budgetplaneringsprocessen.

## <a name="overview-of-budget-planning"></a>Översikt över budgetplanering

En organisation kan konfigurera budgetplanering och sedan ställa in budgetplaneringsprocesser för att uppfylla organisationens policyer, procedurer och krav för budgetförberedelse. Genom att förstå de begrepp och den terminologi som används i Microsoft Dynamics 365 Finance blir det enklare om effektivare att genomföra budgetplaneringen i din organisation.

### <a name="key-terms"></a>Nyckeltermer

- **Budgetplaneringsprocesser** – bestämmer hur budgetplaner kan uppdateras, skickas, granskas och godkännas i budgetorganisationshierarkin. En budgetplaneringsprocess är kopplad till en budgetcykel och en organisation via en juridisk person.
- **Budgetplaner** – budgetplaner innehåller budgetdata för en budgetcykel. Du kan ha flera budgetplaner som används för olika ändamål. Du kan till exempel använda budgetplaner för att skapa budgetbelopp för olika organisationsenheter. Du kan också använda dem om du vill göra jämförelser och fatta välgrundade beslut.
- **Budgetplanscenarier** – definierar datakategorier för budgetplanerna. Du definierar bugdetplanscenarier för att stödja monetära klasser och andra måttenhetsklasser, till exempel kvantiteter. Exempel på monetära budgetplanscenarier är Föregående år för avdelningen och Avdelningsförfrågningar. Exempel på budgetplanscenarier som använder kvantiteter är Föregående års supportsamtal och Heltidslön.
- **Budgetplaneringsfaser** – definierar vilka steg som en budgetplan följer från dess startdatum till sista godkännande. Budgetplaneringsfaser arrangeras i budgetplaneringsarbetsflöden.
- **Budgetplaneringsarbetsflöden** – budgetplaneringsarbetsflöden består av och definierar och budgetplaneringsfaser. Budgetplaneringsarbetsflöden är kopplade till budgeteringsarbetsflöden. Budgeteringsarbetsflöden är de automatiserade och manuella processer som flyttar budgetplaner genom budgetplaneringsfaserna.

[![Terminologi för budgetplanering.](./media/budgetplanning-terms-1024x504.png)](./media/budgetplanning-terms.png)

### <a name="typical-tasks"></a>Vanliga uppgifter

Du kan använda budgetplanering för att utföra följande uppgifter:

- Skapa budgetplaner för att definiera de förväntade intäkterna och utgifterna i en budgetcykel.
- Analysera och uppdatera budgetplaner genom att använda olika scenarier.
- Du kan automatiskt skicka budgetplanerna tillsammans med kalkylblad, justeringsdokument och andra bilagor, för granskning och godkännande.
- Konsolidera flera budgetplaner från en lägre nivå i organisationen till en enda överordnad budgetplan på en högre nivå. Du kan också utveckla en enskild budgetplan på en högre nivå i organisationen och fördela budgeten till lägre nivåer.

Integrering av budgetplanering med andra moduler. Därför kan du hämta information från tidigare i budgetar, verkliga utgifter, anläggningstillgångar och personal. Eftersom budgetplanering också är integrerad med Microsoft Excel och Microsoft Word kan du använda dessa verktyg för att arbeta med budgetplaneringsdata. En budgetchef kan till exempel exportera en avdelnings budgetbegäran från ett budgetplanscenario till Excel. Data kan analyseras, uppdateras och mappas i kalkylbladet och sedan publiceras tillbaka till budgetplansraderna.

## <a name="configuring-budget-planning"></a>Konfigurera budgetplanering

Funktioner som introducerades i Dynamics 365 Finance version 10.0.9 (april 2020) innehåller en funktion som förbättrar prestanda när du använder knappen **publicera** för att uppdatera befintliga poster i Excel och sedan publicera dem på nytt till klienten. Den här funktionen påskyndar uppdateringsprocessen och minskar risken för att en uppdatering ska blockeras när flera poster uppdateras samtidigt. Om du vill göra den här funktionen tillgänglig går du till **funktionshantering** och aktivera funktionen **Budgetplanering frågeoptimering för resultat** under **budgetering**. Vi rekommenderar att du aktiverar den här funktionen.

Sidan **Budgetplaneringskonfiguration** innehåller de flesta inställningar som du behöver för att ställa in budgetplanering. I följande avsnitt beskrivs några viktiga faktorer du bör beakta när du konfigurerar budgetplaneringen. När du har slutfört konfigurationen, ställer du in budgetplaneringsprocesserna.

### <a name="budget-planning-schema-optional"></a>Budgetplaneringsschema (valfritt)

Ett valfritt men rekommenderat första steg är att skapa ett schema som innehåller din organisations procedurer för att formulera en budget. Du kan använda en valfri metod när du skapar det här schemat.

Illustrationen visar ett allmänt exempel, där separata budgetplaneringsarbetsflöden skapas för olika nivåer i organisationen. Faser anges i varje arbetsflöde, och specifika scenarier tilldelas varje fas för att innehålla budgetdata. Uppgifter utförs för att flytta data från en fas till nästa. Belopp till exempel fördelas eller aggregeras till olika konton, godkännanden och andra granskningar. I det här exemplet visar kursiv stil ett scenario som inte går att redigera under fas, eller data som är historisk eller godkänts i en tidigare fas och därför inte bör ändras.

[![Allmänt schema för budgetplanering.](./media/budgetplanninggenericschema-300x145.png)](./media/budgetplanninggenericschema.png) 

Följande illustration visar ett exempel där företagets huvudkontor uppskattar basbeloppet för den initiala budgeten och distribuerar dem till försäljningsavdelningarna. Försäljningsavdelningarna beräknar sedan prognoserna och skickar dem till högkvarteret, där budgetchefen sammanställer och justerar prognosen. Slutligen skickar budgetchefen de justerade budgetbeloppen till sin ekonomichef för granskning, slutjustering och godkännande.

[![Exempel på budgetplaneringsschema.](./media/budgetplanningexampleschema-300x145.png)](./media/budgetplanningexampleschema.png)

### <a name="organization-hierarchy-for-budget-planning"></a>Organisationshierarki för budgetplanering

På sidan **Organisationshierarki** kan du välja en organisationshierarki som budgetplaneringshierarki för varje budgetplaneringsprocess. Budgetplaneringshierarkin måste inte matcha den vanliga organisationshierarkin som används för andra ändamål. Eftersom den här hierarkin används för att sammanställa och fördela data, kanske du vill att den ska ha en annan struktur. I exempelschemat är försäljningsavdelningarna under huvudkontorsnivån som innefattar budgetavdelningen och ekonomiavdelningen. Strukturen skiljer sig antagligen från strukturen som används för att hantera driften på försäljningsavdelningarna. Endast en organisationshierarki kan tilldelas varje budgetplaneringsprocess.

Mer information finns i [Organisationer och organisationens hierarkier](../../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md).

### <a name="user-security"></a>Användarsäkerhet

Budgetplanering kan följa en av två säkerhetsmodeller för att definiera användarbehörigheter. Om du vill ange säkerhetsmodellen ställer du in en budgetplaneringsparameter på sidan **Budgetplaneringskonfiguration**.

### <a name="budget-planning-workflows-stages"></a>Arbetsflödesfaser för budgetplanering

Budgetplaneringsarbetsflöden används tillsammans med budgetarbetsflöden för att hantera framtagningen och utvecklandet av budgetplaner.

Ett budgetplaneringsarbetsflöde består av en ordnad uppsättning faser som en budgetplan går igenom. Varje budgetplaneringsarbetsflöde är kopplat till ett budgeteringsarbetsflöde. Budgeteringsarbetsflöden en av de arbetsflödestyperna som används i Dynamics 365 Finance. De dirigerar budgetplanerna, tillsammans med kalkylblad, justeringar och bilagor, genom organisationen för granskning och godkännande.

Du skapar budgeteringsplaneringsarbetsflödet i avsnittet **Arbetsflödefaser** på sidan **Budgetplaneringskonfiguration**. Där kan du välja faserna och budgeteringsarbetsflödet som kan användas, och även ytterligare inställningar.

En bra tips är att skapa ett budgetplaneringsarbetsflöde för varje nivå i en budgeteringshierarki. Du kan sedan tilldela ett budgeteringsarbetsflöde som innehåller element som motsvarar faserna i budgetplaneringsarbetsflödet. I exempelschemat som visades tidigare i den här artikeln, skapades ett budgetplaneringsarbetsflöde för försäljningsavdelningarna, och andra för huvudkontoret. Ett budgeteringsarbetsflöde flyttar budgetplanerna igenom faserna.

Du skapar budgeteringsarbetsflödet för budgetplanering på sidan **Budgeteringsarbetsflöden**. Processen liknar processen för att skapa andra arbetsflöden. Illustrationen nedan visar ett exempel på ett arbetsflöde för administration.

[![Budgetera arbetsflöde för budgetplanering.](./media/budgetingworkflowforbudgetplanning-300x300.png)](./media/budgetingworkflowforbudgetplanning.png) 

Arbetsflödestyperna innehåller följande element:

- Allokering till försäljningsavdelningar och aggregering av deras sändningar
- Granskning av budgetchef
- Godkännande av ekonomichef
- Mellanlagring av övergångar mellan varje steg i budgetplaneringens arbetsflöde

Du tilldelar budgeteringsarbetsflödet till varje budgetplaneringsarbetsflöde i avsnittet **Arbetsflödefaser** på sidan **Budgetplaneringskonfiguration**.

### <a name="parameters-scenarios-and-stages"></a>Parametrar, scenarier och faser

De första inställningarna på sidan **Budgetplaneringskonfiguration** gör att du kan skapa byggstenar för senare konfigurationssteg:

- **Parametrar** – Parametrar definierar säkerheten du vill använda för budgetplaner och de ekonomiska standarddimensionerna som ska användas när användaren borrar nedåt i beloppen i budgetplanscenarierna.
- **Scenarier** – Scenarier omfattar kategorier av data som du vill använda för de här budgetplanerna. Du definierar bugdetplanscenarier för att stödja monetära klasser och andra måttenhetsklasser, till exempel kvantiteter. I en budgetplan representerar scenarier en version av budgetplaneringsdata. Exempel på monetära budgetplanscenarier är Föregående års försäljning och Slutna avtal. Exempel på scenarier som använder kvantiteter är Antal säljsamtal och Heltidslön.
- **Faser** – Faser definierar vilka steg som en budgetplan följer från dess startdatum till sista godkännande. Exempel på budgetplaneringsfaser inkluderar HQ-beräkningar, Vd-granskning och Slutversion.

### <a name="allocation-schedules"></a>Allokeringsscheman

I budgetplaneringen kan du allokera beloppen eller kvantiteterna på budgetplansraderna från ett scenario till ett annat scenario eller t.o.m till samma scenario. Du kan till exempel fördela belopp eller kvantiteter till samma scenario, om du vill använda ändringar av ekonomiska dimensioner eller datumen för beloppen i detta scenario. En allokering kan göras inom en budgetplan eller från en budgetplan till en annan.

Allokeringsplaner fördelar automatiskt budgetplansrader under bearbetning i arbetsflödet. Du kan utföra allokeringar genom att använda någon av följande metoder i listan **Allokeringsmetod**:

- **Allokera över perioder** – Använd en periodallokeringsnyckel när du vill allokera budgetplansrader från källbudgetplanscenariot över perioder i målscenariot.

    > [!NOTE]
    > Obs! Innan du kan allokera över perioder, måste du ställa in periodallokeringsnycklar på sidan **Kategorier för periodallokering**.

- **Fördela på dimensioner** – Budgetplanraderna allokeras från källbudgetplanscenariot över ekonomiska dimensioner i målscenariot.

    > [!NOTE]
    > Innan du kan tilldela till dimensioner, måste du ställa in budgetallokeringsvillkor på sidan **Budgetallokeringsvillkor**.

- **Sammansättning** – Budgetplanraderna sammanställs av källbudgetplansscenariot i associerade budgetplaner till målscenariot i den överordnade budgetplanen.
- **Fördela** – Budgetplanraderna distribueras från källbudgetplansscenariot i den överordnade budgetplanen till målscenariot i de associerade budgetplanerna.
- **Använd allokeringsregler för redovisning** – Budgetplanraderna distribueras från källbudgetplaneringsscenariot till målscenariot baserat på vald allokeringsregel för redovisning.
- **Kopiera från budgetplan** – Du kan välja en annan budgetplan som ska användas som allokeringens källa.

### <a name="stage-allocations"></a>Fasallokeringar

Fasallokeringsscheman och fasallokeringar används för att automatiskt allokera budgetplansrader under arbetsflödesprocessen. När fasallokeringar används kan budgetplanrader i målscenariot kan skapas och ändras utan ingripande av den person som förberett budgetplanen eller granskaren.

När du ställer in en fasallokering kopplar du budgetplaneringsarbetsflödet och fasen med allokeringstidsplanen. Budgetplaneringsarbetsflödet måste vara kopplat till ett budgeteringsarbetsflöde som använder den automatiserade arbetsflödesuppgiften **Fasallokering för budgetplanering**. När arbetsflödet når den angivna fasen, sker allokeringen automatiskt. Denna automatiska uppgift kan användas för att skapa rader för budgetplaner i ett nytt scenario.

I exempelschemat som visas tidigare i den här artikeln utförs en allokering för att överföra belopp från en budgetplan och scenarier i fasen Baslinje för huvudkontor till en annan budgetplan och andra scenarier i fasen Uppskatta för försäljningsavdelningen. Illustrationen visar den relevanta delen av exempelschemat.

[![Fasallokering.](./media/stageallocation-204x300.png)](./media/stageallocation.png) 

Fasallokering I exempelschemat görs också en sammanställning från budgetplanerna och scenarierna i fasen Skickad för säljavdelningen till en överordnad plan i fasen Samlad uppdatering för huvudkontoren. Illustrationen visar den relevanta delen av exempelschemat.

[![Sammansättning.](./media/aggregation-109x300.png)](./media/aggregation.png)

### <a name="priorities"></a>Prioriteter

Du kan även använda budgetplanprioriteter för att definiera kategorier och mål för budgetplanerna som du har ställt in. Du kan också använda prioriteter för att ordna, klassificera och utvärdera flera budgetplaner. Du kan till exempel skapa en budgetplaneringsprioritet för hälsa och säkerhet och sedan utvärdera budgetplaner som tilldelats den prioriteten. Du kan också tilldela budgetplanerna ett nummer om du vill ange en rangordning.

### <a name="columns-and-layouts"></a>Kolumner och layout

I en budgetplan visas budgetsiffror visas i rader och kolumner. Du definierar först kolumnerna, och sedan kan du skapa en layout för att definiera utseendet på kolumnerna.

Välj ett budgetplanscenario att definiera en kolumn. Radbeloppet från det här scenariot visas i budgetplanen. Du kan välja en period för att filtrera beloppet, och du kan även använda filter som baseras på huvudbokskontot.

När du har definierat en layout, välj redovisningsdimension som anges för att skapa budgetplansraderna som du vill visa och välj kolumnerna som layoutelement. Du kan skapa flera layouter så att en budgetplan visar önskade data vid olika faser i budgetplaneringsprocessen.

Förutom kolumner för budgetbelopp kan du definiera kolumner för projektet, förslag till projekt, tillgångar och föreslagna tillgångfält från budgetplanen. Du kan också definiera en kolumn för budgeterade befattningar. Det här alternativet är praktiskt när du måste analysera personalbudgeter.

I exempelschemat kan det vara en bra idé att skapa kolumner för scenarierna "kopiera försäljning", "kontrakt" och "prognos". (Följande bild visar den relevanta delen av schemat.) Du kan sedan bryta ut ett eller alla dessa scenarier till separata kolumner för varje kvartal av räkenskapsåret, så att försäljningschefen kan ange exakt prognosbelopp för varje period.

[![Illustration av avsnitt i schemat för att lägga till kolumner.](./media/columns.png)](./media/columns.png)

Du kan också ange om respektive layoutelement (kolumn) ska gå att redigera och om det finns tillgängligt i alla kalkylbladsmallar som skapas för layouten. För exempelschemat i layouten som används för uppskattningsfasen är prognoskolumnerna redigerbara, men kolumnerna för försäljning och kontrakt är skrivskyddade.

> [!NOTE]
> Som standard kommer du att vara begränsad till 36 kolumner om du inte utökar budgeteringsplaneringen i stegen [Utöka budgetplaneringslayouten](./extending-budget-planning-layout.md).

### <a name="templates"></a>Mallar

I avsnittet **Layouter** på sidan **Budgetplaneringskonfiguration** kan du också skapa, visa och överföra en Excel-mall för varje layout. Dessa mallar är arbetsböckerna som är kopplade till varje budgetplan för att kunna ge ytterligare analys, mappning och datapostkapaciteter.

När en mall skapas, är layouten låst och kan inte redigeras. Detta hjälper garanterar att mallformatet stämmer med budgetplanens layout och innehåller samma uppgifter. När en mall har skapats, kan den visas och redigeras. Du kan till exempel lägga till diagram i mallen eller anpassa dess utseende.

> [!NOTE]
> Mallen ska sparas på en plats som användaren har tillgång till, så att den kan överföras till layouten när redigeringen är klar. På så vis används mallen med budgetplaner som använder layouten.

### <a name="descriptions"></a>Beskrivningar

I avsnittet **Layouter** kan du tilldela beskrivningar för att visa namnet på en ekonomisk dimension som är inkluderad i en layout. En organisation kan till exempel vilja visa namnet på huvudkontot bredvid huvudkonto numret i en budgetplan. Det kan dock vara bra att utelämna namnen på andra ekonomiska dimensioner för att undvika att skärmen blir rörig.

## <a name="setting-up-budget-planning-processes"></a>Ställa in budgetplaneringsprocesser

När du är klar med konfigureringen av budgetplaneringen, kan du ställa in budgetplaneringsprocesser på sidan **Budgetplaneringsprocess**. Budgetplaneringsprocesser är en uppsättning regler som bestämmer hur budgetplaner kan uppdateras, skickas, granskas och godkännas i budgetorganisationshierarkin.

Välj först budgetcykel och redovisning för varje budgetplaneringsprocess. Varje budgetplaneringsprocess är enbart relaterad till en budgetcykel och en huvudbok. Välj sedan budgetorganisationshierarki på snabbfliken **Administrering av budgetplaneringsprocessen** och tilldela ett budgetplaneringsarbetsflöde till alla ansvarsställen i organisationen som visas i rutnätet.

Klicka på **Tilldela arbetsflöde** och välj sedan organisationstyp och budgetplaneringsarbetsflöde när du ska tilldela eller ändra ett budgetplaneringsarbetsflöde till liknande typer av ansvarsområdesställen. Det budgeteringsarbetsflödes-ID som är kopplat till varje budgetplanläggningsarbetsflöde läggs till i rutnätet automatiskt.

När du definierar fasregler och mallar på snabbfliken **Regler och layouter för budgetplaneringsfaser** kan du definiera en annan uppsättning regler och standardlayouter för varje budgetplaneringsfas. Till exempel kan fasen Uppskatta för säljavdelningen tillåta användarna att ändra raderna i en budgetplan men förbjuda användare från att lägga till rader. Sändfasen kan tillåta användare att visa rader, men inte att lägga till eller ändra dem, eftersom arbetet i den fasen redan har slutförts och ändringar måste förhindras. Om du vill välja layouterna som är tillgängliga för budgetplaner klickar du på **Alternativa layouter**.

Du kan även välja budgetplanläggningsprioriter på snabbfliken **Begränsningar för budgetplansprioritet** . Prioriteter kan sedan väljas i budgetplanerna.

Det sista steget är att aktivera budgetplaneringsprocessen genom att använda menyn **åtgärder**. Det går inte att använda en budgetplaneringsprocess förrän den har aktiverats.

Du kan också använda menyn **Åtgärder** för att skapa en ny process att kopiera en process. Den här funktionen är användbar för organisationer som följer samma processflödet för varje budgetcykel och gör få eller inga ändringar.

Ett annat användbart kommando på menyn **Åtgärder** är **Visa budgetprocessens status**. Detta kommando visar grafiskt budgetplanerna i en process, tillsammans med relevanta data, till exempel planernas arbetsflödesstatus, sammanfattningar efter belopp och enhet och enklicksnavigering till själva budgetplanerna.

[![Status för budgetplaneringsprocess.](./media/budgetplanningprocessstatus-300x171.png)](./media/budgetplanningprocessstatus.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
