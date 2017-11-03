---
title: "Översikt över avancerad bankavstämning"
description: "Det här avsnittet beskriver flödet för den avancerade bankavstämningsprocessen. Med hjälp av den avancerade bankavstämningsfunktionen kan du importera bankutdrag som kan vara automatiskt avstämda inom banktransaktioner."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 33150777222faa97af7488c59ab13cb0fb9e8e2c
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

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
    -   En regel för avstämningsmatchning är en uppsättning villkor som används för att filtrera bankutdragsrader och transaktionsrader för Microsoft Dynamics 365 for Finance and Operations, Enterprise edition under avstämningsprocessen. Du kan ställa in mer än en matchningsregel att automatisera och optimera din avstämningsprocess beroende på din affärsverksamhet.

3.  Stäm av bankutdragen med banktransaktioner för Finance and Operations.
    -   Utför automatisk matchning och genereringen av avstämningsjournaler.
    -   Visa bankutdrag och Finance and Operations-banktransaktioner sida vid sida.
    -   Bokför Finance and Operations-banktransaktioner automatiskt om de visas på ett bankutdrag men inte i Finance and Operations.
    -   Generera ett avstämningsutdrag.






