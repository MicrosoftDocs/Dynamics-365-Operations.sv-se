---
title: Hämta produktrekommendationer med hjälp av demodata
description: Det här dokumentet ger vägledning om hur du kan utnyttja produktrekommendationer i flera kanaler i en nivå 1 enskilda miljöer med hjälp av i förväg ifyllda, anpassningsbara demodata.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1456feb0665b6ec79a36a3704f17da80ffd759a0
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042790"
---
# <a name="get-product-recommendations-using-demo-data"></a><span data-ttu-id="4127a-103">Hämta produktrekommendationer med hjälp av demodata</span><span class="sxs-lookup"><span data-stu-id="4127a-103">Get product recommendations using demo data</span></span>
<span data-ttu-id="4127a-104">Det här dokumentet ger vägledning om hur du kan utnyttja produktrekommendationer i flera kanaler i en nivå 1 enskilda miljöer med hjälp av i förväg ifyllda, anpassningsbara demodata.</span><span class="sxs-lookup"><span data-stu-id="4127a-104">This document provides guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="4127a-105">Produktrekommendationer i flera kanaler innehåller en uppsättning av redaktionellt granskade eller programmässigt genererade listor över produkter i en ordnad lista.</span><span class="sxs-lookup"><span data-stu-id="4127a-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated list of products.</span></span> <span data-ttu-id="4127a-106">Dessa listor kan användas i flera situationer, beroende på vad som behövs i verksamheten.</span><span class="sxs-lookup"><span data-stu-id="4127a-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="4127a-107">Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="4127a-107">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

<span data-ttu-id="4127a-108">För att produktrekommendationer på nivåer 2 och högre beräknas Dynamics 365-miljöer automatiskt baserat på kunddata.</span><span class="sxs-lookup"><span data-stu-id="4127a-108">For Tier-2 and higher Dynamics 365 environments, product recommendations are automatically computed based on customer data.</span></span> <span data-ttu-id="4127a-109">Att använda demodata för produktrekommendationer inaktiverar inte någon produktrekommendationslösning som redan har etablerats i miljön och kostnader som är förknippade med användningen.</span><span class="sxs-lookup"><span data-stu-id="4127a-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="4127a-110">Produktrekommendationer på nivå 1 baseras bara på de statiska demodata som lagras i en .csv-fil.</span><span class="sxs-lookup"><span data-stu-id="4127a-110">For Tier-1 environments, product recommendations are based only off the static demo data stored in a .csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="4127a-111">Aktivera demodata för produktrekommendationer i en miljö</span><span class="sxs-lookup"><span data-stu-id="4127a-111">Enabling product recommendations demo data in an environment</span></span>
<span data-ttu-id="4127a-112">För att aktivera produktrekommendationer demonstrationsdatum måste du distribuera Dynamics 365 Commerce förhandsgranskningsdemo för respektive miljö.</span><span class="sxs-lookup"><span data-stu-id="4127a-112">To enable product recommensations demo date, you need to deploy the Dynamics 365 Commerce Preview Demo Extension to the respective environment.</span></span> <span data-ttu-id="4127a-113">Då aktiveras demonstrationsdata för produktrekommendationer automatiskt.</span><span class="sxs-lookup"><span data-stu-id="4127a-113">Doing so automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="4127a-114">Standarddemodata</span><span class="sxs-lookup"><span data-stu-id="4127a-114">Default demo data</span></span>
<span data-ttu-id="4127a-115">Varje enskild miljö innehåller en förinstallerad uppsättning med demodata för produktrekommendationer som lagras i den kommaseparerade filen "reco_demo_data. csv", som finns i skalningsenhet för handel.</span><span class="sxs-lookup"><span data-stu-id="4127a-115">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated ‘reco_demo_data.csv’ file, located on the Commerce Scale Unit.</span></span>

<span data-ttu-id="4127a-116">Dessa data struktureras längs följande kolumner.</span><span class="sxs-lookup"><span data-stu-id="4127a-116">The data is structured along the following columns.</span></span>

| <span data-ttu-id="4127a-117">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="4127a-117">Column name</span></span>         | <span data-ttu-id="4127a-118">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="4127a-118">Mandatory</span></span>          | <span data-ttu-id="4127a-119">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4127a-119">Description</span></span>                                                                                                                                 | <span data-ttu-id="4127a-120">Möjliga värden</span><span class="sxs-lookup"><span data-stu-id="4127a-120">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="4127a-121">Recolist</span><span class="sxs-lookup"><span data-stu-id="4127a-121">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="4127a-123">Den specifika listtypen för produktrekommendationer som demodatapunkten ska generera.</span><span class="sxs-lookup"><span data-stu-id="4127a-123">The specific product recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="4127a-124">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="4127a-124">RecoBestSelling</span></span></li><li><span data-ttu-id="4127a-125">RecoNew</span><span class="sxs-lookup"><span data-stu-id="4127a-125">RecoNew</span></span></li><li><span data-ttu-id="4127a-126">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="4127a-126">RecoTrending</span></span></li><li><span data-ttu-id="4127a-127">RecoCart</span><span class="sxs-lookup"><span data-stu-id="4127a-127">RecoCart</span></span></li><li><span data-ttu-id="4127a-128">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="4127a-128">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="4127a-129">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="4127a-129">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="4127a-131">Det specifika driftenhetsnummer som produktrekommendationer förväntas bli indelade.</span><span class="sxs-lookup"><span data-stu-id="4127a-131">The specific operating unit number where product recommendations are expected to be   surfaced.</span></span>                                        |                                                                              |
| <span data-ttu-id="4127a-132">Kategori</span><span class="sxs-lookup"><span data-stu-id="4127a-132">Category</span></span>            |                    |    <span data-ttu-id="4127a-133">Den kategori som den specifika listan ska returneras för.</span><span class="sxs-lookup"><span data-stu-id="4127a-133">The category the specific list should be returned for.</span></span> <span data-ttu-id="4127a-134">Om ingen kategori har angetts är listan endast till för navigeringshierarkin.</span><span class="sxs-lookup"><span data-stu-id="4127a-134">If no category is specified, the list is for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="4127a-135">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="4127a-135">SeedItemId</span></span>          |                    |    <span data-ttu-id="4127a-136">För listor som kräver startvärde (RecoPeopleAlsoBuy och RecoCart) av produkten bör dessa listor innehålla ytterligare produkter.</span><span class="sxs-lookup"><span data-stu-id="4127a-136">For lists that require seed (RecoPeopleAlsoBuy and RecoCart), the product those lists should show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="4127a-137">ItemIds</span><span class="sxs-lookup"><span data-stu-id="4127a-137">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="4127a-139">En eller flera produkter som kommer att returneras som resultat, avgränsade med ";".</span><span class="sxs-lookup"><span data-stu-id="4127a-139">One or more products to be returned as the result, separated by ‘;’.</span></span>                                                                  |                                                                              |

## <a name="customize-demo-data"></a><span data-ttu-id="4127a-140">Anpassa demodata</span><span class="sxs-lookup"><span data-stu-id="4127a-140">Customize demo data</span></span>
<span data-ttu-id="4127a-141">Du kan redigera standarddemodata med all produkt- och kategoriinformation som är konfigurerad i HQ.</span><span class="sxs-lookup"><span data-stu-id="4127a-141">You can edit the default demo data with any product and category information configured in HQ.</span></span> <span data-ttu-id="4127a-142">När du har uppdaterat .csv-filen kommer de produktrekommendationer som returneras till kunderna att omedelbart avspegla ändringarna.</span><span class="sxs-lookup"><span data-stu-id="4127a-142">Once you update the .csv, the product recommendations that are returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="4127a-143">Tillägget innehåller en datafil som heter RecoMockDataset.csv, vilket gör att du kan styra den datauppsättning som används för att styrka resultaten från samma modell.</span><span class="sxs-lookup"><span data-stu-id="4127a-143">The extension contains a datafile called 'RecoMockDataset.csv' which allows you to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="4127a-144">Filnamnet kan styras genom tilläggskonfiguration med hjälp av inställningen **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="4127a-144">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="4127a-145">Detta gör det möjligt för dig att ha flera datauppsättningar tillgängliga som kan växlas enkelt genom konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4127a-145">This enables you to have multiple datasets available that can be switched between easily through configuration.</span></span>


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a><span data-ttu-id="4127a-146">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4127a-146">Additional Resources</span></span>

[<span data-ttu-id="4127a-147">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="4127a-147">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="4127a-148">Miljöplanering</span><span class="sxs-lookup"><span data-stu-id="4127a-148">Environment planning</span></span>](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
