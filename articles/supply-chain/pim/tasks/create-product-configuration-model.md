--- 
title: Skapa en produktkonfigurationsmodell
description: "I den här proceduren visas hur du skapar en modell för produktkonfiguration och anger grundläggande information som attribut och delkomponenter."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: d494a20ba6f1f9c33a3935779b4bd3a8eefce26a
ms.contentlocale: sv-se
ms.lasthandoff: 11/14/2017

---
# <a name="create-a-product-configuration-model"></a>Skapa en produktkonfigurationsmodell

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar en modell för produktkonfiguration och anger grundläggande information som attribut och delkomponenter. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-a-product-model"></a>Skapa en produktmodell
1. Klicka på Definition av produktvariantmodell.
2. Klicka på Modeller för produktkonfiguration.
3. Klicka på Ny.
4. Skriv ett värde i fältet Namn.
5. Ange ett värde i fältet Beskrivning.
6. Markera ett alternativ i fältet Lösarstrategi.
    * Problemlösarstrategin bestämmer hur begränsningarna i en begränsningsbaserad modell för produktkonfiguration bearbetas. Det här valet kan påverka resultatet av produktkonfigurationsmodellen.  
7. Skriv ett värde i fältet Namn.
    * Rotkomponenten representerar produktkonfigurationsmodellen, men den kan även användas i andra produktmodeller.  
8. Klicka på OK.
9. Markera ett alternativ i fältet Återanvänd konfigurationer.
    * Om parametern för återanvändningskonfiguration ställs in på Ja, söker systemet efter identiska konfigurationer efter varje konfigurationssession och återanvänder om en exakt matchning hittas.  

## <a name="add-attributes"></a>Lägg till attribut
1. Expandera avsnittet Attribut.
2. Klicka på Lägg till.
3. Markera vald rad i listan.
4. Skriv ett värde i fältet Namn.
5. Skriv ett värde i fältet Lösarnamn.
    * Problemlösarnamnet används av begränsningslösaren för produktkonfigureraren. Det får inte innehålla blanksteg eller specialtecken utom _(understreck).  
6. Ange ett värde i fältet Beskrivning.
    * Beskrivningstexten visas för konfigurationsanvändaren och kan därför fungera som hjälp när rätt attributvärde ska väljas.  
7. Ange eller välj ett värde i fältet Attributtyp.
    * Attributtypen avgör vilka värden som är tillgängliga för attributet.  
8. Markera kryssrutan Inkludera i återanvändning.
    * Det här alternativet är endast tillgängligt när alternativet Återanvänd konfigurationer har valts. Kryssrutan för inkludering av attributet i återanvändningen innebär att attribut övervägs när systemet söker efter en exakt träff.  

## <a name="add-subcomponents"></a>Lägg till delkomponenter
1. Utöka avsnittet Delkomponenter.
2. Klicka på Lägg till.
3. Markera vald rad i listan.
4. Skriv ett värde i fältet Namn.
5. Skriv ett värde i fältet Lösarnamn.
6. Ange ett värde i fältet Beskrivning.
7. Ange eller välj ett värde i fältet Komponent.
    * Varje delkomponent måste referera till en komponentdefinition. Den här designen stöder återvinningsbara komponenter och innebär att när en komponent har definierats så kan den användas i många produktmodeller.  
8. Klicka på Spara.
9. Klicka på Information för strukturlisterad.
    * Raddetaljerna för strukturlistan gör att användaren kan välja egenskaper för delkomponenten. Varje egenskap kan ges ett fast värde eller mappas till ett attribut. Mappning till ett attribut leder till att radegenskapen för strukturlistan får olika värden beroende konfigurationsvalet.  
10. Ange eller välj ett värde i fältet Artikelnummer.
    * Varje delkomponent representerar en konfigurerbar produktmall med begränsningsbaserad konfigurationsteknik. Referensen görs via artikelnumret.  
11. Markera kryssrutan Uppsättning.
12. Välj Ja i fältet Beräkning.
    * Att ställa in beräkningsalternativet gör att produkten tas med när en kostnadsberäkning förs för produkten.  
13. Klicka på fliken Inställningar.
14. Markera kryssrutan Uppsättning.
15. Ange ett tal i fältet Kvantitet.
    * Kvantitetsfältet bestämmer hur mycket av den här produkten som ska förbrukas i den konfigurerade produkten.  
16. Markera kryssrutan Uppsättning.
17. Ange ett värde i fältet Per serie.
18. Klicka på OK.


