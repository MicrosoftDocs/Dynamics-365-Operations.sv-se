---
title: Det går inte att filtrera huvudplaneringsartiklar efter relaterade disponeringsgruppvärden
description: Det går inte att filtrera huvudplaneringsartiklar efter relaterade disponeringsgruppvärden.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049491"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a><span data-ttu-id="14691-103">Det går inte att filtrera huvudplaneringsartiklar efter relaterade disponeringsgruppvärden</span><span class="sxs-lookup"><span data-stu-id="14691-103">You can't filter master planning items by their related coverage group values</span></span>

<span data-ttu-id="14691-104">KB-nummer: 4612572</span><span class="sxs-lookup"><span data-stu-id="14691-104">KB number: 4612572</span></span>

## <a name="symptoms"></a><span data-ttu-id="14691-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="14691-105">Symptoms</span></span>

<span data-ttu-id="14691-106">Du vill filtrera artiklarna som inkluderas i ett batchjobb för huvudplanering utifrån värdena för relaterade poster från artikel disponeringsregistret.</span><span class="sxs-lookup"><span data-stu-id="14691-106">You want to filter the items that will be included in a master planning batch job, based on the values of related records from the item coverage table.</span></span> <span data-ttu-id="14691-107">(Du vill till exempel filtrera artiklar efter värdet **Leverantör** och/eller **Disponeringsgrupp**).</span><span class="sxs-lookup"><span data-stu-id="14691-107">(For example, you want to filter items by their **Vendor** and/or **Coverage group** value).</span></span> <span data-ttu-id="14691-108">Med filterinställningarna för batchjobbet kan du skapa en koppling från registret **Artikel** till **Artikeldisponering** och ange sedan fältvärden från artikeldisponeringsregistret i din fråga.</span><span class="sxs-lookup"><span data-stu-id="14691-108">The filter setup for the batch job lets you create a join from the **Items** table to the **Item coverage** table, and then specify field values from the item coverage table in your query.</span></span> <span data-ttu-id="14691-109">När du har slutfört inställningen skapar systemet ändå planerade order för hela artikeldisponeringen, inte bara för de artiklar som matchar de angivna fältvärdena från registret för artikeldisponering.</span><span class="sxs-lookup"><span data-stu-id="14691-109">However, after you complete this setup, the system still creates planned orders for the whole item coverage, not just for the items that match the specified field values from the item coverage table.</span></span>

## <a name="resolution"></a><span data-ttu-id="14691-110">Lösning</span><span class="sxs-lookup"><span data-stu-id="14691-110">Resolution</span></span>

<span data-ttu-id="14691-111">Batchjobbfiltret kan bara filtreras för artiklar.</span><span class="sxs-lookup"><span data-stu-id="14691-111">The batch job filter can filter only on items.</span></span> <span data-ttu-id="14691-112">Även om du kan lägga till en koppling till registret **Artikeldisponering**, påverkar inte de filterinställningar som du gör mot registret frågans utdata.</span><span class="sxs-lookup"><span data-stu-id="14691-112">Although you can add a join to the **Item coverage** table, filter settings that you make against that table won't affect the query output.</span></span> <span data-ttu-id="14691-113">Under körning kör systemet planering för alla disponeringsgrupper och alla variationer som de filtrerade artiklarna har.</span><span class="sxs-lookup"><span data-stu-id="14691-113">At runtime, the system runs planning for all the coverage groups and all the variations that the filtered items have.</span></span> <span data-ttu-id="14691-114">När en artikel redan har inkluderats i körningen påverkas inte planeringsutdata av de disponeringsgrupper som inkluderas i artikelfiltret.</span><span class="sxs-lookup"><span data-stu-id="14691-114">After an item is already included in the run, any coverage groups that are included in the item filter a won't affect the planning output.</span></span>
