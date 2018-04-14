---
title: "Konfigurera ett arbetsflöde för radartiklar"
description: "I det här avsnittet beskrivs hur du konfigurerar ett arbetsflödeselement för radartiklar."
author: sericks007
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d30d6aeda6be7bc81763c0b3f20c568d3fc81526
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="configure-a-line-item-workflow"></a>Konfigurera ett arbetsflöde för radartiklar

[!INCLUDE [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar ett arbetsflödeselement för radartiklar.

Höger klicka på elementet i arbetsflödesredigeraren och klicka sedan på **Properties** för att öppna sidan **Properties**, om du vill konfigurera ett arbetsflöde för radartiklar. Du kan sedan använda följande procedurer för att konfigurera olika egenskaper för arbetsflödet för radartikel.

## <a name="name-the-line-item-workflow-element"></a>Namnge arbetsflödet för radartikel
Följ dessa steg när du vill ange ett namn för arbetsflödet för radartikel.

1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  I fältet **Namn** anger du ett unikt namn för arbetsflödet för radartikel.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Ange om samma arbetsflöde används för att bearbeta alla radartiklar
Gör på följande sätt när du vill ange om samma arbetsflöde används för att bearbeta alla radartiklar i ett dokument.

1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  Om samma arbetsflöde ska bearbeta alla radartiklar i ett dokument, klicka på **Anropa ett enskilt arbetsflöde för alla radartiklar**. Välj sedan arbetsflödet som ska användas för att bearbeta radartiklarna.
3.  Om ett specifikt arbetsflöde ska processa radartiklar som uppfyller en viss uppsättning villkor, klicka på **Anropa ett arbetsflöde för varje radartikel**. Följ därefter dessa steg när du vill definiera uppsättningen villkor:
    1.  Klicka på **Lägg till**.
    2.  Välj villkoret i tabellen.
    3.  I fliken **Villkorsnamn** anger du ett namn på den villkorsuppsättning som du vill definiera.
    4.  Klicka på **Lägg till villkor** för att ange ett villkor.
    5.  Ange eventuellt ytterligare villkor som krävs.
    6.  Klicka på **Test** för att bekräfta att den uppsättning villkor som du har angett också har ställts in korrekt. På sidan **Testa arbetsflödesvillkor**, i området **Validera villkor**, väljer du en post innan du klickar på **Testa**. Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett. När du vill återgå till sidan **Egenskaper** klickar du på **OK** eller på **Avbryt**.

    I fliken **Workflow** markerar du det arbetsflöde du vill använda för att processa radartiklar som uppfyller den uppsättning villkor som du har angett.





