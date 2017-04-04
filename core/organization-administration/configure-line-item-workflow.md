---
title: "Konfigurera ett arbetsflöde för radartiklar"
description: "I det här avsnittet beskrivs hur du konfigurerar ett arbetsflödeselement för radartiklar."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 6c2b2c863d0783bd436db57d9fd3c7c5aa8dba5c
ms.lasthandoff: 03/31/2017


---

# <a name="configure-a-line-item-workflow"></a>Konfigurera ett arbetsflöde för radartiklar

I det här avsnittet beskrivs hur du konfigurerar ett arbetsflödeselement för radartiklar.

Höger klicka på elementet i arbetsflödesredigeraren och klicka sedan på **Properties** för att öppna sidan **Properties**, om du vill konfigurera ett arbetsflöde för radartiklar. Du kan sedan använda följande procedurer för att konfigurera olika egenskaper för arbetsflödet för radartikel.

## <a name="name-the-lineitem-workflow-element"></a>Namnge lineitem arbetsflödeselementet
Följ dessa steg när du vill ange ett namn för arbetsflödet för radartikel.

1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  I fältet **Name** anger du ett unikt namn för arbetsflödet för radartikel.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Ange om samma arbetsflöde används för att bearbeta alla radartiklar
Gör på följande sätt när du vill ange om samma arbetsflöde används för att bearbeta alla radartiklar i ett dokument.

1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  Om samma arbetsflöde ska bearbeta alla radartiklar i ett dokument, klicka på **Invoke a single workflow for all line-items**. Välj sedan arbetsflödet som ska användas för att bearbeta radartiklarna.
3.  Om ett specifikt arbetsflöde ska processa radartiklar som uppfyller en viss uppsättning villkor, klicka på **Invoke a workflow for each line-item**. Följ därefter dessa steg när du vill definiera uppsättningen villkor:
    1.  Klicka på **Lägg till**.
    2.  Välj villkoret i tabellen.
    3.  I fliken **Condition name** anger du ett namn på den villkorsuppsättning som du vill definiera.
    4.  Klicka på **Lägg till villkor** för att ange ett villkor.
    5.  Ange eventuellt ytterligare villkor som krävs.
    6.  Klicka på **Test** för att bekräfta att den uppsättning villkor som du har angett också har ställts in korrekt. På sidan **Test workflow condition**, i området **Validate condition**, väljer du en post innan du klickar på **Test**. Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett. När du vill återgå till sidan **Egenskaper** klickar du på **OK** eller på **Avbryt**.

    I fliken **Workflow** markerar du det arbetsflöde du vill använda för att processa radartiklar som uppfyller den uppsättning villkor som du har angett.



