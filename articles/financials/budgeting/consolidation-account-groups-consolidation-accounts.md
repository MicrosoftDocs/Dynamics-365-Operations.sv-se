---
title: Skapa konsolideringskontogrupper och ytterligare konsolideringskonton
description: "Det här avsnittet innehåller information om konsolideringskontogrupper och ytterligare konsolideringskonton, och förklarar hur de används i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4fcdaa26eb2f15bbf6f7d80bd59a54899f637a2c
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Skapa konsolideringskontogrupper och ytterligare konsolideringskonton

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om konsolideringskontogrupper och ytterligare konsolideringskonton, och förklarar hur de används i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

<a name="consolidation-account-groups"></a>Konsolideringskontogrupper
----------------------------

Med konsolideringskontogrupper kan du skapa grupper av konton som du vill använda för att konsolidera data. Oftast representerar konsolideringskontogrupp en myndighetsbeviljad kontoplan eller mappar konton till en grupp som definieras av företagets huvudkontor. Du hittar konsolideringskontogrupper i avsnittet **Inställningar** i modulen **Konsolideringar**. När du lägger till en ny grupp kan du ange en unik identifierare för kontogruppen och ett namn.

## <a name="additional-consolidation-accounts"></a>Ytterligare konsolideringskonton
Med ytterligare konsolideringskonton kan du tilldela en konsolideringskontogrupp ett konto från en befintlig kontoplan. Du kan sedan ange ett värde för konsolideringskonto och ett namn. 

Du hittar ytterligare konsolideringskonton i avsnittet **Inställningar** i modulen **Konsolideringar**. När du skapar ett nytt konsolideringskonto måste du ange följande information:

-   **Huvudkontot** – Detta fält är en sökning som visar alla huvudkonton som baseras på den kontoplan som du valde på sidan När du väljer ett konto anges namnet automatiskt i fältet **Huvudkontonamn**.
-   **Konsolideringskontogrupp** – Använd detta fält för att ange den grupp som kontot ska tilldelas till. Om du konsoliderar på två olika sätt måste du lägga till samma konto i alla fyra konsolideringskontogrupper.
-   **Konsolideringskonto** – Ange värdet för konsolideringskontot. Det här värdet måste inte vara ett konto från en kontoplan. Det kan vara ett valfritt värde som du behöver.
-   **Namn på konsolideringskonto** – Ange namnet på det konto som du vill ska visas på förfrågningar och rapporter.
-   **SAT-nivå** – Detta fält används för att rapportera kontoutdrag till de mexikanska skattemyndigheterna. 

När du har skapat dina konsolideringskontogrupper och ytterligare konsolideringskonton kan du välja gruppen i processen för onlinekonsolidering.


För mer information, se [Skapa konsolideringsgrupper och ytterligare konsolideringskonton](../general-ledger/tasks/create-consolidation-groups.md) 




