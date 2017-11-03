---
title: "Utvärdera lönsamhet för kunder och produkter"
description: "Den här artikeln beskriver hur du kan använda det inbyggda minnet och realtidanalys för att komma åt, utforska och få insikt om kunder och produktlönsamhet från dina Microsoft Dynamics 365 for Retail-data."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 04ebc624212e6909eda7589b71cd84a22010e721
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="f452c-103">Utvärdera lönsamhet för kunder och produkter</span><span class="sxs-lookup"><span data-stu-id="f452c-103">Assess customer and product profitability</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="f452c-104">Den här artikeln beskriver hur du kan använda det inbyggda minnet och realtidanalys för att komma åt, utforska och få insikt om kunder och produktlönsamhet från dina Microsoft Dynamics 365 for Retail-data.</span><span class="sxs-lookup"><span data-stu-id="f452c-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Microsoft Dynamics 365 for Retail data.</span></span> 

<span data-ttu-id="f452c-105">Som en del av Dynamics 365 for Retail kan användare studera lönsamheten för de främsta kunderna (10-100) mellan olika nivåer i organisationshierarkin, baserat på ett av följande kriterier:</span><span class="sxs-lookup"><span data-stu-id="f452c-105">As part of Dynamics 365 for Retail, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

-   <span data-ttu-id="f452c-106">Försäljningsbelopp</span><span class="sxs-lookup"><span data-stu-id="f452c-106">Sales amount</span></span>
-   <span data-ttu-id="f452c-107">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="f452c-107">Quantity</span></span>
-   <span data-ttu-id="f452c-108">Bruttovinstmarginal</span><span class="sxs-lookup"><span data-stu-id="f452c-108">Gross profit margin</span></span>
-   <span data-ttu-id="f452c-109">Marginalprocent</span><span class="sxs-lookup"><span data-stu-id="f452c-109">Margin percentage</span></span>

<span data-ttu-id="f452c-110">För denna bedömning kan du använda färdiga **översta kunder** , som du kan öppna från någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="f452c-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

-   <span data-ttu-id="f452c-111">Arbetsytan **Butikshantering** &gt; **Butik** &gt; **Kanaler** &gt; **Butikshantering** &gt; **Rapporter** &gt; **Främsta kunderna - rapport**</span><span class="sxs-lookup"><span data-stu-id="f452c-111">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top customers report**</span></span>
-   <span data-ttu-id="f452c-112">Avsnittet **Förfrågningar och rapporter** &gt; **Butik** &gt; **Förfrågningar och rapporter** &gt; **Försäljningsrapporter** &gt; **Främsta kunderna - rapport**</span><span class="sxs-lookup"><span data-stu-id="f452c-112">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="f452c-113">Likaså användare kan studera lönsamheten för produkter (10 till 100) mellan olika nivåer i organisationshierarkin, baserat på ett av följande kriterier:</span><span class="sxs-lookup"><span data-stu-id="f452c-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

-   <span data-ttu-id="f452c-114">Försäljningsbelopp</span><span class="sxs-lookup"><span data-stu-id="f452c-114">Sales amount</span></span>
-   <span data-ttu-id="f452c-115">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="f452c-115">Quantity</span></span>
-   <span data-ttu-id="f452c-116">Bruttovinstmarginal</span><span class="sxs-lookup"><span data-stu-id="f452c-116">Gross profit margin</span></span>
-   <span data-ttu-id="f452c-117">Marginalprocent</span><span class="sxs-lookup"><span data-stu-id="f452c-117">Margin percentage</span></span>

<span data-ttu-id="f452c-118">För denna bedömning kan du använda färdiga **topprodukter** betänkande, som du kan öppna från någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="f452c-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

-   <span data-ttu-id="f452c-119">Arbetsytan **Butikshantering** &gt; **Butik** &gt; **Kanaler** &gt; **Butikshantering** &gt; **Rapporter** &gt; **Främsta produkterna - rapport**</span><span class="sxs-lookup"><span data-stu-id="f452c-119">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
-   <span data-ttu-id="f452c-120">Arbetsytan **Kategori och produkthantering** &gt; **Butik** &gt; **Produkter och kategorier** &gt; **Butikshantering** &gt; **Rapporter** &gt; **Främsta produkterna - rapport**</span><span class="sxs-lookup"><span data-stu-id="f452c-120">**Category and product management** workspace &gt; **Retail** &gt; **Products and categories** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
-   <span data-ttu-id="f452c-121">Avsnittet **Förfrågningar och rapporter** &gt; **Butik** &gt; **Förfrågningar och rapporter** &gt; **Försäljningsrapporter** &gt; **Främsta produkterna - rapport**</span><span class="sxs-lookup"><span data-stu-id="f452c-121">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>




