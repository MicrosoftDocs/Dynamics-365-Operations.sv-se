---
title: Konfigurera Butiksparametrar som berör butiksutdrag
description: I det här avsnittet visas konfigurationer för detaljhandelsparametrarna som påverkar hur detaljhandelsutdrag skapas och bokförs.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
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
ms.openlocfilehash: b9a0386a4d61395903e82d988244dd131c1febaf
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867281"
---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a>Konfigurera Butiksparametrar som berör butiksutdrag

[!include[task guide banner](../includes/task-guide-banner.md)]

I det här avsnittet visas konfigurationer för detaljhandelsparametrarna som påverkar hur detaljhandelsutdrag skapas och bokförs. I den här proceduren används demonstrationsföretaget USRT.

1. I Navigeringsfönstret, gå till **Moduler > Butik och handel > Administrationsinställning > Parametrar > Butiksparametrar**.
2. Välj fliken **Bokför**.
    - Välj **Ja** om du vill bokföra de tidsbegränsade rabattbeloppen specifikt.  
    - Välj **Standard** för att använda standardkonton eller välj **Periodisk** om du vill ange vilket konto som ska användas för respektive tidsbegränsad rabatt.  
      - Välj **Sammanfattning** om lagerraderna ska sammansättas när det är möjligt.  
      - Välj **Ja** om fakturor och betalningar automatiskt ska kvittas som en del av utdragbokföringsprocessen.  
      - Välj **Ja** om transaktioner från lämning av pengar i kassaskåp ska sammansättas.  
      - Välj **Ja** om transaktioner från bankinsättningar ska sammansättas.  
      - Välj **Ja** för att aktivera sammansättning för utdragsbokföring.  
      - Välj **Ja** när du skapar och bearbetar order parallellt när utdrag bokförs.  
      - Ange det högsta antal order som ska bearbetas i varje batchjobbuppgift.  
3. Välj **Spara**.

