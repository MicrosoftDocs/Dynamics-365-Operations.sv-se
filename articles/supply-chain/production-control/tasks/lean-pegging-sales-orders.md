---
title: Lean-pegging från försäljningsorder
description: Den här proceduren är avsedd för att validera peggingträdet från en försäljningsrad där artikeln produceras med kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 90032539d59b310cb2d4c1324312eac6593fba6b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843611"
---
# <a name="lean-pegging-from-sales-orders"></a>Lean-pegging från försäljningsorder

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren är avsedd för att validera peggingträdet från en försäljningsrad där artikeln produceras med kanban. När du har validerat pegging-trädet planeras alla kanban-jobb. Detta är användbart för orderscenarier där ordermottagaren behöver se till att produktion kan starta omedelbart. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för den avancerade ordermottagaren som arbetar på ett lean-företag.


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a>Skapa en försäljningsorder för en kanban-kontrollerad artikel
1. Gå till Alla försäljningsorder.
2. Klicka på Ny.
3. I fältet Kundkonto, ange eller välj ett värde.
    * Använd US-001.  
4. Klicka på OK.
5. Skriv "L0001" i fältet Artikelnummer.
6. Ställ in kvantiteten på 30.
    * Det är viktigt att kvantiteten är högre än 24 för att utlösa kanban-regeln för händelsen.  

## <a name="open-a-pegging-tree"></a>Öppna ett pegging-träd 
1. Klicka på Produkt och leverans.
2. Klicka på Visa pegging-träd.
    * Observera att peggingträdet visar alla nivåer för peggingen som behövs för försäljningsorderraden. I det här fallet finns det två nivåer för kanban och alla nödvändiga komponenter.  

## <a name="plan-the-pegging-tree"></a>Planera pegging-trädet
1. I trädet, välj försäljningsrad 000832\Kanban 000558.
2. Expandera avsnittet Kanban-jobb.
    * Observera att jobbstatusen för kanban-jobbet är Inte planerad.  
3. Klicka på Planera helt pegging-träd.
    * Då planeras alla kanban-jobb i peggingträdet och jobbstatusen ändras från Inte planerad till Planerad.  
4. Uppdatera sidan.
    * Observera att kanban-jobbets status ändras från Inte planerad till Planerad.  
5. I trädet, välj försäljningsrad 000832\Kanban 000558\Utleverans för L0001\Kanban 000559.
    * Jobbet för den andra kanban planeras även, eftersom hela pegging-trädet planeras. Observera att kanban-jobbets status ändras från Inte planerad till Planerad.  

