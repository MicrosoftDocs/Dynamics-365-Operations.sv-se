---
title: Ställa in attributbaserad prissättning för konfigurerbara produkter
description: I denna artikel visas hur du konfigurerar attributbaserad prissättning.
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec16a0a8078cddd433c99592aa4a7474cf923aec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849399"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Ställa in attributbaserad prissättning för konfigurerbara produkter

[!include [banner](../../includes/banner.md)]

I denna artikel visas hur du konfigurerar attributbaserad prissättning. Som en förutsättning måste du ha en modell för produktkonfiguration som har en eller flera komponenter och attribut. Detta exempel använder produktmodellen High End Speaker i demonstrationsföretaget USMF. Vanligtvis använder en produktchef denna procedur.


## <a name="create-a-new-price-model"></a>Skapa en ny prismodell

1. Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.
1. Välj raden **High End Speaker** i listan, men välj inte länken för namn.
1. Klicka på **Modell** i åtgärdsfönstret.
1. Välj **Prismodeller**.
1. Välj **Ny**.
1. Ange ett värde i fältet **Prismodellnamn**. Använd ett namn som gör modellen enkel att identifiera.  
1. I fältet **Beskrivning** anger du ett värde.
1. Välj **Spara**.

## <a name="add-price-elements"></a>Lägg till priselement

1. Välj **Redigera**. Varje komponent i en produktmodell kan ha ett grundpriselement och ett valfritt antal prisuttrycksregler. Du kan också lägga till priser i olika valutor.  
2. Ange ett värde i fältet **Grundprisuttryck**. Ange till exempel 100. Ett grundprisuttryck kan utgöras av ett numeriskt värde eller bestå av en aritmetisk beräkning som gäller ett eller flera attribut.  
3. Markera **Lägg till**.
4. I fältet **Namn** skriver du `Rosewood`. Namnet för prisuttrycket hjälper till att identifiera det som priselementet representerar. I detta exempel skapar vi ett priselement för alternativet med rosenträfinish på högtalarkabinettet.  
5. Välj **Redigeringsvillkor**. Ett prisvillkor hjälper till att säkerställa att ett prisuttryckselement ingår i försäljningspriset endast om en specifik attributkombination förekommer.  
6. Ange `CabinetFinish=="Rosewood"` i fältet **ConstraintBody**.
7. Välj **OK**.
8. Ange ett värde i fältet **Uttryck**. Ange till exempel `50`. 
9. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]