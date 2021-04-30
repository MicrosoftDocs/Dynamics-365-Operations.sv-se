---
title: Ställa in en miljö för att söka efter huvuddata
description: I det här avsnittet beskrivs hur du ställer in din miljön att använda sökfunktionen huvuddata för skatteberäkning.
author: kai-cloud
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eda093a75898bace2f3c7968933b83ccafa7fabb
ms.sourcegitcommit: 66095f1b7e0fd2756aa29fd7deb9ce5392b7e0b2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2021
ms.locfileid: "5869100"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="87b82-103">Ställa in en miljö för att söka efter huvuddata</span><span class="sxs-lookup"><span data-stu-id="87b82-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="87b82-104">I det här avsnittet beskrivs hur du ställer in din miljön att använda sökfunktionen huvuddata för skatteberäkning.</span><span class="sxs-lookup"><span data-stu-id="87b82-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="87b82-105">Konfigurera Power Platform-integrering i Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="87b82-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="87b82-106">Mer information finns i [Microsoft Power Platform-integrering - tilläggsöversikt](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="87b82-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="87b82-107">Konfigurera Dynamics 365 Finance och Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="87b82-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="87b82-108">Mer information finns i [Skaffa lösningen](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) samt i [Autentisering och auktorisering](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="87b82-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="87b82-109">Importera *Virtuell entitetslösning för erforderlig skattetjänst* från [Virtuell entitet för skattetjänst](https://go.microsoft.com/fwlink/?linkid=2158160).</span><span class="sxs-lookup"><span data-stu-id="87b82-109">Import the *Prerequisite tax service virtual entity solution* from the [Tax service virtual entity](https://go.microsoft.com/fwlink/?linkid=2158160).</span></span>
4. <span data-ttu-id="87b82-110">Konfigurera Dynamics 365 Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="87b82-110">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="87b82-111">Skapa en tjänstebegäran för Microsoft i syfte att aktivera förhandsversioner av följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="87b82-111">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="87b82-112">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="87b82-112">ERCdsFeature</span></span>
      - <span data-ttu-id="87b82-113">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="87b82-113">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="87b82-114">I arbetsytan **Funktionshantering** aktiverar du följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="87b82-114">In Finance, go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="87b82-115">(Förhandsgranskning) Dataverse-datakällor för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="87b82-115">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="87b82-116">(Förhandsversion) Stöd för Dataverse-datakällor</span><span class="sxs-lookup"><span data-stu-id="87b82-116">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="87b82-117">(Förhandsversion) Globaliseringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="87b82-117">(Preview) Globalization features</span></span>

5. <span data-ttu-id="87b82-118">Logga in på RCS med hjälp av ett admin-konto för klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="87b82-118">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="87b82-119">Gå till **Elektronisk rapportering** > **Anslutna program**.</span><span class="sxs-lookup"><span data-stu-id="87b82-119">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="87b82-120">Om du vill lägga till en post, välj **Ny** och ange följande fältinformation.</span><span class="sxs-lookup"><span data-stu-id="87b82-120">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="87b82-121">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="87b82-121">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="87b82-122">I fältet **Typ** väljer du **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="87b82-122">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="87b82-123">I fältet **Program** anger du din Dataverse-URL.</span><span class="sxs-lookup"><span data-stu-id="87b82-123">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="87b82-124">I fältet **Klientorganisation** anger du din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="87b82-124">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="87b82-125">I fältet **Anpassad URL** anger du din Dataverse-URL och tillägger "/api/data/v9.1".</span><span class="sxs-lookup"><span data-stu-id="87b82-125">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="87b82-126">Välj **Kontrollera anslutning** och slutför anslutningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="87b82-126">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="87b82-127">[![Knappen Kontrollera anslutning](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="87b82-127">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="87b82-128">Gå till **Elektronisk rapportering** > **Skattekonfigurationer** och importera skattekonfigurationer från [Skattekonfigurationer](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="87b82-128">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="87b82-129">[![Sidan Skattekonfigurationer, modellträd för skattedata](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="87b82-129">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="87b82-130">Gå till **Modellmappning för beskattningsbart dokument** eller **Modellmappning för Dataverse** om du använder en Microsoft-konfiguration, och i fältet **Anslutet program** väljer du sedan den post som du skapade i steg 7.</span><span class="sxs-lookup"><span data-stu-id="87b82-130">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="87b82-131">Ange **Standard för modellmappning** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="87b82-131">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="87b82-132">[![Modellmappningssida](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="87b82-132">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
