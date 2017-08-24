--- 
title: " Konfigurera maskininlärningsdrivna produktrekommendationer"
description: "I den här proceduren uppdateras datan i enhetsbutiken som används av maskininlärningssystemet som driver produktrekommendationerna, och sedan aktiveras produktrekommendationer på kassaklienter."
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: c51c5f82efb50db1e238f4046506920975f33218
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

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


