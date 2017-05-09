---
title: "Stäm av frakt i transporthantering"
description: "Den här artikeln ger en beskrivning av fraktavstämningsprocessen."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c85806132efb65c2d4bc85ef1921c003c5c7453b
ms.lasthandoff: 03/31/2017


---

# <a name="reconcile-freight-in-transportation-management"></a>Stäm av frakt i transporthantering

[!include[banner](../includes/banner.md)]


Den här artikeln ger en beskrivning av fraktavstämningsprocessen.

Fraktavstämning kan utföras manuellt eller ställas in för att utföras automatiskt. Om du vill använda automatisk fraktavstämning måste du ställa in en granskningsmall där du kan definiera kriterierna som avgör vilka fraktväxlar som matchas automatiskt.

## <a name="the-freight-reconciliation-process"></a>Fraktavstämningsprocessen
Fraktsatser beräknas med hjälp av tariffmotorer som kopplas till relevanta transportföretag. När en last bekräftas genereras en fraktsedel och fraktsatser överförs till den. Fraktsatser fördelas som tilläggsavgifter till det aktuella källdokumentet (inköpsorder, försäljningsorder och/eller överföringsorder) beroende på inställningarna som används för den vanliga faktureringsprocessen. Fraktavstämningsprocessen (som också kallas matchande processen) kan starta så snart fraktfakturan inkommer från transportföretaget. Fakturan kan tas emot elektroniskt eller som pappersfaktura. Om det är en pappersfaktura kan du generera en elektronisk faktura med hjälp av fraktsedeln som mall. 

[![Fraktavstämningsprocess](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Manuell avstämning
Om du stämmer av frakten manuellt måste du matcha varje fakturarad med fraktsedelns rad eller rader för lasten som faktureras. Du utför den här matchningen på sidan **Fraktsedel och fakturamatchning**. Om beloppet på fakturaraden inte överensstämmer med beloppet på fraktsedeln måste du välja en orsak till avstämningsavvikelsen. Om det finns flera skäl för avstämning kan du dela upp omatchade belopp över dem. Avstämningsorsaken avgör hur de avvikande beloppen bokförs i redovisningen. När avstämningen av hela fakturabeloppet redovisas skickas den för godkännande och sedan bokförs.journalen. Bilden nedan visar hur du genererar en fraktfaktura och utför fraktavstämning i Microsoft Dynamics 365 for Operations. 
[![Fraktavstämningsuppgifter i Dynamics AX](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)
## <a name="automatic-reconciliation"></a>Automatisk avstämning
Du måste ange tidsplanen för avstämning, fakturorna och vilket transportföretag som ska användas om du vill använda automatisk avstämning. Matchningen av fakturarader och fraktsedlarna utförs enligt inställningarna för granskningsmallen och fraktsedelstypen. När du har kört automatisk avstämning måste du hantera alla fakturor som systemet inte kan matcha. Du måste sedan behandla dessa fakturor manuellt innan du kan bokföra alla fakturor för betalning.




