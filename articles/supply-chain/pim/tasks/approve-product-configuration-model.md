---
title: Godkänn en produktkonfigurationsmodell
description: När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c196731046fa01059d61f2df08f47639ba839642
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568637"
---
# <a name="approve-a-product-configuration-model"></a>Godkänn en produktkonfigurationsmodell

[!include [task guide banner](../../includes/task-guide-banner.md)]

När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration. I proceduren används högtalarmodellen i demonstrationsföretaget USMF. Observera att den modellen redan har godkänts, men proceduren går igenom hela processen.

1. Klicka på Definition av produktvariantmodell.
2. Klicka på Modeller för produktkonfiguration.
3. Hitta och markera önskad post i listan.
    * Välj högtalarmodellen till den här proceduren.  
4. Klicka på Versioner.
5. Klicka på Ny.
6. Ange eller välj ett värde i fältet Produktnummer.
    * Referensen till en produkt representerar en version av produktkonfigurationsmodellen. Endast produktmallar som har begränsningsbaserad konfiguration visas i listan.  
7. Ange ett datum i fältet Från datum.
    * Välj när produktmodellsversionen ska vara tillgänglig.  
8. Ange ett datum i fältet Till datum.
    * Välj ett slutdatum när produktmodellsversion ska upphöra, eller markerar Aldrig.  
9. Klicka på Godkänn om du vill öppna dialogrutan.
10. Ange eller välj ett värde i fältet Godkänd.
    * Välj den person som är ansvarig för att godkänna produktmodeller för användning i operationer.  
11. Klicka på OK.
12. Markera ett alternativ i fältet Prissättningsmetod.
    * Aktivera produktmodellsversionen. Det är endast möjligt att ha en aktiv produkt för en produktmodell åt gången.  
13. Stäng sidan.

