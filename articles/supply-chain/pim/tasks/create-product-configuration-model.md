---
title: Skapa en produktkonfigurationsmodell
description: I den här proceduren visas hur du skapar en modell för produktkonfiguration och anger grundläggande information som attribut och delkomponenter.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca99c0346a3f982164076167c3429587aac18be6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568434"
---
# <a name="create-a-product-configuration-model"></a>Skapa en produktkonfigurationsmodell

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar en modell för produktkonfiguration och anger grundläggande information som attribut och delkomponenter. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-a-product-model"></a>Skapa en produktmodell

1. Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.
1. Välj **Ny**.
1. Skriv ett värde i fältet **Namn**.
1. I fältet **Beskrivning** anger du ett värde.
1. I fältet **Problemlösarstrategi** väljer du ett alternativ.
    * Problemlösarstrategin bestämmer hur begränsningarna i en begränsningsbaserad modell för produktkonfiguration bearbetas. Det här valet kan påverka resultatet av produktkonfigurationsmodellen.  
1. Skriv ett värde i fältet **Namn**.
    * Rotkomponenten representerar produktkonfigurationsmodellen, men den kan även användas i andra produktmodeller.  
1. Välj **OK**.
1. Välj ett alternativ i fältet **Återanvänd konfigurationer**.
    * Om parametern för återanvändningskonfiguration ställs in på Ja, söker systemet efter identiska konfigurationer efter varje konfigurationssession och återanvänder om en exakt matchning hittas.  

## <a name="add-attributes"></a>Lägg till attribut

1. Visa avsnittet **Attribut**.
2. Markera **Lägg till**.
3. Markera vald rad i listan.
4. Skriv ett värde i fältet **Namn**.
5. Ange ett värde i fältet **Problemlösarnamn**.
    * Problemlösarnamnet används av begränsningslösaren för produktkonfigureraren. Det får inte innehålla blanksteg eller specialtecken utom _(understreck).  
6. I fältet **Beskrivning** anger du ett värde.
    * Beskrivningstexten visas för konfigurationsanvändaren och kan därför fungera som hjälp när rätt attributvärde ska väljas.  
7. Ange eller välj ett värde i fältet **Attributtyp**.
    * Attributtypen avgör vilka värden som är tillgängliga för attributet.  
8. Markera kryssrutan **Inkludera i återanvändning**.
    * Det här alternativet är endast tillgängligt när alternativet Återanvänd konfigurationer har valts. Kryssrutan för inkludering av attributet i återanvändningen innebär att attribut övervägs när systemet söker efter en exakt träff.  

## <a name="add-subcomponents"></a>Lägg till delkomponenter

1. Utöka avsnittet **Delkomponenter**.
2. Markera **Lägg till**.
3. Markera vald rad i listan.
4. Skriv ett värde i fältet **Namn**.
5. Ange ett värde i fältet **Problemlösarnamn**.
6. I fältet **Beskrivning** anger du ett värde.
7. Ange eller välj ett värde i fältet **Komponent**.
    * Varje delkomponent måste referera till en komponentdefinition. Den här designen stöder återvinningsbara komponenter och innebär att när en komponent har definierats så kan den användas i många produktmodeller.  
8. Välj **Spara**.
9. Välj **Detaljerad information för strukturlisterader**.
    * Raddetaljerna för strukturlistan gör att användaren kan välja egenskaper för delkomponenten. Varje egenskap kan ges ett fast värde eller mappas till ett attribut. Mappning till ett attribut leder till att radegenskapen för strukturlistan får olika värden beroende konfigurationsvalet.  
10. I fältet **artikelnummer** anger du eller väljer ett värde.
    * Varje delkomponent representerar en konfigurerbar produktmall med begränsningsbaserad konfigurationsteknik. Referensen görs via artikelnumret.  
11. Markera kryssrutan **Ställ in**.
12. Välj **Ja** i fältet **Beräkning**.
    * Att ställa in beräkningsalternativet gör att produkten tas med när en kostnadsberäkning förs för produkten.  
13. Välj fliken **Inställningar**.
14. Markera kryssrutan **Ställ in**.
15. Ange ett nummer i fältet **Kvantitet**.
    * Kvantitetsfältet bestämmer hur mycket av den här produkten som ska förbrukas i den konfigurerade produkten.  
16. Markera kryssrutan **Ställ in**.
17. Ange ett värde i fältet **Per serie**.
18. Välj **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]