---
title: Tilldela nummerserier
description: I det här ämnet beskrivs hur du skapar nummerserier för leasing-ID:n. Det innehåller även information om hur du skapar unika ID:n som används i ombedömningsprocessen för index.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3e89fb7616aff323d5815918a37e1fccf9b7f578
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207265"
---
# <a name="assign-number-sequences"></a><span data-ttu-id="d7cbf-104">Tilldela nummerserier</span><span class="sxs-lookup"><span data-stu-id="d7cbf-104">Assign number sequences</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="d7cbf-105">I det här ämnet beskrivs hur du skapar nummerserier för leasing-ID:n.</span><span class="sxs-lookup"><span data-stu-id="d7cbf-105">This topic explains how to create number sequences for lease IDs.</span></span> <span data-ttu-id="d7cbf-106">Det innehåller även information om hur du skapar unika ID:n som används i ombedömningsprocessen för index.</span><span class="sxs-lookup"><span data-stu-id="d7cbf-106">It also explains how to create unique IDs that are used in the index revaluation process.</span></span>

1. <span data-ttu-id="d7cbf-107">Gå till **Leasing av tillgångar \> Konfigurera \> Parametrar för tillgångsleasing**.</span><span class="sxs-lookup"><span data-stu-id="d7cbf-107">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="d7cbf-108">Välj sidofliken **Nummerserier**.</span><span class="sxs-lookup"><span data-stu-id="d7cbf-108">Select the **Number sequences** side tab.</span></span>
3. <span data-ttu-id="d7cbf-109">Välj **Nummerserier** i sidofältet.</span><span class="sxs-lookup"><span data-stu-id="d7cbf-109">Select **Number sequences** in the side bar.</span></span>
4. <span data-ttu-id="d7cbf-110">Välj nummerserien för referensen **Leasing-ID**.</span><span class="sxs-lookup"><span data-stu-id="d7cbf-110">Select the number sequence for the **Lease ID** reference.</span></span> <span data-ttu-id="d7cbf-111">Denna nummerserie används för att generera den unika identifieraren för varje leasing.</span><span class="sxs-lookup"><span data-stu-id="d7cbf-111">This number sequence will be used to generate the unique identifier for each lease.</span></span>
5. <span data-ttu-id="d7cbf-112">Välj nummerserien för referensen **Process-ID**.</span><span class="sxs-lookup"><span data-stu-id="d7cbf-112">Select the number sequence for the **Process ID** reference.</span></span> <span data-ttu-id="d7cbf-113">Denna nummerserie används för att generera den unika identifieraren för varje indexombedömningsprocess.</span><span class="sxs-lookup"><span data-stu-id="d7cbf-113">This number sequence will be used to generate the unique identifier for each index revaluation process.</span></span>
6. <span data-ttu-id="d7cbf-114">Välj nummerserien för referensen **ID för uppsägningsförslag**.</span><span class="sxs-lookup"><span data-stu-id="d7cbf-114">Select the number sequence for the **Termination Proposal ID** reference.</span></span> <span data-ttu-id="d7cbf-115">Denna nummerserie används för att generera den unika identifieraren för respektive uppsägningsförslag.</span><span class="sxs-lookup"><span data-stu-id="d7cbf-115">This number sequence will be used to generate the unique identifier for each termination proposal.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]