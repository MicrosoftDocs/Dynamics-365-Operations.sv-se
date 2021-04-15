---
title: Produkter och kategorier saknas efter en miljökopia
description: Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när produkter och kategorier saknas när en site har kopierats mellan olika miljöer eller i samma miljö.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 527fd0fa62775f65f61b538474b1d45d1a0155ed
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801733"
---
# <a name="products-and-categories-missing-after-environment-copy"></a><span data-ttu-id="71c75-103">Produkter och kategorier saknas efter en miljökopia</span><span class="sxs-lookup"><span data-stu-id="71c75-103">Products and categories missing after environment copy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="71c75-104">Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när produkter och kategorier saknas när en site har kopierats mellan olika miljöer eller i samma miljö.</span><span class="sxs-lookup"><span data-stu-id="71c75-104">This topic provides troubleshooting guidance that can help when products and categories are missing after a site is copied between environments or within the same environment.</span></span>

## <a name="description"></a><span data-ttu-id="71c75-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="71c75-105">Description</span></span>

<span data-ttu-id="71c75-106">När en webbplats har kopierats från en miljö till en annan, eller inom samma miljö, saknas produkter och kategorier från webbplats.</span><span class="sxs-lookup"><span data-stu-id="71c75-106">After a site is copied from one environment to another, or within the same environment, the products and categories are missing from the site.</span></span> <span data-ttu-id="71c75-107">Produkter och kategorier saknas i e-handelsbutiken och på fliken **Produkter** i Commerce-webbplatsbyggaren.</span><span class="sxs-lookup"><span data-stu-id="71c75-107">The products and categories will be missing from the e-commerce storefront and from the **Products** tab in Commerce site builder.</span></span>

## <a name="resolution"></a><span data-ttu-id="71c75-108">Upplösning</span><span class="sxs-lookup"><span data-stu-id="71c75-108">Resolution</span></span>

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a><span data-ttu-id="71c75-109">Mappa numret på kanalens operativsystem till en ny kopierad webbplats i Commerce-webbplatsbyggaren</span><span class="sxs-lookup"><span data-stu-id="71c75-109">Map the channel operating unit number to a newly copied site in Commerce site builder</span></span>

<span data-ttu-id="71c75-110">Mappa numret på kanalens operativsystem (OUN) till en ny kopierad webbplats i Commerce-webbplatsbyggaren, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="71c75-110">To map the channel operating unit number (OUN) to a newly copied site in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="71c75-111">Markera den nya kopierade webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="71c75-111">Select the newly copied site.</span></span>
1. <span data-ttu-id="71c75-112">Under **webbplatsinställningar**, välj **kanaler**.</span><span class="sxs-lookup"><span data-stu-id="71c75-112">Under **Site settings**, select **Channels**.</span></span>
1. <span data-ttu-id="71c75-113">Bredvid kanalens namn väljer du ellipsen (**...**) och väljer sedan **Ändra nätbutikskanal**.</span><span class="sxs-lookup"><span data-stu-id="71c75-113">Next to the channel name, select the ellipsis (**...**), and then select **Change online store channel**.</span></span>
1. <span data-ttu-id="71c75-114">I dialogrutan **Ändra nätbutikskanal** väljer du den kanal som du vill mappa till den nya, kopierade webbplatsen och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="71c75-114">In the **Change online store channel** dialog box, select the channel to map to the newly copied site, and then select **OK**.</span></span>
1. <span data-ttu-id="71c75-115">Välj **Spara och publicera**.</span><span class="sxs-lookup"><span data-stu-id="71c75-115">Select **Save and publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71c75-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="71c75-116">Additional resources</span></span>

[<span data-ttu-id="71c75-117">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="71c75-117">Associate a Dynamics 365 Commerce site with an online channel</span></span>](../associate-site-online-store.md)
