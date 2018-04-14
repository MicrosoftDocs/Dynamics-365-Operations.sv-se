--- 
title: "Ställ in en anskaffningskategorihierarki"
description: "I den här proceduren visas hur du skapar nya noder i en anskaffningskategorihierarki och hur du konfigurerar en anskaffningskategori som ska användas i en anskaffningsprocess."
author: mkirknel
manager: AnnBe
ms.date: 11/06/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 6ad5c8552a6989e9093d0b1325754bc0f6d19372
ms.openlocfilehash: 4541d029c9c3be3ee42332e5d8ff183dd503f13e
ms.contentlocale: sv-se
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-a-procurement-category-hierarchy"></a>Ställ in en anskaffningskategorihierarki

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar nya noder i en anskaffningskategorihierarki och hur du konfigurerar en anskaffningskategori som ska användas i en anskaffningsprocess. Dessa uppgifter utförs vanligtvis av en inköpschef. Innan du kan starta den här proceduren måste det finnas en kategorihierarki av typen anskaffning. Om du använder ett demonstrationsdataföretag kan du köra denna procedur i USMF-företaget.


## <a name="add-a-new-procurement-category"></a>Lägg till en ny anskaffningskategori.
1. Gå till Anskaffning och källa > Anskaffningskategorier.
2. Klicka på Redigera kategorihierarki.
    * Den aktuella anskaffningskategorihierarkin visas till vänster på sidan. Du är på väg att ändra hierarkin.  
3. Klicka på Ny kategorinod.
    * Systemet väljer toppnoden som standard. Om du kör den här proceduren som en uppgiftsguide kan du klicka på fliken Lås upp och välja en annan överordnad nod att infoga den nya noden i. Lås uppgifthandboken igen och klicka på noden Ny kategori när det är klart.  
4. Skriv ett värde i fältet Namn.
5. Ange ett värde i fältet Beskrivning.
6. Skriv ett värde i fältet Eget namn.
    * Det egna namnet är valfritt. Detta visas i kategorisökningar tillsammans med kategorinamnet.  
7. Klicka på Spara.

## <a name="add-products-to-your-new-procurement-category"></a>Lägg till produkter i den nya anskaffningskategorin
1. Gå till Anskaffning och källa > Anskaffningskategorier.
    * Välj den nod som du precis lade till. Om du kör den här proceduren som en uppgiftsguide kanske du behöver låsa upp uppgiftsguiden för att välja noden.  
2. Växla expansionen av avsnittet Produkter.
3. Klicka på Lägg till i associerade produkter med anskaffningskategorin.
4. Välj den produkt som du vill lägga till i anskaffningskategorin.
5. Klicka på pilen för att välja produkten.
6. Välj en annan produkt som du vill lägga till i anskaffningskategorin.
7. Klicka på pilen för att välja produkten.
8. Klicka på OK.

## <a name="add-approved-and-preferred-vendors"></a>Lägg till godkända och prioriterade leverantörer
1. Växla utökningen av avsnittet Leverantörer.
2. Klicka på Lägg till.
    * Du kan lägga till en leverantör i en anskaffningskategori och ange om en leverantör är prioriterad eller precis godkänd för kategorin. När du tar bort en leverantör från en kategori, tas historiska transaktioner med leverantör i kategorin inte bort.   
3. Sök efter den leverantör som du vill lägga till i kategorin.
4. Klicka på pilen för att välja leverantören.
5. Klicka på OK.
6. Välj den leverantörsrad som du vill ändra.
7. Välj ett alternativ i fältet Leverantörsstatus.
    * Inställningen av leverantörsurval i kategoripolicyregeln styr om prioriterade, godkända eller alla leverantörer är tillgängliga på inköpsrekvisitioner.   

## <a name="add-additional-information-to-the-category"></a>Lägg till ytterligare information till kategorin
1. Växla expansionen av avsnittet Kriteriegrupper för leverantörsutvärdering.
    * På den här fliken kan du definiera vilka kriterier som leverantörerna i anskaffningskategorin ska bedömas mot. Om du vill göra det måste du först klicka på Lägg till och sedan välja en leverantörsutvärderingsgrupp som innehåller de kriterier du vill använda.  
2. Växla utökningen av avsnittet Enkäter.
    * På den här fliken kan du lägga till enkäter som ska visas på rekvisitionen så länge som du har ställt in aktivitetstypen till ”Rekvisition”. Beställaren måste sedan fylla i ett frågeformulär innan han/hon skickar en rekvisition för den specifika produkten eller produkterna i anskaffningskategorin.  
3. Växla expansionen av avsnittet Artikelmomsgrupper.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.
5. Välj en momsgrupp.
6. Växla utökningen av avsnittet Kategorisida.
    * Kategorisidor skapas på sidan Kategorihierarki. De innehåller information om anskaffningskategorin, till exempel information om typen av produkter i en kategori, bilder av produkter i en kategori eller meddelanden som till exempel vilka rabatter som är tillgängliga i en kategori. Informationen på en kategorisida visas på inköpsrekvisitioner.  
7. Stäng sidan.


