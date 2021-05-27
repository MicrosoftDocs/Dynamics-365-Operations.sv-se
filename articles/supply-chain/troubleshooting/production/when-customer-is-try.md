---
title: Batchnummer rensas när ett nytt parti-ID väljs
description: När du granskar en plocklistejournalrad rensas värdet i fältet Batchnummer om du väljer ett nytt värde i fältet Parti-ID.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 71977a04adb066a8b51c9bf7b8c5a4e752ca902e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026900"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a><span data-ttu-id="55b0e-103">Batchnummer rensas när ett nytt parti-ID väljs</span><span class="sxs-lookup"><span data-stu-id="55b0e-103">Batch number is cleared when a new lot ID is selected</span></span>

<span data-ttu-id="55b0e-104">KB-nummer: 4613107</span><span class="sxs-lookup"><span data-stu-id="55b0e-104">KB number: 4613107</span></span>

## <a name="symptoms"></a><span data-ttu-id="55b0e-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="55b0e-105">Symptoms</span></span>

<span data-ttu-id="55b0e-106">När du granskar en plocklistejournalrad rensas värdet i fältet **Batchnummer** om du väljer ett nytt värde i fältet **Parti-ID**.</span><span class="sxs-lookup"><span data-stu-id="55b0e-106">When you're reviewing a picking list journal line, the value in the **Batch number** field is cleared if you select a new value in the **Lot ID** field.</span></span>

## <a name="resolution"></a><span data-ttu-id="55b0e-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="55b0e-107">Resolution</span></span>

<span data-ttu-id="55b0e-108">Systemet beter sig som det är utformat.</span><span class="sxs-lookup"><span data-stu-id="55b0e-108">The system is behaving as designed.</span></span> <span data-ttu-id="55b0e-109">Om du ändrar parti-ID ändrar du artikelkontexten.</span><span class="sxs-lookup"><span data-stu-id="55b0e-109">If you change the lot ID, you change the item context.</span></span> <span data-ttu-id="55b0e-110">Därför återställs batchnumret.</span><span class="sxs-lookup"><span data-stu-id="55b0e-110">Therefore, the batch number is reset.</span></span>

<span data-ttu-id="55b0e-111">Om du vill associera batchnumret med ett parti-ID måste du först ange parti-ID.</span><span class="sxs-lookup"><span data-stu-id="55b0e-111">To associate the batch number with a lot ID, you must set the lot ID first.</span></span>
