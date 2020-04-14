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
ms.openlocfilehash: 7892a216d836ebcc297a5b7eb87bc996dd9b91bf
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140856"
---
# <a name="configure-parameters-that-affect-retail-statements"></a>Konfigurera parametrar som berör butiksutdrag

[!include [banner](../includes/banner.md)]

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

