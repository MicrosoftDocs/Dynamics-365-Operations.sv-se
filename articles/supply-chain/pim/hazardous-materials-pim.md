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
ms.openlocfilehash: 5006f06d90ddcc314a51878e9e21337de7d493e7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208480"
---
# <a name="hazardous-materials"></a><span data-ttu-id="0c5b5-103">Farliga material</span><span class="sxs-lookup"><span data-stu-id="0c5b5-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0c5b5-104">Information om farligt material ställs in i produktinformationshantering.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="0c5b5-105">Modulen innehåller också dokument som kan skrivas ut via lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="0c5b5-106">När du levererar material som klassificeras som farligt gods, måste ytterligare pappersarbete inkluderas i försändelserna.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="0c5b5-107">Med hjälp av funktionen för farliga material kan du informera kunder om klassificeringsinformation och relatera den till att frisläppa artiklar.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="0c5b5-108">Denna information kan sedan användas för att förbereda leveransdokumentationen.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c5b5-109">För att hantera transporter av farligt gods kan du med hjälp av Microsoft Dynamics 365 Supply Chain Management ställa in ytterligare referensinformation om produkter.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-109">To help manage shipments of dangerous goods, Microsoft Dynamics 365 Supply Chain Management lets you set up additional reference information that is related to products.</span></span> <span data-ttu-id="0c5b5-110">Du kan också ställa in fler leveransdokument.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-110">You can also set up additional shipment documents.</span></span> <span data-ttu-id="0c5b5-111">Systemet följer dock inte automatiskt upp dina lands- eller regionsregler.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-111">However, the system isn't automatically compliant with your country's or region's regulations.</span></span> <span data-ttu-id="0c5b5-112">I stället är det ett verktyg som kan hjälpa ditt övergripande program.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-112">Instead, it's a tool that can help your overall program.</span></span>

<span data-ttu-id="0c5b5-113">Innan du kan använda den här funktionen, krävs följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0c5b5-113">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="0c5b5-114">**Produktinformationshantering:** Ställ in koder som kan användas för frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-114">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="0c5b5-115">**Lagerstyrning:** Använd ytterligare leveransdokument för att skriva ut leveransinformation.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-115">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="0c5b5-116">Produktinformationshantering</span><span class="sxs-lookup"><span data-stu-id="0c5b5-116">Product information management</span></span>

<span data-ttu-id="0c5b5-117">I produktinformationshantering finns det ett intervall med inställningstabeller där du kan lägga till den referensinformation som finns i listor över farligt gods för väg-, flyg- och sjöfrakt.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-117">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="0c5b5-118">Här är några av de regler som ofta hänvisas till:</span><span class="sxs-lookup"><span data-stu-id="0c5b5-118">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="0c5b5-119">**ADR** – förordningar som rör internationell transport av farligt gods på väg</span><span class="sxs-lookup"><span data-stu-id="0c5b5-119">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="0c5b5-120">**CFR 49** – förordningar i USA för transport av farligt gods</span><span class="sxs-lookup"><span data-stu-id="0c5b5-120">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="0c5b5-121">**IMDG** – internationella koden för sjötransport av farligt gods (IMDG)</span><span class="sxs-lookup"><span data-stu-id="0c5b5-121">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="0c5b5-122">**IATA** – reglerna för farligt gods i IATA (International Air Transport Association)</span><span class="sxs-lookup"><span data-stu-id="0c5b5-122">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="0c5b5-123">Var och en av dessa förordningar har en lista över farligt gods som omfattar referenskoder.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-123">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="0c5b5-124">Förteckningarna över varje transporttyp kombineras på delade internationella klassificeringar.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-124">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="0c5b5-125">Supply Chain Management innehåller en referens tabell för de delade koderna i listorna.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-125">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="0c5b5-126">Varje lista har också vissa unika koder som kan definieras.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-126">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="0c5b5-127">Börja med att konfigurera den här informationen genom att skapa en regel som du kan använda för att konfigurera de ursprungliga parametrarna.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-127">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="0c5b5-128">Lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="0c5b5-128">Warehouse management</span></span>

<span data-ttu-id="0c5b5-129">När en försändelse har förberetts kan flera nya rapporter skrivas ut.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-129">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="0c5b5-130">I dessa rapporter används den information som du ställer in i produktinformationshantering.</span><span class="sxs-lookup"><span data-stu-id="0c5b5-130">These reports use the information that you set up in Product information management.</span></span>
