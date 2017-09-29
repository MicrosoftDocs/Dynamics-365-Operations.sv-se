---
title: Call center-kataloger
description: "Det här avsnittet innehåller en beskrivning av den callcenterspecifika funktionen för kataloger i Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7be87496ceaea2d1d5f97a5cc17e50dcddbaf33d
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---

# <a name="call-center-catalogs"></a><span data-ttu-id="d2655-103">Kundtjänstkataloger</span><span class="sxs-lookup"><span data-stu-id="d2655-103">Call center catalogs</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="d2655-104">Det här avsnittet innehåller en beskrivning av den callcenterspecifika funktionen för kataloger i Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="d2655-104">This article describes the call center–specific functionality for catalogs in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="d2655-105">I en kundtjänst kan du använda produktkataloger för att identifiera de produkter som du vill erbjuda dina kunder.</span><span class="sxs-lookup"><span data-stu-id="d2655-105">In a call center, you can use product catalogs to identify the products that you want to offer to customers.</span></span> <span data-ttu-id="d2655-106">Kundtjänster använder vanligtvis tryckta kataloger.</span><span class="sxs-lookup"><span data-stu-id="d2655-106">Call centers typically use printed catalogs.</span></span> <span data-ttu-id="d2655-107">Design och produktion av en tryckt katalog hanteras utanför Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="d2655-107">The design and production of a printed catalog is handled outside Dynamics 365 for Retail.</span></span> <span data-ttu-id="d2655-108">Du kan emellertid skapa och lagra en digital form av en katalog i detaljhandeln och handel med samma sidor som du använder för att konfigurera online butikskataloger.</span><span class="sxs-lookup"><span data-stu-id="d2655-108">However, you can create and store a digital form of a catalog by using the same pages that you use to set up online retail catalogs.</span></span> <span data-ttu-id="d2655-109">Innan du kan skapa en katalog måste du ställa in produktsortiment och tilldela sortimenten till en kundtjänst.</span><span class="sxs-lookup"><span data-stu-id="d2655-109">Before you can create a catalog, you must set up product assortments and assign the assortments to a call center.</span></span> <span data-ttu-id="d2655-110">Du lägger sedan till produkter till katalogen genom att välja produkter från dessa sortiment.</span><span class="sxs-lookup"><span data-stu-id="d2655-110">You then add products to the catalog by selecting products from these assortments.</span></span> <span data-ttu-id="d2655-111">När produkter har lagts till i katalogen och katalogen är klar måste du validera katalogen för att kontrollera data.</span><span class="sxs-lookup"><span data-stu-id="d2655-111">After products have been added to the catalog, and the catalog is complete, you must validate the catalog to verify the data.</span></span> <span data-ttu-id="d2655-112">Du måste sedan skicka katalogen för granskning och godkännande.</span><span class="sxs-lookup"><span data-stu-id="d2655-112">You must then submit the catalog for review and approval.</span></span> <span data-ttu-id="d2655-113">När katalogen har godkänts, kan den publiceras.</span><span class="sxs-lookup"><span data-stu-id="d2655-113">After the catalog is approved, it can be published.</span></span> <span data-ttu-id="d2655-114">När en kundtjänstkatalog skapas, kan du ta en ögonblicksbild av katalogdatan och tidpunkten när katalogen publiceras.</span><span class="sxs-lookup"><span data-stu-id="d2655-114">When a call center catalog is created, you can take a snapshot of the catalog data at the time that the catalog is published.</span></span> <span data-ttu-id="d2655-115">Den här funktionen för ögonblicksbilder låter dig öppna en viss version av katalogen, även om katalogen senare ändras och uppdateras.</span><span class="sxs-lookup"><span data-stu-id="d2655-115">This snapshot functionality lets you access a particular version of the catalog even if the catalog is later changed and updated.</span></span> <span data-ttu-id="d2655-116">Kundtjänstkataloger kan också ställas in för att innefatta följande tillvalsfunktioner:</span><span class="sxs-lookup"><span data-stu-id="d2655-116">Call center catalogs can also be set up to include the following optional features:</span></span>

-   <span data-ttu-id="d2655-117">**Källkoder** – källkoder används för att spåra kundens reaktion på specifika katalog utskick.</span><span class="sxs-lookup"><span data-stu-id="d2655-117">**Source codes** – Source codes are used to track the customer response to specific catalog mailings.</span></span>
-   <span data-ttu-id="d2655-118">**Gratis produkter** – Produkter som kan ingå i en kunds beställning utan extra kostnad.</span><span class="sxs-lookup"><span data-stu-id="d2655-118">**Free products** – Products can be included in a customer's order at no additional charge.</span></span> <span data-ttu-id="d2655-119">Dessa produkter finnas automatiskt adderat till en order när källkoden för katalog anges i beställningen.</span><span class="sxs-lookup"><span data-stu-id="d2655-119">These products are automatically added to an order when the source code for the catalog is entered into the order.</span></span>
-   <span data-ttu-id="d2655-120">**Manuskript** – manuskript är texter som en call center-arbetare läser en kund när en kundorder skapas.</span><span class="sxs-lookup"><span data-stu-id="d2655-120">**Scripts** – Scripts are texts that a call center worker reads to a customer when a sales order is being created.</span></span> <span data-ttu-id="d2655-121">Skript kan inkludera hälsningar eller inköpförslag.</span><span class="sxs-lookup"><span data-stu-id="d2655-121">Scripts can include greetings or purchase suggestions.</span></span>
-   <span data-ttu-id="d2655-122">**Sidlayout** – En sidlayout fångar sida i den tryckta katalogen.</span><span class="sxs-lookup"><span data-stu-id="d2655-122">**Page layout** – A page layout captures the page position of products in the printed catalog.</span></span> <span data-ttu-id="d2655-123">Denna information används för katalog område analysrapport.</span><span class="sxs-lookup"><span data-stu-id="d2655-123">This information is used for the catalog area analysis report.</span></span>





