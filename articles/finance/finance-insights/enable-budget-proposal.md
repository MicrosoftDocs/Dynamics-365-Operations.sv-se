---
title: Aktivera budgetförslag (förhandsversion)
description: I det här ämnet beskrivs hur du aktiverar funktionen för Budgetförslag i Ekonomiinsikter.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: d8443c4e3e6f3d3a90acedc7c05b2846d6b68369
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646215"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="b18ed-103">Aktivera budgetförslag (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="b18ed-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="b18ed-104">I det här ämnet beskrivs hur du aktiverar funktionen för Budgetförslag i Ekonomiinsikter.</span><span class="sxs-lookup"><span data-stu-id="b18ed-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="b18ed-105">Använd information från miljösidan i Microsoft Dynamics Lifecycle Services (LCS) för att ansluta till den primära instansen av Azure SQL för den miljön.</span><span class="sxs-lookup"><span data-stu-id="b18ed-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="b18ed-106">Kör följande Transact-SQL-kommando (T-SQL) för att aktivera förhandsversioner för sandbox-miljön.</span><span class="sxs-lookup"><span data-stu-id="b18ed-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="b18ed-107">(Du kanske måste aktivera åtkomst för din IP-adress i LCS innan du kan fjärransluta till Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="b18ed-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="b18ed-108">Om din distribution av Microsoft Dynamics 365 Finance är en Service Fabric-distribution kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="b18ed-108">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="b18ed-109">Teamet för Ekonomiinsikter ska redan ha aktiverat förhandsversionen för dig.</span><span class="sxs-lookup"><span data-stu-id="b18ed-109">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="b18ed-110">Om funktionen inte visas i arbetsytan **Funktionshantering**, eller om det uppstår problem när du försöker att aktivera den, skickar du e-post till [teamet för förhandsversionen av Ekonomiinsikts-appen](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b18ed-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, send email to the [Finance Insights App Preview team](mailto:fiap@microsoft.com).</span></span>

2. <span data-ttu-id="b18ed-111">Öppna arbetsytan **Funktionshantering** och gör så här:</span><span class="sxs-lookup"><span data-stu-id="b18ed-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="b18ed-112">Välj **Sök efter uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="b18ed-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="b18ed-113">Sök efter **Budgetförslag** och aktivera den funktionen.</span><span class="sxs-lookup"><span data-stu-id="b18ed-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="b18ed-114">Gå till **Budgetering \> Konfigurera \> Grundläggande budgetering \> Budgetförslag (förhandsversion)** och välj **Aktivera funktion**.</span><span class="sxs-lookup"><span data-stu-id="b18ed-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="b18ed-115">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="b18ed-115">Privacy notice</span></span>
<span data-ttu-id="b18ed-116">Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="b18ed-116">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>