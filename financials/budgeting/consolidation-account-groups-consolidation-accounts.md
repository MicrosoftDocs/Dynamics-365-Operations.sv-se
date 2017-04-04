---
title: Konsolideringskontogrupper och ytterligare konsolideringskonton
description: "I det här avsnittet innehåller information om konsolideringskontogrupper och ytterligare konsolideringskonton och förklarar hur de används i Microsoft Dynamics 365 för operationer."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f9c5aaa389c9c2f85d1ab91cbf3d2222cbebef55
ms.lasthandoff: 03/31/2017


---

# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Konsolideringskontogrupper och ytterligare konsolideringskonton

I det här avsnittet innehåller information om konsolideringskontogrupper och ytterligare konsolideringskonton och förklarar hur de används i Microsoft Dynamics 365 för operationer.

<a name="consolidation-account-groups"></a>Konsolideringskontogrupper
----------------------------

Konsolideringskontogrupper kan du skapa grupper av konton som du vill använda för att konsolidera data. Oftast använder en konsolideringskontogruppen representerar en bestämd myndigheter kontoplan eller ansluter konton till en grupp som definieras av företagets huvudkontor. Du konsolideringen kontogrupper i den **inställningar** del av den **konsolideringar** modul. När du lägger till en ny grupp kan du ange en unik identifierare för kontogruppen och ett namn.

## <a name="additional-consolidation-accounts"></a>Ytterligare konsolideringskonton
Ytterligare konsolideringskonton kan du tilldela en konsolideringskontogruppen ett konto från en befintlig kontoplan. Du kan sedan ange ett värde för konsolidering och namn. 

Du hittar ytterligare konsolideringskonton i den **inställningar** del av den **konsolideringar** modulen. När du skapar ett nytt konsolideringskonto, anger du följande information:

-   **Huvudkontot** – detta fält är en sökning som visar alla huvudkonton utifrån kontoplanen som du valde på sidan. När du väljer ett konto anges automatiskt namnet i den **huvud kontonamnet** fält.
-   **Konsolideringskontogruppen** – använda fältet för att ange om du vill tilldela kontot till gruppen. Om du konsoliderar på två olika sätt, måste du lägga till samma konto alla fyra konsolideringskontogrupper.
-   **Konsolideringskonto** – ange värdet på konsolideringskontot för. Det här värdet måste inte vara ett konto från en kontoplan. Det kan vara ett värde som du vill ha.
-   **Kontonamnet för konsolidering** – ange namnet på kontot som du vill ska visas i förfrågningar och rapporter.
-   **SAT-nivå** – detta fält används vid rapportering till skattemyndigheten mexikansk kontoutdrag. 

När du har skapat dina konsolideringskontogrupper och ytterligare konsolideringskonton, väljer du gruppen i processen konsolidera online.



