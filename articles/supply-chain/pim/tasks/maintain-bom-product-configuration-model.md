---
title: Underhåll strukturlista för produktkonfigurationsmodell
description: När du kör den här proceduren krävs en befintlig modell för produktkonfiguration.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4ad73265e321b6339c061a7866b55cb2769954b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921327"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Underhåll strukturlista för produktkonfigurationsmodell

[!include [banner](../../includes/banner.md)]

När du kör den här proceduren krävs en befintlig modell för produktkonfiguration. Högtalarmodellen i demonstrationsföretaget USMF används för att skapa den här proceduren.

## <a name="add-a-bom-line"></a>Lägga till en strukturlisterad

1. Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.
1. Hitta och markera önskad post i listan.
    * Välj den avancerade högtalaren till proceduren.  
1. Klicka på länken på önskad rad i valda listan.
1. Expandera avsnittet **Strukturlisterader**.
1. Markera **Lägg till**.
1. Skriv ett värde i fältet **Namn**.
1. I fältet **Beskrivning** anger du ett värde.
1. Välj **Spara**.

## <a name="add-bom-line-details"></a>Lägga till information om strukturlisterad

1. Välj **Detaljerad information för strukturlisterader**.
2. I fältet **artikelnummer** anger du eller väljer ett värde.
    * Du kan till exempel välja artikeln M0055.  
    * För varje strukturlisteradsegenskap kan du välja om det behövs ett fast värde eller om det ska mappas till ett attribut.  
3. Markera kryssrutan **Ställ in**.
4. Välj *Ja* i fältet **Beräkning**.
    * När du ställer in egenskapen **Beräkning** som *Ja* garanteras att strukturlisteraden inkluderas i avgiftsberäkningarna.  
5. Välj fliken **Inställningar**.
6. Markera kryssrutan **Ställ in**.
7. Ange ett nummer i fältet **Kvantitet**.
    * Kvantitetsfältet bestämmer hur mycket av artikeln som ska inkluderas i strukturlistan. Detta kan vara en uppenbar kandidat till en attributmappning.  
8. Välj fliken **Dimension**.
    * Kontrollera om någon av produktdimensionerna är aktiva, och därför måste ha ett värde eller ett attribut.  
9. Välj **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]