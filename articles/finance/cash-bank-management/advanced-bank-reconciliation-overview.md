---
title: Översikt över avancerad bankavstämning
description: Det här avsnittet beskriver flödet för den avancerade bankavstämningsprocessen. Med hjälp av den avancerade bankavstämningsfunktionen kan du importera bankutdrag som kan vara automatiskt avstämda inom banktransaktioner.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39ddfde74aaff8bf5d8f22861b7595be1f9b89a9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179997"
---
# <a name="advanced-bank-reconciliation-overview"></a>Översikt över avancerad bankavstämning

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver flödet för den avancerade bankavstämningsprocessen. Med hjälp av den avancerade bankavstämningsfunktionen kan du importera bankutdrag som kan vara automatiskt avstämda inom banktransaktioner.

Den avancerade bankavstämningsfunktionen gör att du kan importera bankutdrag. Det importerade bankutdraget kan sedan automatiskt stämmas av från banktransaktioner. Här följer stegen i flödet för avancerad bankavstämning.

1.  Ställ in import av bankutdrag.
    -   Importera bankutdrag via datatabellsramverket.
    -   Tre vanligaste bankutdragformat är inbyggda i: ISO20022, BAI2 och MT940.
    -   Funktionen kan utökas till alla format.

2.  Ställ in en nummerserie som ska användas för avancerad bankavstämning och definiera matchningsregler för bankavstämning.
    -   Avstämningsmatchningsregler är en uppsättning kriterier som används för att filtrera bankutdragsrader och bankdokumentrader för Microsoft Dynamics 365 Finance under avstämningsprocessen. Du kan ställa in mer än en matchningsregel att automatisera och optimera din avstämningsprocess beroende på din affärsverksamhet.

3.  Stäm av bankutdragen med banktransaktioner för Finance.
    -   Utför automatisk matchning och genereringen av avstämningsjournaler.
    -   Visa bankutdrag och Finance-banktransaktioner sida vid sida.
    -   Bokför Finance-banktransaktioner automatiskt om de visas på ett bankutdrag men inte i Finance-appen.
    -   Generera ett avstämningsutdrag.





