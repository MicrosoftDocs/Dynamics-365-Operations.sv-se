---
title: Skapa en försäljningsorder för en konfigurerbar produkt
description: Denna procedur visar hur du tillämpar en konfigureringsmall på en produkt i en försäljningsorder.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8607de5705354aa58c985fb536f3e1d52acd1f37
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921299"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="a0a21-103">Skapa en försäljningsorder för en konfigurerbar produkt</span><span class="sxs-lookup"><span data-stu-id="a0a21-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a0a21-104">Denna procedur visar hur du tillämpar en konfigureringsmall på en produkt i en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a0a21-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="a0a21-105">Detta exempel använder högtalarmodellen D0006 i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="a0a21-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="a0a21-106">Vanligtvis använder en försäljningsorderbehandlare denna procedur.</span><span class="sxs-lookup"><span data-stu-id="a0a21-106">Typically, a sales order processor uses this procedure.</span></span>

## <a name="create-a-sales-order"></a><span data-ttu-id="a0a21-107">Skapa en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="a0a21-107">Create a sales order</span></span>

1. <span data-ttu-id="a0a21-108">Gå till **Försäljning och marknadsföring \> Arbetsytor \> Försäljningsorderbearbetning och förfrågan**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-108">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="a0a21-109">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-109">Select **New**.</span></span>
1. <span data-ttu-id="a0a21-110">Välj **Försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-110">Select **Sales order**.</span></span>
1. <span data-ttu-id="a0a21-111">I fältet **kundkonto** välj *US-001*.</span><span class="sxs-lookup"><span data-stu-id="a0a21-111">In the **Customer account** field, select *US-001*.</span></span> 
1. <span data-ttu-id="a0a21-112">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-112">Select **OK**.</span></span>
1. <span data-ttu-id="a0a21-113">I fältet **Artikelnummer**, välj *D0006*.</span><span class="sxs-lookup"><span data-stu-id="a0a21-113">In the **Item number** field, select *D0006*.</span></span>
    * <span data-ttu-id="a0a21-114">För den här uppgiften måste du välja en konfigurerbar produkt.</span><span class="sxs-lookup"><span data-stu-id="a0a21-114">For this task, you must select a configurable product.</span></span>  
1. <span data-ttu-id="a0a21-115">Välj **Produkt och leverans**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-115">Select **Product and supply**.</span></span>
1. <span data-ttu-id="a0a21-116">Välj **Konfigurera rad**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-116">Select **Configure line**.</span></span>
    * <span data-ttu-id="a0a21-117">Observera att priset har ändrats baserat på den konfiguration som valdes, och att fältet **Inkludera kabel** nu anges som *True*.</span><span class="sxs-lookup"><span data-stu-id="a0a21-117">Note that the price has changed, based on the configuration that was selected, and that the **Include cable** field is now set to *True*.</span></span>  
    * <span data-ttu-id="a0a21-118">Observera valt standardpris och valda inställningar för kabeln.</span><span class="sxs-lookup"><span data-stu-id="a0a21-118">Note the default price and the settings that are selected for the cable.</span></span>  
1. <span data-ttu-id="a0a21-119">Välj **Läs in mall**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-119">Select **Load template**.</span></span>
    * <span data-ttu-id="a0a21-120">I det här exemplet visas hur du kan använda en mall för att välja en fördefinierad konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a0a21-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="a0a21-121">Om du använder den här proceduren som en uppgiftsguide och vill se andra tillgängliga attributvärden, måste du välja knappen **Lås upp**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must select the **Unlock** button.</span></span>  
1. <span data-ttu-id="a0a21-122">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-122">Select **OK**.</span></span>
1. <span data-ttu-id="a0a21-123">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-123">Select **OK**.</span></span>
1. <span data-ttu-id="a0a21-124">Visa avsnittet **Raddetaljer**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-124">Expand the **Line details** section.</span></span>
1. <span data-ttu-id="a0a21-125">Välj fliken **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="a0a21-125">Select the **Product** tab.</span></span>
    * <span data-ttu-id="a0a21-126">Artikelns konfiguration anges nu under produktdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="a0a21-126">The configuration of the item is now listed under the product dimensions.</span></span>  
1. <span data-ttu-id="a0a21-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a0a21-127">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]