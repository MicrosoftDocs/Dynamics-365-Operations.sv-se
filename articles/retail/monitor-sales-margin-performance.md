---
title: "Övervaka resultat för försäljning och marginaler"
description: "Du kan övervaka försäljning och marginalprestanda i realtid med hjälp av Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailSales
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85123
ms.assetid: ddd15820-c3e6-4607-819e-8cef744ce9c9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4b90d7a9290fb7485fffe959057516795226d99b
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="monitor-sales-and-margin-performance"></a><span data-ttu-id="f61d5-103">Övervaka försäljningsresultat och marginaler</span><span class="sxs-lookup"><span data-stu-id="f61d5-103">Monitor sales and margin performance</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="f61d5-104">Du kan övervaka försäljning och marginalprestanda i realtid med hjälp av Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="f61d5-104">You can monitor sales and margin performance in real time using Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="f61d5-105">Som en del av Dynamics 365 for Retail kan användare övervaka prestanda för försäljning och marginaler i realtid på andra nivåer i organisationshierarkin för följande dimensioner:</span><span class="sxs-lookup"><span data-stu-id="f61d5-105">As part of Dynamics 365 for Retail, users can monitor sales and margin performance in real time across different levels of the organization hierarchy for the following dimensions:</span></span>

-   <span data-ttu-id="f61d5-106">Produkter</span><span class="sxs-lookup"><span data-stu-id="f61d5-106">Products</span></span>
-   <span data-ttu-id="f61d5-107">Kategorier</span><span class="sxs-lookup"><span data-stu-id="f61d5-107">Categories</span></span>
-   <span data-ttu-id="f61d5-108">Rabatter</span><span class="sxs-lookup"><span data-stu-id="f61d5-108">Discounts</span></span>
-   <span data-ttu-id="f61d5-109">År som tidsperiod</span><span class="sxs-lookup"><span data-stu-id="f61d5-109">Years as time period</span></span>
-   <span data-ttu-id="f61d5-110">Kassor/terminaler</span><span class="sxs-lookup"><span data-stu-id="f61d5-110">Registers/terminals</span></span>
-   <span data-ttu-id="f61d5-111">Personal/anställda</span><span class="sxs-lookup"><span data-stu-id="f61d5-111">Staff/employees</span></span>
-   <span data-ttu-id="f61d5-112">Kunder</span><span class="sxs-lookup"><span data-stu-id="f61d5-112">Customers</span></span>
-   <span data-ttu-id="f61d5-113">Driftenheter</span><span class="sxs-lookup"><span data-stu-id="f61d5-113">Operating units</span></span>

<span data-ttu-id="f61d5-114">Dessutom kan två unika rapporter, som används för strukturering av det hierarkiska rutnätet låta användare övervaka försäljning och marginalprestanda genom att detaljgranska från toppkategorinoden till enskilda lövnoder för kategorin i produktkategorihierarkin för butiken.</span><span class="sxs-lookup"><span data-stu-id="f61d5-114">Additionally, two unique reports that take advantage of hierarchical grid structuring let users monitor sales and margin performance by drilling down from the top category node to individual leaf nodes of the category in the default retail product category hierarchy.</span></span> <span data-ttu-id="f61d5-115">Användarna kan också gå ned från den översta driftenheten till en enskild kanal i organisationshierarkin som har definierats som standardorganisationshierarki för hierarkiändamål för butiksrapportering.</span><span class="sxs-lookup"><span data-stu-id="f61d5-115">Users can also drill-down from the top operating unit to an individual channel in the organization hierarchy that is defined as the default organization hierarchy for retail reporting hierarchy purposes.</span></span> <span data-ttu-id="f61d5-116">Du kan öppna rapporterna från någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="f61d5-116">You can open the reports from any of the following locations:</span></span>

-   <span data-ttu-id="f61d5-117">Arbetsytan **Butikshantering** &gt; **Butik** &gt; **Kanaler** &gt; **Butikshantering** &gt; **Rapporter**</span><span class="sxs-lookup"><span data-stu-id="f61d5-117">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports**</span></span>
-   <span data-ttu-id="f61d5-118">Arbetsytan **Kategori och produkthantering** &gt; **Butik** &gt; **Produkter och kategorier** &gt; **Butikshantering** &gt; **Rapporter**</span><span class="sxs-lookup"><span data-stu-id="f61d5-118">**Category and product management** workspace &gt; **Retail** &gt; **Product and categories** &gt; **Retail store management** &gt; **Reports**</span></span>
-   <span data-ttu-id="f61d5-119">Arbetsytan **Pris- och rabatthantering** &gt; **Butik** &gt; **Prissättning och rabatter** &gt; **Butikshantering** &gt; **Rapporter**</span><span class="sxs-lookup"><span data-stu-id="f61d5-119">**Pricing and discount management** workspace &gt; **Retail** &gt; **Pricing and discounts** &gt; **Retail store management** &gt; **Reports**</span></span>
-   <span data-ttu-id="f61d5-120">Avsnittet **Förfrågningar och rapporter** &gt; **Butik** &gt; **Förfrågningar och rapporter** &gt; **Försäljningsrapporter**</span><span class="sxs-lookup"><span data-stu-id="f61d5-120">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports**</span></span>



