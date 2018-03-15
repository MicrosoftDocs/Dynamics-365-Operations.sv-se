---
title: "Skapa elektroniska dokument och uppdatera programdata med hjälp av verktyget för elektronisk rapportering"
description: "Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet Finance and Operations för att generera utgående elektroniska dokument. Du kan också utforma ER-format som tolkar inkommande elektroniska dokument och som använder innehållet i dokumenten för att uppdatera programdata."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: af7f9a373496eee4df354d5dd9e5a25c51317c43
ms.openlocfilehash: e2447274016f517db3ec0eb8f55c6b3163822f50
ms.contentlocale: sv-se
ms.lasthandoff: 02/27/2018

---

# <a name="generate-electronic-documents-and-update-application-data-using-the-electronic-reporting-tool"></a><span data-ttu-id="54d3a-104">Skapa elektroniska dokument och uppdatera programdata med hjälp av verktyget för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="54d3a-104">Generate electronic documents and update application data using the Electronic reporting tool</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="54d3a-105">Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet Finance and Operations för att generera utgående elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="54d3a-105">You can design Electronic reporting (ER) formats that can be used in the Finance and Operations application to generate outgoing electronic documents.</span></span> <span data-ttu-id="54d3a-106">Du kan också utforma ER-format som tolkar inkommande elektroniska dokument och som använder innehållet i dokumenten för att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="54d3a-106">You can also design ER formats that parse incoming electronic documents and use the content in those documents to update application data.</span></span> 

<span data-ttu-id="54d3a-107">På så sätt kan ett enskilt ER-format användas för att generera utgående elektroniska dokument och sedan uppdatera programdatan.</span><span class="sxs-lookup"><span data-stu-id="54d3a-107">With this functionality, a single ER format can be used to generate outgoing electronic documents and then update the application data.</span></span> <span data-ttu-id="54d3a-108">Den här funktionen kan användas i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="54d3a-108">This feature can be used in the following scenarios:</span></span>

- <span data-ttu-id="54d3a-109">För att undvika upprepad användning av programdata i efterföljande processer kan du märka programdata omedelbart efter det att denna används för att generera elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="54d3a-109">To prevent repeated usage of application data in subsequent processes you can mark an application’s data immediately after it is used to generate electronic documents.</span></span> <span data-ttu-id="54d3a-110">Till exempel kan du markera betalningstransaktioner som "redan behandlade" så snart de har inkluderats i ett meddelande om genererad betalning.</span><span class="sxs-lookup"><span data-stu-id="54d3a-110">For example, you can mark payment transactions as already processed immediately after they have been included in a generated payment message.</span></span>
- <span data-ttu-id="54d3a-111">För att lagra behandlingsinformtionen för elektroniska dokument som har skapats med ER-logik.</span><span class="sxs-lookup"><span data-stu-id="54d3a-111">To store the processing details of electronic documents that have been generated using ER logic.</span></span> <span data-ttu-id="54d3a-112">Till exempel en unik betalningsmeddelandeidentifiering som genereras med uttrycket ER.</span><span class="sxs-lookup"><span data-stu-id="54d3a-112">For example, a unique payment message identification that is generated using the ER expression.</span></span> <span data-ttu-id="54d3a-113">Uttrycket baseras på information som angetts i ER-dialogrutan när formatet ER körs för att skapa dokument.</span><span class="sxs-lookup"><span data-stu-id="54d3a-113">The expression is based on information entered in the ER dialog box when the ER format is run to generate documents.</span></span>

<span data-ttu-id="54d3a-114">Om du vill veta mer om den här funktionen kan du spela upp ER-uppgiftsguiderna för Generera dokument med uppdatering av programdata (ingår i affärsprocessen 7.5.4.3 Införskaffa/utveckla komponenter för IT-tjänst/-lösning (10677) som vägleder dig genom informationen om Intrastat-rapportering och -arkivering.</span><span class="sxs-lookup"><span data-stu-id="54d3a-114">To learn more about this feature, play the set of ER Generate documents with application data update Task guides (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walk you through the details of Intrastat reporting and archiving.</span></span> <span data-ttu-id="54d3a-115">Följande filer krävs för att kunna utföra vissa åtgärder i dessa uppgiftsguider.</span><span class="sxs-lookup"><span data-stu-id="54d3a-115">The following files are required to complete certain steps in these Task guides.</span></span> <span data-ttu-id="54d3a-116">Hämta och spara filerna på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="54d3a-116">Download and save these files to your local machine.</span></span>

- [<span data-ttu-id="54d3a-117">Konfiguration av ER-datamodell: Intrastat (modell)</span><span class="sxs-lookup"><span data-stu-id="54d3a-117">ER data model configuration: Intrastat (model)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="54d3a-118">Mappningskonfiguration för ER-modell: Intrastat (mappning)</span><span class="sxs-lookup"><span data-stu-id="54d3a-118">ER model mapping configuration: Intrastat (mapping)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="54d3a-119">ER-formatkonfiguration: Intrastat (format)</span><span class="sxs-lookup"><span data-stu-id="54d3a-119">ER format configuration: Intrastat (format)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)

