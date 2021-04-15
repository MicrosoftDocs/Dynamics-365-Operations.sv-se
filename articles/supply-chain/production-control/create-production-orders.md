---
title: Livscykel för produktionsorder – översikt
description: När du skapar en produktionsorder initieras en begäran om att starta produktionen av en artikel. Produktionsordern innehåller information om vad som ska produceras, hur mycket samt planerat slutdatum. Den innehåller också information om vilka material som ska förbrukas och vilken process som ska följas vid produktionen av artikeln.
author: johanhoffmann
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df773cf13b8ccd9ee4f861955b1a4321af38a150
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811808"
---
# <a name="production-order-lifecycle-overview"></a><span data-ttu-id="d30b1-105">Livscykel för produktionsorder – översikt</span><span class="sxs-lookup"><span data-stu-id="d30b1-105">Production order lifecycle overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d30b1-106">När du skapar en produktionsorder initieras en begäran om att starta produktionen av en artikel.</span><span class="sxs-lookup"><span data-stu-id="d30b1-106">When a production order is created, a request is initiated to start producing an item.</span></span> <span data-ttu-id="d30b1-107">Produktionsordern innehåller information om vad som ska produceras, hur mycket samt planerat slutdatum.</span><span class="sxs-lookup"><span data-stu-id="d30b1-107">The production order contains information about what will be produced, the quantity to produce, and the planned finish date.</span></span> <span data-ttu-id="d30b1-108">Den innehåller också information om vilka material som ska förbrukas och vilken process som ska följas vid produktionen av artikeln.</span><span class="sxs-lookup"><span data-stu-id="d30b1-108">It also contains information about which materials to consume and which process to follow to produce the item.</span></span>

<span data-ttu-id="d30b1-109">En tillverkningsorder passerar genom faser i produktionslivscykeln.</span><span class="sxs-lookup"><span data-stu-id="d30b1-109">A production order passes through stages of the production life cycle.</span></span> <span data-ttu-id="d30b1-110">När en order skapas tilldelas den statusen **Skapad**.</span><span class="sxs-lookup"><span data-stu-id="d30b1-110">When an order is created, it is assigned the status **Created**.</span></span> <span data-ttu-id="d30b1-111">När en order har avslutats tilldelas den statusen **Avslutad**.</span><span class="sxs-lookup"><span data-stu-id="d30b1-111">When an order is finished, it is assigned the status **Ended**.</span></span> <span data-ttu-id="d30b1-112">Ett parameterinställning i varje fas gör att en användare kan konfigurera varje steg.</span><span class="sxs-lookup"><span data-stu-id="d30b1-112">A parameter setting in each stage allows a user to configure each step.</span></span> <span data-ttu-id="d30b1-113">Inställningen kan ställas in för en enskild användare eller för alla användare.</span><span class="sxs-lookup"><span data-stu-id="d30b1-113">The setting can be set up for a single user or for all users.</span></span>

<span data-ttu-id="d30b1-114">Produktionsstrukturlistan och produktionsflödet är de huvudsakliga enheterna för tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="d30b1-114">The production bill of material and the production route are the main entities of the production order.</span></span> <span data-ttu-id="d30b1-115">De kopieras till tillverkningsordern baserat på den valda artikeln och kvantiteten som ska produceras.</span><span class="sxs-lookup"><span data-stu-id="d30b1-115">They are copied to the production order based on the selected item and quantity that are going to be produced.</span></span> <span data-ttu-id="d30b1-116">Innan tillverkningsordern startas kan produktionsstrukturlistan och -flödet redigeras.</span><span class="sxs-lookup"><span data-stu-id="d30b1-116">Before the production order is started, the production bill of material and route can be edited.</span></span>

<span data-ttu-id="d30b1-117">En tillverkningsorder kan skapas i följande situationer:</span><span class="sxs-lookup"><span data-stu-id="d30b1-117">A production order can be created in the following scenarios:</span></span>

-   <span data-ttu-id="d30b1-118">Skapas av huvudplaneringsutförandet baserat på materialefterfrågan.</span><span class="sxs-lookup"><span data-stu-id="d30b1-118">Created by master planning execution based on material demand.</span></span>
-   <span data-ttu-id="d30b1-119">Skapas direkt från en försäljningsorderrad eller när en tillverkningsorder på högre nivå skapas och beräknas (peggad leverans).</span><span class="sxs-lookup"><span data-stu-id="d30b1-119">Created directly from a sales order line or when a higher-level production order is created and estimated (pegged supply).</span></span>
-   <span data-ttu-id="d30b1-120">Skapas manuellt.</span><span class="sxs-lookup"><span data-stu-id="d30b1-120">Created manually.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]