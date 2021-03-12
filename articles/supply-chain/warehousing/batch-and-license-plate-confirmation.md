---
title: Bekräftelse av batch och ID-nummer
description: Det här avsnittet beskriver hur du ställer in och använder bekräftelse av batch och registreringsskylt från en mobil enhet.
author: Mirzaab
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97790b91d4de536b89b580c26ef1e37145f7d7c6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977448"
---
# <a name="batch-and-license-plate-confirmation"></a><span data-ttu-id="5339a-103">Bekräftelse av batch och ID-nummer</span><span class="sxs-lookup"><span data-stu-id="5339a-103">Batch and license plate confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5339a-104">Batch-bekräftelse låter dig bekräfta att korrekt batch hämtas från den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="5339a-104">Batch confirmation allows you to confirm that the correct batch is being picked from the mobile device.</span></span> <span data-ttu-id="5339a-105">På den första plockningen för batch ovan-objekt, anger batch ovan att om batch-intervall överskrider placering i sökningshierarkin måste du kontrollera att den batch som plockas matchar batchen på arbetsraden.</span><span class="sxs-lookup"><span data-stu-id="5339a-105">On the initial pick of work for batch above-items only, where batch above indicates that batch ranges higher than location in the search hierarchy, you must verify that the batch that is picked matches the batch on the work line.</span></span>

<span data-ttu-id="5339a-106">Bekräftelse för registreringsskylt låter dig bekräfta att korrekt registreringsskylt hämtas från den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="5339a-106">License plate confirmation allows you to confirm that the correct license plate is being picked from the mobile device.</span></span> <span data-ttu-id="5339a-107">När du plockar arbete från en fasplats måste du kontrollera att registreringsskylten som plockas matchar registreringsskylten som associeras med arbetet.</span><span class="sxs-lookup"><span data-stu-id="5339a-107">When picking work from a stage location, you must verify that the license plate that is picked matches the license plate that is associated with the work.</span></span> <span data-ttu-id="5339a-108">Om arbetet har påbörjats genom att skanna en registreringsskylt, kommer detta bekräftelsesteg att hoppas över.</span><span class="sxs-lookup"><span data-stu-id="5339a-108">If the work is started by scanning a license plate, this confirmation step will be skipped.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="5339a-109">När det gäller</span><span class="sxs-lookup"><span data-stu-id="5339a-109">Where it applies</span></span>

<span data-ttu-id="5339a-110">Bekräftelse tillämpas detta i följande fall:</span><span class="sxs-lookup"><span data-stu-id="5339a-110">Confirmation applies in the following scenarios:</span></span>

- <span data-ttu-id="5339a-111">Batch-bekräftelse gäller första plockningen för arbete för batch ovan-objekt.</span><span class="sxs-lookup"><span data-stu-id="5339a-111">Batch confirmation applies to the initial picks of work for batch above-items.</span></span>
- <span data-ttu-id="5339a-112">Bekräftelse för registreringsskylt gäller för plockning från fasplatser.</span><span class="sxs-lookup"><span data-stu-id="5339a-112">License plate confirmation applies to picks from stage locations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5339a-113">Påfyllning stöds inte för bekräftelse av ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="5339a-113">Replenishment is not supported for license plate confirmation.</span></span> <span data-ttu-id="5339a-114">När påfyllningsarbetet körs skapas inget bekräftelsesteg för ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="5339a-114">When executing replenishment work, no license plate confirmation step is created.</span></span>

## <a name="set-up-batch-and-license-plate-confirmation"></a><span data-ttu-id="5339a-115">Ange bekräftelse av batch och registreringsskylt</span><span class="sxs-lookup"><span data-stu-id="5339a-115">Set up batch and license plate confirmation</span></span>

<span data-ttu-id="5339a-116">Du kan konfigurera bekräftelse av batch och registreringsskylt från mobila enhetens menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="5339a-116">You can configure batch and license plate confirmation from the mobile device menu items.</span></span>

1. <span data-ttu-id="5339a-117">Ange inställning av arbetsbekräftelse från mobila enhetens menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="5339a-117">From the mobile device menu items, enter the work confirmation setup.</span></span>  
1. <span data-ttu-id="5339a-118">Välj alternativ för bekräftelse av batch eller registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="5339a-118">Select the option for either batch or license plate confirmation.</span></span> <span data-ttu-id="5339a-119">Båda alternativen är tillgängliga för arbetstypen plockning som inte har automatisk bekräftelse aktiverad.</span><span class="sxs-lookup"><span data-stu-id="5339a-119">Both options are available for work type picks that do not have automatic confirmation enabled.</span></span>  
