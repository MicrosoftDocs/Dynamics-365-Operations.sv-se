---
title: Tolka inkommande dokument i Excel-format
description: Det här avsnittet innehåller information om hur du utformar elektronisk rapportering (ER)-format för att tolka innehållet på inkommande filer i Microsoft Excel-filer.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
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
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 3f83271327df186d407516ff1a197800ffc8c78c
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249366"
---
# <a name="parse-incoming-documents-in-excel-format"></a><span data-ttu-id="cd9d8-103">Tolka inkommande dokument i Excel-format</span><span class="sxs-lookup"><span data-stu-id="cd9d8-103">Parse incoming documents in Excel format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cd9d8-104">Du kan utforma elektronisk rapportering (ER)-format för att analysera inkommande filer i Microsoft Excel som visar data i Microsoft Excel-arbetsböcker (filerna i XLSX-format).</span><span class="sxs-lookup"><span data-stu-id="cd9d8-104">You can design Electronic reporting (ER) formats to parse incoming Microsoft Excel files that represent data in Microsoft Excel workbooks (files in XLSX format).</span></span> <span data-ttu-id="cd9d8-105">Du kan sedan använda innehållet från dessa filer till att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="cd9d8-105">You can then use the content from these files to update application data.</span></span> <span data-ttu-id="cd9d8-106">Detta är användbart om du:</span><span class="sxs-lookup"><span data-stu-id="cd9d8-106">This is useful if you:</span></span>

- <span data-ttu-id="cd9d8-107">Designar en ny modell och format och vill testa dem under körning.</span><span class="sxs-lookup"><span data-stu-id="cd9d8-107">Design a new model and format and want to test them at run-time.</span></span> <span data-ttu-id="cd9d8-108">I det här fallet simulerar Excel verkliga programdata.</span><span class="sxs-lookup"><span data-stu-id="cd9d8-108">In this case, Excel will simulate the actual application data.</span></span>
- <span data-ttu-id="cd9d8-109">Hantera data utanför programmet i Excel och vill importera denna data för att skicka en specifik rapport.</span><span class="sxs-lookup"><span data-stu-id="cd9d8-109">Manage data beyond your application in Excel and want to import this data to submit a specific report.</span></span>

<span data-ttu-id="cd9d8-110">Om du vill veta mer om den här funktionen kan du spela upp uppgiftsguiderna **ER importera data från en Microsoft Excel-fil (Del 1: Designformat)** och **ER importera data från en Microsoft Excel-fil (Del 2: Importera data)** (delar av affärsprocessen 7.5.4.3 hämta/utveckla IT-tjänst/lösningskomponenter (10677)).</span><span class="sxs-lookup"><span data-stu-id="cd9d8-110">To learn more about this feature, play the task guides **ER Import data from a Microsoft Excel file (Part 1: Design format)** and **ER Import data from a Microsoft Excel file (Part 2: Import data)** (parts of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span> <span data-ttu-id="cd9d8-111">Uppguftsguidera uppgift går igenom hur den inkommande Excel-filen kan tolkas med ER-formatet för att importera information från inkommande dokument och uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="cd9d8-111">These task guides walk through how the incoming Excel file can be parsed by using the ER format to import information from incoming documents and update application data.</span></span> <span data-ttu-id="cd9d8-112">Du kan hämta uppgiftsguidefilerna från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="cd9d8-112">You can download the task guide files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

<span data-ttu-id="cd9d8-113">Hämta följande filer för att slutföra uppgiftsguiderna som nämns ovan.</span><span class="sxs-lookup"><span data-stu-id="cd9d8-113">Download the following files to complete the task guides mentioned above.</span></span>

| <span data-ttu-id="cd9d8-114">Beskrivning av innehåll</span><span class="sxs-lookup"><span data-stu-id="cd9d8-114">Content description</span></span>                         | <span data-ttu-id="cd9d8-115">Fil</span><span class="sxs-lookup"><span data-stu-id="cd9d8-115">File</span></span>                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="cd9d8-116">Inkommande fil i XLSX-format - mall</span><span class="sxs-lookup"><span data-stu-id="cd9d8-116">Incoming file in .XLSX format - template</span></span>    | [<span data-ttu-id="cd9d8-117">1099import template.xlsx</span><span class="sxs-lookup"><span data-stu-id="cd9d8-117">1099import-template.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
| <span data-ttu-id="cd9d8-118">Inkommande fil i XLSX-format - exempeldata</span><span class="sxs-lookup"><span data-stu-id="cd9d8-118">Incoming file in .XLSX format - sample data</span></span> | [<span data-ttu-id="cd9d8-119">1099import data.xlsx</span><span class="sxs-lookup"><span data-stu-id="cd9d8-119">1099import-data.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)     |

<span data-ttu-id="cd9d8-120">Om du inte har spelat upp följande uppgiftguide än [ER Skapa erforderliga konfigurationer för att importera data från en extern fil f](./tasks/er-required-configurations-import-data.md) i den aktuella Finance and Operation-appen, hämta följande fil.</span><span class="sxs-lookup"><span data-stu-id="cd9d8-120">If you have not yet played the following task guide, [ER Create required configurations to import data from an external file](./tasks/er-required-configurations-import-data.md) in the current Finance and Operations application, download the following file.</span></span>

| <span data-ttu-id="cd9d8-121">Beskrivning av innehåll</span><span class="sxs-lookup"><span data-stu-id="cd9d8-121">Content description</span></span>    | <span data-ttu-id="cd9d8-122">Fil</span><span class="sxs-lookup"><span data-stu-id="cd9d8-122">File</span></span>                                                            |
|------------------------|-----------------------------------------------------------------|
| <span data-ttu-id="cd9d8-123">ER modellkonfiguration</span><span class="sxs-lookup"><span data-stu-id="cd9d8-123">ER model configuration</span></span> | [<span data-ttu-id="cd9d8-124">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="cd9d8-124">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
