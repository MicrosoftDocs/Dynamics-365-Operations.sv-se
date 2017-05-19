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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 6977cb3b315a90b504fc6748d2a4d02854a9d5ef
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Översikt över avancerad bankavstämning

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver flödet för den avancerade bankavstämningsprocessen. Med hjälp av den avancerade bankavstämningsfunktionen kan du importera bankutdrag som kan vara automatiskt avstämda inom banktransaktioner.

Den avancerade bankavstämningsfunktionen gör att du kan importera bankutdrag. Det importerade bankutdraget kan sedan automatiskt stämmas av från banktransaktioner. Här följer stegen i flödet för avancerad bankavstämning.

1.  Ställ in import av bankutdrag.
    -   Importera bankutdrag via datatabellsramverket.
    -   Tre vanligaste bankutdragformat är inbyggda i: ISO20022, BAI2 och MT940.
    -   Funktionen kan utökas till alla format.

2.  Ställ in en nummerserie som ska användas för avancerad bankavstämning och definiera matchningsregler för bankavstämning.
    -   En regel för avstämningsmatchning är en uppsättning villkor som används för att filtrera bankutdragsrader och transaktionsrader för Microsoft Dynamics 365 for Operations under avstämningsprocessen. Du kan ställa in mer än en matchningsregel att automatisera och optimera din avstämningsprocess beroende på din affärsverksamhet.

3.  Stäm av bankutdragen med banktransaktioner för Dynamics 365 for Operation.
    -   Utför automatisk matchning och genereringen av avstämningsjournaler.
    -   Visa bankutdrag och Microsoft 365 for Operations-banktransaktioner sida vid sida.
    -   Bokför Microsoft Dynamics 365 for Operations-banktransaktioner automatiskt om de visas på ett bankutdrag men inte i Microsoft 365 for Operations.
    -   Generera ett avstämningsutdrag.






