---
title: " Parameterkonfigurationer för Retail-utdrag"
description: I den här proceduren visas konfigurationer för detaljhandelsparametrarna som påverkar hur detaljhandelsutdrag skapas och bokförs.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6dacd2b80ca0d51d81d2bdf5bc2636b47da621ee
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564303"
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

