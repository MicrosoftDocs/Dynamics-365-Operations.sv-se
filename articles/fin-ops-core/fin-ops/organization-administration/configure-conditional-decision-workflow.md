---
title: Konfigurera villkorsbeslut i ett arbetsflöde
description: Använd följande procedur om du vill konfigurera egenskaperna för ett villkorsbeslut.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed53eeb26e1b4b1df1647739ce1d115c7dd169f8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747941"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a>Konfigurera villkorsbeslut i ett arbetsflöde

[!include [banner](../includes/banner.md)]

Använd följande procedur om du vill konfigurera egenskaperna för ett villkorsbeslut.

Ett villkorligt beslut är en punkt vid vilken ett arbetsflöde delas i två grenar. Högerklicka på villkorsbeslutet och klicka sedan på **Properties** i arbetsflödesredigeraren för att öppna formuläret **Properties** om du vill konfigurera ett villkorsbeslut.

## <a name="name-a-decision"></a>Namnge ett beslut

Följ dessa steg när du vill ange ett namn för ett villkorsbeslut.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. I fältet **Namn** anger du ett unikt namn för villkorsbeslutet.

## <a name="set-conditions"></a> Ange villkor

Systemet avgör vilken gren som ska användas genom att utvärdera det skickade dokumentet för att bestämma om det uppfyller specifika villkor.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. Klicka på **Lägg till villkor**.
3. Ange ett villkor.
4. Ange ytterligare villkor vid behov.
5. Slutför följande steg för att bekräfta att de villkor som du har angett har ställts in korrekt:

    1. Klicka på **Testa** för att öppna formuläret **Testa arbetsflödesvillkor**.
    2. Markera en post i området **Validera villkor** i formuläret.
    3. Klicka på **Ja**. Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.
    4. Klicka på **OK** eller **Avbryt** för att återgå till formuläret **Egenskaper**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]