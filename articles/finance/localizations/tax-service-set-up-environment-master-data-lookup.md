---
title: Ställa in en miljö för att söka efter huvuddata
description: I det här avsnittet beskrivs hur du ställer in din miljön att använda sökfunktionen huvuddata för skatteberäkning.
author: kai-cloud
ms.date: 04/21/2021
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
ms.openlocfilehash: 9f9b385df1db60b27698d90281c43fabb574af49
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924164"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="8e330-103">Ställa in en miljö för att söka efter huvuddata</span><span class="sxs-lookup"><span data-stu-id="8e330-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8e330-104">I det här avsnittet beskrivs hur du ställer in din miljön att använda sökfunktionen huvuddata för skatteberäkning.</span><span class="sxs-lookup"><span data-stu-id="8e330-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="8e330-105">Konfigurera Power Platform-integrering i Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8e330-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="8e330-106">Mer information finns i [Microsoft Power Platform-integrering – tilläggsöversikt](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8e330-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="8e330-107">Konfigurera Dynamics 365 Finance och Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="8e330-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="8e330-108">Mer information finns i [Skaffa lösningen](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) samt i [Autentisering och auktorisering](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="8e330-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="8e330-109">Ställ in följande entiteter:</span><span class="sxs-lookup"><span data-stu-id="8e330-109">Set up the following entities.</span></span> <span data-ttu-id="8e330-110">Mer information finns i [Aktivera virtuella entiteter](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="8e330-110">For more information, see [Enabling virtual entities](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span></span>
      - <span data-ttu-id="8e330-111">CompanyInfoEntity</span><span class="sxs-lookup"><span data-stu-id="8e330-111">CompanyInfoEntity</span></span>
      - <span data-ttu-id="8e330-112">CurrencyEntity</span><span class="sxs-lookup"><span data-stu-id="8e330-112">CurrencyEntity</span></span>
      - <span data-ttu-id="8e330-113">CustCustomerV3Entity</span><span class="sxs-lookup"><span data-stu-id="8e330-113">CustCustomerV3Entity</span></span>
      - <span data-ttu-id="8e330-114">DeliveryTermsEntity</span><span class="sxs-lookup"><span data-stu-id="8e330-114">DeliveryTermsEntity</span></span>
      - <span data-ttu-id="8e330-115">EcoResProductCategoryEntity</span><span class="sxs-lookup"><span data-stu-id="8e330-115">EcoResProductCategoryEntity</span></span>
      - <span data-ttu-id="8e330-116">EcoResReleasedProductV2Entity</span><span class="sxs-lookup"><span data-stu-id="8e330-116">EcoResReleasedProductV2Entity</span></span>
      - <span data-ttu-id="8e330-117">LogisticsAddressCityEntity</span><span class="sxs-lookup"><span data-stu-id="8e330-117">LogisticsAddressCityEntity</span></span>
      - <span data-ttu-id="8e330-118">LogisticsAddressCountryRegionTranslationEntity</span><span class="sxs-lookup"><span data-stu-id="8e330-118">LogisticsAddressCountryRegionTranslationEntity</span></span>
      - <span data-ttu-id="8e330-119">LogisticsAddressStateEntity</span><span class="sxs-lookup"><span data-stu-id="8e330-119">LogisticsAddressStateEntity</span></span>
      - <span data-ttu-id="8e330-120">PurchProcurementChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="8e330-120">PurchProcurementChargeCDSEntity</span></span>
      - <span data-ttu-id="8e330-121">SalesChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="8e330-121">SalesChargeCDSEntity</span></span>
      - <span data-ttu-id="8e330-122">TaxGroupEntity</span><span class="sxs-lookup"><span data-stu-id="8e330-122">TaxGroupEntity</span></span>
      - <span data-ttu-id="8e330-123">TaxItemGroupHeadingEntity</span><span class="sxs-lookup"><span data-stu-id="8e330-123">TaxItemGroupHeadingEntity</span></span>
      - <span data-ttu-id="8e330-124">VendVendorV2Entity</span><span class="sxs-lookup"><span data-stu-id="8e330-124">VendVendorV2Entity</span></span>
4. <span data-ttu-id="8e330-125">Konfigurera Dynamics 365 Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="8e330-125">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="8e330-126">Skapa en tjänstebegäran för Microsoft i syfte att aktivera förhandsversioner av följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="8e330-126">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="8e330-127">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="8e330-127">ERCdsFeature</span></span>
      - <span data-ttu-id="8e330-128">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="8e330-128">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="8e330-129">Gå till arbetsytan **Funktionshantering** och aktivera följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="8e330-129">Go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="8e330-130">(Förhandsgranskning) Dataverse-datakällor för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="8e330-130">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="8e330-131">(Förhandsversion) Stöd för Dataverse-datakällor</span><span class="sxs-lookup"><span data-stu-id="8e330-131">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="8e330-132">(Förhandsversion) Globaliseringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="8e330-132">(Preview) Globalization features</span></span>

5. <span data-ttu-id="8e330-133">Logga in på RCS med hjälp av ett admin-konto för klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="8e330-133">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="8e330-134">Gå till **Elektronisk rapportering** > **Anslutna program**.</span><span class="sxs-lookup"><span data-stu-id="8e330-134">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="8e330-135">Om du vill lägga till en post, välj **Ny** och ange följande fältinformation.</span><span class="sxs-lookup"><span data-stu-id="8e330-135">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="8e330-136">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="8e330-136">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="8e330-137">I fältet **Typ** väljer du **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="8e330-137">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="8e330-138">I fältet **Program** anger du din Dataverse-URL.</span><span class="sxs-lookup"><span data-stu-id="8e330-138">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="8e330-139">I fältet **Klientorganisation** anger du din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="8e330-139">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="8e330-140">I fältet **Anpassad URL** anger du din Dataverse-URL och tillägger "/api/data/v9.1".</span><span class="sxs-lookup"><span data-stu-id="8e330-140">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="8e330-141">Välj **Kontrollera anslutning** och slutför anslutningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="8e330-141">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="8e330-142">[![Knappen Kontrollera anslutning](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="8e330-142">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="8e330-143">Gå till **Elektronisk rapportering** > **Skattekonfigurationer** och importera skattekonfigurationer från [Skattekonfigurationer](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="8e330-143">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="8e330-144">[![Sidan Skattekonfigurationer, modellträd för skattedata](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="8e330-144">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="8e330-145">Gå till **Modellmappning för beskattningsbart dokument** eller **Modellmappning för Dataverse** om du använder en Microsoft-konfiguration, och i fältet **Anslutet program** väljer du sedan den post som du skapade i steg 7.</span><span class="sxs-lookup"><span data-stu-id="8e330-145">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="8e330-146">Ange **Standard för modellmappning** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8e330-146">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="8e330-147">[![Modellmappningssida](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="8e330-147">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
