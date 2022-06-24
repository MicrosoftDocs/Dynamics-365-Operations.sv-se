---
title: Typer av arbetsorder
description: Denna artikel innehåller förklaringar av arbetsordertyper i Tillgångshantering.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 12745960f903ebc14208f2c8a01f076ed27a38d3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891188"
---
# <a name="work-order-types"></a>Typer av arbetsorder

[!include [banner](../../includes/banner.md)]

 

Arbetsordertyper används för att kategorisera arbetsorder. Du kan till exempel ha arbetsorder som är relaterade till förebyggande underhåll eller korrigerande underhåll.

En arbetsordertyp definierar en anknytning till en livscykelmodell för arbetsorder. En livscykelmodell för arbetsorder anger livscykeltillstånd som kan anges för en arbetsorder. (Exempel på livscykeltillstånd för arbetsorder är bland annat **Skapat**, **Pågår** och **Slutfört**.)

Mer information om livscykeltillstånd för arbetsorder och projektfaser finns [Livscykeltillstånd för arbetsorder](work-order-lifecycle-states.md).

1. Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Arbetsordertyper**.
2. Skapa en ny arbetsordertyp genom att välja **Ny**.
3. I fältet **Arbetsordertyp** anger du ett ID för arbetsordertypen.
4. Ange sedan ett namn i fältet **Namn**.
5. Välj en livscykelmodell i fältet **Livscykelmodell för arbetsorder**.
5. Ställ in alternativet **En underhållsarbetare** på **Ja** om alla arbetsorderjobb som är relaterade till en arbetsorder av den här typen ska planeras till samma underhållsarbetare.
6. I fältet **Kostnadstyp** väljer du **Korrigerande**, **Förebyggande** eller **Investering**, beroende på vad som är tillämpligt. Alla arbetsorderjob på en arbetsorder måste ha samma kostnadstyp.
7. I avsnittet **Obligatoriskt** anger du de relevanta alternativen till **Ja** för att ange vilka felrelaterade eller underhållsstopptid-relaterade uppgifter som ska läggas till i en arbetsorder av den här typen.

    > [!NOTE]
    > Alternativetn i avsnittet **Obligatorisk** är relaterade till alternativen på snabbfliken **Validera** på sidan **Livscykeltillstånd för arbetsorder** (**Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Livscykeltillstånd**).

8. Välj **Spara**.

![Typer av arbetsorder.](media/16-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]