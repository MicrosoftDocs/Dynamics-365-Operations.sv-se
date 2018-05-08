--- 
title: "Skapa en strukturlista för en dimensionsbaserad produktmall"
description: "För den här proceduren bör du ha slutfört de tidigare 4 guiderna i denna sekvens av åtta inspelningar."
author: YuyuScheller
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8b5432addd1dd79a64dcbb751a59cf3084a63ab1
ms.openlocfilehash: 05837c2b21957133729074f614a6d3d7b7c08dad
ms.contentlocale: sv-se
ms.lasthandoff: 11/04/2017

---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Skapa en strukturlista för en dimensionsbaserad produktmall

[!include [task guide banner](../../includes/task-guide-banner.md)]

För den här proceduren bör du ha slutfört de tidigare 4 guiderna i denna sekvens av åtta inspelningar. De första 4 inspelningarna anger de data som krävs för att slutföra den här proceduren. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Denna uppgift utförs vanligtvis av produktdesignern.


## <a name="select-the-product"></a>Välj produkten
1. Klicka på Underhåll av frisläppt produkt.
2. Klicka på Frisläppta produkter.
3. Markera vald rad i listan.
    * Hitta den frisläppta produktmallen med dimensionsbaserad konfigurationsteknologi som du skapade i den första uppgiftsguiden i denna sekvens.  
4. Klicka på Konstruera i åtgärdsfönstret.
5. Klicka på Strukturlisteversioner.

## <a name="create-new-bom-and-bom-version"></a>Skapa en ny strukturlista och strukturlisteversion
1. Klicka på Ny.
2. Klicka på strukturlista och strukturlisteversion.
3. Skriv ett värde i fältet Namn.
    * Ange en site  
    * I den här proceduren anger vi inte en specifik site för strukturlistan.  
4. Klicka på OK.
5. Klicka på Ny.
    * I den här proceduren kommer vi att lägga till fyra rader i strukturlistan. Två rader representerar kabelalternativ, och två rader representerar skåpalternativ.  
6. Markera vald rad i listan.
7. Ange eller välj ett värde i fältet Artikelnummer.
    * Välj artikelnummer A0001, HDMI 6 tums kablar.  
8. Ange eller välj ett värde i fältet Konfigurationsgrupp.
    * Välj kabelkonfigurationsgruppen som skapas i guide 4 i denna sekvens.  
9. Klicka på Ny.
    * Välj artikelnummer A0002, HDMI 12 tums kablar.  
10. Markera vald rad i listan.
11. Ange eller välj ett värde i fältet Artikelnummer.
12. Ange eller välj ett värde i fältet Konfigurationsgrupp.
    * Markera Kabelkonfigurationsgruppen igen.  
13. Klicka på Ny.
14. Markera vald rad i listan.
15. Ange eller välj ett värde i fältet Artikelnummer.
    * Välj artikelnummer D0002 Skåp.  
16. Ange eller välj ett värde i fältet Konfigurationsgrupp.
    * Välj Skåpkonfigurationsgruppen för den här strukturlisteraden.  
17. Klicka på Ny.
18. Markera vald rad i listan.
19. Ange eller välj ett värde i fältet Artikelnummer.
    * Välj artikelnummer M0007 Standardskåp som sista strukturlisteraden.  
20. Ange eller välj ett värde i fältet Konfigurationsgrupp.
    * Välj eller Skåpkonfigurationsgrupp för den sista strukturlisteraden.  

## <a name="approve-and-activate"></a>Godkänn och aktivera
1. Stäng sidan.
2. Klicka på Godkänn.
3. Ange eller välj ett värde i fältet Godkänd.
4. Välj ja i fältet Vill du även godkänna strukturlistan? .
5. Klicka på OK.
6. Klicka på Aktivera.


