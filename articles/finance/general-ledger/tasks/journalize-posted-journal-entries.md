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
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad18063e0a66a4aac0ebef7f0ce45c73137abcc7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968539"
---
# <a name="journalize-posted-journal-entries"></a>Journalföra bokförda poster i redovisningsjournal

[!include [banner](../../includes/banner.md)]

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

