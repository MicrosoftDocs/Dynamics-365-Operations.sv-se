---
title: Journalföra bokförda poster i redovisningsjournal
description: Den här proceduren visar dig hur du journalför bokförda journalposter.
author: aprilolson
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e20229ca910aa0d7d820434c22edf5a27030bba5
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916263"
---
# <a name="journalize-posted-journal-entries"></a>Journalföra bokförda poster i redovisningsjournal

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar dig hur du journalför bokförda journalposter. I proceduren används demonstrationsföretag USMF.

1. I **Navigeringsfönster**, gå till **Moduler > Redovisning > Redovisningsinställning > Allmänna redovisningsparametrar**.
2. Fältet **Utökad redovisningsjournal** kan anges som Ja eller Nej. Om "Yes" kommer rapportutdatan att skilja sig åt.
3. Välj om perioden kan stängas även om journalföringsprocessen inte har körts. Om detta alternativ är inställt på "Yes" kan inte perioden stängas förrän journalföringsprocessen har slutförts för den perioden.  
4. Stäng sidan.
5. I **Navigeringsfönstret**, gå till **Moduler > Redovisning > Periodiska uppgifter > Journalför**.
6. Klicka på **Filter**.
7. Markera raden med filtervillkoret som du vill definiera.
8. Ange eller välj filterkriterier i fältet **Kriterier**.
9. Klicka på **OK** för att stänga filtersidan.
10. Starta journalföringsprocessen genom att klicka på **OK**. En rapport skapas när processen är slutförd.  

