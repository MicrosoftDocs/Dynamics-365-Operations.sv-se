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
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: cc19110f481c11ab28532d69a4689c1db048f6c3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233377"
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