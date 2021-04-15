---
title: Generera elektroniska dokument och uppdatera programdata med hjälp av ER
description: Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet för att skapa utgående elektroniska dokument.
author: NickSelin
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 863c69446e9a7d447847483ec129788e85a8fd58
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750044"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a><span data-ttu-id="7a83b-103">Generera elektroniska dokument och uppdatera programdata genom att använda ER</span><span class="sxs-lookup"><span data-stu-id="7a83b-103">Generate electronic documents and update application data by using ER</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a83b-104">Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet för att skapa utgående elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="7a83b-104">You can design Electronic reporting (ER) formats that can be used in the application to generate outgoing electronic documents.</span></span> <span data-ttu-id="7a83b-105">Du kan också utforma ER-format som tolkar inkommande elektroniska dokument och som använder innehållet i dokumenten för att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="7a83b-105">You can also design ER formats that parse incoming electronic documents and use the content in those documents to update application data.</span></span>

<span data-ttu-id="7a83b-106">På så sätt kan ett enskilt ER-format användas för att skapa utgående elektroniska dokument och sedan uppdatera programdatan.</span><span class="sxs-lookup"><span data-stu-id="7a83b-106">With this functionality, a single ER format can be used to generate outgoing electronic documents and then update the application data.</span></span> <span data-ttu-id="7a83b-107">Den här funktionen kan användas i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="7a83b-107">This feature can be used in the following scenarios:</span></span>

- <span data-ttu-id="7a83b-108">För att undvika upprepad användning av programdata i efterföljande processer kan du märka programdata omedelbart efter det att denna används för att skapa elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="7a83b-108">To prevent repeated usage of application data in subsequent processes you can mark an application’s data immediately after it is used to generate electronic documents.</span></span> <span data-ttu-id="7a83b-109">Till exempel kan du markera betalningstransaktioner som "redan behandlade" så snart de har inkluderats i ett meddelande om skapad betalning.</span><span class="sxs-lookup"><span data-stu-id="7a83b-109">For example, you can mark payment transactions as already processed immediately after they have been included in a generated payment message.</span></span>
- <span data-ttu-id="7a83b-110">För att lagra behandlingsinformtionen för elektroniska dokument som har skapats med ER-logik.</span><span class="sxs-lookup"><span data-stu-id="7a83b-110">To store the processing details of electronic documents that have been generated using ER logic.</span></span> <span data-ttu-id="7a83b-111">Till exempel en unik betalningsmeddelandeidentifiering som skapas med uttrycket ER.</span><span class="sxs-lookup"><span data-stu-id="7a83b-111">For example, a unique payment message identification that is generated using the ER expression.</span></span> <span data-ttu-id="7a83b-112">Uttrycket baseras på information som angetts i ER-dialogrutan när formatet ER körs för att skapa dokument.</span><span class="sxs-lookup"><span data-stu-id="7a83b-112">The expression is based on information entered in the ER dialog box when the ER format is run to generate documents.</span></span>

<span data-ttu-id="7a83b-113">Om du vill veta mer om den här funktionen kan du spela upp ER-uppgiftsguiderna för Skapa dokument med uppdatering av programdata (ingår i affärsprocessen 7.5.4.3 Införskaffa/utveckla komponenter för IT-tjänst/-lösning (10677) som vägleder dig genom informationen om Intrastat-rapportering och -arkivering).</span><span class="sxs-lookup"><span data-stu-id="7a83b-113">To learn more about this feature, play the set of ER Generate documents with application data update Task guides (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walk you through the details of Intrastat reporting and archiving.</span></span> <span data-ttu-id="7a83b-114">Följande filer krävs för att kunna utföra vissa åtgärder i dessa uppgiftsguider.</span><span class="sxs-lookup"><span data-stu-id="7a83b-114">The following files are required to complete certain steps in these Task guides.</span></span> <span data-ttu-id="7a83b-115">Hämta och spara filerna på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="7a83b-115">Download and save these files to your local machine.</span></span>

- [<span data-ttu-id="7a83b-116">Konfiguration av ER-datamodell: Intrastat (modell)</span><span class="sxs-lookup"><span data-stu-id="7a83b-116">ER data model configuration: Intrastat (model)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="7a83b-117">Mappningskonfiguration för ER-modell: Intrastat (mappning)</span><span class="sxs-lookup"><span data-stu-id="7a83b-117">ER model mapping configuration: Intrastat (mapping)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="7a83b-118">ER-formatkonfiguration: Intrastat (format)</span><span class="sxs-lookup"><span data-stu-id="7a83b-118">ER format configuration: Intrastat (format)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]