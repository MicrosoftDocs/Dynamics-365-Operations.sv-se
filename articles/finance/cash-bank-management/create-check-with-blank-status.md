---
title: Skapa checkar med statusvärdet Tom
description: I den här artikeln beskrivs hur du skapar en tom check för ett bankkonto.
author: angelad116
ms.date: 10/24/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 86020d9088d8135c83716128a77090608536a78f
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804031"
---
# <a name="create-checks-that-have-blank-status"></a>Skapa checkar med statusvärdet Tom

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du skapar tomma checkar. Du kan till exempel skapa en tom check om du vill registrera en check som har skadats och inte kan användas för betalning.

Du utför underhåll för checkar på sidan **Checkar**. Du kan till exempel skapa nya checknummer och ta bort checkar. Du kan också skapa checkar som har statusvärdet **Tom**. När du har skapat tomma checkar kan de inte tas bort eller återanvändas i systemet.

> [!NOTE]
> Den här funktionen är bara tillgänglig på sidan **Checkar** om du aktiverar funktionen **Skapa checkar med tom status på sidan Checkar** på sidan **Funktionshantering**. Om funktionen inte är aktiverad kan du bara skapa checkar med statusvärdet **Tom** från dialogrutan **Betalning med check** under betalningsgenereringen i Leverantörsreskontra.

Du öppnar sidan **Checkar** genom att gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton** och sedan välja **Checkar** på fliken **Hantera betalningar** i gruppen **Relaterad information** i åtgärdsfönstret. Du kan också gå till **Kassa- och bankhantering \> Förfrågningar och rapporter \> Checkar**.

Du skapar sedan checkar med statusvärdet **Tom** genom att välja **Skapa tomma checkar** i åtgärdsfönstret. Medan de tomma checkarna skapas inaktiveras det associerade bankkontot tillfälligt. På grund av detta minskar risken för att betalningar genereras samtidigt som tomma checkar skapas. När processen är klar återaktiveras det associerade bankkontot.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
