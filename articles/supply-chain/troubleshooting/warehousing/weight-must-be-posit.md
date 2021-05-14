---
title: Vikten måste vara positiv
description: Vikten måste vara positiv
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dcbcde3143cb509b68b277cb7c709263e2659b5b
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924313"
---
# <a name="weight-must-be-positive"></a><span data-ttu-id="4a3ab-103">Vikten måste vara positiv</span><span class="sxs-lookup"><span data-stu-id="4a3ab-103">Weight must be positive</span></span>

<span data-ttu-id="4a3ab-104">Felkod: WeightMustBePositive</span><span class="sxs-lookup"><span data-stu-id="4a3ab-104">Error code: WeightMustBePositive</span></span>

## <a name="symptoms"></a><span data-ttu-id="4a3ab-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="4a3ab-105">Symptoms</span></span>

<span data-ttu-id="4a3ab-106">Systemet visar följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="4a3ab-106">The system shows the following error message:</span></span>

> <span data-ttu-id="4a3ab-107">Vikten måste vara positiv.</span><span class="sxs-lookup"><span data-stu-id="4a3ab-107">Weight must be positive.</span></span>

## <a name="cause"></a><span data-ttu-id="4a3ab-108">Orsak</span><span class="sxs-lookup"><span data-stu-id="4a3ab-108">Cause</span></span>

<span data-ttu-id="4a3ab-109">Fältet **Bruttovikt** ställs in på *0* (noll) eller ett negativt värde.</span><span class="sxs-lookup"><span data-stu-id="4a3ab-109">The **Gross Weight** field is set to *0* (zero) or a negative value.</span></span>

## <a name="resolution"></a><span data-ttu-id="4a3ab-110">Upplösning</span><span class="sxs-lookup"><span data-stu-id="4a3ab-110">Resolution</span></span>

<span data-ttu-id="4a3ab-111">Om du vill ange en vikt gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="4a3ab-111">To specify a weight, follow one of these steps.</span></span>

- <span data-ttu-id="4a3ab-112">Ange ett värde i fältet **Bruttovikt**.</span><span class="sxs-lookup"><span data-stu-id="4a3ab-112">In the **Gross weight** field, set a value.</span></span> <span data-ttu-id="4a3ab-113">Välj sedan en enhet i listrutan.</span><span class="sxs-lookup"><span data-stu-id="4a3ab-113">Then select a unit in the drop-down list.</span></span>
- <span data-ttu-id="4a3ab-114">Välj **Hämta systemvikt** för att beräkna värdet för **Bruttovikt**.</span><span class="sxs-lookup"><span data-stu-id="4a3ab-114">Select **Get system weight** to calculate the **Gross weight** value.</span></span>
