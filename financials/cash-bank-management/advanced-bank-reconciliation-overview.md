---
title: "Översikt över avancerad bankavstämning"
description: "Det här avsnittet beskriver flödet för den avancerade bankavstämningsprocessen. Med hjälp av den avancerade bankavstämningsfunktionen kan du importera bankutdrag som kan vara automatiskt avstämda inom banktransaktioner."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 00f022da597b1de2454e93123de31731c6a65962
ms.openlocfilehash: 20363ef1917f7d0796cb0d5cd8e623c598b5ee01
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Översikt över avancerad bankavstämning

Det här avsnittet beskriver flödet för den avancerade bankavstämningsprocessen. Med hjälp av den avancerade bankavstämningsfunktionen kan du importera bankutdrag som kan vara automatiskt avstämda inom banktransaktioner.

Den avancerade bankavstämningsfunktionen gör att du kan importera bankutdrag. Det importerade bankutdraget kan sedan automatiskt stämmas av från banktransaktioner. Här följer stegen i flödet för avancerad bankavstämning.

1.  Ställ in import av bankutdrag.
    -   Importera bankutdrag via datatabellsramverket.
    -   Tre vanligaste bankutdragformat är inbyggda i: ISO20022, BAI2 och MT940.
    -   Funktionen kan utökas till alla format.

2.  Ställ in en nummerserie som ska användas för avancerad bankavstämning och definiera matchningsregler för bankavstämning.
    -   Matchningsregel för bankavstämning är en uppsättning villkor som används för att filtrera bankutdragsrader och Microsoft Dynamics 365 för operationer bank transaktionsrader under avstämningsprocessen. Du kan ställa in fler än en matchande regel att automatisera och optimera din avstämningsprocessen beroende på din affärsverksamhet.

3.  Stämma av bankutdrag med Dynamics 365 för operationer banktransaktioner.
    -   Utför automatisk matchning och genereringen av avstämningsjournaler.
    -   Visa bankkontoutdrag och Dynamics 365 för operationer banktransaktioner sida vid sida.
    -   Bokför Dynamics 365 för operationer banktransaktioner automatiskt om de visas på kontoutdraget från banken inte men i Dynamics 365 för operationer.
    -   Generera ett avstämningsutdrag.




