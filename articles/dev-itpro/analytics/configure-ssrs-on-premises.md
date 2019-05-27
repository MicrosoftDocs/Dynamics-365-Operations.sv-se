---
title: Konfigurera SQL Server Reporting Services för lokal distribution
description: Det här avsnittet innehåller information om hur du konfigurerar SQL Server Reporting Services (SSRS) för en lokal distribution.
author: sarvanisathish
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: sarvanis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 166d419f16866f699b96013222ce8da147a5ec21
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548729"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a><span data-ttu-id="68b2b-103">Konfigurera SQL Server Reporting Services för lokal distribution</span><span class="sxs-lookup"><span data-stu-id="68b2b-103">Configure SQL Server Reporting Services for on-premises deployments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="68b2b-104">Använd stegen i det här avsnittet för att konfigurera SQL Server Reporting Services (SSRS) för din Microsoft Dynamics 365 for Finance and Operations (lokala) distribution.</span><span class="sxs-lookup"><span data-stu-id="68b2b-104">Use the steps in this topic to configure SQL Server Reporting Services (SSRS) for your Microsoft Dynamics 365 for Finance and Operations (on-premises) deployment.</span></span>

1. <span data-ttu-id="68b2b-105">Öppna Reporting Services Configuration Manager-programmet.</span><span class="sxs-lookup"><span data-stu-id="68b2b-105">Open the Reporting Services Configuration Manager application.</span></span>
2. <span data-ttu-id="68b2b-106">Lämna standardnamnet **servernamn**, som bör vara namnet på den aktuella datorn och **rapportserverinstansen**, **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="68b2b-106">Leave the default **Server name**, which should be the name of the current machine, and the **Report Server Instance**, **MSSQLSERVER**.</span></span>
3. <span data-ttu-id="68b2b-107">Klicka på **anslut**.</span><span class="sxs-lookup"><span data-stu-id="68b2b-107">Click **Connect**.</span></span>

    <span data-ttu-id="68b2b-108">[![Anslutning för rapporteringsserverkonfiguration](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-108">[![Reporting services configuration connection](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span></span>

4. <span data-ttu-id="68b2b-109">Klicka på fliken **tjänstkonto** och verifiera att inställningarna stämmer med bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="68b2b-109">Click the **Service Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="68b2b-110">[![Fliken Tjänstkonto](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-110">[![Service account tab](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span></span>

5. <span data-ttu-id="68b2b-111">Klicka på fliken **Webbtjänst-URL** och verifiera att inställningarna stämmer med bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="68b2b-111">Click the **Web Service URL** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="68b2b-112">[![Fliken Webbtjänst-URL](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-112">[![Web service URL tab](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span></span>

6. <span data-ttu-id="68b2b-113">Klicka på fliken **database** och kontrollera att den **databasnamn** och **inställning av autentiseringsuppgifter** matchar följande bild.</span><span class="sxs-lookup"><span data-stu-id="68b2b-113">Click the **Database** tab and verify that the **Database Name** and **Credential settings** match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="68b2b-114">Du behöver skapa en ny databas.</span><span class="sxs-lookup"><span data-stu-id="68b2b-114">You will need to create a new database.</span></span> <span data-ttu-id="68b2b-115">För att göra detta klickar du på **ändra databasen** och kontrollerar att det nya databasnamnet är: **DynamicsAxReportServer**.</span><span class="sxs-lookup"><span data-stu-id="68b2b-115">To do this, click **Change Database**, and then verify that the new database name is: **DynamicsAxReportServer**.</span></span>

    <span data-ttu-id="68b2b-116">[![Fliken Databas](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-116">[![database tab](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span></span>

7. <span data-ttu-id="68b2b-117">Klicka på fliken **Webbportal-URL** och verifiera att inställningarna stämmer med bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="68b2b-117">Click the **Web Portal URL** tab and verify that the settings match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="68b2b-118">Du måste klicka på **Använd** för att skapa och konfigurera portalen.</span><span class="sxs-lookup"><span data-stu-id="68b2b-118">You must click **Apply** to create and properly configure the Portal.</span></span>

    <span data-ttu-id="68b2b-119">[![Fliken Webbportal-URL](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-119">[![web portal url tab](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span></span>

    <span data-ttu-id="68b2b-120">När portalen har konfigurerats kommer fliken **webbportal** att matcha följande bild.</span><span class="sxs-lookup"><span data-stu-id="68b2b-120">After the Portal is configured, the **Web Portal** tab will match the following graphic.</span></span>

    <span data-ttu-id="68b2b-121">[![Fliken Webbportal](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-121">[![web portal tab](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span></span>

8. <span data-ttu-id="68b2b-122">Klicka på rapport-URL om du vill visa webbportalen SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="68b2b-122">Click the reports URL to view the SQL Server Reporting Services web portal.</span></span>
9. <span data-ttu-id="68b2b-123">När du är på portalen kan du skapa en ny mapp med namnet **Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="68b2b-123">When you are in the portal, create a new folder named **Dynamics**.</span></span>

    <span data-ttu-id="68b2b-124">[![Mappen Dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-124">[![dynamics folder](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span></span>

10. <span data-ttu-id="68b2b-125">I **Reporting Services Configuration Manager** klickar du på fliken **E-postinställningar** och verifierar att inställningarna stämmer med bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="68b2b-125">In the **Reporting Services Configuration Manager**, click the **E-mail Settings** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="68b2b-126">[![Fliken E-postinställningar](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-126">[![email settings tab](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span></span>

11. <span data-ttu-id="68b2b-127">Klicka på fliken **Körningskonto** och verifiera att inställningarna stämmer med bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="68b2b-127">Click the **Execution Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="68b2b-128">[![Fliken Körningskonto](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-128">[![execution account tab](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span></span>

    <span data-ttu-id="68b2b-129">Ändra inte standardinställningarna på fliken **krypteringsnycklar**.</span><span class="sxs-lookup"><span data-stu-id="68b2b-129">Don't change the default settings on the **Encryption Keys** tab.</span></span>

    <span data-ttu-id="68b2b-130">[![Fliken Krypteringsnycklar](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-130">[![encryption keys tab](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span></span>

12. <span data-ttu-id="68b2b-131">Klicka på fliken **Abonnemangsinställningar** och verifiera att inställningarna stämmer med bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="68b2b-131">Click the **Subscription Settings** tab, and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="68b2b-132">[![Fliken Abonnemangsinställningar](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-132">[![subscription settings tab](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span></span>

    <span data-ttu-id="68b2b-133">Ändra inte standardinställningarna på fliken **Skala ut-distribution**.</span><span class="sxs-lookup"><span data-stu-id="68b2b-133">Don't change the default settings on the **Scale-out Deployment** tab.</span></span>

    <span data-ttu-id="68b2b-134">[![Fliken Skala ut-distribution](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-134">[![scale-out deployment tab](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span></span>

    <span data-ttu-id="68b2b-135">Ändra inte standardinställningarna på fliken **Power BI Integration**.</span><span class="sxs-lookup"><span data-stu-id="68b2b-135">Don't change the default settings on the **Power BI Integration** tab.</span></span>

    <span data-ttu-id="68b2b-136">[![Fliken Power BI-integration](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-136">[![power bi integration tab](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span></span>

13. <span data-ttu-id="68b2b-137">Klicka på **Avsluta** för att stänga **Reporting Services Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="68b2b-137">Click **Exit** to close the **Reporting Services Configuration Manager**.</span></span>

    <span data-ttu-id="68b2b-138">[![Stänga reporting services configuration manager](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span><span class="sxs-lookup"><span data-stu-id="68b2b-138">[![close reporting services configuration manager](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span></span>
