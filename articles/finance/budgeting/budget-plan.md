---
title: Budgetplanering
description: Målet med den här övningen är att ge en guidad visning av funktionen Microsoft Dynamics 365 Finance-uppdateringar inom området Budgetplanering. Syftet med övningen är att illustrera ett kort konfigureringsexempel av budgetplaneringsmodulen och visa hur budgetplaneringen kan utföras med hjälp av den här konfigurationen.
author: ShylaThompson
manager: AnnBe
ms.date: 06/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9558013236a728e0fb9691f4edd719fe58d5457
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772155"
---
# <a name="budget-planning"></a>Budgetplanering

[!include [banner](../includes/banner.md)]

Målet med den här övningen är att ge en guidad visning av funktionen Microsoft Dynamics 365 Finance-uppdateringar inom området Budgetplanering. Syftet med övningen är att illustrera ett kort konfigureringsexempel av budgetplaneringsmodulen och visa hur budgetplaneringen kan utföras med hjälp av den här konfigurationen.  I det här övningen fokuseras på följande processer och uppgifter:
- Skapa organisationshierarki för budgetplanering och säkerhetsinställningar för användare
- Definiera budgetplanscenarier, budgetplankolumner, layouter och Excel-mallar
- Skapa och aktivera en budgetplaneringsprocess
- Skapa budgetplandokument genom att dra i verkliga värden från redovisningen
- Använda allokeringar för att justera dokumentdata för budgetplanen
- Redigera dokumentdata för budgetplan i Excel 

<a name="prerequisites"></a>Förutsättningar 
------------------

I den här självstudien måste du ha tillgång till Microsoft Dynamics 365 Finance-miljön med Contoso-demonstrationsdata och vara administratör för instansen. Använd inte i webbläsaren i privat läge i övningen – logga ut från alla andra konton på webbläsaren och logga in med administratörsautentiseringsuppgifter. När du loggar in **MÅSTE** du markera kryssrutan Håll mig inloggad. Då skapas en beständig cookie som Excel-appen behöver. Om du loggar in i appen med en annan webbläsare än IE, uppmanas du att logga in via Excel-appen. När du klickar på Logga in i Excel-appen visas ett IE-popup-fönster och när du loggar in **MÅSTE** du markera kryssrutan Håll mig inloggad. Om det inte händer något när du klickar på logga in i Excel-appen rensar du cookiecachen i IE.

## <a name="scenario-overview"></a>**Scenarioöversikt**
Julia arbetar som ekonomichef i Contoso Entertainment Systems i Tyskland (DEMF). Eftersom FY2016 närmar sig, måste hon arbeta med företagets budget för det kommande året. Budgetförberedelserna ser ut så här:

1.  Julia använder föregående års faktiska belopp som utgångspunkt för att skapa budgeten.
2.  Baserat på tidigare år skapar hon uppskattningar för tolv månader i det kommande året.
3.  Julia går igenom budgeten med finansdirektören. När hon är klar gör hon de nödvändiga justeringarna för budgetplanen och slutför budgetförberedelserna.

Konfigurationsschemat budgetplaneringen för scenariot ser ut på följande sätt:

![Konfigurationsschema för budgetplanering](./media/screenshot1-300x152.png)

Julia använder följande Excel-mall för att förbereda budgeten:

[![Excel-mall](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

## <a name="exercise-1-configuration"></a>Övning 1: Konfiguration

### <a name="task-1-create-organizational-hierarchy"></a>**Uppgift 1: Skapa en organisationshierarki**
Eftersom all budgetbearbetning bara görs på finansavdelningen, skapar Julia en mycket enkel hierarki som bara består av finansavdelningen. 

1.1. Navigera till organisationshierarkier (Organisationsadministration &gt; Organisationer &gt; Organisationshierarkier) och klickar på knappen Nytt

![Organisationshierarkier](./media/screenshot3.png) 

1.2. Ange namnet på organisationshierarkin i namnrutan och klicka på Tilldela syfte.

1.3. Välj Budgetplaneringssyfte, klicka på knappen Lägg till och tilldela den nyligen skapade organisationshierarkin. 

[![Tilldela syfte](./media/screenshot5.png)](./media/screenshot5.png)

1.4. Upprepa steget ovan för säkerhetssyftet. Stäng formuläret när du är klar.

1.5. I formuläret Organisationshierarkier klickar du på knappen Visa. Klicka på Redigera i hierarkidesignern och skapa en hierarki genom att klicka på knappen Infoga.

[![Skriv in](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. Välj finansavdelningen för budgethierarkin. 

[![Finansiellt](./media/screenshot8.png)](./media/screenshot8.png)

1.7. När du är klar klickar du på knappen Publicera och stäng. Välj 1/1/2015 som giltighetsdatum för hierarkipublicering.

[![Gäller från](./media/screenshot9.png)](./media/screenshot9.png)

### <a name="task-2-configure-user-security"></a>Uppgift 2: Konfigurera användarsäkerhet
Budgetplaneringen använder särskilda säkerhetsprinciper för att kunna konfigurera åtkomst till budgetplandata. Julia måste ge åtkomst till finansbudgetplaner till sig själv. 

2.1. Växla till kontexten för juridisk person DEMF. 


2.2. Navigera till Budgetering &gt; Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration. Navigera till fliken Parametrar och ställ in säkerhetsmodellen på Baserat på säkerhetsorganisationer. 

[![Parameters](./media/screenshot11.png)](./media/screenshot11.png) 

2.3. Navigera till Systemadministration &gt; Användare &gt; Användare. Ange administratörsanvändaren (Julia Funderburk) rollen som Budgetchef. 

[![Budgetchef](./media/screenshot12.png)](./media/screenshot12.png) 

2.4. Välj användarroll och klicka på Tilldela organisationer. 

[![Tilldela organisationer](./media/screenshot13.png)](./media/screenshot13.png)

2.5. Välj Ge tillgång till vissa organisationer. Välj organisationshierarkin som skapades i det första steget. Välj finansnoden och klicka på knappen Bevilja med underordnad knapp. 

***Viktigt!*** *Se till att du är i kontexten för den juridiska personen DEMF när du genomför den här uppgiften, eftersom organisationssäkerhet tilldelas efter juridisk person* 

### <a name="task-3-create-scenarios"></a>Uppgift 3: Skapa scenarier
3.1. Navigera till Budgetering&gt;Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration. På scenariosidan kan du se scenarierna som vi ska använda i den här labbövningen: Utfall föregående år och Budgeterat. 

*Obs! Du kan skapa nya scenarier för den här övningen och använda dem istället.* 

[![Nya scenarier](./media/screenshot15.png)](./media/screenshot15.png) 

*Obs! Eftersom Julia inte använder den formella godkännandeprocessen för budgetförberedelser hoppar vi över inställningsstegen för arbetsflöden, faser och arbetsflödesfaser i övningen. I stället använder vi den befintliga inställningen för automatiskt godkända arbetsflöden. Se appendix för denna arbetsflödeskonfiguration.*

### <a name="task-4-create-budget-plan-columns"></a>Uppgift 4: Skapa budgetplankolumner
Budgetplankolumner är antingen monetära eller kvantitetsbaserade och kan användas i budgetplandokumentlayouten. I vårt exempel måste du skapa en kolumn för utfall föregående år och tolv kolumner som ska representera varje månad i ett budgeterat år. Kolumner kan skapas antingen genom att klicka på knappen Lägg till och sedan ange värden eller med hjälp av Datatabell. I den här övningen ska vi använda datatabellen för att fylla i värdena. 

4.1. Öppna sidan Kolumner under Budgetering&gt;Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration. Klicka på Office-knappen överst till höger i formuläret och välj Kolumner (ofiltrerade). 

[![Ofiltrerade kolumner](./media/screenshot16.png)](./media/screenshot16.png) 

4.2. Systemet öppnar en Excel-arbetsbok som ska användas för att fylla i värdena. Om du uppmanas aktiverar du redigering och förtroende för den här appen. 

4.3. Vi behöver fler kolumner att fylla i värdena i. Klicka på Design i höger sidfönster om du vill lägga till kolumnerna i rutnätet. 

[![Design](./media/screenshot19.png)](./media/screenshot19.png) 

4.4. Klicka på den lilla pennknappen bredvid PlanColumns för att se kolumner som går att lägga till i rutnätet. 

[![Redigera](./media/screenshot20.png)](./media/screenshot20.png) 

4.5. Dubbelklicka på varje tillgängligt fält för att lägga till dem i rutan för valda fält och klicka på Uppdatera. 

4.6. Lägg till alla kolumner som ska skapas i Excel-tabell. Använd autofyllfunktionen i Excel om du vill lägga till raderna snabbt. Kontrollera att raderna läggs till som en del av tabellen (när du rullar vertikalt kan du se kolumnrubrikerna överst i rutnätet). 

4.7. Gå tillbaka till appen och uppdatera sidan. Publicerade värden visas. 

[![Förnya](./media/screenshot23.png)](./media/screenshot23.png)

### <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Uppgift 5: Skapa mallar och dokumentlayouter för budgetplanen
Layout definierar hur rutnätet med budgetplanens dokumentrader ser ut när du öppnar budgetplansdokumentet. Det går också att ändra layouten för budgetplandokumentet för att se samma uppgifter ur olika vinklar. Nu när Julia har definierat kolumnerna som ska användas i budgetplandokumentet, ska hon skapa en dokumentlayout för budgetplanen. Den ska se ut om Excel-tabellen hon använde när hon skapade budgetdata (se avsnittet Översikt över scenario i övningen) 

5.1. Öppna sidan Layouter i Budgetering&gt;Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration. Skapa en ny layout för den månatliga budgetpost:

-   Välj MA+BU-dimensionsuppsättningen om du vill inkludera huvudkonton och affärsenheter i layouten.
-   Ange alla budgetplankolumner som skapades i föregående steg i elementavsnittet. Gör alla utom Utfall föregående år, redigerbara.
-   Klicka på beskrivningsknappen när du vill välja vilka ekonomiska dimensioner ska visa beskrivningar i rutnätet.

[![Beskrivningar](./media/screenshot24.png)](./media/screenshot24.png) 

Baserat på layoutdefinitionen av budgetplanen kan vi skapa en Excel-mall som ska användas som en alternativ väg för att redigera budgetdata. Eftersom Excel-mallen måste matcha budgetplanens layoutdefinition, kan du inte redigera layouten efter genereringen av Excel-mallen. Därför ska uppgiften göras när alla layoutkomponenter har definierats. 

5.2. För layout skapad i steg 5.1. , klicka på knappen Mall &gt; Skapa. Bekräfta varningsmeddelandet. Visa mallen genom att klicka på Mall &gt; Visa. 

*Obs: Se till att välja "Spara som" och välj den plats där mallen ska sparas, om du vill redigera. Om användaren väljer "Öppna" i dialogrutan utan att spara, behålls inte ändringar som gjorts i filen när filen stängs.* 
[![Mallvy](./media/screenshot25.png)](./media/screenshot25.png) 

5.3. &lt;Valfritt steg&gt; Ändra Excel-mallen för att göra den mer användarvänlig – lägg till formler för summor, rubrikfält, formatering osv. Spara ändringarna och skicka filen till budgetplanlayouten genom att klicka på Layout &gt;Överför. 


### <a name="task-6-create-a-budget-planning-process"></a>Uppgift 6: Skapa en budgetplaneringsprocess
Julia behöver skapa och aktivera en ny budgetplaneringsprocess som kombinerar alla inställningar ovan för att börja registrera budgetplaner. Budgetplaneringsprocessen definiera vilka budgeteringsorganisationer, arbetsflöden, layouter och mallar som ska användas för att skapa budgetplaner. 

6.1. Navigera till Budgetering &gt; Inställningar &gt; Budgetplanering &gt; Budgetplaneringsprocess och skapa en ny post.

-   Budgetplaneringsprocess – DEMF budgeterar FY2016
-   Budgetcykel – FY2016
-   Redovisning – DEMF
-   Standardkontostruktur – tillverkningsresultat
-   Organisationshierarki – välj hierarkin som skapades i början av övningen
-   Budget planeringsarbetsflöde – tilldela auto – godkänn arbetsflöde för finansavdelningen
-   I regler och mallar för budgetplaneringsfaser ska det väljas om tilläggning av rader och ändring av rader tillåts och vilken layout som ska användas som standard för varje fas i arbetsflödesbudgeteringsplaneringen

*Obs! Du kan skapa ytterligare dokumentlayouter och göra dem tillgängliga i arbetsflödesfasen för budgetplanering genom att klicka på knappen för alternativa layouter.* 

[![Alternativa layouter](./media/screenshot27.png)](./media/screenshot27.png) 

6.2. Välj Åtgärder &gt; Aktivera för att aktivera budgetplaneringsarbetsflödet. 

[![Aktivera](./media/screenshot28.png)](./media/screenshot28.png)

## <a name="exercise-2-process-simulation"></a>Övning 2: Processimulering

### <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Uppgift 7: Skapa initiala data för budgetplan från redovisning
7.1. Navigera till Budgetering &gt; Periodisk &gt; Skapa budgetplan från huvudbok. Fyll i de periodiska processparametrarna och klicka på Skapa. 

7.2. Navigera till Budgetering &gt; Budgetplaner för att hitta en budgetplan som har skapats av genereringsprocessen. 

[![Budgetplan](./media/screenshot30.png)](./media/screenshot30.png) 

7.3. Öppna dokumentdetaljer genom att klicka på hyperlänken för dokumentnummer. Budgetplanen visas enligt definitionen i layouten som skapades i den här övningen. 

[![Budgetplandokument](./media/screenshot31.png)](./media/screenshot31.png)

### <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Uppgift 8: Skapa innevarande års budget baserad på utfall för tidigare år
Allokeringsmetoder kan användas i budgetplaner för att enkelt kopiera information för budgetplaner från ett scenario till ett annat eller fördela dem över perioder eller allokera till dimensioner. Vi använder allokeringar för att skapa innevarande års budget från tidigare års utfall. 

8.1. Välj alla rader i rutnätet i budgetplandokumentet och klicka på knappen för allokering av budget. 

[![Alla rader](./media/screenshot32.png)](./media/screenshot32.png) 

8.2. Välj allokeringsmetod, Periodnyckel, käll- och målscenarier och klicka på Allokera. 

[![Allokera](./media/screenshot33.png)](./media/screenshot33.png)

De faktiska beloppen för föregående kopieras till budgeten för aktuellt år och fördelas över perioder via försäljningskurvans periodnyckel. 

[![Försäljningskurva](./media/screenshot34.png)](./media/screenshot34.png)

### <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Uppgift 9: Justera budgetplandokumentet med hjälp av Excel och slutför dokumentet
9.1. Klicka på knappen för kalkylbladet för att öppna dokumentinnehållet i Excel.

9.2. När Excel öppnas justerar du siffrorna i budgetplandokumentet och klickar på knappen Publicera.

9.3. Gå tillbaka till budgetplandokument. Klicka på Arbetsflöde &gt; Skicka för att godkänna dokumentet automatiskt.

[![Automatiskt godkänd](./media/screenshot37.png)](./media/screenshot37.png) 

När arbetsflödet har slutförts, ändras steget för budgetplandokument till Godkänt. [![Godkänd](./media/screenshot38.png)](./media/screenshot38.png)

## <a name="appendix"></a>Bilaga

### <a name="auto-approve-workflow-configuration"></a>Konfiguration för automatiskt godkännande arbetsflöde

A. Budgetering &gt; inställningar &gt; budgetplanering &gt; budgetarbetsflöden. Skapa ett nytt arbetsflöde med hjälp av mallen arbetsflöden för budgetplanering:

[![Skapa ett nytt arbetsflöde](./media/screenshot39.png)](./media/screenshot39.png)

Arbetsflödet innehåller endast en aktivitet – Fasövergångsbudgetplan. 

[![Fasövergångsbudgetplan](./media/screenshot40.png)](./media/screenshot40.png) 

Spara och aktivera arbetsflödet. 

B. Navigera till Budgetering &gt; Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration. Skapa 2 faser i fliken Faser – Inledande och Skickad. 

[![Ursprungliga och överförda](./media/screenshot41.png)](./media/screenshot41.png)

C. Navigera till Budgetering &gt; Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration. I fliken Arbetsflödesfaser kopplar du arbetsflödet Automatiskt godkänd som skapades i steg A till faserna Inledande och Skickad.

[![Budgetering och budgetplanering](./media/screenshot42.png)](./media/screenshot42.png)  



