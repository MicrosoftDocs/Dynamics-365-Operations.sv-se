---
title: Godkänn en produktkonfigurationsmodell
description: När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2aefc1a26158fd23af7330bfff7a6ac0e8f3e347
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578186"
---
# <a name="approve-a-product-configuration-model"></a>Godkänn en produktkonfigurationsmodell

[!include [banner](../../includes/banner.md)]

När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration. I proceduren används högtalarmodellen i demonstrationsföretaget USMF. Observera att den modellen redan har godkänts, men proceduren går igenom hela processen.

1. Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.
1. Hitta och markera önskad post i listan.
    * Välj högtalarmodellen till den här proceduren.  
1. Välj **Versioner**.
1. Välj **Ny**.
1. I fältet **Produktnumme** anger eller väljer du ett värde.
    * Referensen till en produkt representerar en version av produktkonfigurationsmodellen. Endast produktmallar som har begränsningsbaserad konfiguration visas i listan.  
1. I fältet **Från datum** anger du ett datum.
    * Välj när produktmodellsversionen ska vara tillgänglig.  
1. I fältet **Till-datum**, anger du ett datum.
    * Välj ett slutdatum när produktmodellsversion ska upphöra, eller markerar Aldrig.  
1. Klicka på **Godkänn** för att öppna dialogrutan.
1. I fältet **Godkändes av** anger eller väljer du ett värde.
    * Välj den person som är ansvarig för att godkänna produktmodeller för användning i operationer.  
1. Välj **OK**.
1. Ange ett alternativ i fältet **Prissättningsmetod**.
    * Aktivera produktmodellsversionen. Det är endast möjligt att ha en aktiv produkt för en produktmodell åt gången.  
1. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]