---
title: Ändra format för elektronisk rapportering genom att återtillämpa Microsoft Excel-mall
description: Det här ämnet innehåller information om hur du ändrar formatet för elektronisk rapportering (ER) som används för att skapa affärsdokument genom att tillämpa en ändrad Excel-mall.
author: NickSelin
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8707f7b184bb66648edd0e48672c5514a0a5caf1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "313668"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a><span data-ttu-id="6165f-103">Ändra format för elektronisk rapportering genom att återtillämpa Microsoft Excel-mall</span><span class="sxs-lookup"><span data-stu-id="6165f-103">Modify Electronic reporting formats by reapplying Excel templates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6165f-104">Verktyget för elektronisk rapportering (ER) används för att skapa affärsdokument i elektroniskt format.</span><span class="sxs-lookup"><span data-stu-id="6165f-104">The Electronic reporting (ER) tool is used to generate business documents in an electronic format.</span></span> <span data-ttu-id="6165f-105">Om du vill skapa ett affärsdokument måste du skapa ett ER-format, och sedan använda ER-designer för att definiera utseendet på affärsdokumentet och ange de data som ska inkluderas i den.</span><span class="sxs-lookup"><span data-stu-id="6165f-105">To generate a business document, you must create an ER format, and then use the ER designer to define the layout of the business document and specify the data that should be included in it.</span></span> <span data-ttu-id="6165f-106">Kör sedan ER-formatet för att skapa affärsdokumentet.</span><span class="sxs-lookup"><span data-stu-id="6165f-106">You can then run the ER format to generate the business document.</span></span>

<span data-ttu-id="6165f-107">ER-verktyget kan användas för att skapa affärsdokument som Microsoft Excel-filer.</span><span class="sxs-lookup"><span data-stu-id="6165f-107">The ER tool can be used to generate business documents as Microsoft Excel files.</span></span> <span data-ttu-id="6165f-108">Du kan använda Excel-dokument som en mall för dessa dokument.</span><span class="sxs-lookup"><span data-stu-id="6165f-108">You can use an Excel document as a template for these documents.</span></span> <span data-ttu-id="6165f-109">Om du vill ange dokumentets layout i ER-designer kan du importera innehållet i Excel-dokument som du vill använda som mall i det definierade formatet för ER.</span><span class="sxs-lookup"><span data-stu-id="6165f-109">To define the document layout in the ER designer, you can import the contents of the Excel document that you want to use as a template into the defined ER format.</span></span> <span data-ttu-id="6165f-110">För mer detaljer, och för att träna detta scenario, spela upp arbetsguiden **ER utformar en konfiguration för rapportgenerering i OPENXML-format** (del av 7.5.4.3 affärsprocessen skaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677).</span><span class="sxs-lookup"><span data-stu-id="6165f-110">For more details, and to practice this scenario, play the task guide **ER Design a configuration for generating reports in OPENXML format** (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span>

<span data-ttu-id="6165f-111">Om du redigerar Excel-dokument som används som en mall för ett affärsdokument gör ny ER-funktion att du kan återanvända den uppdaterade mallen till ER-format.</span><span class="sxs-lookup"><span data-stu-id="6165f-111">If you edit the Excel document that is used as a template for a business document, new ER functionality lets you reapply the updated template to the ER format.</span></span> <span data-ttu-id="6165f-112">Då uppdateras ER-formatet så att det följer den uppdaterade mallen.</span><span class="sxs-lookup"><span data-stu-id="6165f-112">The ER format is then updated so that it adheres to the updated template.</span></span> <span data-ttu-id="6165f-113">För mer information om den här funktionen, spela uppgiftsguiden **ER ändra formatet genom att använda en Excel-mall** (del av 7.5.5.3 affärsprocessen skaffa/utveckla komponenter för IT-tjänster eller IT-lösningar (10683).</span><span class="sxs-lookup"><span data-stu-id="6165f-113">For more details about this functionality, play the task guide **ER Modify a format by reapplying an Excel template** (part of the 7.5.5.3 Acquire/Develop IT service/solution components (10683) business process).</span></span> <span data-ttu-id="6165f-114">I uppgiftsguiden där du importerar en uppdaterad mall använder du en ändrad mall av betalningsrapportens Excel-fil, SampleVendPaymWsReport2 som en mall.</span><span class="sxs-lookup"><span data-stu-id="6165f-114">In the task guide step where you import an updated template, use the modified template of the Payment Report Excel file, SampleVendPaymWsReport2, as a template.</span></span>
