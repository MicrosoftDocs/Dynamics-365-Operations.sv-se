---
title: Aktivera budgetförslag
description: I det här ämnet beskrivs hur du aktiverar funktionen för Budgetförslag i Finance-insikter.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: ab65d1b0e366bfe6bdb07688f89d440662165063
ms.sourcegitcommit: 822aea26c5da259efe11ff3b3dc4cf1598425689
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2021
ms.locfileid: "7386496"
---
# <a name="enable-budget-proposals"></a>Aktivera budgetförslag

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du aktiverar funktionen för Budgetförslag i Finance-insikter.

1. Använd information från miljösidan i Microsoft Dynamics Lifecycle Services (LCS) för att ansluta till den primära instansen av Azure SQL för den miljön. Kör följande Transact-SQL-kommando (T-SQL) för att aktivera förhandsversioner för sandbox-miljön. (Du kanske måste aktivera åtkomst för din IP-adress i LCS innan du kan fjärransluta till Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > Hoppa över det här steget om du använder version 10.0.20 eller senare, eller om du använder en Service Fabric-distribution. Teamet för ekonomiinsikter ska redan ha aktiverat förhandsversionen för dig. Om funktionen inte visas på arbetsytan **Funktionshantering**, eller om det uppstår problem när du försöker att aktivera den, kontaktar du <fiap@microsoft.com>.

2. Öppna arbetsytan **Funktionshantering** och gör så här:

    1. Välj **Sök efter uppdateringar**.
    2. Sök efter **Budgetförslag** och aktivera den funktionen.

3. Gå till **Budgetering \> Konfigurera \> Grundläggande budgetering \> Budgetförslag (förhandsversion)** och välj **Aktivera funktion**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
