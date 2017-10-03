--- 
title: "Ställ in policyer för hierarkier för anskaffningskategorier"
description: "Använd den här proceduren för att ställa in regler för att beställa produkter i en kategori."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5ad4c448077ef9cf40555d39bb69c3ba8e2bce1e
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>Ställ in policyer för hierarkier för anskaffningskategorier

[!include[task guide banner](../../includes/task-guide-banner.md)]

Använd den här proceduren för att ställa in regler för att beställa produkter i en kategori. Policyreglerna definieras för en specifik inköpspolicy. Åtkomstregeldata kontrollerar vilka anskaffningskategorier som anställda har åtkomst till när de skapar en rekvisition. När en rekvisition skapas fastställs den inköpspolicy och den kategoriåtkomstregel som ska användas av den juridiska person och den driftenhet som medarbetaren tillhör. Du kan köra den här proceduren i demonstrationsdataföretaget USMF. Denna uppgift utförs vanligtvis av en inköpschef.


## <a name="find-the-procurement-policy"></a>Hitta anskaffningpolicyn
1. Gå till anskaffning och källa > Inställningar > Policyer > Inköpspolicyer.
2. Klicka på länken för anskaffningspolicy USMF.
    * Detta är policyn som du vill lägga till en regel till. Den måste vara en aktiv policy.  

## <a name="create-a-category-access-rule"></a>Skapa en kategoriåtkomstregel
1. Välj Policyregel för kategoriåtkomst.
    * Om knappen Skapa policyregel tonasned är det på grund av att det redan finns en aktiv policyregel för Kategoriåtkomst. Kontrollera fälten Giltighet och Utgångsdatum för att bestämma vilket den är, sedan väljer du den och klickar på Dra tillbaka policyregel. Om knappen Skapa policyregel är tillgänglig behöver du inte att göra någonting.  
2. Klicka på Skapa policyregel.
3. Ange datum och tid i fältet Giltighetsdatum.
    * Tiden får inte överlappa med en annan regel som redan är aktiv.  
    * Välj en kategori som regeln ska gälla för. Gör en notering av vilken kategori detta är – du behöver den senare. När du väljer en kategori kommer alla dess överordnade kategorier också att läggas till i listan för Valda kategorier.  
    * Om du vill att regeln ska gälla alla underkategorier för den valda kategorin, markerar du kryssrutan Inkludera underkategorier.  
4. Klicka på Lägg till.
    * Om du ställer in alternativet Inkludera överordnad regel kommer policyregeln som du definierar för en överordnad kategori också att tilldelas till dess underordnade kategorier, om ingen policyregel har definierats för de underordnade kategorierna.  
5. Klicka på OK.

## <a name="create-a-category-policy-rule"></a>Skapa en kategoripolicyregel
1. Välj Policyregel för kategoriåtkomst
    * Om knappen Skapa policyregel är nedtonad väljer du den aktiva policyregeln och klickar sedan på Dra tillbaka policyregel.  
2. Klicka på Skapa policyregel.
3. Ange datum och tid i fältet Giltighetsdatum.
4. Klicka på Lägg till.
5. Markera samma kategori som du använde för kategoriåtkomstregeln.
6. Välj ett alternativ i fältet Leverantörsurval.
    * Välj en regel för att kontrollera vilken typ av leverantörer som kan väljas för kategorin, när rekvisitioner skapas.  
7. Klicka på Stäng.
    * De policyregler som du har definierat har varit för rekvisitioner av typen Förbrukning. Om du vill definiera policyer för rekvisitioner av typen Återanskaffning, ska du skapa en regel för Policyregeltypen som kallas "Åtkomstpolicyregel för återanskaffningskategori".  


