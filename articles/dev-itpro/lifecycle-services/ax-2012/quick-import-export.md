---
title: "Använd Snabb import/export"
description: "Syftet med funktionen Snabb import/export är att du ska kunna importera och exportera med färre steg."
author: margoc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: 
ms.technology: 
audience: Application User
ms.reviewer: margoc
ms.search.scope: AX 2012 R3 CU8, UnifiedOperations
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5c54d0590856755e208ada9d97af7790a6de95ec
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a><span data-ttu-id="04a10-103">Kör Test Data Transfer Tool (beta) för Dynamics AX (AX 2012)</span><span class="sxs-lookup"><span data-stu-id="04a10-103">Run the Test Data Transfer Tool (beta) for Dynamics AX (AX 2012)</span></span>

[!include[banner](../../includes/banner.md)]


<span data-ttu-id="04a10-104">Syftet med funktionen Snabb import/export är att du ska kunna importera och exportera med färre steg.</span><span class="sxs-lookup"><span data-stu-id="04a10-104">The purpose of Quick import export is to let you import and export with fewer steps.</span></span>

<span data-ttu-id="04a10-105">Vi har lagt till funktionen Snabb import/export så att användarna kan importera eller exportera enkla jobb som de vill köra snabbt.</span><span class="sxs-lookup"><span data-stu-id="04a10-105">We added the Quick Import Export feature to let users import or export simple jobs that they want to execute quickly.</span></span> <span data-ttu-id="04a10-106">Den här funktionen används bäst i scenarier där en fil mappas automatiskt till systemet och där användaren inte behöver gå via Avancerad mappning eller Skapa återkommande import- eller exportjobb.</span><span class="sxs-lookup"><span data-stu-id="04a10-106">Ideally this feature is used in scenarios in which a file automatically maps to the system and user does not need to go through advanced mapping or create repeated import or export jobs.</span></span>

-   <span data-ttu-id="04a10-107">Den här funktionen stöder arbete med både OOB- och anpassade entiteter.</span><span class="sxs-lookup"><span data-stu-id="04a10-107">This feature supports working with both out-of-the-box and custom entities.</span></span>
-   <span data-ttu-id="04a10-108">Du kan importera från filer och om du använder en ODBC-datakälla kan du välja en fråga som du använder för att definiera importen.</span><span class="sxs-lookup"><span data-stu-id="04a10-108">You can import from files, and if you are using an ODBC data source, you can select a query to use to define your import.</span></span>
-   <span data-ttu-id="04a10-109">Du måste tidigare har definierat källdataformat för antingen AX eller Fil och veta var de finns.</span><span class="sxs-lookup"><span data-stu-id="04a10-109">You must have previously defined source data formats for either AX or File, and know where they are located.</span></span>
-   <span data-ttu-id="04a10-110">Du behöver inte skapa en bearbetningsgrupp för att använda funktionen Snabb import/export. Det skapas en automatiskt av systemet när du kör import- eller exportjobbet.</span><span class="sxs-lookup"><span data-stu-id="04a10-110">You do not need to create a processing group to use quick import/export, one will be automatically created by the system when executing the import or export job.</span></span> <span data-ttu-id="04a10-111">Du kan också välja spara historiken över de data som importerats med hjälp av funktionen Snabb import/export.</span><span class="sxs-lookup"><span data-stu-id="04a10-111">You can also choose keep the history of the data imported by the quick import/export.</span></span>

  <span data-ttu-id="04a10-112">Observera att funktionen Snabb import/export förutsätter att du känner till DIXF-begrepp.</span><span class="sxs-lookup"><span data-stu-id="04a10-112">Note that Quick import export assumes that you are familiar with the concepts of DIXF.</span></span>




