---
title: Transporthantering i nummersekvens
description: I det här avsnittet beskrivs hur du ställer in nummerserier för transporthantering.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2c3f087ac76412cd2dce93dcb31b796ce2cb3bc4
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "4438132"
---
# <a name="transportation-management-number-sequence"></a><span data-ttu-id="a1ae1-103">Transporthantering i nummersekvens</span><span class="sxs-lookup"><span data-stu-id="a1ae1-103">Transportation management number sequence</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1ae1-104">Använd sidan **Nummerserier** i transporthanteringsmodulen för att ställa in olika pro-nummer.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-104">Use the **Number sequences** page in the transportation management module to set up various pro numbers.</span></span> <span data-ttu-id="a1ae1-105">Pro-nummer används av transportföretag för att ordna och spåra förloppet för varje försändelse.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-105">Pro numbers are used by carriers to organize and track the progress of each shipment.</span></span>

## <a name="create-a-number-sequence-for-a-pro-number"></a><span data-ttu-id="a1ae1-106">Skapa en nummerserie för ett pro-nummer</span><span class="sxs-lookup"><span data-stu-id="a1ae1-106">Create a number sequence for a pro number</span></span>

<span data-ttu-id="a1ae1-107">Gör följande om du vill skapa en nummerserie för ett pro-nummer:</span><span class="sxs-lookup"><span data-stu-id="a1ae1-107">To create a number sequence for a pro number, do the following:</span></span>

1. <span data-ttu-id="a1ae1-108">Gå till **Transporthantering \> Inställningar \> Transportföretag \> Nummerserie**.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-108">Go to **Transportation management \> Setup \> Carriers \> Number sequences**.</span></span>
1. <span data-ttu-id="a1ae1-109">Skapa en ny nummerserie genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-109">Select **New** to create a new number sequence.</span></span>
1. <span data-ttu-id="a1ae1-110">Ange ett unikt ID och ett beskrivande namn på nummerserien.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-110">Enter a unique ID and descriptive name for the number sequence.</span></span>
1. <span data-ttu-id="a1ae1-111">I fältet **nummerserietyp** är *pro-nummer* det enda alternativet.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-111">In the **Number sequence type** field, *Pro number* is the only option.</span></span>
1. <span data-ttu-id="a1ae1-112">I fältet **Kontrollsiffra** är *Kontrollsiffra* det enda alternativet och den ställs in som en allmän motor.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-112">In the **Check digit** field, *Check digit* is the only option and is set up as a generic engine.</span></span>
1. <span data-ttu-id="a1ae1-113">På snabbfliken **sekvens** ange information om sekvensen.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-113">On the **Sequence** FastTab, provide information about the sequence.</span></span>
1. <span data-ttu-id="a1ae1-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-114">Close the page.</span></span>

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a><span data-ttu-id="a1ae1-115">Koppla en nummerserie till ett transportföretag</span><span class="sxs-lookup"><span data-stu-id="a1ae1-115">Link a number sequence to a shipping carrier</span></span>

<span data-ttu-id="a1ae1-116">Gör följande om du vill koppla en nummerserie till ett transportföretag:</span><span class="sxs-lookup"><span data-stu-id="a1ae1-116">To link a number sequence to a carrier, do the following:</span></span>

1. <span data-ttu-id="a1ae1-117">Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportföretag**.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-117">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="a1ae1-118">Välj ett transportföretag.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-118">Select a shipping carrier.</span></span>
1. <span data-ttu-id="a1ae1-119">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-119">Select **Edit**.</span></span>
1. <span data-ttu-id="a1ae1-120">På snabbfliken **Översikt** väljer du ett alternativ i fältet **Pro-nummerserie**.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-120">On the **Overview** FastTab, select an option in the **Pro number sequence** field.</span></span>
1. <span data-ttu-id="a1ae1-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a1ae1-121">Close the page.</span></span>
