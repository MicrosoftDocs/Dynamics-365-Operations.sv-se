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
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c21c8e33ab3a88e1b93ca81d6f0770f1c77fe139
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017

---

# <a name="configure-a-conditional-decision-in-a-workflow"></a>Konfigurera ett villkorsbeslut i ett arbetsflöde

[!include[banner](../includes/banner.md)]


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






