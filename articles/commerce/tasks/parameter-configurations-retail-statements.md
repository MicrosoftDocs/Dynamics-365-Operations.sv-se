---
title: Konfigurera parametrar som berör butiksutdrag
description: I det här avsnittet visas konfigurationer för handelsparametrarna som påverkar hur utdrag skapas och bokförs.
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
ms.openlocfilehash: d8cae6d2fa7c469f50fa92141a6cb5a0af1df4b0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024054"
---
# <a name="configure-parameters-that-affect-retail-statements"></a>Konfigurera parametrar som berör butiksutdrag

[!include[task guide banner](../includes/task-guide-banner.md)]

I det här avsnittet visas konfigurationer för handelsparametrarna som påverkar hur utdrag skapas och bokförs. I den här proceduren används demonstrationsföretaget USRT.

1. I Navigeringsfönstret, gå till **Moduler > Butik och handel > Administrationsinställning > Parametrar > Handelsparametrar**.
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

