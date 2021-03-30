---
title: Utvärdera lönsamhet för kunder och produkter
description: Den här artikeln beskriver hur du kan använda det inbyggda minnet och realtidanalys för att komma åt, utforska och få insikt om lönsamhet för kunder och produkter från dina Dynamics 365 Commerce-data.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: SysOperationsTemplateForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e0589748247cf9195116687cf70228b4ef36e29b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211556"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="58f60-103">Utvärdera lönsamhet för kunder och produkter</span><span class="sxs-lookup"><span data-stu-id="58f60-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="58f60-104">Den här artikeln beskriver hur du kan använda det inbyggda minnet och realtidanalys för att komma åt, utforska och få insikt om lönsamhet för kunder och produkter från dina Dynamics 365 Commerce-data.</span><span class="sxs-lookup"><span data-stu-id="58f60-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Dynamics 365 Commerce data.</span></span>

<span data-ttu-id="58f60-105">Som en del av Commerce användare kan studera lönsamheten för kunder (10 till 100) mellan olika nivåer i organisationshierarkin, baserat på ett av följande kriterier:</span><span class="sxs-lookup"><span data-stu-id="58f60-105">As part of Commerce, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="58f60-106">Försäljningsbelopp</span><span class="sxs-lookup"><span data-stu-id="58f60-106">Sales amount</span></span>
- <span data-ttu-id="58f60-107">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="58f60-107">Quantity</span></span>
- <span data-ttu-id="58f60-108">Bruttovinstmarginal</span><span class="sxs-lookup"><span data-stu-id="58f60-108">Gross profit margin</span></span>
- <span data-ttu-id="58f60-109">Marginalprocent</span><span class="sxs-lookup"><span data-stu-id="58f60-109">Margin percentage</span></span>

<span data-ttu-id="58f60-110">För denna bedömning kan du använda färdiga **översta kunder** , som du kan öppna från någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="58f60-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="58f60-111">Arbetsytan **Butikshantering** &gt; **Butik och handel** &gt; **Kanaler** &gt; **Butikshantering** &gt; **Rapporter** &gt; **Främsta kunderna – rapport**</span><span class="sxs-lookup"><span data-stu-id="58f60-111">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="58f60-112">Avsnitt **Undersökningar och rapporter** &gt; **Butik och handel** &gt; **Undersökningar och rapporter** &gt; **Försäljningsrapporter** &gt; **Översta kunder rapport**</span><span class="sxs-lookup"><span data-stu-id="58f60-112">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="58f60-113">Likaså användare kan studera lönsamheten för produkter (10 till 100) mellan olika nivåer i organisationshierarkin, baserat på ett av följande kriterier:</span><span class="sxs-lookup"><span data-stu-id="58f60-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="58f60-114">Försäljningsbelopp</span><span class="sxs-lookup"><span data-stu-id="58f60-114">Sales amount</span></span>
- <span data-ttu-id="58f60-115">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="58f60-115">Quantity</span></span>
- <span data-ttu-id="58f60-116">Bruttovinstmarginal</span><span class="sxs-lookup"><span data-stu-id="58f60-116">Gross profit margin</span></span>
- <span data-ttu-id="58f60-117">Marginalprocent</span><span class="sxs-lookup"><span data-stu-id="58f60-117">Margin percentage</span></span>

<span data-ttu-id="58f60-118">För denna bedömning kan du använda färdiga **topprodukter** betänkande, som du kan öppna från någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="58f60-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="58f60-119">Arbetsytan **Butikshantering** &gt; **Butik och handel** &gt; **Kanaler** &gt; **Butikshantering** &gt; **Rapporter** &gt; **Främsta produkterna – rapport**</span><span class="sxs-lookup"><span data-stu-id="58f60-119">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="58f60-120">Arbetsytan **Kategori och produkthantering** &gt; **Butik och handel** &gt; **Produkter och kategorier** &gt; **Butikshantering** &gt; **Rapporter** &gt; **Främsta produkterna – rapport**</span><span class="sxs-lookup"><span data-stu-id="58f60-120">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Products and categories** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="58f60-121">Avsnitt **Undersökningar och rapporter** &gt; **Butik och handel** &gt; **Undersökningar och rapporter** &gt; **Försäljningsrapporter** &gt; **Översta produkter rapport**</span><span class="sxs-lookup"><span data-stu-id="58f60-121">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]