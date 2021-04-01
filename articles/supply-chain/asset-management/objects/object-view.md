---
title: Tillgångsvy
description: I detta avsnitt beskrivs tillgångsvy i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTree, EntAssetFunctionalLocationTree
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a770831c564d44de534642cc462b27b0818e9a2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253120"
---
# <a name="asset-view"></a>Tillgångsvy

[!include [banner](../../includes/banner.md)]

 

I detta avsnitt beskrivs tillgångsvy i Tillgångshantering. Sidan **Tillgångsvy** visar aktiva tillgångar och funktionsplatser i en trädvy. Därför kan du enkelt få en översikt över tillgångsrelationer till funktionsplatser. Dessutom kan du visa detaljerad information om funktionsplatser, tillgångar och relaterade strukturlistor. Du kan också få en snabb överblick över aktiva underhållsbegäranden och arbetsorder som är relaterade till en tillgång.

1. Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Tillgångsvy**
2. Om du vill ändra vyn som visas på sidan väljer du ett nytt värde i fältet **Vy**.

    > [!NOTE]
    > Standardvyn som visas när du öppnar sidan **Tillgångsvy** beror på värdet som valts i fältet **Vy** på fliken **tillgångar** på sidan **parametrar för tillgångshantering** (**tillgångshantering** \> **inställning** \> **parametrar för tillgångshantering**).

Till höger på sidan visar snabbflikar information om den valda vyn.

Navigeringssökvägen som visas ovanför trädvyn visar den aktuella markeringen i trädvyn. Denna navigeringssökväg använder följande format:

Funktionellt plats-ID/funktionellt plats-ID (om det finns fler än en funktionsplats) \> tillgångs-ID/tillgångs-ID (om det finns mer än en tillgång) - artikelnummer.

Om du har valt en tillgång i trädvyn kan du välja **aktiva begäranden** eller **aktiva arbetsorder** för att visa de underhållsbegäranden eller arbetsorder som är relaterade till tillgången. Du kan också välja **öppna** \> **funktionsplats**, **tillgång** eller **tillgångsstruktur** för att öppna den relaterade vyn.

Alternativet **funktionsplatser för tillgång** som du kan välja i fältet **Vy** är också tillgängligt i alla tillgångssökning där du kan välja en tillgång. Trädvyn visas på fliken **tillgångsvy**, till exempel där du [skapar en tillgång](../objects/create-an-object.md), skapar en underhållsbegäran eller skapar en arbetsorder.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]