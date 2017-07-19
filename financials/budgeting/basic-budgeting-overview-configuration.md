---
title: "Budgetöversikt"
description: "I stort sett alla företag som använder funktionen ekonomi i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition måste kunna skapa rapporter över budget kontra faktiska värden. Den här artikeln beskriver den minimikonfiguration som krävs för att skapa budgetar i Finance and Operations, Enterprise edition eller läsa in dem från ett tredjepartsprogram."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 60113
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: sigitac
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: f35db274a6b14f6bae185b69348d3829c77801b5
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="budgeting-overview"></a>Budgetöversikt

[!include[banner](../includes/banner.md)]


I stort sett alla företag som använder funktionen ekonomi i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition måste kunna skapa rapporter över budget kontra faktiska värden. Den här artikeln beskriver den minimikonfiguration som krävs för att skapa budgetar i Finance and Operations eller läsa in dem från ett tredjepartsprogram.

<a name="overview"></a>Översikt
--------

Den godkända budgeten för ett rättssubjekt är kvar i ett dokument som kallas en *budget registret*. Raderna i ett dokument för budgetregistreringsposter kallas för *budgetkonto*-poster och innehåller information om ekonomiska dimensioner, datum och godkända budgetbelopp. Dokumentet för budgetregistreringsposter är integrerat i grundläggande ekonomiska rapporter och frågesidor, där faktiska redovisningsbelopp jämförts med budgeterade belopp. 

Det finns flera metoder för att skapa budgetregisterposter i Finance and Operations.

-   Ange information om **budgeten registrera poster** sida.
-   Använd Microsoft Excel mallen som du kan öppna genom att klicka på **Öppna i Excel-** knappen på **budgeten registrera poster** sida.
-   Använd **Budgetkonto poster** data i Data Management (Datahantering) för att importera poster i registret. Du bör överväga att använda denna metod och att aktivera parameterns **Uppsättningsbaserad** **bearbetningsparameter** när du måste importera budgetkontoposter i systemet.
-   Om företaget använder Budget planeringsfunktionen för att förbereda budgeten data, kan du använda funktionen **Generera budget registret** regelbundet återkommande process.

Budgetregisterposten anses slutförd när budgetsaldona har uppdaterats. På sidan **Budgetregisterposter** klickar du på **Uppdatera budgetsaldon** för en vald budgetregisterpost eller flera poster. När du uppdaterar budgetsaldon, budgetens status registret ändras till **Avslutad**. Klar budget registret kan inte öppnas för redigering. Därför, om budget data måste justeras, måste du skapa en ny budget registret i stället för att korrigera data i den färdiga budgeten registret.

## <a name="configuration"></a>Konfiguration
När du konfigurerar budgetering, starta om **budgetering parametrar sidan** . På den här sidan måste du definiera den budget journal, nummersekvensen för budget registrera poster, och standardinställningen i arbetsytorna.

Om det finns en policy som reglerar godkännandet av budgeten registrera poster, baserat på budget typ (t.ex. transfereringar eller revisioner), måste du skapa budget registret arbetsflöden på **budgetering arbetsflöden** . Om det finns scenarier där överföringar kan tillåtas utan workflow godkännande kan du definiera budgetöverföring regler att stödja dessa scenarion. 

Om **Budgetering mått** sida, måste du välja finansiella mått som används för budgetering, baserat på de dimensioner som används i kontoplanen. Du kan välja alla finansiella mått eller en delmängd av dem för budgetering.

Definiera en *budgetmodell* som motsvarar hela eller en del av budgeten. Du kan använda en enda budget modell för alla budget registrera poster. Alternativt kan du skapa separata modeller som baseras på budgeten, geografisk placering, eller några andra sätt som en budget kan klassificeras. 

> [!NOTE] 
> Om budgetkontroll används kan du bara associera en enda budgetmodell med en specifik tidsrymd för budgetcykel. 

Skapa *budget koder* som identifierar typ av budgettransaktioner till urkunden och tillhörande arbetsflöde. Budget koder kan stödja följande budgetposter:

-   Ursprunglig budget
-   Överför
-   Ändring
-   Inteckning
-   Förinteckning
-   Överförd budget

Budget koder lät dig att ha en verifieringskedja av godkända ändringar av budgeten under hela budgetperioden. Om ett arbetsflöde associeras med en budgetkod kommer arbetsflödet att aktiveras för alla budgetregisterposter som använder denna budgetkod, och arbetsflödesstegen måste slutföras innan budgetregisterposten når fasen **Slutförd**.  

Du kan också ställa in *Budgetöverföringsregler* (valfritt). Om du vill använda budgetöverföringsregler väljer du **Använd regler för budgetöverföringar** på sidan **Budgetparametrar**. När budgeten överföringsregler används, om användaren skapar ett dokument med hjälp av en budget av **överföringstyp** , budgetsaldon inte uppdateras om budgetöverföringsregler överträds. Du kan till exempel låta budget överföra dokument där budget överförs mellan de huvudsakliga bokföring för försäljnings- och marknadsavdelningen, men kan förbjuda budget överförs från eller till att avdelningen om arbetsflödet typgodkännande har beviljats för den typen av budgetkontot.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Med hjälp av arbetsytor och utredning sidor till bana budget vs. actuals
Den budgetansvarige kan granska det aktuella tillståndet för en budget i **huvudboken budgetar och prognoser som** arbetsyta. **Kostnader över budget** och **intäkterna under budget** flikar ger en snabb överblick över den ekonomiska dimensionen kombinationer där budgetmål inte uppfylls eller närmar sig gränsen. Du kan anpassa budgeten tröskelprocentsats och finansiella mått som används på dessa flikar genom att klicka på **Konfigurera min arbetsyta**. Du kan klicka på **enheten chefer** att se de anställda som är ansvariga för specifik ekonomisk dimension kombinationer som är vald på dessa flikar. Om du till exempel ser att budget för den operativa avdelningen går över budget tröskelvärde kan du enkelt hitta och kontakta avdelningen för att diskutera frågan. 

> [!NOTE] 
> Fältet **Avdelningschef** på sidan **Organisationsenheter** bestämmer vilka chefer som hanterar specifika ekonomiska dimensionskombinationer. Klicka på **Se mer** längst ner på fliken för att öppna **Budget kontra utfall** undersökning sidan för mer information om budget kontra faktiska belopp. 

Den **faktiska vs budget** undersökning sidan kan du borra i detaljerna i budgeten kontra faktiska belopp. Markera en rad på förfrågan och klicka sedan **periodsaldon** att se budget och faktiska belopp fördelade över verksamhetsåret perioder. **Budgetkontot poster** sida ger djupare genom att detaljerna i budgeten beloppet i budgeten registrera poster. **Allmänna journalposter** sidan öppnar reskontratransaktioner som ingår i beräknade **faktiska** belopp. 

Ett företag som använder Budget planeringsfunktionen kan skapa och använda *budget prognoser* i **huvudboken budgetar och prognoser som** arbetsyta.




