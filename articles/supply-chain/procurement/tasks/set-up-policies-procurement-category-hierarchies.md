---
title: Ställ in policyer för hierarkier för anskaffningskategorier
description: Använd den här proceduren för att ställa in regler för att beställa produkter i en kategori.
author: mkirknel
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicy, ProcCategoryAccessPolicyRule, ProcCategoryPolicyRule, EcoResCategorySingleLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8c259ad081d02395c6ae3c3b7cf66b89933fdf
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149514"
---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>Ställ in policyer för hierarkier för anskaffningskategorier

[!include [banner](../../includes/banner.md)]

Använd den här proceduren för att ställa in regler för att beställa produkter i en kategori. Policyreglerna definieras för en specifik inköpspolicy. Åtkomstregeldata kontrollerar vilka anskaffningskategorier som anställda har åtkomst till när de skapar en rekvisition. När en rekvisition skapas fastställs den inköpspolicy och den kategoriåtkomstregel som ska användas av den juridiska person och den driftenhet som medarbetaren tillhör. Du kan köra den här proceduren i demonstrationsdataföretaget USMF. Denna uppgift utförs vanligtvis av en inköpschef.


## <a name="find-the-procurement-policy"></a>Hitta anskaffningpolicyn
1. I navigeringsfönstret går du till **moduler > anskaffning och källa > inställningar > principer > inköpspolicyer**.
2. Klicka på länken för anskaffningspolicy USMF. Detta är policyn som du vill lägga till en regel till. Den måste vara en aktiv policy.  

## <a name="create-a-category-access-rule"></a>Skapa en kategoriåtkomstregel
1. Expandera snabbfliken **Policyregler**.
2. I listan **Policyregeltyp** väljer du **policyregel för kategoriåtkomst**. Om knappen **Skapa policyregel** tonas ned är det på grund av att det redan finns en aktiv policyregel för Kategoriåtkomst. Kontrollera fälten **Giltighet** och **Utgångsdatum** för att bestämma vilket den är, sedan väljer du den och klickar på **Dra tillbaka policyregel**. Om knappen **Skapa policyregel** är tillgänglig behöver du inte att göra någonting.  
3. Klicka på **Skapa regel för policyn.**
4. I fältet **Gäller från** anger du datum och tid. Tiden får inte överlappa med en annan regel som redan är aktiv.  
5. Välj en kategori som regeln ska gälla för. Gör en notering av vilken kategori detta är – du behöver den senare. När du väljer en kategori kommer alla dess överordnade kategorier också att läggas till i listan för Valda kategorier. Om du vill att regeln ska gälla alla underkategorier för den valda kategorin, markerar du kryssrutan **Inkludera underkategorier**.
6. Klicka på högerpilen för att lägga till listan **valda kategorier**.  
4. Klicka på **OK**. Om du ställer in alternativet **Inkludera överordnad regel** kommer policyregeln som du definierar för en överordnad kategori också att tilldelas till dess underordnade kategorier, om ingen policyregel har definierats för de underordnade kategorierna.

## <a name="create-a-category-policy-rule"></a>Skapa en kategoripolicyregel
1. I listan **Policyregeltyp** väljer du **policyregel för kategori**. Om knappen **Skapa policyregel** är nedtonad väljer du den aktiva policyregeln och klickar sedan på **Dra tillbaka policyregel**.  
2. Klicka på **Skapa regel för policyn.**
3. I fältet **Gäller från** anger du datum och tid.
4. Klicka på **Lägg till**.
5. I fältet **kategori** välj samma kategori som du använde för **kategoriåtkomstregel**.
6. I fältet **Leverantörsurval** väljer du ett alternativ. Välj en regel för att kontrollera vilken typ av leverantörer som kan väljas för kategorin, när rekvisitioner skapas.  
7. Klicka på **Stäng**. De policyregler som du har definierat har varit för rekvisitioner av typen Förbrukning. Om du vill definiera policyer för rekvisitioner av typen Återanskaffning, ska du skapa en regel för Policyregeltypen som kallas "Åtkomstpolicyregel för återanskaffningskategori".  

