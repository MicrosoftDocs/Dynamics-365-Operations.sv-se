---
title: Tolka inkommande dokument i Excel-format
description: Det här avsnittet innehåller information om hur du utformar elektronisk rapportering (ER)-format för att tolka innehållet på inkommande filer i Microsoft Excel-filer.
author: NickSelin
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 0c41a062d817307adb2889d3678764f1ea4066e2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755190"
---
# <a name="parse-incoming-documents-in-excel-format"></a><span data-ttu-id="cd96d-103">Tolka inkommande dokument i Excel-format</span><span class="sxs-lookup"><span data-stu-id="cd96d-103">Parse incoming documents in Excel format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cd96d-104">Du kan utforma elektronisk rapportering (ER)-format för att analysera inkommande filer i Microsoft Excel som visar data i Microsoft Excel-arbetsböcker (filerna i XLSX-format).</span><span class="sxs-lookup"><span data-stu-id="cd96d-104">You can design Electronic reporting (ER) formats to parse incoming Microsoft Excel files that represent data in Microsoft Excel workbooks (files in XLSX format).</span></span> <span data-ttu-id="cd96d-105">Du kan sedan använda innehållet från dessa filer till att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="cd96d-105">You can then use the content from these files to update application data.</span></span> <span data-ttu-id="cd96d-106">Detta är användbart om du:</span><span class="sxs-lookup"><span data-stu-id="cd96d-106">This is useful if you:</span></span>

- <span data-ttu-id="cd96d-107">Designar en ny modell och format och vill testa dem under körning.</span><span class="sxs-lookup"><span data-stu-id="cd96d-107">Design a new model and format and want to test them at run-time.</span></span> <span data-ttu-id="cd96d-108">I det här fallet simulerar Excel verkliga programdata.</span><span class="sxs-lookup"><span data-stu-id="cd96d-108">In this case, Excel will simulate the actual application data.</span></span>
- <span data-ttu-id="cd96d-109">Hantera data utanför programmet i Excel och vill importera denna data för att skicka en specifik rapport.</span><span class="sxs-lookup"><span data-stu-id="cd96d-109">Manage data beyond your application in Excel and want to import this data to submit a specific report.</span></span>

<span data-ttu-id="cd96d-110">Om du vill veta mer om den här funktionen kan du spela upp uppgiftsguiderna **ER importera data från en Microsoft Excel-fil (Del 1: Designformat)** och **ER importera data från en Microsoft Excel-fil (Del 2: Importera data)** (delar av affärsprocessen 7.5.4.3 hämta/utveckla IT-tjänst/lösningskomponenter (10677)).</span><span class="sxs-lookup"><span data-stu-id="cd96d-110">To learn more about this feature, play the task guides **ER Import data from a Microsoft Excel file (Part 1: Design format)** and **ER Import data from a Microsoft Excel file (Part 2: Import data)** (parts of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span> <span data-ttu-id="cd96d-111">Uppguftsguidera uppgift går igenom hur den inkommande Excel-filen kan tolkas med ER-formatet för att importera information från inkommande dokument och uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="cd96d-111">These task guides walk through how the incoming Excel file can be parsed by using the ER format to import information from incoming documents and update application data.</span></span> <span data-ttu-id="cd96d-112">Du kan hämta uppgiftsguidefilerna från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="cd96d-112">You can download the task guide files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

<span data-ttu-id="cd96d-113">Hämta följande filer för att slutföra uppgiftsguiderna som nämns ovan.</span><span class="sxs-lookup"><span data-stu-id="cd96d-113">Download the following files to complete the task guides mentioned above.</span></span>

| <span data-ttu-id="cd96d-114">Beskrivning av innehåll</span><span class="sxs-lookup"><span data-stu-id="cd96d-114">Content description</span></span>                         | <span data-ttu-id="cd96d-115">Fil</span><span class="sxs-lookup"><span data-stu-id="cd96d-115">File</span></span>                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="cd96d-116">Inkommande fil i XLSX-format - mall</span><span class="sxs-lookup"><span data-stu-id="cd96d-116">Incoming file in .XLSX format - template</span></span>    | [<span data-ttu-id="cd96d-117">1099import template.xlsx</span><span class="sxs-lookup"><span data-stu-id="cd96d-117">1099import-template.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
| <span data-ttu-id="cd96d-118">Inkommande fil i XLSX-format - exempeldata</span><span class="sxs-lookup"><span data-stu-id="cd96d-118">Incoming file in .XLSX format - sample data</span></span> | [<span data-ttu-id="cd96d-119">1099import data.xlsx</span><span class="sxs-lookup"><span data-stu-id="cd96d-119">1099import-data.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)     |

<span data-ttu-id="cd96d-120">Om du inte har spelat upp följande uppgiftsguide, [ER Skapa erforderliga konfigurationer för att importera data från en extern fil](./tasks/er-required-configurations-import-data.md) i den aktuella Finance and Operations-appen ska du hämta följande fil.</span><span class="sxs-lookup"><span data-stu-id="cd96d-120">If you have not yet played the following task guide, [ER Create required configurations to import data from an external file](./tasks/er-required-configurations-import-data.md) in the current Finance and Operations application, download the following file.</span></span>

| <span data-ttu-id="cd96d-121">Beskrivning av innehåll</span><span class="sxs-lookup"><span data-stu-id="cd96d-121">Content description</span></span>    | <span data-ttu-id="cd96d-122">Fil</span><span class="sxs-lookup"><span data-stu-id="cd96d-122">File</span></span>                                                            |
|------------------------|-----------------------------------------------------------------|
| <span data-ttu-id="cd96d-123">ER modellkonfiguration</span><span class="sxs-lookup"><span data-stu-id="cd96d-123">ER model configuration</span></span> | [<span data-ttu-id="cd96d-124">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="cd96d-124">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]