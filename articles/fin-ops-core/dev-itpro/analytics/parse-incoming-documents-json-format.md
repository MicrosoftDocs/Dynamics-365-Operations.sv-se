---
title: Tolka inkommande dokument i JSON-format
description: Det här avsnittet innehåller information om hur du ställer in format för elektronisk rapportering (ER) för parsning av inkommande dokument i JSON-format (JavaScript Object Notation).
author: kfend
manager: AnnBe
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 8be4e225507a18a92d642ff0f3a6ca3d0ff68564
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772545"
---
# <a name="parse-incoming-documents-in-json-format"></a><span data-ttu-id="4c8c6-103">Tolka inkommande dokument i JSON-format</span><span class="sxs-lookup"><span data-stu-id="4c8c6-103">Parse incoming documents in JSON format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4c8c6-104">Du kan utforma format för elektronisk rapportering (ER) för att tolka inkommande elektroniska dokument som representerar data i ett textformat som baseras på Java Script (dvs. filer i \[JSON\]-format JavaScript Object Notation).</span><span class="sxs-lookup"><span data-stu-id="4c8c6-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents that represent data in a text format that is based on JavaScript (in other words, files in JavaScript Object Notation \[JSON\] format).</span></span>

<span data-ttu-id="4c8c6-105">Om du vill veta mer om den här funktionen kan du hämta filerna i följande tabell och sedan spela upp filen för att skapa en formatkonfiguration för import av data från en extern uppgiftsguide för JSON-filer.</span><span class="sxs-lookup"><span data-stu-id="4c8c6-105">To learn more about this feature, download the files in the following table, and then play the ER Create a format configuration to import data from an external JSON file task guide.</span></span> <span data-ttu-id="4c8c6-106">Den här uppgiftsguiden visar hur ett ER-format kan användas för att tolka en inkommande JSON-fil för att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="4c8c6-106">This task guide shows how an ER format can be used to parse an incoming JSON file to update application data.</span></span>

| <span data-ttu-id="4c8c6-107">Namn</span><span class="sxs-lookup"><span data-stu-id="4c8c6-107">Title</span></span>                                  | <span data-ttu-id="4c8c6-108">Filnamn</span><span class="sxs-lookup"><span data-stu-id="4c8c6-108">File name</span></span> |
|----------------------------------------|-----------|
| <span data-ttu-id="4c8c6-109">Konfiguration för ER-fomat</span><span class="sxs-lookup"><span data-stu-id="4c8c6-109">ER format configuration</span></span>                | [<span data-ttu-id="4c8c6-110">Format för import av leverantörers trans_JSON.xml</span><span class="sxs-lookup"><span data-stu-id="4c8c6-110">Format for importing vendors' trans_JSON.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |
| <span data-ttu-id="4c8c6-111">Exempel på inkommande fil i .csv-format</span><span class="sxs-lookup"><span data-stu-id="4c8c6-111">Sample of incoming file in .csv format</span></span> | [<span data-ttu-id="4c8c6-112">1099entries_JSON.txt</span><span class="sxs-lookup"><span data-stu-id="4c8c6-112">1099entries_JSON.txt</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a><span data-ttu-id="4c8c6-113">Behov</span><span class="sxs-lookup"><span data-stu-id="4c8c6-113">Requirements</span></span>

<span data-ttu-id="4c8c6-114">Innan du slutför ER skapar du en formatkonfiguration för att importera data från en extern uppgiftsguide för JSON-filer måste följande krav uppfyllas:</span><span class="sxs-lookup"><span data-stu-id="4c8c6-114">Before you complete the ER Create a format configuration to import data from an external JSON file task guide, the following requirement must be met:</span></span>

- <span data-ttu-id="4c8c6-115">De överordnade elementen i JSON-filen kan bara vara objektelement.</span><span class="sxs-lookup"><span data-stu-id="4c8c6-115">Parent elements in the JSON file can be only object elements.</span></span>
- <span data-ttu-id="4c8c6-116">Kapslade element för ett objekt ska vara egenskapselement, så att en giltig JSON-struktur skapas.</span><span class="sxs-lookup"><span data-stu-id="4c8c6-116">Nested elements for an object should be property elements, so that a valid JSON structure is created.</span></span>
- <span data-ttu-id="4c8c6-117">JSON-matriser kan bara innehålla kapslade element för ett objekts egenskapselement.</span><span class="sxs-lookup"><span data-stu-id="4c8c6-117">JSON arrays can be only nested elements of the property elements of an object.</span></span>
- <span data-ttu-id="4c8c6-118">JSON-matriser kan bara innehålla JSON-objekt.</span><span class="sxs-lookup"><span data-stu-id="4c8c6-118">JSON arrays can contain only JSON objects.</span></span> <span data-ttu-id="4c8c6-119">De får inte innehålla direkta strängar/numeriska värden och kapslade matriser.</span><span class="sxs-lookup"><span data-stu-id="4c8c6-119">They can't contain direct string/numeric values and nested arrays.</span></span> <span data-ttu-id="4c8c6-120">Element i dessa matriser tolkas i angiven ordning, eftersom de anges i formatet.</span><span class="sxs-lookup"><span data-stu-id="4c8c6-120">Elements in these arrays will be parsed in order, as they are specified in the format.</span></span> <span data-ttu-id="4c8c6-121">Sammansatta inställningar för varje JSON-objekt kommer att beaktas.</span><span class="sxs-lookup"><span data-stu-id="4c8c6-121">Multiplicity settings on each JSON object will be considered.</span></span>

<span data-ttu-id="4c8c6-122">Du måste dessutom fylla i uppgiftsguiden [ER Skapa erforderliga konfigurationer för att importera data från en extern fil](tasks/er-required-configurations-import-data.md) om du inte redan har fyllt i den.</span><span class="sxs-lookup"><span data-stu-id="4c8c6-122">Additionally, you must complete the [ER Create required configurations to import data from an external file](tasks/er-required-configurations-import-data.md) task guide if you haven't already completed it.</span></span> <span data-ttu-id="4c8c6-123">Hämta följande fil för att slutföra uppgiftsguiden.</span><span class="sxs-lookup"><span data-stu-id="4c8c6-123">Download the following file to complete the task guide.</span></span>

| <span data-ttu-id="4c8c6-124">Namn</span><span class="sxs-lookup"><span data-stu-id="4c8c6-124">Title</span></span>                  | <span data-ttu-id="4c8c6-125">Filnamn</span><span class="sxs-lookup"><span data-stu-id="4c8c6-125">File name</span></span> |
|------------------------|-----------|
| <span data-ttu-id="4c8c6-126">ER modellkonfiguration</span><span class="sxs-lookup"><span data-stu-id="4c8c6-126">ER model configuration</span></span> | [<span data-ttu-id="4c8c6-127">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="4c8c6-127">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |
