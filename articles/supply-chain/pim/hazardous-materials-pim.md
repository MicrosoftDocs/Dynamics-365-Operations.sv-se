---
title: Farliga material
description: Det här avsnittet innehåller information om dokument och information om farliga material som lagras i din miljö.
author: lachlancashMS
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 079c8d23250368c92e5d79f0e2624f8340db2077
ms.sourcegitcommit: c009ec75f53872272f11c92a1ce81a391e3845a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/18/2020
ms.locfileid: "3699546"
---
# <a name="hazardous-materials"></a><span data-ttu-id="3cb73-103">Farliga material</span><span class="sxs-lookup"><span data-stu-id="3cb73-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3cb73-104">Information om farligt material ställs in i produktinformationshantering.</span><span class="sxs-lookup"><span data-stu-id="3cb73-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="3cb73-105">Modulen innehåller också dokument som kan skrivas ut via lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="3cb73-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="3cb73-106">När du levererar material som klassificeras som farligt gods, måste ytterligare pappersarbete inkluderas i försändelserna.</span><span class="sxs-lookup"><span data-stu-id="3cb73-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="3cb73-107">Med hjälp av funktionen för farliga material kan du informera kunder om klassificeringsinformation och relatera den till att frisläppa artiklar.</span><span class="sxs-lookup"><span data-stu-id="3cb73-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="3cb73-108">Denna information kan sedan användas för att förbereda leveransdokumentationen.</span><span class="sxs-lookup"><span data-stu-id="3cb73-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cb73-109">Funktionerna för farliga material i Microsoft Dynamics 365 Supply Chain Management tillhandahåller en samling användbara produktinformationsfält och tillhörande funktioner som kan hjälpa dig att registrera och referera till information som rör dina farliga produkter.</span><span class="sxs-lookup"><span data-stu-id="3cb73-109">The hazardous materials features in Microsoft Dynamics 365 Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="3cb73-110">Dessa funktioner kan också hjälpa dig att utforma och skriva ut leveransdokument som innehåller en del av samma information om något farligt material som du levererar.</span><span class="sxs-lookup"><span data-stu-id="3cb73-110">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="3cb73-111">Systemet gör dock inte att du automatiskt följer alla tillämpliga regler i ditt land eller din region.</span><span class="sxs-lookup"><span data-stu-id="3cb73-111">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="3cb73-112">Även om dessa verktyg är avsedda att hjälpa dig att följa gemensamma regler är de varken tillräckliga i sig eller garanterat.</span><span class="sxs-lookup"><span data-stu-id="3cb73-112">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="3cb73-113">Organisationen är ansvarig för att vara medveten om alla tillämpliga regler och vidta alla nödvändiga åtgärder för att följa dem.</span><span class="sxs-lookup"><span data-stu-id="3cb73-113">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

<span data-ttu-id="3cb73-114">Innan du kan använda den här funktionen, krävs följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="3cb73-114">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="3cb73-115">**Produktinformationshantering:** Ställ in koder som kan användas för frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="3cb73-115">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="3cb73-116">**Lagerstyrning:** Använd ytterligare leveransdokument för att skriva ut leveransinformation.</span><span class="sxs-lookup"><span data-stu-id="3cb73-116">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="3cb73-117">Produktinformationshantering</span><span class="sxs-lookup"><span data-stu-id="3cb73-117">Product information management</span></span>

<span data-ttu-id="3cb73-118">I produktinformationshantering finns det ett intervall med inställningstabeller där du kan lägga till den referensinformation som finns i listor över farligt gods för väg-, flyg- och sjöfrakt.</span><span class="sxs-lookup"><span data-stu-id="3cb73-118">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="3cb73-119">Här är några av de regler som ofta hänvisas till:</span><span class="sxs-lookup"><span data-stu-id="3cb73-119">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="3cb73-120">**ADR** – förordningar som rör internationell transport av farligt gods på väg</span><span class="sxs-lookup"><span data-stu-id="3cb73-120">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="3cb73-121">**CFR 49** – förordningar i USA för transport av farligt gods</span><span class="sxs-lookup"><span data-stu-id="3cb73-121">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="3cb73-122">**IMDG** – internationella koden för sjötransport av farligt gods (IMDG)</span><span class="sxs-lookup"><span data-stu-id="3cb73-122">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="3cb73-123">**IATA** – reglerna för farligt gods i IATA (International Air Transport Association)</span><span class="sxs-lookup"><span data-stu-id="3cb73-123">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="3cb73-124">Var och en av dessa förordningar har en lista över farligt gods som omfattar referenskoder.</span><span class="sxs-lookup"><span data-stu-id="3cb73-124">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="3cb73-125">Förteckningarna över varje transporttyp kombineras på delade internationella klassificeringar.</span><span class="sxs-lookup"><span data-stu-id="3cb73-125">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="3cb73-126">Supply Chain Management innehåller en referens tabell för de delade koderna i listorna.</span><span class="sxs-lookup"><span data-stu-id="3cb73-126">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="3cb73-127">Varje lista har också vissa unika koder som kan definieras.</span><span class="sxs-lookup"><span data-stu-id="3cb73-127">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="3cb73-128">Börja med att konfigurera den här informationen genom att skapa en regel som du kan använda för att konfigurera de ursprungliga parametrarna.</span><span class="sxs-lookup"><span data-stu-id="3cb73-128">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="3cb73-129">Lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="3cb73-129">Warehouse management</span></span>

<span data-ttu-id="3cb73-130">När en försändelse har förberetts kan flera nya rapporter skrivas ut.</span><span class="sxs-lookup"><span data-stu-id="3cb73-130">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="3cb73-131">I dessa rapporter används den information som du ställer in i produktinformationshantering.</span><span class="sxs-lookup"><span data-stu-id="3cb73-131">These reports use the information that you set up in Product information management.</span></span>
