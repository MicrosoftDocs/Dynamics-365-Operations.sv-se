---
title: Transporthantering i nummersekvens
description: I det här avsnittet beskrivs hur du ställer in nummerserier för transporthantering.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2c3f087ac76412cd2dce93dcb31b796ce2cb3bc4
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "4438132"
---
# <a name="transportation-management-number-sequence"></a>Transporthantering i nummersekvens

[!include [banner](../includes/banner.md)]

Använd sidan **Nummerserier** i transporthanteringsmodulen för att ställa in olika pro-nummer. Pro-nummer används av transportföretag för att ordna och spåra förloppet för varje försändelse.

## <a name="create-a-number-sequence-for-a-pro-number"></a>Skapa en nummerserie för ett pro-nummer

Gör följande om du vill skapa en nummerserie för ett pro-nummer:

1. Gå till **Transporthantering \> Inställningar \> Transportföretag \> Nummerserie**.
1. Skapa en ny nummerserie genom att välja **Nytt**.
1. Ange ett unikt ID och ett beskrivande namn på nummerserien.
1. I fältet **nummerserietyp** är *pro-nummer* det enda alternativet.
1. I fältet **Kontrollsiffra** är *Kontrollsiffra* det enda alternativet och den ställs in som en allmän motor.
1. På snabbfliken **sekvens** ange information om sekvensen.
1. Stäng sidan.

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a>Koppla en nummerserie till ett transportföretag

Gör följande om du vill koppla en nummerserie till ett transportföretag:

1. Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportföretag**.
1. Välj ett transportföretag.
1. Välj **Redigera**.
1. På snabbfliken **Översikt** väljer du ett alternativ i fältet **Pro-nummerserie**.
1. Stäng sidan.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]