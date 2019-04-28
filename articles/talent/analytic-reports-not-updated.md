---
title: Analysrapporter uppdateras inte
description: Det här avsnittet beskriver vad du ska göra om en kunds dataändringar inte visas i någon av kundens arbetsytor.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d6a6487b50908093f876237ffef840a3144b3fe6
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "857463"
---
# <a name="analytic-reports-are-not-updated"></a><span data-ttu-id="9f46f-103">Analysrapporter uppdateras inte</span><span class="sxs-lookup"><span data-stu-id="9f46f-103">Analytic reports are not updated</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9f46f-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="9f46f-104">**Issue**</span></span>

<span data-ttu-id="9f46f-105">En kunds data visas inte på fliken **Analys** av någon av kundens arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="9f46f-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="9f46f-106">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="9f46f-106">**Cause**</span></span>

<span data-ttu-id="9f46f-107">Som standard uppdateras Microsoft Power BI-rapporter var fjärde timme enligt schemat för batchjobbet Distribuera mått.</span><span class="sxs-lookup"><span data-stu-id="9f46f-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="9f46f-108">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="9f46f-108">**Resolution**</span></span>

<span data-ttu-id="9f46f-109">Det här problemet kanske bara är fråga om tidmätning.</span><span class="sxs-lookup"><span data-stu-id="9f46f-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="9f46f-110">Följ dessa steg om du vill starta batch-jobbet och uppdatera analysarbetsytorna.</span><span class="sxs-lookup"><span data-stu-id="9f46f-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="9f46f-111">Öppna sidan **Batchjobb** på **Systemadministration \> Länkar \> Batchjobb \> Batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="9f46f-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="9f46f-112">Alternativt använder du Sök och anger **Batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="9f46f-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="9f46f-113">Hitta jobbet **Distribuera mätning** i listan.</span><span class="sxs-lookup"><span data-stu-id="9f46f-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="9f46f-114">Välj **Redigera** överst på sidan och ange det schemalagda startdatumet/tiden som uppdaterar analysen närmare till aktuell tid.</span><span class="sxs-lookup"><span data-stu-id="9f46f-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Batchjobb](media/batch-jobs.png)
