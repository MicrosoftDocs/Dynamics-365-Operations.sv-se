---
title: Godkänn en produktkonfigurationsmodell
description: När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7b548e2369f30e998ecde45408ff45893b88f9a8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987114"
---
# <a name="approve-a-product-configuration-model"></a>Godkänn en produktkonfigurationsmodell

[!include [banner](../../includes/banner.md)]

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

