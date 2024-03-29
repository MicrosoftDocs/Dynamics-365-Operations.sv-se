---
title: Servicenivå och beskrivning
description: I denna artikel beskrivs servicenivå och beskrivning i Tillgångshantering.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 753ad36b1d01d1ce0594f477cf863ca0e4a1ac75
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879204"
---
# <a name="service-level-and-description"></a>Servicenivå och beskrivning

[!include [banner](../../includes/banner.md)]

 

När du skapar en arbetsorder kanske du vill definiera servicenivåerna för den och lägga till en allmän beskrivning i den. Du kan skapa servicenivåer för arbetsorder på sidan **Servicenivåer för arbetsorder** och beskrivningar på sidan **Arbetsorderbeskrivning**.

## <a name="create-a-service-level"></a>Skapa en servicenivå

1. Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Servicenivå**.
2. Välj **Ny**.
3. I fältet **Servicenivå** anger du servicenivå (t.ex. en siffra).
4. Ange sedan ett namn i fältet **Namn**.

    På snabbfliken **Arbetsorder** kan du definiera förväntade start-och slutdatum och start- och sluttider. Fälten på den här snabbfliken definierar den period som arbetsorder ska startas och avslutas under. De används för arbetsorder som skapas manuellt och arbetsorder som skapas baserat på underhållsbegäranden. 

5. I fältet **Startdag** anger du ett antal dagar för att definiera den period som arbetsordern ska starta under. Antalet dagar beräknas från arbetsorderns skapandedatum. Om till exempel arbetsordern ska starta när den skapas anger du **0**. Om arbetsordern ska starta inom en vecka efter att den skapats anger du **7**.
6. Om du vill ange en starttid för arbetsordern, utöver startdatumet, ställer du in alternativet **Ange starttid** till **Ja**. Ange starttiden i fältet **Starttid**. Om du konfigurerar alternativet till **Nej**, används den aktuella tiden på dagen.
7. I fältet **Slutdag** anger du ett antal dagar för att definiera den period som arbetsordern ska sluta under. Antalet dagar beräknas från arbetsorderns startdatum. Om arbetsordern t.ex. ska sluta inom en vecka efter startdatum anger **7**.
8. Om du vill ange en sluttid för arbetsordern, utöver slutdatumet, ställer du in alternativet **Ange sluttid** till **Ja**. Ange sluttiden i fältet **Sluttid**. Om du konfigurerar alternativet till **Nej**, används den aktuella tiden på dagen.
9. Välj **Spara**.

![Sidan Servicenivå för arbetsorder.](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a>Skapa en beskrivning

1. Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Beskrivningar**.
2. Välj **Ny**.
3. Ange en beskrivning i fältet **Beskrivning**.
4. Välj **Spara**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]