---
title: " Konfigurera en arbetare"
description: I den här proceduren visas hur du konfigurerar en medarbetare som en säljare som är berättigad till provision på försäljning i POS.
author: jblucher
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a21d5f2d5963db2a92b653e8e520f96f11ba1bf6acbb238812211154d5b39fc0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726393"
---
# <a name="configure-a-worker"></a> Konfigurera en arbetare

[!include [banner](../includes/banner.md)]

I den här proceduren visas hur du konfigurerar en medarbetare som en säljare som är berättigad till provision på försäljning i POS. I proceduren används demonstrationsföretaget USRT.


## <a name="create-a-commission-sales-group-for-the-worker"></a>Skapa en provisionsförsäljningsgrupp för arbetaren
1. Gå till Försäljning och marknadsföring > Provisioner > Säljgrupper.
    * Arbetare kan tilldelas en eller flera försäljningsgrupper. I POS kan du välja valfri försäljningsgrupp som innehåller arbetare från butikens adressbok.  
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
4. Klicka på fliken Commerce.
    * En arbetare kan tilldelas en förvald försäljningsgrupp. Den förvalda försäljningsgruppen läggs automatiskt till i försäljningsrader i POS om alternativet aktiveras i funktionsprofilen för butiken.  
5. Klicka på Redigera.
6. Ange eller välj ett värde i fältet Default group.
7. Klicka på Spara.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]