---
title: " Konfigurera maskininlärningsdrivna produktrekommendationer"
description: I den här proceduren uppdateras datan i enhetsbutiken som används av maskininlärningssystemet som driver produktrekommendationerna, och sedan aktiveras produktrekommendationer på kassaklienter.
author: ashishmsft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BIMeasurementDeployManagementEntityStore, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 700af913f18e23c66db53a92033def06818af1ec
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548449"
---
# <a name="configure-machine-learning-powered-product-recommendations"></a> Konfigurera maskininlärningsdrivna produktrekommendationer

[!include[task guide banner](../includes/task-guide-banner.md)]

I den här proceduren uppdateras datan i enhetsbutiken som används av maskininlärningssystemet som driver produktrekommendationerna, och sedan aktiveras produktrekommendationer på kassaklienter. I proceduren används demonstrationsföretaget USRT.

1. Gå till System administration > Inställningar > Entity Store.
2. Välj posten "RetailSales" i listan.
3. Klicka på Uppdatera.
4. Klicka på OK.
5. Stäng sidan.
6. Gå till Butik och handel > Administrationsinställning > Parametrar > Butiksparametrar.
7. Klicka på fliken Machine learning.
8. Välj "Yes" i fältet "Enable product recommendations".
    * Om du får meddelandet "The recommendation models couldn't be retrieved" sker detta eftersom du nyligen uppdaterade enhetsbutiken och systemet kanske ännu inte har slutat assimilera den nya datan. Vänta i 2-3 timmar och försök igen.  
9. Klicka på Spara.
10. Stäng sidan.

