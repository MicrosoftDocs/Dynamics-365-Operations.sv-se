--- 
title: " Parameterkonfigurationer för Retail-utdrag"
description: "I den här proceduren visas konfigurationer för detaljhandelsparametrarna som påverkar hur detaljhandelsutdrag skapas och bokförs."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: ba3b528f8739e4e84ffdbeea5d0af5817f2d9c10
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="parameter-configurations-for-retail-statements"></a> Parameterkonfigurationer för Retail-utdrag

[!include[task guide banner](../includes/task-guide-banner.md)]

I den här proceduren visas konfigurationer för detaljhandelsparametrarna som påverkar hur detaljhandelsutdrag skapas och bokförs. I den här proceduren används demonstrationsföretaget USRT.

1. Gå till Butik och handel > Administrationsinställning > Parametrar > Butiksparametrar.
2. Klicka på fliken Bokföring.
    * Välj Ja om du vill bokföra de tidsbegränsade rabattbeloppen specifikt.  
    * Välj Standard för att använda standardkonton eller välj Periodisk om du vill ange vilket konto som ska användas för respektive tidsbegränsad rabatt.  
    * Välj Sammanfattning om lagerraderna ska sammansättas när det är möjligt.  
    * Välj Ja om fakturor och betalningar automatiskt ska kvittas som en del av utdragbokföringsprocessen.  
    * Välj Ja om transaktioner från lämning av pengar i kassaskåp ska sammansättas.  
    * Välj Ja om transaktioner från bankinsättningar ska sammansättas.  
    * Välj Ja för att aktivera sammansättning för utdragsbokföring.  
    * Välj Ja när du skapar och bearbetar order parallellt när utdrag bokförs.  
    * Ange det högsta antal order som ska bearbetas i varje batchjobbuppgift.  
3. Klicka på Spara.


