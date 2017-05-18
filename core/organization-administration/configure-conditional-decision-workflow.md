---
title: "Konfigurera ett villkorsbeslut i ett arbetsflöde"
description: "Använd följande procedur om du vill konfigurera egenskaperna för ett villkorsbeslut."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d3efb6106df7d66ebe9b1a061f9976b8978704b1
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


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






