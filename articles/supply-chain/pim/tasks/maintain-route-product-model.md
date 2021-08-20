---
title: Underhåll flöde för produktkonfigurationsmodellen
description: När du kör den här proceduren krävs det att det finns en modell för produktkonfiguration.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 704a6b72c9eb8dc49ba9410ccd3689ba5ccfdd1f03e538b95ad174f6c1ee9796
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746146"
---
# <a name="maintain-route-for-a-product-model"></a>Underhåll flöde för produktkonfigurationsmodellen

[!include [banner](../../includes/banner.md)]

När du kör den här proceduren krävs det att det finns en modell för produktkonfiguration. I den här proceduren använder högtalarmodellen i demonstrationsföretaget USMF.

## <a name="add-a-route-operation"></a>Lägga till en flödesoperation

1. Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.
1. Hitta och markera önskad post i listan.
    * Välj högtalarmodellen till den här övningen.  
1. Klicka på länken på önskad rad i valda listan.
1. Expandera avsnittet **Flödesfunktioner**.
1. Markera **Lägg till**.
1. Skriv ett värde i fältet **Namn**.
1. I fältet **Beskrivning** anger du ett värde.
1. Välj **Spara**.

## <a name="enter-route-operation-details"></a>Ange flödesoperationsinformation

1. Välj **Information om flödesfunktioner**.
1. Ange eller välj ett värde i fältet **Funktion**.
1. I fältet **Funktionsnr.** fältet anger du ett tal.
    * Operationsnummer bestämmer ordningsföljden.  
    * Varje egenskap i en flödesoperation kan få ett statiskt värde eller mappas till ett attribut. Mappning till ett attribut leder till att värdet ställs in dom en del av konfigurationen.  
1. Ange eller välj ett värde i fältet **Flödesgrupp**.
    * Flödesgruppen bestämmer beteendet för kostnadsredovisning, förbrukning och inställning.  
1. Välj fliken **Inställningar**.
1. Välj fliken **Tider**.
1. I fältet **Processkvantitet** anger du ett värde.
    * Bestäm hur många som ska bearbetas under en operation.  
1. I fältet **Timmar/tid** anger du ett värde.
    * Ange en tid.  
1. Markera kryssrutan **Ställ in**.
1. I fältet **Körningstid** anger du ett värde.
    * Bestäm bearbetningstiden för den kvantitet som du har angett.  
1. Välj fliken **Resurskrav**.
1. Markera **Lägg till**.
1. Markera vald rad i listan.
1. I fältet **Kravtyp** väljer du ett alternativ.
    * Bestäm om du vill ange specifika resurser eller kvalifikationer som de måste ha.  
1. I fältet **Krav** anger eller väljer du ett värde.
1. Välj **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]