---
title: Konfigurera och hantera databasloggning
description: Du kan spåra ändringar i register och fält i Dynamics 365 Human Resources med databasloggning.
author: andreabichsel
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 50346cc495fe08f49137dba59dbcbb3f7f838c7b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129289"
---
# <a name="configure-and-manage-database-logging"></a>Konfigurera och hantera databasloggning

Du kan spåra ändringar i register och fält i Dynamics 365 Human Resources med databasloggning. I det här avsnittet beskrivs hur du:

- Hantera säkerhet och prestanda för databasloggning
- Ställ in databasloggning
- Rensa databasloggar

## <a name="overview-of-database-logging"></a>Översikt över databasloggning

Databasloggning spårar specifika ändringar av Microsoft Dynamics 365 Human Resources tabeller och fält. Ändringarna omfattar infogning, uppdatering och borttagning. Databasloggning lagrar en post med ändringar i register eller fält i databaslogg registret.

Databasloggningen omfattar bland annat följande:

- Skapa en granskningspost av ändringar i specifika register som innehåller känslig information.
- Spåra enskilda transaktioner. Databasloggning är inte avsett för spårning av automatiserade transaktioner som körs i batchjobb.

## <a name="security-for-database-logging"></a>Säkerhet vid databasloggning

Databasloggar kan innehålla känsliga data. Begränsa åtkomsten till inkludera endast säkerhetsroller som behöver åtkomst till loggdata.

## <a name="database-logging-and-performance"></a>Databasloggning och prestanda

Samtidigt som det är värdefullt från ett affärsperspektiv kan databasloggning vara dyrt att använda och hantera resurser. Prestandakonsekvenser för databasloggningen omfattar bland annat följande:

- Tabellen databaslogg kan växa snabbt och leda till att storleken på databasen ökar. Tillväxten beror på mängden loggade data som du vill behålla. Som standard innehåller tabellen databaslogg endast 30 dagars loggdata. 

- Databasloggning kan påverka avancerade automatiserade processer, t.ex. tidskrävande dataimporter.

### <a name="best-practices"></a>Regelverk

För att förbättra prestanda begränsar du loggposter genom att välja specifika fält för att logga istället för hela tabeller.. Databasloggningen är begränsad till 20 tabeller för att upprätthålla den allmänna prestandan.

> [!NOTE]
> Endast uppdateringar kan loggas för enskilda fält.

## <a name="set-up-database-logging"></a>Ställ in databasloggning

Du kan använda guiden **Loggar databasändringar** när du vill konfigurera databasloggning. Med hjälp av guiden kan du på ett flexibelt sätt ställa in loggning för register eller fält.

1. Gå till **Systemadministration > Länkar > Databasen > Inställningar för databaslogg**. Välj **Ny** om du vill starta guiden **Loggar databasändringar**.
2. Slutför guiden.

## <a name="clean-up-database-logs"></a>Rensa databasloggar

Du kan ta bort alla eller en del av databasloggarna med följande alternativ:

- Välj alla loggar för en viss tabell.
- Välj specifika typer av databaslogg.
- Välj ett datum och en tidpunkt då en logg skapas.

Följ dessa steg för att ställa in rensning av databaslogg: 

1. Gå till **Systemadministration > Länkar > Databasen > Databaslogg**. Välj **Rensa logg**.

2. Välj en metod för att välja loggar att ta bort genom att ange något av följande alternativ:

   - Register-ID
   - Typ av logg
   - Skapat datum och klockslag

3. Använd fliken **Rensning i databasloggen** för att bestämma när loggrensningsuppgiften ska köras. Som standard är databasloggar tillgängliga i 30 dagar.


[!INCLUDE[footer-include](../includes/footer-banner.md)]