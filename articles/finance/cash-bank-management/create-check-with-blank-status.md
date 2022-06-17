---
title: Skapa checkar med statusvärdet Tom
description: I den här artikeln beskrivs hur du skapar en tom check för ett bankkonto.
author: abruer
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 834e11e0e359521c674e2b6fd78c93dcb23961a0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861456"
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
