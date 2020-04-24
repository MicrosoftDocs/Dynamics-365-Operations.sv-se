---
title: Ställ in produkter som antingen kan produceras eller anskaffas
description: Produkter kan införskaffas på flera olika sätt - de kan produceras (tillverkas) eller anskaffas (köpas). Den här artikeln beskriver några typiska punkter att beakta när du konfigurerar produkter för att stödja fleranskaffning.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e68488a714764e7260fb141ccecdc361a8fd7bfa
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214721"
---
# <a name="set-up-products-that-can-be-produced-or-procured"></a><span data-ttu-id="542bc-104">Ställ in produkter som antingen kan produceras eller anskaffas</span><span class="sxs-lookup"><span data-stu-id="542bc-104">Set up products that can be produced or procured</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="542bc-105">Produkter kan införskaffas på flera olika sätt - de kan produceras (tillverkas) eller anskaffas (köpas).</span><span class="sxs-lookup"><span data-stu-id="542bc-105">Products can be sourced in various ways -  they can be produced (manufactured) or procured (purchased).</span></span> <span data-ttu-id="542bc-106">Den här artikeln beskriver några typiska punkter att beakta när du konfigurerar produkter för att stödja fleranskaffning.</span><span class="sxs-lookup"><span data-stu-id="542bc-106">This article describes some typical points to consider when you configure products to support multi-sourcing.</span></span> 

<span data-ttu-id="542bc-107">Fleranskaffning används vanligtvis för en inköpt artikel som i vissa fall tillverkas, eller när en artikel som primärt var en tillverkad artikel ändras så att den nu är primärt en inköpt artikel.</span><span class="sxs-lookup"><span data-stu-id="542bc-107">Multi-sourcing is typically used for a purchased item that is occasionally manufactured, or when an item that was primarily a manufactured item is changed so that it's now primarily a purchased item.</span></span> <span data-ttu-id="542bc-108">Artikeln betecknas inledningsvis som en tillverkad artikel så att strukturlistan och flödesinformationen kan definieras, och så att tillverkningsorder kan användas för artikeln.</span><span class="sxs-lookup"><span data-stu-id="542bc-108">The item is first designated as a manufactured item, so that bill of materials (BOM) and route information can be defined, and to support production orders for the item.</span></span> <span data-ttu-id="542bc-109">Produktiontypen ska anges som **Strukturlista** (eller vid processtillverkning som **Recept** eller **Samprodukt**).</span><span class="sxs-lookup"><span data-stu-id="542bc-109">The production type should be set to **BOM** (or, for process manufacturing, **Formula** or **Co-Product**).</span></span>

<span data-ttu-id="542bc-110">När du använder standardkostnad kan artikelkostnadsposten beräknas för den tillverkade artikeln.</span><span class="sxs-lookup"><span data-stu-id="542bc-110">When you use standard cost, the item cost record can be calculated for the manufactured item.</span></span> <span data-ttu-id="542bc-111">Men artikelkostnadsposten kanske inte matchar standardenkostnaden som du vill ha i inköpssyfte.</span><span class="sxs-lookup"><span data-stu-id="542bc-111">However, the item cost record might not match the standard cost that you want for purchasing purposes.</span></span> <span data-ttu-id="542bc-112">I detta fall måste standardkostnaden anges och aktiveras manuellt för artikelkostnadsposten.</span><span class="sxs-lookup"><span data-stu-id="542bc-112">In this case, the standard cost must be manually entered and activated for the item cost record.</span></span> <span data-ttu-id="542bc-113">Överväg att använda en särskild strukturlista och ett flöde som representerar den produktens leveransmix över en räkenskapsperiod, för att minimera avvikelser över tid.</span><span class="sxs-lookup"><span data-stu-id="542bc-113">For the cost calculation, consider using a special BOM and route that represent the supply mix of the product over the course of a fiscal period, to minimize the variances over time.</span></span> <span data-ttu-id="542bc-114">Dessutom kan en tillverkad artikel på en plats överförs till en annan plats.</span><span class="sxs-lookup"><span data-stu-id="542bc-114">Additionally, a manufactured item at one site can be transferred to another site.</span></span> <span data-ttu-id="542bc-115">Därför måste artikelns kostnad registreras och aktiveras manuellt för den plats som artikeln ska överföras till.</span><span class="sxs-lookup"><span data-stu-id="542bc-115">Therefore, the item's cost must be manually entered and activated for the site that the item is transferred to.</span></span> <span data-ttu-id="542bc-116">När du använder den tillverkade artikeln som en komponent i produkter på högre nivåer, ska komponentens kostnad behandlas som en inköpt artikel.</span><span class="sxs-lookup"><span data-stu-id="542bc-116">When you use the manufactured item as a component in higher-level products, the component's costs should be treated as a purchased item.</span></span> <span data-ttu-id="542bc-117">Denna riktlinje gäller oavsett om komponentens kostnader beräknas eller registreras manuellt.</span><span class="sxs-lookup"><span data-stu-id="542bc-117">This guideline applies, regardless of whether the component’s costs were calculated or manually entered.</span></span> <span data-ttu-id="542bc-118">Med andra ord ska strukturlisteberäkningen behandla artikelns kostnader som en inköpt komponent, i stället för att använda artikelns strukturliste- och flödesinformation för att beräkna kostnader.</span><span class="sxs-lookup"><span data-stu-id="542bc-118">In other words, a BOM calculation should treat the item's costs as a purchased component instead of using the item's BOM and route information to calculate costs.</span></span> 

<span data-ttu-id="542bc-119">Du kan förhindra den här beräkningen genom att välja flaggan **Stoppa nedbrytningen** som bäddas in i strukturlisteberäkningsgruppen som tilldelas artikeln.</span><span class="sxs-lookup"><span data-stu-id="542bc-119">To prevent the calculation from occurring, select the **Stop explosion** flag that is embedded in the BOM calculation group that is assigned to the item.</span></span> <span data-ttu-id="542bc-120">För att förhindra att huvudplaneringsberäkningar bryter ned behov via artikeln, ställs nedbrytningsgränsen in på = (noll) dagar i artikeldisponering eller i disponeringsgruppen.</span><span class="sxs-lookup"><span data-stu-id="542bc-120">To prevent master scheduling calculations from exploding requirements through the item, set the explosion fence to 0 (zero) days in item coverage or in the coverage group.</span></span> <span data-ttu-id="542bc-121">Huvudplaneringsberäkningen kommer sedan att behandla artikeln som en inköpt artikel och kan inte utföra fler beräkningar för artikelns strukturliste- och flödesinformation.</span><span class="sxs-lookup"><span data-stu-id="542bc-121">The master scheduling calculation will then treat the item as a purchased item and won't perform more calculations for the item's BOM and route information.</span></span>





