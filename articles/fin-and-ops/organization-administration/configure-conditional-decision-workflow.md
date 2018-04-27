---
title: "Konfigurera ett villkorsbeslut i ett arbetsflöde"
description: "Använd följande procedur om du vill konfigurera egenskaperna för ett villkorsbeslut."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 597a6a254dcd623f9e7c59a0309eeedee1b5adee
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="configure-a-conditional-decision-in-a-workflow"></a>Konfigurera ett villkorsbeslut i ett arbetsflöde

[!INCLUDE [banner](../includes/banner.md)]

Använd följande procedur om du vill konfigurera egenskaperna för ett villkorsbeslut.

Ett villkorligt beslut är en punkt vid vilken ett arbetsflöde delas i två grenar. Högerklicka på villkorsbeslutet och klicka sedan på **Properties** i arbetsflödesredigeraren för att öppna formuläret **Properties** om du vill konfigurera ett villkorsbeslut.

## <a name="name-a-decision"></a>Namnge ett beslut
Följ dessa steg när du vill ange ett namn för ett villkorsbeslut.
1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  I fältet **Namn** anger du ett unikt namn för villkorsbeslutet.

## <a name="set-conditions"></a> Ange villkor
Systemet avgör vilken gren som ska användas genom att utvärdera det skickade dokumentet för att bestämma om det uppfyller specifika villkor.
1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  Klicka på **Lägg till villkor**.
3.  Ange ett villkor.
4.  Ange ytterligare villkor vid behov.
5.  Slutför följande steg för att bekräfta att de villkor som du har angett har ställts in korrekt:
    1.  Klicka på **Testa** för att öppna formuläret **Testa arbetsflödesvillkor**.
    2.  Markera en post i området **Validera villkor** i formuläret.
    3.  Klicka på **Ja**. Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.
    4.  Klicka på **OK** eller **Avbryt** för att återgå till formuläret **Egenskaper**.






