---
title: Aktivera budgetförslag (förhandsversion)
description: I det här ämnet beskrivs hur du aktiverar funktionen för Budgetförslag i Finance-insikter.
author: ShivamPandey-msft
ms.date: 06/03/2021
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
ms.openlocfilehash: 948a3e051e5964c5c773cefd90c8587cf833a450
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222544"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="a066c-103">Aktivera budgetförslag (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="a066c-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="a066c-104">I det här ämnet beskrivs hur du aktiverar funktionen för Budgetförslag i Finance-insikter.</span><span class="sxs-lookup"><span data-stu-id="a066c-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="a066c-105">Använd information från miljösidan i Microsoft Dynamics Lifecycle Services (LCS) för att ansluta till den primära instansen av Azure SQL för den miljön.</span><span class="sxs-lookup"><span data-stu-id="a066c-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="a066c-106">Kör följande Transact-SQL-kommando (T-SQL) för att aktivera förhandsversioner för sandbox-miljön.</span><span class="sxs-lookup"><span data-stu-id="a066c-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="a066c-107">(Du kanske måste aktivera åtkomst för din IP-adress i LCS innan du kan fjärransluta till Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="a066c-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="a066c-108">Hoppa över det här steget om du använder version 10.0.20 eller senare, eller om du använder en Service Fabric-distribution.</span><span class="sxs-lookup"><span data-stu-id="a066c-108">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="a066c-109">Teamet för ekonomiinsikter ska redan ha aktiverat förhandsversionen för dig.</span><span class="sxs-lookup"><span data-stu-id="a066c-109">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="a066c-110">Om funktionen inte visas på arbetsytan **Funktionshantering**, eller om det uppstår problem när du försöker att aktivera den, kontaktar du <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="a066c-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="a066c-111">Öppna arbetsytan **Funktionshantering** och gör så här:</span><span class="sxs-lookup"><span data-stu-id="a066c-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="a066c-112">Välj **Sök efter uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="a066c-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="a066c-113">Sök efter **Budgetförslag** och aktivera den funktionen.</span><span class="sxs-lookup"><span data-stu-id="a066c-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="a066c-114">Gå till **Budgetering \> Konfigurera \> Grundläggande budgetering \> Budgetförslag (förhandsversion)** och välj **Aktivera funktion**.</span><span class="sxs-lookup"><span data-stu-id="a066c-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
