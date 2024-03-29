---
title: Arbetsorder och anläggningstillgångar
description: Denna artikel innehåller förklaringar av arbetsorder och anläggningstillgångar i Tillgångshantering.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ed83450592d85205743c9ff1aefd0e66e5d2b90c
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112001"
---
# <a name="work-orders-and-fixed-assets"></a>Arbetsorder och anläggningstillgångar

[!include [banner](../../includes/banner.md)]


I Tillgångshantering kan tillgångar relateras till anläggningstillgångar och du kan skapa arbetsorder för dessa tillgångar. Om du använder den här funktionen kan du få en fullständig översikt över anläggningstillgångar, relaterade investeringsprojekt och de kostnader som registrerats för investeringsprojekt i modulerna **Projekthantering och redovisning** **Anläggningstillgångar** i appar för ekonomi och drift.

>[!NOTE]
>Fältet **Anläggningstillgångsnummer** på arbetsorderns jobbprojekt anges endast om **investering** väljs som projekttyp för arbetsorders jobbprojekt.

I bilden nedan visas relationen mellan ett investeringsprojekt i **projektlednings- och redovisningsmodulen** och ett jobbprojekt för arbetsorder.

![Figur 1.](media/24-work-orders.png)

Följande procedur beskriver relationen mellan tillgångar, arbetsorder, jobbprojekt för arbetsorder och anläggningstillgångar.

1. Du skapar en tillgång som du kopplar till en anläggningstillgång.

![Figur 2.](media/25-work-orders.png)

2. När du konfigurerar arbetsordertyper på sidan **Arbetsorderordertyper** (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Arbetsordertyper**) skapar du en arbetsordertyp för hantering av investeringar. Se även [Arbetsordertyper](../setup-for-work-orders/work-order-types.md).

![Figur 3.](media/26-work-orders.png)

3. När du konfigurerar projektgrupper för arbetsorder i fliken **Projektgrupp** på sidan **Projektinställningar för arbetsorder** (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Projktinställningar**) skapas en relation mellan arbetsordertypen som används för investeringar och projektgruppen som skapas för investeringar på sidan **Projektgrupper** i modulen **Projekthantering och redovisning** (**Projekthantering och redovisning** > **Inställningar** > **Bokföring** > **Projektgrupper**).

![Figur 4.](media/27-work-orders.png)

4. När du skapar en arbetsorder som är relaterad till en anläggningstillgång väljer du den arbetsordertyp som brukar användas för att hantera investeringar, t.ex. **investeringar**.

5. När arbetsordern skapas visas den relaterade arbetsordertypen på sidan **Alla arbetsorder.**

![Figur 5.](media/28-work-orders.png)

6. När arbetsordern skapas kommer projektet som är relaterat till arbetsordern på sidan **Alla projekt** skapas i modulen **Projekthantering och redovisning** (**Projekthantering och redovisning** > **Projekt** > **Alla projekt**). För att visa projektrelaterad information, välj länken i fältet **Projekt-ID** på fliken **Allmänt** på snabbfliken **Raddetaljer** i detaljvyn för sidan **Alla arbetsorder** i modulen **Tillgångshantering** (**Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder**).

![Figur 6.](media/29-work-orders.png)

7. Om du vill visa en översikt över de projekt som är kopplade till en anläggningstillgång **anläggningstillgångar** > **anläggningstillgångar** > **anläggningstillgångar** och sedan i fältet **anläggningstillgångsnummer**, välj länken för anläggningstillgången för att öppna detaljvyn. Expandera fönstret **relaterad information** till höger på sidan och välj snabbfliken **associerade projekt**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
