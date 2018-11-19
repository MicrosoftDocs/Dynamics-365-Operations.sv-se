---
title: Utbyggbarhet i Attract
description: "Det här avsnittet beskriver hur du kan utöka Microsoft Dynamics 365 for Talent - Attract-appen med Microsoft Power platform."
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 0af60a0aea0f7a5de793631445aaebb37dbb0d74
ms.contentlocale: sv-se
ms.lasthandoff: 10/22/2018

---

# <a name="extensibility-in-attract"></a>Utbyggbarhet i Attract

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Talent byggs ovanför Common Data Service (CDS) for Apps-plattformen och kan utökas på olika sätt med hjälp av Microsofts Power platform och funktionerna som Common Data Service for Apps ger. Därför kan du konfigurera och anpassa systemet med hjälp av Microsoft PowerApps och Microsoft Flow. Du kan också få ytterligare analys om personer genom att använda Microsoft Power BI. Dessutom gör nya anpassade aktiviteter, till exempel PowerApps och webbinnehåll (iframe), anställningsprocessen mer anpassningsbar än någonsin. Genom att använda dessa nya aktiviteter kan du skräddarsy anställningsprocessen till dina affärsbehov och processer och kan se till att både anställningsteam och sökande har en smidig och anpassad upplevelse.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Utnyttja Microsoft Power platform 

Eftersom all data från Attract finns i Common Data Service for Apps kan du använda verktyg från Microsoft Power platform för att inkludera unika affärsbehov i Attract.

### <a name="powerapps"></a>PowerApps

Du kan använda PowerApps för att enkelt skapa appar som ansluter dig till dina Attract-data och som använder uttryck såsom uttryck i Microsoft Excel för att lägga till logik. Appar som du skapar genom att använda PowerApps kan köras på webben och på Apple iOS- och Google Android-enheter.

Exempelvis kan du göra universitetskarriärmässor enklare för rekryterare genom att skapa en enkel app där du skannar in meritförteckningarna, och matar kandidater till en plats i Attract. Alternativt kan du bygga ett program som hjälper till att uppfylla ditt företags krav på efterlevnad. Mer information om PowerApps och hur man skapar appar finns i [integrera data i Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps).

### <a name="microsoft-flow"></a>Microsoft Flow 

Du kan använda Microsoft Flow till att skapa automatiska arbetsflöden som körs ovanpå Attract-data. Du kan enkelt ansluta till hundratals populära appar och tjänster utan att behöva skriva kod. Du kan automatisera olika åtgärder genom att skapa flöden som samverkar med Attract jobb-, kandidat- och sökandeentiteter i Common Data Service for Apps. Till exempel när en kandidat godkänner ett erbjudande, kan ett meddelande skickas till ett integrationsteam eller nyheterna kan meddelas på Twitter. Mer information om flöden finns i [Microsoft Flow-dokumentation](https://docs.microsoft.com/en-us/flow/).

### <a name="power-bi"></a>Power BI

Power BI låter dig skapa och visa anpassade rapporter och instrumentpaneler som ger dig bättre inblick i Attract-data. Mer information om Power BI och hur du skapar interaktiva rapporter och instrumentpaneler finns i [Power BI-dokumentationen](https://docs.microsoft.com/en-us/power-bi/).

### <a name="custom-activities"></a>Anpassade aktiviteter 

Du kan lägga till anpassade aktiviteter, till exempel PowerApps-program och webbinnehållsaktiviteter (iframe), i nivå med jobbprocessmallen eller medan du skapar ett nytt jobb. Aktiviteterna låter dig anpassa anställningsprocessen och ta med affärslogik som är unik för din organisation i Attract.

#### <a name="powerapps-activity"></a>PowerApps-aktivitet 

PowerApps-aktiviteten låter skaparen av ett jobb eller en jobbprocessmall bädda in ett PowerApps-app anställningsflödet. När du har skapat och publicerat programmet anger du dess program-ID i aktivitetskonfigurationen. Genom att använda en PowerApps-app kan du läsa och skriva data i Common Data Service for Apps. Du kan även koppla appen till ett flöde. Exempelvis har du en app som rekryterare använder för att fylla i ett formulär när de genomför telefonintervjuer. I det här fallet kan du koppla programmet till ett flöde som bedömer om en sökande kan avancera ytterligare i jobbsökningsprocessen eller inte. Den här typen av aktivitet kan endast visas av medlemmarna av anställningsteamet. Mer information om hur du konfigurerar PowerApps-aktiviteten finns i [aktiviteter i Attract](./activities-attract.md).

> [!NOTE]
> PowerApps-aktiviteten är endast tillgänglig med tillägget för omfattande anställning.

#### <a name="web-content-iframe-activity"></a>Webbinnehållsaktivitet (iframe)

Webbinnehållsaktiviteten (iframe) låter dig bädda in en anpassat webblösning som du byggt in i anställningsprocessen eller kandidatportalen. Du kan läsa och skriva data direkt från Common Data Service for Apps. Du kan också anpassa lösningen så att den utlöser flöden eller utnyttjar Microsoft Azure-funktioner. Mer information om hur du konfigurerar webbinnehållsaktiviteten finns i [aktiviteter i Attract](./activities-attract.md).

> [!NOTE]
> Webbinnehållsaktiviteten är endast tillgänglig med tillägget för omfattande anställning.

