---
title: "Budgetöversikt"
description: "I stort sett alla företag som använder funktionen ekonomi i Microsoft Dynamics 365 för operationer måste kunna skapa rapporter över budget kontra faktiska värden. Den här artikeln beskrivs den lägsta konfigurationen som krävs för att skapa budgetar i Dynamics 365 för operationer eller läsa in dem från ett externt program."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 60113
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a639e509cf6a3d2f1b850f27481d7b95546522b8
ms.openlocfilehash: b62e14f7c91692ae97bb332b38b0deeb328cc1bd
ms.lasthandoff: 03/31/2017


---

# <a name="budgeting-overview"></a>Budgetöversikt

I stort sett alla företag som använder funktionen ekonomi i Microsoft Dynamics 365 för operationer måste kunna skapa rapporter över budget kontra faktiska värden. Den här artikeln beskrivs den lägsta konfigurationen som krävs för att skapa budgetar i Dynamics 365 för operationer eller läsa in dem från ett externt program.

<a name="overview"></a>Översikt
--------

Den godkända budgeten för ett rättssubjekt är kvar i ett dokument som kallas en *budget registret*. Rader i ett dokument i budgeten register posten kallas *budgetkonto* poster, och innehåller information om ekonomisk dimension, datum och belopp för godkänd budget. Dokumentet budget register posten är integrerat i grundläggande ekonomiska rapporter och förfrågan sidor där faktiska redovisningsbeloppen med budgeterade belopp. 

Det finns flera metoder för att skapa budgetregisterposter i Dynamics 365 för operationer:

-   Ange information om **budgeten registrera poster** sida.
-   Använd Microsoft Excel mallen som du kan öppna genom att klicka på**Öppna i Excel-** knappen på **budgeten registrera poster** sida.
-   Använd**Budgetkonto poster** data i Data Management (Datahantering) för att importera poster i registret. Du använder denna metod och aktivera den **in utifrån** ** bearbetning ** snart måste du importera många budgetkontoposter i systemet.
-   Om företaget använder Budget planeringsfunktionen för att förbereda budgeten data, kan du använda funktionen**Generera budget registret** regelbundet återkommande process.

Budgetregisterposten anses avslutad när budgetsaldon har uppdaterats. I den **budgetregisterposter** klickar du på **uppdatera budgetsaldon** för en vald budget registrera post eller flera poster. När du uppdaterar budgetsaldon, budgetens status registret ändras till **Avslutad**. Klar budget registret kan inte öppnas för redigering. Därför, om budget data måste justeras, måste du skapa en ny budget registret i stället för att korrigera data i den färdiga budgeten registret.

## <a name="configuration"></a>Konfiguration
När du konfigurerar budgetering, starta om **budgetering parametrar sidan** . På den här sidan måste du definiera den budget journal, nummersekvensen för budget registrera poster, och standardinställningen i arbetsytorna.

Om det finns en policy som reglerar godkännandet av budgeten registrera poster, baserat på budget typ (t.ex. transfereringar eller revisioner), måste du skapa budget registret arbetsflöden på **budgetering arbetsflöden** . Om det finns scenarier där överföringar kan tillåtas utan workflow godkännande kan du definiera budgetöverföring regler att stödja dessa scenarion. 

Om **Budgetering mått** sida, måste du välja finansiella mått som används för budgetering, baserat på de dimensioner som används i kontoplanen. Du kan välja alla finansiella mått eller en delmängd av dem för budgetering.

Definiera en * budgetmodell * som motsvarar alla eller vissa av budgetarna. Du kan använda en enda budget modell för alla budget registrera poster. Alternativt kan du skapa separata modeller som baseras på budgeten, geografisk placering, eller några andra sätt som en budget kan klassificeras. 

> [!NOTE] 
> Om budgetkontroll används du kan koppla endast en budgetmodell med en budgetcykel för specifika tidsintervall. 

Skapa *budget koder *som identifierar typ av budgettransaktioner till urkunden och tillhörande arbetsflöde. Budget koder kan stödja följande budgetposter:

-   Ursprunglig budget
-   Överför
-   Ändring
-   Inteckning
-   Förinteckning
-   Överförd budget

Budget koder lät dig att ha en verifieringskedja av godkända ändringar av budgeten under hela budgetperioden. Om ett arbetsflöde associeras med en budgetkod arbetsflödet ska aktiveras för alla budgetregisterposter med denna budget och arbetsflödesstegen måste slutföras innan budgetregisterposten når den **slutförd** fasen.  

Du kan också ställa in *budgetöverföringsregler*. Om du vill använda budgetöverföringsregler **Använd regler för budgetöverföringar** på de **Budgetparametrar** sida. När budgeten överföringsregler används, om användaren skapar ett dokument med hjälp av en budget av **överföringstyp** , budgetsaldon inte uppdateras om budgetöverföringsregler överträds. Du kan till exempel låta budget överföra dokument där budget överförs mellan de huvudsakliga bokföring för försäljnings- och marknadsavdelningen, men kan förbjuda budget överförs från eller till att avdelningen om arbetsflödet typgodkännande har beviljats för den typen av budgetkontot.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Med hjälp av arbetsytor och utredning sidor till bana budget vs. actuals
Den budgetansvarige kan granska det aktuella tillståndet för en budget i **huvudboken budgetar och prognoser som** arbetsyta. **Kostnader över budget** och **intäkterna under budget** flikar ger en snabb överblick över den ekonomiska dimensionen kombinationer där budgetmål inte uppfylls eller närmar sig gränsen. Du kan anpassa budgeten tröskelprocentsats och finansiella mått som används på dessa flikar genom att klicka på **Konfigurera min arbetsyta**. Du kan klicka på **enheten chefer** att se de anställda som är ansvariga för specifik ekonomisk dimension kombinationer som är vald på dessa flikar. Om du till exempel ser att budget för den operativa avdelningen går över budget tröskelvärde kan du enkelt hitta och kontakta avdelningen för att diskutera frågan. 

> [!NOTE] 
> Den **avdelningschef** på de **organisationsenheter** sidan avgör vilka chefer stöder kombinationer av specifika ekonomiska dimensioner. Klicka på **Se mer** längst ner på fliken för att öppna**Budget vs actuals** undersökning sidan för mer information om budget kontra faktiska belopp. 

Den **faktiska vs budget** undersökning sidan kan du borra i detaljerna i budgeten kontra faktiska belopp. Markera en rad på förfrågan och klicka sedan **periodsaldon** att se budget och faktiska belopp fördelade över verksamhetsåret perioder. **Budgetkontot poster**sida ger djupare genom att detaljerna i budgeten beloppet i budgeten registrera poster. **Allmänna journalposter** sidan öppnar reskontratransaktioner som ingår i beräknade **faktiska** belopp. 

Ett företag som använder Budget planeringsfunktionen kan skapa och använda *budget prognoser *i **huvudboken budgetar och prognoser som** arbetsyta.

