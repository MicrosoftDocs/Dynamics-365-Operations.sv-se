---
title: Skapa en strukturlista för en dimensionsbaserad produktmall
description: För den här proceduren bör du ha slutfört de tidigare 4 guiderna i denna sekvens av åtta inspelningar.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13053dd87242963586678b46c64493feb3383c4c
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920715"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Skapa en strukturlista för en dimensionsbaserad produktmall

[!include [banner](../../includes/banner.md)]

För den här proceduren bör du ha slutfört de tidigare 4 guiderna i denna sekvens av åtta inspelningar. De första 4 inspelningarna anger de data som krävs för att slutföra den här proceduren. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Denna uppgift utförs vanligtvis av produktdesignern.

## <a name="select-the-product"></a>Välj produkten

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Markera vald rad i listan.
    * Hitta den frisläppta produktmallen med dimensionsbaserad konfigurationsteknologi som du skapade i den första uppgiftsguiden i denna sekvens.  
1. Klicka på **Tekniker** i åtgärdsfönstret.
1. Välj **Strukturlisteversioner**.

## <a name="create-new-bom-and-bom-version"></a>Skapa en ny strukturlista och strukturlisteversion

1. Välj **Ny**.
1. Välj **Strukturlista och strukturlisteversion**.
1. Skriv ett värde i fältet **Namn**.
    * Ange en site  
    * I den här proceduren anger vi inte en specifik site för strukturlistan.  
1. Välj **OK**.
1. Välj **Ny**.
    * I den här proceduren kommer vi att lägga till fyra rader i strukturlistan. Två rader representerar kabelalternativ, och två rader representerar skåpalternativ.  
1. Markera vald rad i listan.
1. I fältet **artikelnummer** anger du eller väljer ett värde.
    * Välj artikelnummer A0001, HDMI 6 tums kablar.  
1. I fältet **Konfigurationsgrupp** anger eller väljer du ett värde.
    * Välj kabelkonfigurationsgruppen som skapas i guide 4 i denna sekvens.  
1. Välj **Ny**.
    * Välj artikelnummer A0002, HDMI 12 tums kablar.  
1. Markera vald rad i listan.
1. I fältet **artikelnummer** anger du eller väljer ett värde.
1. I fältet **Konfigurationsgrupp** anger eller väljer du ett värde.
    * Markera kabelkonfigurationsgruppen igen.  
1. Välj **Ny**.
1. Markera vald rad i listan.
1. I fältet **artikelnummer** anger du eller väljer ett värde.
    * Välj artikelnummer D0002 Skåp.  
1. I fältet **Konfigurationsgrupp** anger eller väljer du ett värde.
    * Välj skåpkonfigurationsgruppen för denna strukturlisterad.  
1. Välj **Ny**.
1. Markera vald rad i listan.
1. I fältet **artikelnummer** anger du eller väljer ett värde.
    * Välj artikelnummer M0007 Standardskåp som sista strukturlisteraden.  
1. I fältet **Konfigurationsgrupp** anger eller väljer du ett värde.
    * Välj skåpkonfigurationsgruppen för den sista strukturlisteraden.  

## <a name="approve-and-activate"></a>Godkänn och aktivera

1. Stäng sidan.
1. Välj **Godkänn**.
1. I fältet **Godkändes av** anger eller väljer du ett värde.
1. Välj *Ja* i fältet **Vill du även godkänna strukturlistan?**.
1. Välj **OK**.
1. Välj **aktivera**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]