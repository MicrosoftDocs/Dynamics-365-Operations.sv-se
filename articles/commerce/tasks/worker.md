---
title: " Konfigurera en arbetare"
description: I den här proceduren visas hur du konfigurerar en medarbetare som en säljare som är berättigad till provision på försäljning i kassan.
author: jblucher
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd437f549ffc1f8879ce3814ace1193040b280e1
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140688"
---
# <a name="configure-a-worker"></a> Konfigurera en arbetare

[!include [banner](../includes/banner.md)]

I den här proceduren visas hur du konfigurerar en medarbetare som en säljare som är berättigad till provision på försäljning i kassan. I proceduren används demonstrationsföretaget USRT.


## <a name="create-a-commission-sales-group-for-the-worker"></a>Skapa en provisionsförsäljningsgrupp för arbetaren
1. Gå till Försäljning och marknadsföring > Provisioner > Säljgrupper.
    * Arbetare kan tilldelas en eller flera försäljningsgrupper. I kassan kan du välja valfri försäljningsgrupp som innehåller arbetare från butikens adressbok.  
2. Klicka på Ny.
3. Ange ett värde i fältet Grupp.
4. Skriv ett värde i fältet Namn.
5. Klicka på Spara.
6. Klicka på Allmänt i åtgärdsfönstret.
7. Klicka på Sales rep.
    * En försäljningsgrupp kan innehålla mer än en arbetare. Provision kan delas mellan arbetare baserat på hur du definierar provisionsdelningen.  
8. Ange eller välj ett värde i fältet Namn.
9. Ange ett värde i fältet Commission share.
10. Klicka på Spara.
11. Stäng sidan.
12. Stäng sidan.

## <a name="assign-the-workers-default-sales-group"></a>Tilldela förvald försäljningsgrupp för arbetare
1. Gå till Butik och handel > Medarbetare > Alla arbetare.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Klicka på fliken Handel.
    * En arbetare kan tilldelas en förvald försäljningsgrupp. Den förvalda försäljningsgruppen läggs automatiskt till i försäljningsrader i kassan om alternativet aktiveras i funktionsprofilen för butiken.  
5. Klicka på Redigera.
6. Ange eller välj ett värde i fältet Default group.
7. Klicka på Spara.
