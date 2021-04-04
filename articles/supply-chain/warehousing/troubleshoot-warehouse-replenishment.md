---
title: 'Felsökning: lagerpåfyllning'
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerpåfyllning i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8dfb58c9156df106f58dfdc0ee2e0ef8defb9d9f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263214"
---
# <a name="troubleshoot-warehouse-replenishment"></a><span data-ttu-id="faf60-103">Felsökning: lagerpåfyllning</span><span class="sxs-lookup"><span data-stu-id="faf60-103">Troubleshoot warehouse replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="faf60-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerpåfyllning i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="faf60-104">This topic describes how to fix common issues that you might encounter while you work with warehouse replenishment in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a><span data-ttu-id="faf60-105">Jag får följande felmeddelande: "Arbete %1 kan inte avblockeras eftersom det har oavslutat lagerpåfyllnadsarbete".</span><span class="sxs-lookup"><span data-stu-id="faf60-105">I receive the following error message: "Work %1 cannot be unblocked because it has unfinished replenishment work."</span></span>

### <a name="issue-description"></a><span data-ttu-id="faf60-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="faf60-106">Issue description</span></span>

<span data-ttu-id="faf60-107">Plocknings arbetet spärras på grund av beroende återanskaffningsarbete.</span><span class="sxs-lookup"><span data-stu-id="faf60-107">Picking work is blocked because of dependent replenishment work.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="faf60-108">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="faf60-108">Issue resolution</span></span>

<span data-ttu-id="faf60-109">När du använder lagerpåfyllnadsbegäran om en plockplats måste fyllas på skapar systemet både påfyllningsarbetet och plockningsarbetet om en plockplats måste fyllas på för att uppfylla källorderns behov.</span><span class="sxs-lookup"><span data-stu-id="faf60-109">When you use wave demand replenishment, if a picking location must be replenished to fulfill the source order demand, the system creates both the replenishment work and the picking work.</span></span> <span data-ttu-id="faf60-110">Men det blockerar plockningsarbetet tills påfyllningsarbetet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="faf60-110">However, it blocks the picking work until the replenishment work is completed.</span></span> <span data-ttu-id="faf60-111">Det här beteendet är avsiktligt eftersom plockplatsen inte har tillräckligt med lager om inte lagerpåfyllnadsarbetet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="faf60-111">This behavior is intentional, because the picking location won't have enough inventory unless the replenishment work is completed.</span></span> <span data-ttu-id="faf60-112">Slutför påfyllningsarbetet och bearbeta sedan plockningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="faf60-112">Complete the replenishment work, and then process the picking work.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]