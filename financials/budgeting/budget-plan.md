---
title: Budgetplanering
description: "Syftet med den här övningen är en guidad visning av Microsoft Dynamics 365 för att funktionen operationer uppdateringar i området för budgetplaneringsprocessen. Syftet med övningen är att illustrera ett kort konfigureringsexempel av budgetplaneringsmodulen och visa hur budgetplaneringen kan utföras med hjälp av den här konfigurationen.  I den här övningen fokuserar särskilt på följande affärsprocesser eller uppgifter – skapa organisationshierarkin för planering och konfigurera användarsäkerhet – definiera budgetplanscenarier budget planen kolumner, layouter och mallar för Excel - skapa och aktivera planering process - skapa budgetplandokument genom att dra i verkliga värden från redovisning - använda allokeringar för att justera budgetdata planen dokument - Redigera budget planen dokumentet budgetdata i Excel"
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 81b44aa7af3a05ebc28963f406fab98bfbbb340d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning"></a>Budgetplanering

Syftet med den här övningen är en guidad visning av Microsoft Dynamics 365 för att funktionen operationer uppdateringar i området för budgetplaneringsprocessen. Syftet med övningen är att illustrera ett kort konfigureringsexempel av budgetplaneringsmodulen och visa hur budgetplaneringen kan utföras med hjälp av den här konfigurationen.  I den här övningen fokuserar särskilt på följande affärsprocesser eller uppgifter – skapa organisationshierarkin för planering och konfigurera användarsäkerhet – definiera budgetplanscenarier budget planen kolumner, layouter och mallar för Excel - skapa och aktivera planering process - skapa budgetplandokument genom att dra i verkliga värden från redovisning - använda allokeringar för att justera budgetdata planen dokument - Redigera budget planen dokumentet budgetdata i Excel 

<a name="prerequisites"></a>Förutsättningar 
------------------

I den här självstudien måste du komma åt Dynamics 365 för operationer miljö med Contoso demodata och konfigureras som en administratör på instansen. Använd inte i privat läge webbläsaren logga ut från ett annat konto i webbläsaren om det behövs för övningen - och logga in med Dynamics 365 för operationer administratörsbehörighet. När du loggar in på Dynamics 365 för åtgärder du **måste** Markera kryssrutan "Håll mig inloggad". Då skapas en beständig cookie som Excel-appen behöver. Om du loggar in till Dynamics 365 för operationer som använder en annan webbläsare än Internet Explorer sedan uppmanas du att logga in i Excel-programmet. När du klickar på Logga in i Excel-appen visas ett IE-popup-fönster och när du loggar in **MÅSTE** du markera kryssrutan Håll mig inloggad. Om det inte händer något när du klickar på logga in i Excel-appen rensar du cookiecachen i IE.

## <a name="scenario-overview"></a>**Scenario overview**
Julia arbetar som ekonomichef i Contoso Entertainment Systems i Tyskland (DEMF). Eftersom FY2016 närmar sig, måste hon arbeta med företagets budget för det kommande året. Budgetförberedelserna ser ut så här:

1.  Julia använder föregående års faktiska belopp som utgångspunkt för att skapa budgeten.
2.  Baserat på tidigare år skapar hon uppskattningar för tolv månader i det kommande året.
3.  Julia går igenom budgeten med finansdirektören. När hon är klar gör hon de nödvändiga justeringarna för budgetplanen och slutför budgetförberedelserna.

Budgetplaneringsprocessen konfigurationsschema för scenariot ser ut på följande sätt:

![Screenshot1](./media/screenshot1-300x152.png)

Julia används följande Excel-mall för att förbereda budgeten:

[![](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

<a name="exercise-1-configuration"></a>Övning 1: Konfiguration
=========================

## <a name="task-1-create-organizational-hierarchy"></a>**Åtgärd 1: Skapa en organisationshierarki**
Eftersom all budgetbearbetning bara görs på finansavdelningen, skapar Julia en mycket enkel hierarki som bara består av finansavdelningen. 1.1. Navigera till organisationshierarkier (Organisationsadministration &gt;organisationer &gt;organisationshierarkier) och klicka på knappen Nytt

![Screenshot3](./media/screenshot3.png) 

1.2. Namn för organisationshierarkin och klicka på knappen Tilldela syfte

[![Screenshot4](./media/screenshot4.png)](./media/screenshot4.png) 

1.3. Markera Budgetplaneringssyftet och klicka på knappen Lägg till tilldela nyskapade organisationshierarkin: 

[![Screenshot5](./media/screenshot5.png)](./media/screenshot5.png)

1.4. Upprepa steget ovan för säkerhetssyftet. Stäng formuläret när du är klar.

[![Screenshot6](./media/screenshot6.png)](./media/screenshot6.png)

1.5. I formuläret Organisationshierarkier klickar du på knappen Visa. Klicka på Redigera i hierarkidesignern och skapa en hierarki genom att klicka på knappen Infoga.

[![Screenshot7](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. Välj finansavdelningen för budgethierarkin. 

[![Screenshot8](./media/screenshot8.png)](./media/screenshot8.png)

1.7. När du är klar klickar du på knappen Publicera och stäng. Välj 1/1/2015 som giltighetsdatum för hierarkipublicering.

[![Screenshot9](./media/screenshot9.png)](./media/screenshot9.png)

## <a name="task-2-configure-user-security"></a>Uppgift 2: Konfigurera användarsäkerhet
Budgetplaneringen använder särskilda säkerhetsprinciper för att kunna konfigurera åtkomst till budgetplandata. Julia måste ge åtkomst till finansbudgetplaner till sig själv. 2.1. Växla till DEMF juridisk person kontext: [![Screenshot10](./media/screenshot10.png)](./media/screenshot10.png) 2.2. Navigera till budget &gt;inställningar &gt;budgetplanering &gt;budgetplaneringskonfiguration. På fliken Parametrar värdet säkerhet modell baserad på trygghetssystemet [![Screenshot11](./media/screenshot11.png)](./media/screenshot11.png) 2.3. Navigera till systemadministration &gt;användare &gt;användare. Ange administratörsanvändaren (Julia Funderburk) rollen som Budgetchef. [![Screenshot12](./media/screenshot12.png)](./media/screenshot12.png) 2.4. Välj roll och tilldela organisationer på [![Screenshot13](./media/screenshot13.png)](./media/screenshot13.png)2.5. Välj Ge tillgång till vissa organisationer. Välj organisationshierarkin som skapades i det första steget. Välj noden ekonomi och på bevilja med underordnade ***viktigt!*** *– Kontrollera du att du är i DEMF juridiska sammanhang när du utför den här uppgiften som organisationens säkerhet tillämpas per juridisk person*[![Screenshot14](./media/screenshot14.png)](./media/screenshot14.png)

## <a name="task-3-create-scenarios"></a>Uppgift 3: Skapa scenarier
3.1. Navigera till budget&gt;inställningar &gt;budgetplanering &gt;budgetplaneringskonfiguration. På scenariosidan kan du se scenarierna som vi ska använda i den här labbövningen: Utfall föregående år och Budgeterat. *Obs! Du kan skapa nya scenarier för den här övningen och använda dem istället.* [![Screenshot15](./media/screenshot15.png)](./media/screenshot15.png)*notering: Julia inte använder formella godkännandeprocessen för förberedelse av budgeten, vi hoppar arbetsflöden faser och arbetsflödessteg som ställts in i den här övningen och använder befintliga inställningar för automatisk – Godkänn arbetsflöde. Se tillägg för den här arbetsflödeskonfiguration.*

## <a name="task-4-create-budget-plan-columns"></a>Uppgift 4: Skapa budgetplankolumner
Budgetplankolumner är antingen monetära eller kvantitetsbaserade och kan användas i budgetplandokumentlayouten. I vårt exempel måste du skapa en kolumn för utfall föregående år och tolv kolumner som ska representera varje månad i ett budgeterat år. Kolumner kan skapas antingen genom att klicka på knappen Lägg till och sedan ange värden eller med hjälp av Datatabell. I den här övningen ska vi använda datatabellen för att fylla i värdena. 4.1. I budgetering&gt;inställningar &gt;budgetplanering &gt;Budget planering öppna kolumner konfigurationssida. Klicka i det övre högra hörnet i formuläret Office och Välj kolumner (ofiltrerad) [![Screenshot16](./media/screenshot16.png)](./media/screenshot16.png) 4.2. En Excel-arbetsbok öppnas som ska användas för att fylla i värdena. Om du uppmanas aktivera redigering och förtroende för den här appen [![Screenshot18](./media/screenshot18.png)](./media/screenshot18.png)[![Screenshot17](./media/screenshot17.png)](./media/screenshot17.png) 4.3. Vi behöver fler kolumner för att fylla värdena i. Klicka på Design i den högra rutan om du vill lägga till kolumnerna i rutnätet: [![Screenshot19](./media/screenshot19.png)](./media/screenshot19.png) 4.4. Klicka på lite pennknappen bredvid PlanColumns om du vill visa tillgängliga kolumner för att lägga till i rutnätet [![Screenshot20](./media/screenshot20.png)](./media/screenshot20.png) 4.5. Dubbelklicka på alla tillgängliga fält som läggs till i valda fält och klicka på Uppdatera [![Screenshot21](./media/screenshot21.png)](./media/screenshot21.png) 4.6. Lägg till alla kolumner som ska skapas i Excel-tabell. Använd autofyllfunktionen i Excel om du vill lägga till raderna snabbt. Kontrollera att raderna läggs till som en del av registret (när du använder lodrät rullningslist du bör kunna se kolumnrubriker ovanför rutnätet) [![Screenshot22](./media/screenshot22.png)](./media/screenshot22.png) 4.7. Återgå till Dynamics 365 för operationer och uppdatera sidan. Publicerade visas i Dynamics 365 för operationer. [![Screenshot23](./media/screenshot23.png)](./media/screenshot23.png)

## <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Uppgift 5: Skapa mallar och dokumentlayouter för budgetplanen
Layout definierar hur rutnätet med budgetplanens dokumentrader ser ut när du öppnar budgetplansdokumentet. Det går också att ändra layouten för budgetplandokumentet för att se samma uppgifter ur olika vinklar. Nu när Julia har definierat kolumnerna som ska användas i budgetplandokumentet, ska hon skapa en dokumentlayout för budgetplanen. Den ska se ut om Excel-tabellen hon använde när hon skapade budgetdata (se avsnittet Översikt över scenario i övningen) 5.1. I budgetering&gt;inställningar &gt;budgetplanering &gt;Budget planering öppna layouter konfigurationssida. Skapa en ny layout för den månatliga budgetpost:

-   Välj MA+BU-dimensionsuppsättningen om du vill inkludera huvudkonton och affärsenheter i layouten.
-   Ange alla budgetplankolumner som skapades i föregående steg i elementavsnittet. Gör alla utom Utfall föregående år, redigerbara.
-   Klicka på beskrivningsknappen när du vill välja vilka ekonomiska dimensioner ska visa beskrivningar i rutnätet.

[![Screenshot24](./media/screenshot24.png)](./media/screenshot24.png) baserat på budgeten planera Layoutdefinitionen kan vi skapa en Excel-mall som ska användas som ett alternativt sätt att redigera budgetdata. Eftersom Excel-mallen måste matcha budgetplanens layoutdefinition, kan du inte redigera layouten efter genereringen av Excel-mallen. Därför ska uppgiften göras när alla layoutkomponenter har definierats. 5.2. För layout från 5.1. Steg genom att klicka på knappen mall &gt;generera. Bekräfta varningsmeddelandet. Klicka på mall om du vill visa mallen &gt;vy. *Obs: Se till att välja "Spara som" och välj den plats där mallen ska sparas om du vill redigera. Om användaren väljer "Öppna" i dialogrutan utan att spara, behålls inte ändringar som gjorts i filen när filen stängs.* [![Screenshot25](./media/screenshot25.png)](./media/screenshot25.png) 5.3. &lt;Obligatoriskt&gt; ändra Excel-mallen så att den påminner mer användarvänliga – Lägg till totala formler, formatering osv Huvudfälten. Spara ändringarna och skicka filen till budgeten planen layout genom att klicka på Layout &gt;överför [![Screenshot26](./media/screenshot26.png)](./media/screenshot26.png)

## <a name="task-6-create-a-budget-planning-process"></a>Uppgift 6: Skapa en budgetplaneringsprocess
Julia behöver skapa och aktivera en ny budgetplaneringsprocess som kombinerar alla inställningar ovan för att börja registrera budgetplaner. Budgetplaneringsprocessen definiera vilka budgeteringsorganisationer, arbetsflöden, layouter och mallar som ska användas för att skapa budgetplaner. 6.1. Navigera till budget &gt;inställningar &gt;budgetplanering &gt;Budget planeringsprocessen och skapa en ny post.

-   Budgetplaneringsprocess – DEMF budgeterar FY2016
-   Budgetcykel – FY2016
-   Redovisning – DEMF
-   Standardkontostruktur – tillverkningsresultat
-   Organisationshierarki – välj hierarkin som skapades i början av övningen
-   Budget planeringsarbetsflöde – tilldela auto – godkänn arbetsflöde för finansavdelningen
-   I regler och mallar för budgetplaneringsfaser ska det väljas om tilläggning av rader och ändring av rader tillåts och vilken layout som ska användas som standard för varje fas i arbetsflödesbudgeteringsplaneringen

*Obs! Du kan skapa ytterligare dokumentlayouter och göra dem tillgängliga i arbetsflödesfasen för budgetplanering genom att klicka på knappen för alternativa layouter.* [![Screenshot27](./media/screenshot27.png)](./media/screenshot27.png) 6.2. Välj åtgärder &gt;aktivering för att aktivera den här budgetplaneringsarbetsflödet [![Screenshot28](./media/screenshot28.png)](./media/screenshot28.png)

<a name="exercise-2-process-simulation"></a>Övning 2: Processimulering
==============================

## <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Uppgift 7: Generera initiala data för budgetplan från redovisning
7.1. Navigera till budget &gt;Periodisk &gt;generera budgetplan från redovisningen. Fyll i de periodiska processparametrarna och klicka på Generera. [![Screenshot29](./media/screenshot29.png)](./media/screenshot29.png) 7.2. Navigera till budget &gt;Budget planer att hitta en budgetplan som skapas av processen skapa. [![Screenshot30](./media/screenshot30.png)](./media/screenshot30.png) 7.3. Öppna dokumentdetaljer genom att klicka på hyperlänken för dokumentnummer. Budgetplanen visas som definierats i layouten som skapats under den här övningen [![Screenshot31](./media/screenshot31.png)](./media/screenshot31.png)

## <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Uppgift 8: Skapa innevarande års budget baserad på utfall för tidigare år
Allokeringsmetoder kan användas i budgetplaner för att enkelt kopiera information för budgetplaner från ett scenario till ett annat eller fördela dem över perioder eller allokera till dimensioner. Vi använder allokeringar för att skapa innevarande års budget från tidigare års utfall. 8.1. Välj alla rader i budgeten planen dokumentrutnätet och klickar på knappen Fördela budget [![Screenshot32](./media/screenshot32.png)](./media/screenshot32.png) 8.2. Välj allokeringsmetod, Periodnyckel, käll- och scenarier och klicka på fördela 

[![Screenshot33](./media/screenshot33.png)](./media/screenshot33.png)

De faktiska belopp föregående år kommer att kopieras till budgeten för aktuellt år och fördela dem över perioder med försäljning kurva periodnyckeln. 

[![Screenshot34](./media/screenshot34.png)](./media/screenshot34.png)

## <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Uppgift 9: Justera budgetplandokumentet med hjälp av Excel och slutför dokumentet
9.1. Klicka på knappen Öppna dokumentets innehåll i Excel-kalkylblad

[![Screenshot35](./media/screenshot35.png)](./media/screenshot35.png)

9.2. När Excel öppnas justerar du siffrorna i budgetplandokumentet och klickar på knappen Publicera.

[![Screenshot36](./media/screenshot36.png)](./media/screenshot36.png)

9.3. Återgå till budgetplandokument i Dynamics 365 för operationer. Klicka på arbetsflöde &gt;skicka dokumentet godkänns automatiskt

[![Screenshot37](./media/screenshot37.png)](./media/screenshot37.png) 

När arbetsflödet har slutförts ändras budgetplanfas dokument till godkänd. [![Screenshot38](./media/screenshot38.png)](./media/screenshot38.png)

<a name="appendix"></a>Bilaga
========

### <a name="auto-approve-workflow-configuration"></a>Konfiguration för automatiskt godkännande arbetsflöde

A. Budgetering &gt;inställningar &gt;budgetplanering &gt;budgeteringsarbetsflöden skapa ett nytt arbetsflöde med hjälp av Budgetplaneringsarbetsflöden i mallen:

[![Screenshot39](./media/screenshot39.png)](./media/screenshot39.png)

Arbetsflödet innehåller endast en aktivitet – Fasövergångsbudgetplan 

[![Screenshot40](./media/screenshot40.png)](./media/screenshot40.png) 

Spara och aktivera arbetsflödet. 

B. Navigera till budget &gt;inställningar &gt;budgetplanering &gt;budgetplaneringskonfiguration. Fliken Skapa i steg 2 faser – inledande och skickad 

[![Screenshot41](./media/screenshot41.png)](./media/screenshot41.png)

C. Navigera till budget &gt;inställningar &gt;budgetplanering &gt;budgetplaneringskonfiguration. Fliken arbetsflödessteg i arbetsflödet automatiskt koppla – Godkänn skapas i ett steg med faserna grundutbildning och skickad 

[![Screenshot42](./media/screenshot42.png)](./media/screenshot42.png)  


