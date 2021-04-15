---
title: Plats för produktionsutleverans
description: Det här avsnittet beskriver den hierarki som används för att identifiera produktionsutleveransplatsen.
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 48b68c36718fa42b7f80e3ffe1f54b7efbbee8bd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814642"
---
# <a name="production-output-location"></a><span data-ttu-id="21dbe-103">Plats för produktionsutleverans</span><span class="sxs-lookup"><span data-stu-id="21dbe-103">Production output location</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21dbe-104">Det här avsnittet beskriver den hierarki som används för att identifiera produktionsutleveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="21dbe-104">This topic describes the hierarchy that is used to identify the production output location.</span></span>

<span data-ttu-id="21dbe-105">Produktionsutleveransplatsen är den plats där en färdig artikel lagras först när den produceras.</span><span class="sxs-lookup"><span data-stu-id="21dbe-105">The production output location is the location where a finished good is first stored after it's produced.</span></span> <span data-ttu-id="21dbe-106">Den här platsen är vanligen nära produktionsprocessen som tillverkar den färdiga varan.</span><span class="sxs-lookup"><span data-stu-id="21dbe-106">Usually, this location is close to the production process that produces the finished good.</span></span> <span data-ttu-id="21dbe-107">Produktionsutleveransplatsen används för materialet som transitlager innan den flyttas till försändelseområde, lagringsplats, en lagringsplats, en produktionsinleveransplats för efterföljande produktionsprocessen, osv.</span><span class="sxs-lookup"><span data-stu-id="21dbe-107">The production output location is used as intermediate storage for the material before it's moved on to the shipment area, a storage location, a production input location for a downstream production process, and so on.</span></span> 

<span data-ttu-id="21dbe-108">En standardplats produktionsutleverans anges när färdiga varor rapporteras för en produktionsorder eller batchorder.</span><span class="sxs-lookup"><span data-stu-id="21dbe-108">A default production output location is set when finished goods are reported on a production order or batch order.</span></span> <span data-ttu-id="21dbe-109">Följande hierarki används för att identifiera den här utdataplatsen:</span><span class="sxs-lookup"><span data-stu-id="21dbe-109">The following hierarchy is used to identify this output location:</span></span>

1. <span data-ttu-id="21dbe-110">Använd den utleveransplats som definieras i rubriken för produktionsordern eller batchordern.</span><span class="sxs-lookup"><span data-stu-id="21dbe-110">Use the output location that is defined on the production order or batch order header.</span></span>
2. <span data-ttu-id="21dbe-111">Om ingen plats hittas där använder du den utleveransplats som definieras för en resurs som används av den sista operationen som definierats i produktionsflödet.</span><span class="sxs-lookup"><span data-stu-id="21dbe-111">If no location is found there, use the output location that is defined on the resource that is used by the last operation that is defined in the production route.</span></span>
3. <span data-ttu-id="21dbe-112">Om ingen plats hittas där använder du den utleveransplats som definieras för en resursgrupp som används av resursen för den sista operationen som definierats i produktionsflödet.</span><span class="sxs-lookup"><span data-stu-id="21dbe-112">If no location is found there, use the output location that is defined on the resource group that is used by the resource for the last operation that is defined in the production route.</span></span>
4. <span data-ttu-id="21dbe-113">Om ingen plats hittas använder du utleveransplatsen som definieras i det lager som definierats för tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="21dbe-113">If no location is found there, use the output location that is defined on the warehouse that is defined for the production order.</span></span>

<span data-ttu-id="21dbe-114">En standardplats för produktionsutleverans anges endast för produkter som har ställts in med hjälp av avancerade lagerprocesser.</span><span class="sxs-lookup"><span data-stu-id="21dbe-114">A default production output location is set only for products that are set up by using advanced warehouse processes.</span></span> <span data-ttu-id="21dbe-115">När den här typen av artikel har rapporterats som färdig skapas lagerarbete av typen **Plats för slutförda varor** eller **Plats för samprodukt och biprodukt** .</span><span class="sxs-lookup"><span data-stu-id="21dbe-115">When this type of item is reported as finished, warehouse work of the **Finished goods put away** or **Co-product and by-product put away** type is created.</span></span> <span data-ttu-id="21dbe-116">Den här typen av arbete använder produktionsutleveransplatsen som plockplats.</span><span class="sxs-lookup"><span data-stu-id="21dbe-116">This type of work uses the production output location as the pick location.</span></span> <span data-ttu-id="21dbe-117">Artikelinförselplatsen bestäms av platsdirektiv.</span><span class="sxs-lookup"><span data-stu-id="21dbe-117">The put-away location is determined by the location directives.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]