---
title: Översikt över farliga material
description: Det här ämnet innehåller en översikt över funktioner som är relaterade till hantering och dokumenterar farligt material vid hantering av produktinformation och lagerstyrning.
author: dasani-madipalli
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 15edf61cba03a57b9b4d2c939228fd064b797942
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829388"
---
# <a name="hazardous-materials-overview"></a><span data-ttu-id="e0b20-103">Översikt över farliga material</span><span class="sxs-lookup"><span data-stu-id="e0b20-103">Hazardous materials overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0b20-104">För att fortsätta att följa sjöfarts- och transportbestämmelserna måste organisationer som skickar material som klassificeras som farligt gods inkludera ytterligare pappersarbete med sina transporter.</span><span class="sxs-lookup"><span data-stu-id="e0b20-104">To remain compliant with shipping and transport regulations, organizations that ship materials that are classified as dangerous goods must include additional paperwork with their shipments.</span></span> <span data-ttu-id="e0b20-105">Med hjälp av funktionen för farliga material kan kunderna lagra information som är relaterad till frisläppta artiklar.</span><span class="sxs-lookup"><span data-stu-id="e0b20-105">The hazardous materials feature lets customers store information that is related to released items.</span></span> <span data-ttu-id="e0b20-106">Denna information kan sedan användas för att förbereda leveransdokumentationen.</span><span class="sxs-lookup"><span data-stu-id="e0b20-106">This information can then be used to help prepare shipping documentation.</span></span> <span data-ttu-id="e0b20-107">En organisation som levererar farligt gods måste ha egna processer och procedurer för hantering av leveransprocessen.</span><span class="sxs-lookup"><span data-stu-id="e0b20-107">An organization that ships dangerous goods must have its own processes and procedures for managing the shipping process.</span></span> <span data-ttu-id="e0b20-108">Microsoft Dynamics 365 Supply Chain Management är bara ett verktyg som kan hjälpa dig att skapa de dokument som krävs.</span><span class="sxs-lookup"><span data-stu-id="e0b20-108">Microsoft Dynamics 365 Supply Chain Management is just a tool that can help generate the required documents.</span></span>

<span data-ttu-id="e0b20-109">Följande diagram illustrerar de steg som behövs för att ställa in och använda funktionen för farliga material.</span><span class="sxs-lookup"><span data-stu-id="e0b20-109">The following diagram illustrates the steps needed to set up and use the hazardous materials feature.</span></span>

<span data-ttu-id="e0b20-110">![Inställning och användning av funktionerna för farliga material](media/hazmat-overview.png "Inställning och användning av funktionerna för farliga material")</span><span class="sxs-lookup"><span data-stu-id="e0b20-110">![Setup and use of the hazardous materials feature](media/hazmat-overview.png "Setup and use of the hazardous materials feature")</span></span>

<span data-ttu-id="e0b20-111">Funktionen för farliga material ställs in i produktinformationshantering och innehåller dokument som kan skrivas ut genom lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="e0b20-111">The hazardous materials feature is set up in Product information management and provides documents that can be printed through Warehouse management.</span></span> <span data-ttu-id="e0b20-112">Därför är dessa områden i stort sett de två huvudområdena där du kommer att granska, ställa in och använda funktionens funktion:</span><span class="sxs-lookup"><span data-stu-id="e0b20-112">Therefore, broadly speaking, those areas are the two main areas where you will review, set up, and use this feature's functionality:</span></span>

- <span data-ttu-id="e0b20-113">**Produktinformationshantering** – Ställ in koder som kan användas för frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="e0b20-113">**Product information management** – Set up the codes that will be applied to a released product.</span></span>
- <span data-ttu-id="e0b20-114">**Lagerstyrning** – arbeta med ytterligare leveransdokument som ska skrivas ut för försändelser.</span><span class="sxs-lookup"><span data-stu-id="e0b20-114">**Warehouse management** – Work with additional shipping documents that will be printed for shipments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0b20-115">Funktionerna för farliga material i Supply Chain Management tillhandahåller en samling användbara produktinformationsfält och tillhörande funktioner som kan hjälpa dig att registrera och referera till information som rör dina farliga produkter.</span><span class="sxs-lookup"><span data-stu-id="e0b20-115">The hazardous materials features in Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="e0b20-116">Dessa funktioner kan också hjälpa dig att utforma och skriva ut leveransdokument som innehåller en del av samma information om något farligt material som du levererar.</span><span class="sxs-lookup"><span data-stu-id="e0b20-116">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="e0b20-117">Systemet gör dock inte att du automatiskt följer alla tillämpliga regler i ditt land eller din region.</span><span class="sxs-lookup"><span data-stu-id="e0b20-117">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="e0b20-118">Även om dessa verktyg är avsedda att hjälpa dig att följa gemensamma regler är de varken tillräckliga i sig eller garanterat.</span><span class="sxs-lookup"><span data-stu-id="e0b20-118">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="e0b20-119">Organisationen är ansvarig för att vara medveten om alla tillämpliga regler och vidta alla nödvändiga åtgärder för att följa dem.</span><span class="sxs-lookup"><span data-stu-id="e0b20-119">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="e0b20-120">Produktinformationshantering</span><span class="sxs-lookup"><span data-stu-id="e0b20-120">Product information management</span></span>

<span data-ttu-id="e0b20-121">I produktinformationshantering finns det ett intervall med inställningstabeller där du kan lägga till den referensinformation som finns i listor över farligt gods för väg-, flyg- och sjöfrakt.</span><span class="sxs-lookup"><span data-stu-id="e0b20-121">Product information management provides a range of setup tables where you can enter reference information for the various dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="e0b20-122">Följande gemensamma förordningar refererades när denna funktion utvecklades:</span><span class="sxs-lookup"><span data-stu-id="e0b20-122">The following common regulations were referenced when this functionality was developed:</span></span>

- <span data-ttu-id="e0b20-123">**ADR** – förordningar som rör internationell transport av farligt gods på väg</span><span class="sxs-lookup"><span data-stu-id="e0b20-123">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="e0b20-124">**CFR 49** – förordningar i USA för transport av farligt gods</span><span class="sxs-lookup"><span data-stu-id="e0b20-124">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="e0b20-125">**IMDG** – internationella koden för sjötransport av farligt gods (IMDG)</span><span class="sxs-lookup"><span data-stu-id="e0b20-125">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="e0b20-126">**IATA** – reglerna för farligt gods i IATA (International Air Transport Association)</span><span class="sxs-lookup"><span data-stu-id="e0b20-126">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="e0b20-127">Varje uppsättning regler innehåller standardiserade listor över farligt gods och referenskoder.</span><span class="sxs-lookup"><span data-stu-id="e0b20-127">Each set of regulations provides standardized lists of dangerous goods and reference codes.</span></span> <span data-ttu-id="e0b20-128">Supply Chain Management innehåller därför en referens tabell för de vanliga koderna i listorna.</span><span class="sxs-lookup"><span data-stu-id="e0b20-128">Therefore, Supply Chain Management provides a reference table for the common codes on those lists.</span></span> <span data-ttu-id="e0b20-129">Varje lista har också vissa unika koder som kan definieras.</span><span class="sxs-lookup"><span data-stu-id="e0b20-129">Each list also has some unique codes that you can define.</span></span>

<span data-ttu-id="e0b20-130">Mer information om hur du ställer in regler och värden för farliga material och hur du tilldelar värden till relevanta produkter finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="e0b20-130">For more information about how to set up regulations and values for hazardous materials, and how to assign the values to relevant products, see the following topics:</span></span>

- [<span data-ttu-id="e0b20-131">Ställa in farliga material</span><span class="sxs-lookup"><span data-stu-id="e0b20-131">Set up hazardous materials</span></span>](hazmat-setup.md)
- [<span data-ttu-id="e0b20-132">Farliga material i produkter, order, leveranser och laster</span><span class="sxs-lookup"><span data-stu-id="e0b20-132">Hazardous materials in products, orders, shipments, and loads</span></span>](hazmat-items.md)

## <a name="warehouse-management"></a><span data-ttu-id="e0b20-133">Lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="e0b20-133">Warehouse management</span></span>

<span data-ttu-id="e0b20-134">När du förbereder en leverans i lagerstyrning kommer du att kunna skriva ut flera nya rapporter som använder informationen som du ställer in i produktinformationshantering.</span><span class="sxs-lookup"><span data-stu-id="e0b20-134">When you prepare a shipment in Warehouse management, you will be able to print several new reports that use the information that you set up in Product information management.</span></span> <span data-ttu-id="e0b20-135">Mer information om tillgängliga rapporter och hur du använder dem finns i [frågor och rapporter om farliga material](hazmat-reports.md).</span><span class="sxs-lookup"><span data-stu-id="e0b20-135">For more information about the available reports and how to use them, see [Hazardous materials inquiries and reports](hazmat-reports.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]