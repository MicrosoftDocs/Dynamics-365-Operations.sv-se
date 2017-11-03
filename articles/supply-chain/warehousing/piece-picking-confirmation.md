---
title: "Enhetsplockningsbekräftelse"
description: "Det här avsnittet beskriver hur du ställer in och använder bekräftelse av komponentplockning från en mobil enhet."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 62b637b81a522c353067248deea79cfbf98518e9
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="piece-picking-confirmation"></a>Enhetsplockningsbekräftelse

[!include[banner](../includes/banner.md)]

Med enhetsplockning kan du bekräfta varje lagerenhet via plocknings- eller inventeringsarbete på en mobil enhet. För plockning, kan du bekräfta mängden arbete ska hanteras upp till den kvantitet som anges på det arbete som ska plockas. För inventeringsarbete kan du skanna lagret du inventerar och spåra det totala antalet.

Bekräftelse av produkten väljs automatiskt när du aktiverar enhetsplockning. För arbetstypen Plockning aktiveras maximalt antal enheter. På så sätt kan du ange maximalt antal enheter som måste bekräftas under arbetsprocessen. Den maximala kvantiteten är baserad på den aktuella arbetsenheten som bearbetas. Arbetstypen Inventering tillåter inte ett maximum.

Du kan också använda kvantitet och måttenhet (UOM) som är associerad med en skannad streckkod. Den här metoden fungerar för inleverans på inkommande flöden inklusive inleverans av blandad registreringsskylt, artikel för inköpsorder, artikel för överföringsorder och lastartikel. Den fungerar även för enhetsplockning där skanning av streckkoden lägger till kvantiteten till det totala antalet bekräftade enheter som konverteras mellan måttenheten på streckkoden och arbetsenheten. Vid bekräftelse på att kvantiteten är godkänd för inventering i sekvensgruppen i samband med inventering av måttenheten på streckkoden läggs kvantiteten till i det totala antalet.

## <a name="where-it-applies"></a>Tillämpning

Enhetsplockning fungerar för allt inventeringsarbete och för den ursprungliga plockningen för alla typer av arbete. Enhetsplockning gäller inte om artikeln styrs av serienummer eller om det är en tillverknings- eller kanban-plockning från en registreringsskyltsplats (LP) och artikeln är inställd till mellanlagring.

## <a name="set-up-piece-picking"></a>Ställa in enhetsplockning

1.  I den mobila enhetens menyalternativ öppnar du inställningsformuläret för arbetsbekräftelse: Lagerstyrning > **Lagerstyrning** > **Inställningar** > **Mobil enhet** > **Mobila enhetens menyalternativ**. 
2. Från den mobila enhetens menyalternativ öppnar du Inställning av arbetsbekräftelse.

Följande alternativ blir tillgängliga när arbetstypen är Plockning eller Inventering.

| Alternativ        | beskrivning   | 
| ------------- | ------------- |
| Enhetsplockningsbekräftelse   | Tillgängliga för arbetstyperna Plockning och Inventering. Bekräftelse av produkten väljs automatiskt. Låter dig bekräfta varje lagerenhet från den mobila enheten. | 
| Maximalt antal enheter     | Tillgänglig för plockningsarbete om enhetsplockningsbekräftelse är aktiverad. Sätter en gräns för hur många enheter du måste bekräfta. |  

