---
title: Skapa checkar med statusvärdet Tom
description: I det här avsnittet beskrivs hur du skapar en tom check för ett bankkonto på sidan Checkar.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 94d3a4ac8a3906e48f5a6053c031001c111549ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254045"
---
# <a name="create-checks-that-have-blank-status"></a>Skapa checkar med statusvärdet Tom

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du skapar tomma checkar. Du kan till exempel skapa en tom check om du vill registrera en check som har skadats och inte kan användas för betalning.

Du utför underhåll för checkar på sidan **Checkar**. Du kan till exempel skapa nya checknummer och ta bort checkar. Du kan också skapa checkar som har statusvärdet **Tom**. När du har skapat tomma checkar kan de inte tas bort eller återanvändas i systemet.

> [!NOTE]
> Den här funktionen är bara tillgänglig på sidan **Checkar** om du aktiverar funktionen **Skapa checkar med tom status på sidan Checkar** på sidan **Funktionshantering**. Om funktionen inte är aktiverad kan du bara skapa checkar med statusvärdet **Tom** från dialogrutan **Betalning med check** under betalningsgenereringen i Leverantörsreskontra.

Du öppnar sidan **Checkar** genom att gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton** och sedan välja **Checkar** på fliken **Hantera betalningar** i gruppen **Relaterad information** i åtgärdsfönstret. Du kan också gå till **Kassa- och bankhantering \> Förfrågningar och rapporter \> Checkar**.

Du skapar sedan checkar med statusvärdet **Tom** genom att välja **Skapa tomma checkar** i åtgärdsfönstret. Medan de tomma checkarna skapas inaktiveras det associerade bankkontot tillfälligt. På grund av detta minskar risken för att betalningar genereras samtidigt som tomma checkar skapas. När processen är klar återaktiveras det associerade bankkontot.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]