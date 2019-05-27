---
title: Produktionsåterrapportering
description: Den här artikeln innehåller information om produktionsåterrapportering, som ger arbetarna återrapportering om produktionsjobb. Artikeln innehåller information om de olika sätten att uppdatera produktionsåterrapportering.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b0a49cf05a7eee838dcf9fb699d273d0f7518a1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548916"
---
# <a name="production-feedback"></a>Produktionsåterrapportering

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller information om produktionsåterrapportering, som ger arbetarna återrapportering om produktionsjobb. Artikeln innehåller information om de olika sätten att uppdatera produktionsåterrapportering.

Produktionåterkoppling ger arbetarna återrapportering om produktionsjobb. Den registrerar materialförbrukning och produktionsorder, operationskvantiteter och status och fel som orsakar att ett jobb eller en operation misslyckas. Produktionåterkoppling kan uppdateras i journaler som är relaterade till produktionsorder. Journalerna **Produktionsjobbkort** och **Produktionsflödekort** används för att rapportera tid och kvantiteter per jobb eller operation. För att rapportera om det sista jobbet eller operationen kan kvantiteter i den färdiga produkten rapporteras som slutförda. Produktionåterkoppling kan också uppdateras på sidorna **Jobbkortterminal** och **Jobbkortenhet**. Dessa sidor låter produktionsåterrapportering uppdateras på tillverkningsstället, och ingår i funktionen tillverkningskörning i modulen **Produktionskontroll**. Sidan**Jobbkortterminal** har ett konfigurerbart användargränssnitt som visar en lista med de frisläppta jobben i en prioriterad order för ett valt arbetsområde. Den erbjuder även avancerade alternativ som till exempel buntning av jobb och teamarbete. Sidan **Jobbkortenhet** har ett pekvänligt användargränssnitt. Produktionåterkoppling på båda sidorna uppdateras från produktionsjournalerna.



