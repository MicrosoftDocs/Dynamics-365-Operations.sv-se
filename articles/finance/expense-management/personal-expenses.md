---
title: Privata utgifter i en utgiftsrapport
description: Det här avsnittet beskriver två metoder för hantering av en arbetares privata utgifter i Microsoft Dynamics 365 Finance.
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
ms.openlocfilehash: 825b6c131c8a65b99d5b7ebdadcd6389886f2d11
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179961"
---
# <a name="personal-expenses-on-an-expense-report"></a>Privata utgifter i en utgiftsrapport

[!include [banner](../includes/banner.md)]

Under en affärsresa kanske medarbetare ibland debiterar sitt företagskreditkort för privata utgifter. Om du inte har definierat någon process för hantering av privata utgifter kanske godkännandeprocessen för utgiftsrapporterna störs när medarbetare skickar sina specificerade utgiftsrapporter. 

Det finns två metoder för hantering av en arbetares privata utgifter:

- **Betald av medarbetaren** – företaget betalar inte privata utgifter som visas på kreditkortsräkningen. I stället skapas en rapport med de privata utgifterna tillsammans med företagets utgifter som har debiterats kortet.
- **Betalad av företaget** – Företaget betalar hela kreditkortsräkningen och debiterar sedan de privata utgifterna på medarbetarkontot.

Du kan välja den metod som används i din organisation på sidan **parametrar för utgiftshantering**.
