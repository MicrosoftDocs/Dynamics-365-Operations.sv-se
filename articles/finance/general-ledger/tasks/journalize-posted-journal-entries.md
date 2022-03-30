---
title: Journalföra bokförda poster i redovisningsjournal
description: Den här proceduren visar dig hur du journalför bokförda journalposter.
author: aprilolson
ms.date: 03/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8fca167563b14c825ebe29874c6488ddfb4d9a
ms.sourcegitcommit: 06acdfbccd7bd213a2397ea7b85d104f01914437
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2022
ms.locfileid: "8400885"
---
# <a name="journalize-posted-journal-entries"></a>Journalföra bokförda poster i redovisningsjournal

[!include [banner](../../includes/banner.md)]

Journalföringsprocessen i redovisningen utgör ett sätt att gruppera och rapportera om bokförda verifikationsposter i redovisningen. Baserat på de kriterier som du anger skapar bearbetningen en lista över verifikationer som använder en unik nummerserie och som har redovisningsvärdet **Journalnummer** som referens.

Följ dessa steg om du vill journalföra bokförda journalposter. I den här proceduren används demonstrationsdataföretaget **USMF**.

1. Gå till **Redovisning** \> **Inställningar för transaktionsregister** \> **Redovisningsparametrar**.
2. I fältet **Utökad redovisningsjournal** ange rdu ett värde. Om du väljer **Ja** kommer rapportresultatet att bli annorlunda.
3. Välj om perioden kan stängas även om journalföringsprocessen inte har körts. Om du väljer **Ja** kan perioden inte stängas förrän journalföringsprocessen har slutförts för den perioden.
4. Stäng sidan.
5. Gå till **Redovisning** \> **Periodiska uppgifter** \> **Journalföring** och välj **Filter**.
6. Markera raden för det filtervillkor som du vill definiera.
7. I fältet **Kriterier** anger eller väljer du filterkriterier.
8. Välj **OK** om du vill stänga sidan.
9. Starta journalföringsprocessen genom att välja **OK**. En rapport skapas när processen är slutförd.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
