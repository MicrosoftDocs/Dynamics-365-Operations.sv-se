---
title: Ställ in attributbaserad prissättning för konfigurerbara produkter
description: I det här avsnittet visas hur du ställer in attributbaserad prissättning.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5abb2e7dc33b46589c1a3699e70b56af6f694aed49294eb81a2122db6d414a96
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743564"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Ställ in attributbaserad prissättning för konfigurerbara produkter

[!include [banner](../../includes/banner.md)]

I det här avsnittet visas hur du ställer in attributbaserad prissättning. Som en förutsättning måste du ha en modell för produktkonfiguration som har en eller flera komponenter och attribut. Detta exempel använder produktmodellen High End Speaker i demonstrationsföretaget USMF. Vanligtvis använder en produktchef denna procedur.


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