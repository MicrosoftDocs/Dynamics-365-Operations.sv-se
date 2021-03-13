---
title: Felsöka analysrapporter
description: Det här avsnittet beskriver vad du ska göra om en kunds dataändringar inte visas i någon av kundens arbetsytor.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c5e1a1d7044567a07acedf71e65ed244275acfd9
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114300"
---
# <a name="troubleshoot-analytic-reports"></a><span data-ttu-id="e761b-103">Felsöka analysrapporter</span><span class="sxs-lookup"><span data-stu-id="e761b-103">Troubleshoot analytic reports</span></span>

<span data-ttu-id="e761b-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="e761b-104">**Issue**</span></span>

<span data-ttu-id="e761b-105">En kunds data visas inte på fliken **Analys** av någon av kundens arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="e761b-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="e761b-106">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="e761b-106">**Cause**</span></span>

<span data-ttu-id="e761b-107">Som standard uppdateras Microsoft Power BI-rapporter var fjärde timme enligt schemat för batchjobbet Distribuera mått.</span><span class="sxs-lookup"><span data-stu-id="e761b-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="e761b-108">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="e761b-108">**Resolution**</span></span>

<span data-ttu-id="e761b-109">Det här problemet kanske bara är fråga om tidmätning.</span><span class="sxs-lookup"><span data-stu-id="e761b-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="e761b-110">Följ dessa steg om du vill starta batch-jobbet och uppdatera analysarbetsytorna.</span><span class="sxs-lookup"><span data-stu-id="e761b-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="e761b-111">Öppna sidan **Batchjobb** på **Systemadministration \> Länkar \> Batchjobb \> Batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="e761b-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="e761b-112">Alternativt använder du Sök och anger **Batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="e761b-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="e761b-113">Hitta jobbet **Distribuera mätning** i listan.</span><span class="sxs-lookup"><span data-stu-id="e761b-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="e761b-114">Välj **Redigera** överst på sidan och ange det schemalagda startdatumet/tiden som uppdaterar analysen närmare till aktuell tid.</span><span class="sxs-lookup"><span data-stu-id="e761b-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Batchjobb](media/batch-jobs.png)
