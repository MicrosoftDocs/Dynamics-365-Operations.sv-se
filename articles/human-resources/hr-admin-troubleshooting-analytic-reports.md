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
ms.openlocfilehash: e0befe1a35aa46b2eabb4516559fe07ce27e9f18
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466674"
---
# <a name="troubleshoot-analytic-reports"></a><span data-ttu-id="dcbc4-103">Felsöka analysrapporter</span><span class="sxs-lookup"><span data-stu-id="dcbc4-103">Troubleshoot analytic reports</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="dcbc4-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="dcbc4-104">**Issue**</span></span>

<span data-ttu-id="dcbc4-105">En kunds data visas inte på fliken **Analys** av någon av kundens arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="dcbc4-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="dcbc4-106">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="dcbc4-106">**Cause**</span></span>

<span data-ttu-id="dcbc4-107">Som standard uppdateras Microsoft Power BI-rapporter var fjärde timme enligt schemat för batchjobbet Distribuera mått.</span><span class="sxs-lookup"><span data-stu-id="dcbc4-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="dcbc4-108">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="dcbc4-108">**Resolution**</span></span>

<span data-ttu-id="dcbc4-109">Det här problemet kanske bara är fråga om tidmätning.</span><span class="sxs-lookup"><span data-stu-id="dcbc4-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="dcbc4-110">Följ dessa steg om du vill starta batch-jobbet och uppdatera analysarbetsytorna.</span><span class="sxs-lookup"><span data-stu-id="dcbc4-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="dcbc4-111">Öppna sidan **Batchjobb** på **Systemadministration \> Länkar \> Batchjobb \> Batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="dcbc4-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="dcbc4-112">Alternativt använder du Sök och anger **Batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="dcbc4-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="dcbc4-113">Hitta jobbet **Distribuera mätning** i listan.</span><span class="sxs-lookup"><span data-stu-id="dcbc4-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="dcbc4-114">Välj **Redigera** överst på sidan och ange det schemalagda startdatumet/tiden som uppdaterar analysen närmare till aktuell tid.</span><span class="sxs-lookup"><span data-stu-id="dcbc4-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Batchjobb](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]