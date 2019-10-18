---
title: Hantera lagerställearbetare
description: Denna artikel beskriver hur du kan använda Dynamics 365 Supply Chain Management - lagerställeappen för att hjälpa till att kontrollera och övervaka det arbete som utförs av anställda i ditt lager.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, InventLocation, WHSLaborStandards, WHSWorker, WHSWorkTable, WHSWorkTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72891
ms.assetid: feaa6f15-49d2-41f5-9b87-453463c52e4e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0de87e10f9213838dd5e5436b8b5699b19547bf
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2018631"
---
# <a name="manage-warehouse-workers"></a>Hantera lagerställearbetare

[!include [banner](../includes/banner.md)]

Denna artikel beskriver hur du kan använda Dynamics 365 Supply Chain Management - lagerställeappen för att hjälpa till att kontrollera och övervaka det arbete som utförs av anställda i ditt lager.

Om du använder funktionerna i lagerhantering, alla lagerarbetare operationer som *arbete*. Arbetet såsom plockning, flytta och räknar lagersaldot registreras med hjälp av mobila enheter. Innan en lagerarbetare kan utföra arbete, han eller hon måste vara associerad med en arbetstagare i mänskliga resurser. Varje **arbetstagare** kan ha flera lagerarbetet användare som är associerade med den. Dessa arbeten kan användarna arbeta i olika lager och kan ha olika nivåer av åtkomst till olika mobila enheten menyer. Du kan tänker av lagerarbetet användare som flera inloggningar för vald anställd. Varje användare har en standard lager, och specifika arbetsflöden exponeras genom menyerna tillgängliga alternativ som fungerar. 

För att skapa en ny arbetsorder användaren, på **arbetstagarnas** sida, på **fliken Allmänt** , i **lagerlokaler** , klicka på **arbetstagare**. Du måste ange ett användar-ID, användarnamn, en standard lager och ett menynamn. Den här menyn är laddad när användaren loggar in till Warehouse Mobile Device Portal och låter dig definiera vilka menyobjekt användaren har tillgång till. 

Som en del av installationen för varje användare, kan du också definiera specifika process arbetsflöden. Du kan till exempel använda **Är ansvarig för rullande inventering** fältet för att ange huruvida användaren kan bearbeta justeringar av rullande inventerings avvikelser under en inventering, eller om dessa justeringar måste först granskas av en annan person.

## <a name="defining-labor-standards"></a>Definiera arbetsnormer
**Arbetsrätten** sidan kan du definiera de beräkningsmetoder som systemet använder för att beräkna det uppskattade tiden som en viss typ av arbete kräver. Denna definition kan ställas in på en allmän nivå eller på en viss nivå. Du kan t.ex. definiera tid som ska krävas för att bearbeta en försäljningsorder plocka per vikt för en specifik enhet definition när en viss plocka processen används. Samtidigt kan du registrera tid, baserat på en annan beräkningsmetod för putten av lagersaldot som plockas. 

För att arbetsnormer som du definierat, måste du markera kryssrutan **Tillåt arbetsnormer** alternativ för varje lager där arbetsnormer skall användas.

## <a name="monitoring-and-controlling-warehouse-work"></a>Övervakning och kontroll av lagerarbetet
**Allt arbete på** sidan låter dig övervaka och underhålla allt arbete som är planerade, pågående och slutförda. Från den här sidan kan du uppdatera olika processer, såsom lagerarbetet användaren uppdrag och arbete prioriteras. Du kan också visa detaljer som är relaterade till arbetsordern huvudet och arbeta för att få en förståelse av den förväntade eller avslutad arbetsprocesser. 

Om du aktiverar **arbetsnormer** , kan du se det beräknade beräknad tid för arbetet. När sedan arbetet är bearbetade, den faktiska tiden visas också för varje arbetsoperation. På detta sätt kan du jämföra den beräknade tiden beräkningar till aktuell tid. 

Du kan dessutom använda beräknad tid i reglerna för automatiskt rämna under skapa arbete. På detta sätt kan du lastbalansera arbetet baserat på förväntad tid att slutföra uppgifter. 

Analysen av den tid som används för att bearbeta arbetsposter kan hjälpa till att driva förbättringar i lagerarbetare" effektivitet. Följande rapporter är tillgängliga för att hjälpa till med denna analys:

-   **Arbete med användaren** – den här rapporten visar medarbetarnas produktivitet, baserat på faktiska tider mot förväntade tider.
-   **Arbete med arbete transaktionstyp** – Du kan använda rapporten för att undersöka bristerna i särskilda lager processer. Till exempel, du märker att plockar för överföringsuppdrag tar längre denna vecka än under föregående veckor. Du kan sedan använda den här informationen för vidare utredning.




