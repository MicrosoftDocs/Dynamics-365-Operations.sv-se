---
title: Privata utgifter i en utgiftsrapport
description: Det här avsnittet beskriver två metoder för hantering av en arbetares privata utgifter i Microsoft Dynamics 365 for Finance and Operations.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a6b6c505e7dc5e6544658b00d9f59e6062353608
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564749"
---
# <a name="personal-expenses-on-an-expense-report"></a>Privata utgifter i en utgiftsrapport

[!include [banner](../includes/banner.md)]

Under en affärsresa kanske medarbetare ibland debiterar sitt företagskreditkort för privata utgifter. Om du inte har definierat någon process för hantering av privata utgifter kanske godkännandeprocessen för utgiftsrapporterna störs när medarbetare skickar sina specificerade utgiftsrapporter. 

I Microsoft Dynamics 365 for Finance and Operations finns två metoder för hantering av en arbetares privata utgifter:

- **Betald av medarbetaren** – företaget betalar inte privata utgifter som visas på kreditkortsräkningen. I stället skapas en rapport med de privata utgifterna tillsammans med företagets utgifter som har debiterats kortet.
- **Betalad av företaget** – Företaget betalar hela kreditkortsräkningen och debiterar sedan de privata utgifterna på medarbetarkontot.

Du kan välja den metod som används i din organisation på sidan **parametrar för utgiftshantering**.
