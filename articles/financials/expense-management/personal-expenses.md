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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b072fa9e78563d3e89b4d60e9ce61473902fee76
ms.sourcegitcommit: ef08bf1258aefb525d56bf85ef19311be26ab94c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2019
ms.locfileid: "1795015"
---
# <a name="personal-expenses-on-an-expense-report"></a>Privata utgifter i en utgiftsrapport

[!include [banner](../includes/banner.md)]

Under en affärsresa kanske medarbetare ibland debiterar sitt företagskreditkort för privata utgifter. Om du inte har definierat någon process för hantering av privata utgifter kanske godkännandeprocessen för utgiftsrapporterna störs när medarbetare skickar sina specificerade utgiftsrapporter. 

I Microsoft Dynamics 365 for Finance and Operations finns två metoder för hantering av en arbetares privata utgifter:

- **Betald av medarbetaren** – företaget betalar inte privata utgifter som visas på kreditkortsräkningen. I stället skapas en rapport med de privata utgifterna tillsammans med företagets utgifter som har debiterats kortet.
- **Betalad av företaget** – Företaget betalar hela kreditkortsräkningen och debiterar sedan de privata utgifterna på medarbetarkontot.

Du kan välja den metod som används i din organisation på sidan **parametrar för utgiftshantering**.
