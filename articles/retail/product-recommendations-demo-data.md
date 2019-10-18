---
title: Demodata för produktrekommendationer i flera kanaler
description: Det här dokumentet syftar till att ge vägledning om hur du kan utnyttja produktrekommendationer i flera kanaler i en nivå 1 enskilda miljöer med hjälp av i förväg ifyllda, anpassningsbara demodata.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 81af4c1bb7828c9b346a3ef514d8657e853dcefb
ms.sourcegitcommit: c526cfd1f823df1ff33ded95e599a72f0a15cc5a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2226461"
---
# <a name="omni-channel-product-recommendations-demo-data"></a><span data-ttu-id="30087-103">Demodata för produktrekommendationer i flera kanaler</span><span class="sxs-lookup"><span data-stu-id="30087-103">Omni-channel product recommendations demo data</span></span>

<span data-ttu-id="30087-104">Det här dokumentet syftar till att ge vägledning om hur du kan utnyttja produktrekommendationer i flera kanaler i en nivå 1 enskilda miljöer med hjälp av i förväg ifyllda, anpassningsbara demodata.</span><span class="sxs-lookup"><span data-stu-id="30087-104">This document aims to provide guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="30087-105">Produktrekommendationer i flera kanaler innehåller en uppsättning av redaktionellt granskade eller programmässigt genererade listor över produkter i en ordnad lista.</span><span class="sxs-lookup"><span data-stu-id="30087-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated ordered list of products.</span></span> <span data-ttu-id="30087-106">Dessa listor kan användas i flera situationer, beroende på vad som behövs i verksamheten.</span><span class="sxs-lookup"><span data-stu-id="30087-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="30087-107">Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt.](product-recommendaitons-overview.md)</span><span class="sxs-lookup"><span data-stu-id="30087-107">For more information about product recommendation lists, see [Product recommendations overview.](product-recommendaitons-overview.md)</span></span>

<span data-ttu-id="30087-108">För att produktrekommendationer på nivåer 2 och högre beräknas Dynamics-miljöer automatiskt baserat på kunddata.</span><span class="sxs-lookup"><span data-stu-id="30087-108">For Tier-2 and higher Dynamics Environments product recommendations are automatically computed based on customer data.</span></span>
<span data-ttu-id="30087-109">Att använda demodata för produktrekommendationer inaktiverar inte någon produktrekommendationslösning som redan har etablerats i miljön och kostnader som är förknippade med användningen.</span><span class="sxs-lookup"><span data-stu-id="30087-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="30087-110">Produktrekommendationer på nivå 1 baseras bara på de statiska demodata som lagras i en csv-fil.</span><span class="sxs-lookup"><span data-stu-id="30087-110">For Tier-1 environments product recommendations are based only off the static demo data stored in a csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="30087-111">Aktivera demodata för produktrekommendationer i en miljö</span><span class="sxs-lookup"><span data-stu-id="30087-111">Enabling product recommendations demo data in an environment</span></span>

<span data-ttu-id="30087-112">Kunderna måste distribuera **tillägget Dynamics 365 Commerce förhandsgranskningsdemo** för respektive miljö, som automatiskt aktiverar produktrekommendationer för demodata.</span><span class="sxs-lookup"><span data-stu-id="30087-112">Customers need to deploy the **Dynamics 365 Commerce Preview Demo Extension** to the respective environment, which automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="30087-113">Standarddemodata</span><span class="sxs-lookup"><span data-stu-id="30087-113">Default demo data</span></span>
<span data-ttu-id="30087-114">Varje enskild miljö innehåller en förinstallerad uppsättning med demodata för produktrekommendationer som lagras i den kommaseparerade filen **"reco_demo_data. csv"**, som finns i samma mapp som det här dokumentet på Retail Server.</span><span class="sxs-lookup"><span data-stu-id="30087-114">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated **‘reco_demo_data.csv’** file, located in the same folder as this document on Retail Server.</span></span>

<span data-ttu-id="30087-115">Dessa data struktureras längs följande kolumner</span><span class="sxs-lookup"><span data-stu-id="30087-115">This data is structured along the following columns</span></span>

| <span data-ttu-id="30087-116">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="30087-116">Column name</span></span>         | <span data-ttu-id="30087-117">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="30087-117">Mandatory</span></span>          | <span data-ttu-id="30087-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="30087-118">Description</span></span>                                                                                                                                 | <span data-ttu-id="30087-119">Möjliga värden</span><span class="sxs-lookup"><span data-stu-id="30087-119">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="30087-120">Recolist</span><span class="sxs-lookup"><span data-stu-id="30087-120">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="30087-122">Den specifika listtypen för produktrekommendationer som demodatapunkten ska generera.</span><span class="sxs-lookup"><span data-stu-id="30087-122">The specific product   recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="30087-123">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="30087-123">RecoBestSelling</span></span></li><li><span data-ttu-id="30087-124">RecoNew</span><span class="sxs-lookup"><span data-stu-id="30087-124">RecoNew</span></span></li><li><span data-ttu-id="30087-125">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="30087-125">RecoTrending</span></span></li><li><span data-ttu-id="30087-126">RecoCart</span><span class="sxs-lookup"><span data-stu-id="30087-126">RecoCart</span></span></li><li><span data-ttu-id="30087-127">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="30087-127">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="30087-128">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="30087-128">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="30087-130">Det specifika driftenhetsnummer som produktrekommendationer förväntas bli indelade på.</span><span class="sxs-lookup"><span data-stu-id="30087-130">The specific   operating unit number where product recommendations are expected to be   surfaced in.</span></span>                                        |                                                                              |
| <span data-ttu-id="30087-131">Kategori</span><span class="sxs-lookup"><span data-stu-id="30087-131">Category</span></span>            |                    |    <span data-ttu-id="30087-132">Den kategori som den specifika listan ska returneras för.</span><span class="sxs-lookup"><span data-stu-id="30087-132">The category the   specific list should be returned for.</span></span> <span data-ttu-id="30087-133">Om ingen kategori har angetts är listan endast till för navigeringshierarkin.</span><span class="sxs-lookup"><span data-stu-id="30087-133">If no category is specified, list is   for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="30087-134">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="30087-134">SeedItemId</span></span>          |                    |    <span data-ttu-id="30087-135">För listor som kräver startvärde (RecoPeopleAlsoBuy och RecoCart) av produkten bör dessa listor innehålla ytterligare produkter för.</span><span class="sxs-lookup"><span data-stu-id="30087-135">For lists that   require seed (RecoPeopleAlsoBuy and RecoCart) the product those lists should   show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="30087-136">ItemIds</span><span class="sxs-lookup"><span data-stu-id="30087-136">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="30087-138">En eller flera produkter som kommer att returneras som resultat, avgränsade med **";"**.</span><span class="sxs-lookup"><span data-stu-id="30087-138">One or more products   to be returned as the result, separated by **‘;’**.</span></span>                                                                  |                                                                              |


## <a name="customize-demo-data"></a><span data-ttu-id="30087-139">Anpassa demodata</span><span class="sxs-lookup"><span data-stu-id="30087-139">Customize demo data</span></span>
<span data-ttu-id="30087-140">Kunder kan redigera standarddemodata med all produkt- och kategoriinformation som är konfigurerad i HQ.</span><span class="sxs-lookup"><span data-stu-id="30087-140">Customers can edit the default demo data with any product and category information that is configured in HQ.</span></span> <span data-ttu-id="30087-141">När du har uppdaterat CSV-filen kommer de produktrekommendationer som returneras till kunderna att omedelbart avspegla ändringarna.</span><span class="sxs-lookup"><span data-stu-id="30087-141">Once the CSV is updated, the Product Recommendations returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="30087-142">Tillägget innehåller en datafil som heter RecoMockDataset.csv, vilket gör att kunden kan styra den datauppsättning som används för att styrka resultaten från samma modell.</span><span class="sxs-lookup"><span data-stu-id="30087-142">The extension contains a datafile called RecoMockDataset.csv which allows the customer to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="30087-143">Filnamnet kan styras genom tilläggskonfiguration med hjälp av inställningen **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="30087-143">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="30087-144">Detta gör det möjligt för kunderna att ha flera datauppsättningar tillgängliga som kan växlas enkelt genom konfiguration.</span><span class="sxs-lookup"><span data-stu-id="30087-144">This enables the customers to have multiple datasets available that can be switched between easily through configuration.</span></span>

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a><span data-ttu-id="30087-145">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="30087-145">Additional resources</span></span>

[<span data-ttu-id="30087-146">Översikt över produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="30087-146">Product recommendations overview</span></span>](product-recommendations-overview.md)

[<span data-ttu-id="30087-147">Miljöplanering</span><span class="sxs-lookup"><span data-stu-id="30087-147">Environment planning</span></span>](environment-planning.md)
