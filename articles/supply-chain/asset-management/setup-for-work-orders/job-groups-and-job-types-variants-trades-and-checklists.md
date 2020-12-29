---
title: Kategorier av underhållsjobbtyp och underhållsjobbtyper, varianter av underhållsjobb, yrkesgrenar för underhållsjobb och underhållschecklistor
description: I detta avsnitt beskrivs kategorier av underhållsjobbtyp och underhållsjobbtyper, varianter av underhållsjobb, yrkesgrenar för underhållsjobb och underhållschecklistor i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetJobTypeDefaultForecast, EntAssetJobTrade, EntAssetJobTypeDefaultCopy, EntAssetChecklistVariableValueLookup, EntAssetChecklistTemplateCreate, EntAssetJobVariant, EntAssetJobTypeDefaultReference, EntAssetJobTypeDefaultChecklist, EntAssetJobTypeDefault, EntAssetJobType, EntAssetJobTypeDefaultChecklistCopy, EntAssetChecklistTemplate, EntAssetJobTypeDefaultDescription, EntAssetJobTypeLookup, EntAssetJobTypeDefaultToolCopy, EntAssetJobTypePreviewPart, EntAssetJobTypeDefaultTool, EntAssetJobTypeDefaultForecastCopy, EntAssetChecklistTemplateLookup, EntAssetJobGroup, EntAssetChecklistVariable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8bf7c53a6150a2beeca5c6e9b5ab4ea98584158d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437650"
---
# <a name="maintenance-job-type-categories-and-maintenance-job-types-maintenance-job-type-variants-maintenance-job-trades-and-maintenance-checklists"></a>Kategorier av underhållsjobbtyp och underhållsjobbtyper, varianter av underhållsjobb, yrkesgrenar för underhållsjobb och underhållschecklistor

[!include [banner](../../includes/banner.md)]

 

En tillgångstyp är kopplad till varje tillgång. Tillgångstyper definierar jobbtyperna för underhåll (och därmed underhållsjobben) som kan utföras på tillgångar. När du skapar en arbetsorder måste du välja en underhållsjobbtyp. Du kan bara välja de typer av underhållsjobb som är relaterade till inställningarna för den tillgångstyp som används för tillgången.

En grafisk översikt över till gångar och underhållsjobbtyper, och deras koppling till arbetsorder, finns i [Funktionsplatser och tillgångar](../overview/functional-locations-and-objects.md).

Varianter av typer av underhållsjobb kan ställas in för en underhållsjobbtyp. Varianter av underhållsjobbtyper definierar varianter av en jobbtyp, t.ex. storlekar (liten, medelstor eller stor), perioder (veckovis, varannan vecka, en månad eller tre månader) och konfigurationer (låg standard, flexibel eller hög prestanda).

Yrkesgrenar för underhållsjobb innehåller information om professionella yrken, t.ex. mekaniska, elektriska och hydrauliska yrkesgrenar. Kompetenskrav kan ställas in för en yrkesgren för underhållsjobb. Alla yrkesgrenar för underhållsjobb kan användas i relation till alla jobbtyper för underhåll. Val av variant av underhållsjobbtyp och/eller yrkesgren för underhållsjobb är valfritt på en arbetsorder.

För varje underhållsjobbtyp kan varianter av inställningen av underhållsjobbtypen skapas. Om du till exempel har en underhållsjobbtyp med namnet **Service**, kan du skapa följande varianter för underhållsjobbtypen: **Lastbilar 30 000 km**, **Bilar 30 000 km** och **Skåpbilar 30 000 km**.

Kategorier av underhållsjobbtyper används för att samla in en grupp med underhållsjobbtyper i översiktssyfte. Exempel på kategorier av underhållsjobbtyper kan vara **Kalibrering**, **Inspektion**, **Översyn** och **Instrumentering**.

Mallar för underhållschecklista och variabler för underhållschecklista används för att ställa in underhållschecklistor. Underhållschecklistor ställs in på underhållsjobbtyper och används på arbetsorder.

Först ställer du in kategorier av underhållsjobbtyp, varianterna av underhållsjobbtyp och yrkesgrenar för underhållsjobb Därefter skapar du underhållsjobbtyper. Till slut, på sidan **Standardvärden för underhållsjobbtyp** skapar du alla varianter av underhållsjobbtyper som krävs för din utrustning. På den sidan kan du också ställa in prognoser, checklistor för underhåll och verktyg för en kombination av underhållsjobbtyper.

> [!NOTE]
> En underhållsjobbtyp kan bara vara relaterad till en kategori av underhållsjobbtyp.

## <a name="create-a-maintenance-job-type-category"></a>Skapa en kategori av underhållsjobbtyp

1. Välj **Tillgångshantering** \> **Inställning** \> **Jobb** \> **Kategorier av underhållsjobbtyp**.
2. Välj **Ny**.
3. I fältet **Kategori av underhållsjobbtyp** anger du ett ID för kategorin av underhållsjobbtypen.
4. Ange sedan ett namn i fältet **Namn**.

    När du har relaterat kategorier av underhållsjobbtyper till underhållsjobbtyper visar fältet **Jobbtyper** antalet underhållsjobbtyper som är relaterade till den här kategorin för underhållsjobbtyp.

![Sidan kategori för typ av underhållsjobb](media/01-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type-variant"></a>Skapa en variant av underhållsjobbtyp

1. Välj **Tillgångshantering** \> **Inställning** \> **Jobb** \> **Varianter av underhållsjobbtyp**.
2. Välj **Ny**.
3. I fältet **Variant av underhållsjobbtyp** anger du ett ID för varianten av underhållsjobbtypen.
4. Ange en beskrivning i fältet **beskrivning**.
5. På snabbfliken **Underhållsjobbtyper** väljer du **Lägg till** om du vill lägga till en underhållsjobbtyp.
6. Välj underhållsjobbtypen i fältet **Underhållsjobbtyp**.
7. Upprepa steg 5 till och med 6 om du vill lägga till fler underhållsjobbtyper i varianten av underhållsjobbtypen.

    På snabbfliken **Detaljer** visar fältet **Jobbtyper** antalet underhållsjobbtyper som har lagts till i denna variant av underhållsjobbtyp.

![Sidan varianter för typ av underhållsjobb](media/02-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-trade"></a>Skapa en yrkesgren för underhållsjobb

1. Välj **Tillgångshantering** \> **Inställning** \> **Jobb** \> **Yrkesgren för underhållsjobb**.
2. Välj **Ny**.
3. Ange ID för yrkesgren för underhållsjobb i fältet **Yrkesgren**.
4. Ange en beskrivning i fältet **beskrivning**.
5. På snabbfliken **Kompetenser** väljer **Lägg till** om du vill lägga till en ny kompetens som ska relateras till yrkesgrenen för underhållsjobb.
6. Välj kompetensen i fältet **Kompetens**.
7. Välj kompetensnivån i fältet **Nivå**.
8. Upprepa steg 5 till 7 om du vill lägga till fler kompetenser i yrkesgrenen för underhållsjobb.

    På snabbfliken **Detaljer** visar fältet **Kompetenser** antalet kompetenser som har lagts till i denna yrkesgren för underhållsjobb.

9. På snabbfliken **Intyg** väljer du **Lägg till** om du vill lägga till ett intyg i yrkesgrenen för underhållsjobb.
10. Välj intyget i fältet **Intygstyp**.
11. Upprepa steg 9 till 10 om du vill lägga till fler intyg i yrkesgrenen för underhållsjobb.

    På snabbfliken **Detaljer** visar fältet **Intyg** antalet intyg som har lagts till i denna yrkesgren för underhållsjobb.

![Sidan yrkesgren för underhållsjobb](media/03-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-variable"></a>Skapa en variabel för underhållschecklista

När du skapar rader för underhållschecklista i standardtypen av underhållsjobb måste du välja en typ av underhållschecklista. **Variabel** är en typ av underhållschecklista. Den används för att definiera ett möjligt resultat i ett intervall på en rad för underhållschecklista som är relaterad till en arbetsorderrad. Med en variabel kan du skapa en uppsättning fördefinierade resultat utan att behöva göra exakt mätning.

**Exempel 1:** Du kan mäta oljenivån genom att definiera tre värden: **För hög nivå**, **För låg nivå** och **Nivå inom intervall**. För varje värde anger du om värdet för resultatet är **Godkänt**, **Underkänt** eller **Inget**.

**Exempel 2:** Du gör en visuell inspektion av en utrustning för att bedöma slitage.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Underhållschecklista** \> **Variabler för underhållschecklista**.
2. Välj **Ny**.
3. I fältet **Variabel**, ange ett ID för variabeln för underhållschecklista.
4. Ange sedan ett namn i fältet **Namn**.
5. På snabbfliken **Allmänt** väljer du **Lägg till** för att lägga till en rad för en variabel.

    Ett sekventiellt nummer anges automatiskt i fältet **Radnummer**. När du har lagt till alla rader kan du ändra radnumren efter behov. När du markerar raden och sedan trycker på **Nedpil** anges nästa nummer i serien automatiskt på nästa rad.

6. I fältet **Värde** anger du en relaterad beskrivning.
7. Välj ett resultat för raden i fältet **Resultat**.

![Sidan variabel för underhållschecklista](media/04-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-template"></a>Skapa en mall för underhållschecklista

Mallar för underhållschecklistor kan användas som en gemensam uppsättning uppgifter som en arbetare måste utföra för att slutföra en arbetsorder korrekt. Mallarna refereras från raderna för underhållschecklistor i standardtypen av underhållsjobb. Det går att referera till mallar över flera rader för standardtyper av underhållsjobb. Därför kan du enkelt återanvända en uppsättning vanliga uppgifter på underhållslistor. Exempel på mallar för checklista innehåller allmänna säkerhetsinstruktioner och en lista över artiklar och villkor som måste kontrolleras på en specifik pump eller liknande modeller av ett transportband.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Underhållschecklista** \> **Mallar för underhållschecklista**.
2. Välj **Ny**.

    Ett mall-ID anges automatiskt i fältet **Mall för underhållschecklista**.

3. Ange ett namn för mallen för underhållschecklista i fältet **Namn**.
4. På snabbfliken **Rader för underhållschecklista** väljer du **Lägg till** om du vill lägga till en mallrad.

    Ett sekventiellt nummer anges automatiskt i fältet **Radnummer**. När du har lagt till alla rader kan du ändra radnumren efter behov. När du markerar raden och sedan trycker på **Nedpil** anges nästa nummer i serien automatiskt på nästa rad.

5. Välj en typ för raden för underhållschecklista i fältet **Typ**. För varje typ av underhållschecklista visar snabbfliken **Radinformation** relaterade fält. Följande värden finns:

    - **Text** – Raden innehåller text som beskriver vad du ska göra. Använd den här typen av underhållschecklista om du vill att en arbetare ska kontrollera eller inspektera något, men du inte förväntar dig ett specifikt (mätbart) resultat. När du har valt den här typen anger du ett namn eller en rubrik i fältet **Namn**. I fältet **Instruktioner** anger du en beskrivning av vad som måste göras. Om steget är obligatoriskt för underhållschecklistan ställer du in alternativet **Obligatoriskt** till **Ja**.
    - **Sidhuvu** – Raden används som en rubrik för att gruppera de rader för underhållschecklista som visas under den. Den här typen är användbar om du har flera rader för underhållschecklista som kan delas in i specifika områden. Rubriker ger en översikt för arbetaren som kommer att genomföra en underhållschecklista som har många rader. När du har valt den här typen anger du ett beskrivande namn i fältet **Namn**.
    - **Mall** – Raden används för att referera till en befintlig mall. När du har valt den här typen anger du ett namn för mallen i fältet **Namn**. I fältet **Mall** väljer du mallen.
    - **Variabel** – Raden används för att definiera ett möjligt resultat i ett intervall. Mer information om hur du ställer in variabler för underhållschecklistor finns i [Skapa en variabel för underhållschecklista](#create-a-maintenance-checklist-variable). När du har valt den här typen anger du ett beskrivande namn för variabeln i fältet **Namn**. Välj variabeln i fältet **Variabel**. I fältet **Instruktioner** anger du en beskrivning av vad som måste göras. Om steget är obligatoriskt för underhållschecklistan ställer du in alternativet **Obligatoriskt** till **Ja**.
    - **Mått** – Raden används för att registrera ett specifikt mått. Du kan ställa in måtten som ska relateras till en fördefinierad räknare. När du har valt den här typen anger du ett namn för mallen i fältet **Namn**. Om steget är obligatoriskt för underhållschecklistan ställer du in alternativet **Obligatoriskt** till **Ja**. Om du vill använda måttraden som en räknarregistrering väljer du räknaren i fältet **Räknare**. Det relaterade fältet **Enhet** uppdateras då automatiskt. Om du har valt en räknare väljer du uppdateringsmetoden i fältet **Värde**. I fälten **Min. värde** och **Max. värde** anger du det tillåtna värdeintervallet. I fältet **Instruktioner** anger du en beskrivning av vad som måste göras.

        > [!NOTE]
        > Alla rader i typen **Mått** som inte har någon inställning för räknare behandlas som en oberoende mätningsregistrering som det inte finns någon automatisk uppföljning för i Tillgångshantering. På samma sätt behandlas uppgiften i underhållschecklistan som ett oberoende mått om den valda räknartypen inte finns på tillgången som hör till arbetsordern. Räknarvärdet kan ändras flera gånger. Det bokförs inte förrän [arbetsorderns livscykeltillstånd](work-order-lifecycle-states.md) ändras till ett tillstånd där alternativet **Bearbeta underhållschecklista** har värdet **Ja**.

    På snabbfliken **Detaljer** visar fältet **Kontroller** det totala antalet checklisterader i mallen. Numret inkluderar de kapslade raderna i en befintlig mall som du har refererat till i mallen.

![Sidan mallar för underhållschecklista](media/05-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type"></a>Skapa en underhållsjobbtyp

1. Välj **Tillgångshantering** \> **Inställning** \> **Jobb** \> **Underhållsjobbtyper**.
2. Välj **Ny**.
3. I fältet **Underhållsjobbtyp** anger du ett ID för underhållsjobbtypen.
4. Ange sedan ett namn i fältet **Namn**.

    På snabbfliken **Detaljer** visas en översikt över antalet varianter av underhållsjobbtyper, kompetenser, intyg, efterföljande jobb och tillgångstyper som har skapats för den här underhållsjobbtypen. I fältet **Inställningsrader** visas antalet standardrader för underhållsjobbtyp som har ställts in för den här underhållsjobbtypen. I fältet **Tillgångar** visas antalet aktiva tillgångar som för närvarande använder underhållsjobbtypen.

5. På snabbfliken **Allmänt** i fältet **Kategori av underhållsjobbtyp** väljer du en kategori av underhållsjobbtyp.
6. Ställ in alternativet **Aktiviteter för underhållsstopp** på **Ja** om underhållsjobbtypen kräver ett underhållsstopp av utrustningen innan jobbet kan utföras.
7. Ange en beskrivning av underhållsjobbtypen i på snabbfliken **Beskrivning**.
8. På snabbfliken **Varianter av underhållsjobbtyp** kan du lägga till varianter för underhållsjobbtypen.
9. På snabbflikarna **Obligatorisk kompetens** och **Obligatoriska intyg** kan du lägga till kompetens- och intygskrav för underhållsjobbtypen.
10. Om en viss typ av underhållsjobb måste utföras härnäst lägger du till den på snabbfliken **Efterföljande jobb**. Du kan också ställa in en variant av och yrkesgren för underhållsjobbtyp som hör till underhållsjobbtypen. Om det efterföljande jobbet ska börja ett visst antal dagar före eller efter att jobbet som använder den här underhållsjobbtypen har startat, anger du antalet dagar i fältet **Fördröj med antal dagar**. Positiva tal representerar dagar efter starten av det relaterade jobbet, och negativa tal representerar dagar före den schemalagda starten av det relaterade jobbet. Om du till exempel anger **5** kommer det efterföljande jobbet att starta fem dagar efter att jobbet som är relaterat till underhållsjobbtypen har startats. Om du anger **-3** kommer det efterföljande jobbet att starta tre dagar innan den schemalagda starten för jobbet som är relaterat till underhållsjobbtypen.

    > [!NOTE]
    > Om du lägger till fler än en rad för underhållsjobbtyp, visar ordningsföljden för raderna den ordning som de ska utföras i. Sekvensen börjar högst upp i listan.

11. På snabbfliken **Anläggningstyper** kan du lägga till tillgångstyper till underhållsjobbtypen.

![Sidan typer för underhållsjobb](media/06-setup-for-work-orders.png)

## <a name="create-maintenance-job-type-default-lines-and-related-forecasts-maintenance-checklists-tools-description-and-attachments"></a>Skapa standardrader för underhållsjobbtyp och relaterade prognoser, underhållschecklistor, verktyg, beskrivningar och bilagor

1. Välj **Tillgångshantering** \> **Inställning** \> **Jobb** \> **Standardvärden för underhållsjobbtyp**.

    –eller–

    Välj **Tillgångshantering** \> **Inställning** \> **Jobb** \> **Underhållsjobbtyper**, välj en underhållsjobbtyp och välj sedan **Standardvärden för underhållsjobbtyp**.

2. Välj **Ny**.
3. I fälten **Funktionsplats**, **Tillgångstyp**, **Tillverkare**, **Modell** och **Tillgångar** väljer du lämpliga värden beroende på hur specifik standardtypen av underhållsjobb ska vara.
4. I fältet **Underhållsjobbtyp** väljer du en underhållsjobbtyp om den inte har valts automatiskt.
5. I fälten **Variant av underhållsjobbtyp** och **Yrkesgren** väljer du en variant av underhållsjobbtypen och en yrkesgren för underhållsjobb.
6. Välj **Prognos**.
7. På sidan **Standardprognos för underhållsjobbtyp** kan du göra prognoser för timmar, artiklar och utgifter. Välj **Lägg till** på relevanta flikar och gör urval för att skapa de nödvändiga prognoserna för underhållsjobbtypen.
8. På fliken **Artikelprognos** kan du välja lagerdimensioner som ska visas på artikelraden. Välj **Lager** \> **Dimensioner**, välj dimensionerna som ska visas, ställ in alternativet **Spara inställning** till **Ja** och välj **OK**.
9. På fliken **Artikelprognos**, välj **Artikeln har använts** om du vill få en översikt över var artikeln på den valda raden används i Tillgångshantering i relation till tillgångar, standardtyp av underhållsjobb, reservdelar och arbetsorder. 

    På snabbfliken **Underhållsprognossummor** visas en översikt över prognossummor. I den här översikten ingår det totala antalet timmar och prognosrader som har skapats.

    > [!NOTE]
    > Om du vill kopiera prognosinställningarna från en annan underhållsjobbtyp väljer du **Kopiera prognos** och väljer sedan den typ av underhållsjobb som du vill kopiera inställningarna från.

11. Spara ändringarna genom att klicka på **Spara**.
12. Stäng sidan **Standardprognos för underhållsjobbtyp** för att återgå till sidan **Standardvärden för underhållsjobbtyp**.
13. Välj **Underhållschecklistor**.
14. På sidan **Standardchecklista för underhållsjobbtyp** kan du lägga till rader för underhållschecklista i den valda standardtypen av underhållsjobb. På snabbfliken **Rader för underhållskontroll** väljer du **Ny** om du vill lägga till en rad för underhållschecklista.

    Radnummer anges automatiskt i fältet **Radnummer** för att visa ordningsföljden på raderna i underhållschecklistan. Du kan redigera radnummer efter behov. När du har skapat den första raden i underhållschecklistan väljer du raden och trycker på **Nedåtpil** för att lägga till en rad under den. Du kan också välja en rad för underhållschecklista och sedan välj **Ny**. I det här fallet läggs en ny rad till ovanför den valda raden för underhållschecklista.

15. Välj radtypen i fältet **Typ** och lägg sedan till information som är relaterad till typen av underhållschecklista. En beskrivning av tillgängliga typer och relaterade fält finns i avsnittet [Skapa en mall för underhållschecklista](#create-a-maintenance-checklist-template).

    > [!NOTE]
    > Om du vill kopiera inställningen av underhållschecklista från en annan underhållsjobbtyp väljer du **Kopiera underhållschecklista** och väljer sedan den typ av underhållsjobb som du vill kopiera inställningarna från.
    >
    > Du kan enkelt skapa en mall från en befintlig underhållschecklista. Du kan sedan återanvända mallen för flera underhållschecklistor. Den nya mallen blir en exakt kopia av den aktiva underhållschecklistan. Välj **Skapa mall** och ange ett namn för mallen. Om du vill ersätta den befintliga underhållschecklistan med en enda rad som refererar till den nya mallen ställer du in alternativet **Ersätt** till **Ja**. Du kan visa innehållet i mallen på informationssidan **Mallar för underhållschecklista**.

16. Spara ändringarna genom att klicka på **Spara**.
17. Återgå till sidan **Standardvärden för underhållsjobbtyp**.
18. Välj **Verktyg**.
19. På sidan **Standardverktyg för underhållsjobbtyp** kan du lägga till de verktyg (resurser) som ska användas för underhållsjobbtypen. Välj **Nytt** och välj sedan verktyget i fältet **Resurs**.

    > [!NOTE]
    > Om du vill kopiera verktygsinställningarna från en annan underhållsjobbtyp väljer du **Kopiera verktyg** och väljer sedan den typ av underhållsjobb som du vill kopiera inställningarna från.

20. Spara ändringarna genom att klicka på **Spara**.
21. Återgå till sidan **Standardvärden för underhållsjobbtyp**.
22. Välj **Arbetsbeskrivning**.
23. Välj **Redigera** på sidan **Arbetsbeskrivning** och lägg sedan till en beskrivning som är relaterad till den valda standardtypen av underhållsjobb efter behov.
24. Välj **Spara** för att spara beskrivningen.

    Om du lägger till en arbetsbeskrivning här åsidosätter den eventuell beskrivning som har ställts in för underhållsjobbtypen på sidan **Underhållsjobbtyper**. Om du inte lägger till en arbetsbeskrivning här används en beskrivning som har ställts in för underhållsjobbtypen. Beskrivningar överförs automatiskt till arbetsorder där typen av underhållsjobb eller standardtypen för underhållsjobb används.

25. Återgå till sidan **Standardvärden för underhållsjobbtyp**.
26. Om du vill ställa in bilagor på en vald rad för standardtyp av underhållsjobb väljer du **Bifoga dokument**. Bilagor som ställs in på en standardrad för underhållsjobbtyp inkluderas automatiskt på arbetsorder rader där standardraden för underhållsjobbtypen används.
27. Välj **Ny** och välj en dokumenttyp.
28. Överför dokumentet eller filen.
29. Ställ in fälten på sidan **Bilagor**. Inställningen av den bifogade filen använder standardfunktionen för dokumentinställningar.
30. Välj **Spara** för att spara bilagan.

    > [!NOTE]
    > Bilagor på en underhållsjobbtyp standardrad skrivs ut tillsammans med en arbetsorderrapport endast om dokumenttyperna för de bifogade filerna väljs på fliken **Dokumenttyper** på sidan **Parametrar för tillgångshantering** (**Tillgångshantering** \> **Inställning** \> **Parametrar för tillgångshantering**). Exempel på bilagor är riktlinjer som förklarar hur du slutför ett visst jobb eller en fördefinierad underhållschecklista (om du inte använder funktionen för underhållschecklista för standardrader för underhållsjobbtyp).

    På sidan **Standardvärden för underhållsjobbtyp** visar varje rad antalet prognostiserade timmar och även antalet rader som har skapats för artiklar, utgifter, underhållschecklistor och verktyg. I fältet **Tillgångar** visas antalet aktiva tillgångar som är relaterade till standardraden för underhållsjobbtyp.

31. Om du vill kopiera en standardtyp av underhållsjobb till en annan standardtyp av underhållsjobb markerar du standardraden för underhållsjobbtyp som du vill kopiera en annan inställning till, väljer **Kopiera inställning** och väljer sedan den standardtyp av underhållsjobb som du vill kopiera.
32. Om du vill visa en lista över tillgångar, underhållsplaner eller underhållsomgångar som för tillfället använder en standardrad för underhållsjobbtyp markerar du raden och väljer **Används av**.

![Sidan standard för typ av underhållsjobb](media/07-setup-for-work-orders.png)

När systemet väljer den standardtyp av underhållsjobb som ska användas på en arbetsorderrad, baseras valet på tillgången och inställningen för relaterad tillgångstyp. Tillgångshantering går igenom de standardposter för underhållsjobbtyp som är relaterade till den underhållsjobbtyp som är relaterade till tillgångstypen för att kontrollera om en möjlig matchning finns. Den kontrollerar alltid den mest specifika kombinationen först. Med andra ord, för att hitta den mest specifika kombinationen kontrollerar Tillgångshantering först om det finns en möjlig matchning för fältet **Yrkesgren**. Om ingen matchning hittas söker den efter en matchning för fältet **underhållsjobbtypvariant** och så vidare. Om det inte finns någon matchning söker programmet efter en matchning för fältet **Underhållsjobbtyp**, och så vidare (**Yrkesgren**, sedan **Variant av underhållsjobbtyp**, sedan **Underhållsjobbtyp**, sedan **Tillgång**, sedan **Modell**, sedan **Tillverkare** och sedan **Tillgångstyp**). Om det inte finns någon matchning används den standardpost där endast underhållsjobbtypen väljs.

Ett projektaktivitets-ID relateras automatiskt till varje standardrad för underhållsjobbtyp som du skapar. Projektaktiviteten skapas på det prognosprojekt som väljs i fältet **Underhållsprognosprojekt** på fliken **Tillgångar** på sidan **Parametrar för tillgångshantering**. Syftet med projektaktiviteten är att hantera prognoser för timmar, artiklar och utgifter i relation till arbetsorder. Prognoser för underhållsjobbtyp överförs automatiskt till arbetsorderraden och kopieras från prognosprojektet till det arbetsorderprojekt som har skapats för arbetsorderraden. Syftet med projektaktiviteten är att hantera prognoser i relation till arbetsorder.

Du kan ställa in ett batchjobb för att uppdatera underhållsjobbtypens standardreferenser med jämna mellanrum, eller köra jobbet manuellt. Om du vill skapa ett batchjobb eller köra en manuell uppdatering väljer du **Tillgånghantering** \> **Periodiskt** \> **Förebyggande underhåll** \> **Uppdatera standardreferenser för förebyggande underhåll**.

## <a name="overview-of-maintenance-job-types-that-are-related-to-assets"></a>Översikt över underhållsjobbtyper som är relaterade till tillgångar

När du har skapat de nödvändiga standardkombinationerna för underhållsjobbtyper kan du använda sidan **Alla tillgångar** för att få en översikt över den aktuella standardtypen för underhållsjobb som är kopplad till en viss tillgång. I översikten visas alla standardkombinationer av underhållsjobbtyper som kan användas på till gångstypen som har valts för tillgången. Dessa kombinationer inkluderar kombinationer som har varianter av underhållsjobbtypvarianter och yrkesgrenar för underhållsjobb.

1. Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar** eller **Aktiva tillgångar**.
2. Välj den tillgång i listan som du vill se en översikt över kombinationer av underhållsjobbtyper för.
3. I åtgärdsfönstret, på fliken **Allmänt**, i gruppen **Relaterad information**, väljer du **Underhållsjobbtyper**.

    I det vänstra fönstret på sidan **Underhållsjobbtyper för tillgång** visas en lista över alla kombinationer av underhållsjobbtyper som är relaterade till den valda till gången.

4. Välj en kombination av underhållsjobbtyper för att se den relaterade inställningen för underhållschecklistor, prognoser och verktyg. Avsnittet **Detaljer** på snabbfliken **Standardvärden för underhållsjobbtyp** visar antalet relaterade underhållschecklistor, prognostiserade timmar, artiklar och så vidare, som är relaterade till den valda kombinationen av underhållsjobbtyp.
5. Om du vill visa information om den valda underhållsjobbtypen väljer du **Underhållsjobbtyper**.

![Sidan underhållsjobbtyper för tillgång](media/08-setup-for-work-orders.png)

## <a name="automatic-update-of-maintenance-job-type-forecasts"></a>Automatisk uppdatering av prognoser för underhållsjobbtyper

I Tillgångshantering kan du automatiskt uppdatera alla ändringar av prognoser för underhållsjobbtypen för timkostnader, artikelkostnader och utgifter som har uppdaterats i andra moduler. På så sätt garanterar du alltid att du använder de senaste självkostnaderna med hjälp av prognoser för underhållsjobbtyper.

1. Välj **Tillgångshantering** \> **Periodisk** \> **Prognos** \> **Uppdatera prognos för underhållsjobbtyp**.
2. I dialogrutan **Uppdatera prognos för underhållsjobbtyp**, på snabbfliken **Poster som ska ingå** kan du lägga till urval för specifika underhållsjobbtyper efter behov. Välj **Filter** och välj **Välj** för att göra urvalen.
3. På snabbfliken **Kör i bakgrunden** kan du ställa in den automatiska uppdateringen som ett batchjobb, efter behov.
4. Starta prognosuppdateringen genom att välja **OK**.
