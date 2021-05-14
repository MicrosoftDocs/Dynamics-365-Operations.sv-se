---
title: Dela skapade XML-filer utifrån filstorlek och innehållskvantitet
description: Det här avsnittet innehåller information om hur du delar skapade filer baserat på filstorlek och innehållartikelkvantitet.
author: NickSelin
ms.date: 04/23/2021
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
ms.openlocfilehash: 9b0c8d215d1932a4c897488cb9c6ed7fa2127d82
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944351"
---
# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a><span data-ttu-id="0600a-103">Dela skapade XML-filer utifrån filstorlek och innehållskvantitet</span><span class="sxs-lookup"><span data-stu-id="0600a-103">Split generated XML files based on file size and content quantity</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0600a-104">Du kan utforma elektronisk rapportering (ER)-format som skapar utgående dokument i XML-format.</span><span class="sxs-lookup"><span data-stu-id="0600a-104">You can design Electronic reporting (ER) formats to generate outgoing documents in XML format.</span></span> <span data-ttu-id="0600a-105">Ibland kan dessa dokument endast godkännas om de uppfyller vissa kriterier såsom maximal filstorlek eller maximalt antal för vissa XML-noder.</span><span class="sxs-lookup"><span data-stu-id="0600a-105">Sometimes, those documents can be accepted only when they meet specific criteria, such a maximum file size or a maximum number of some XML nodes.</span></span> <span data-ttu-id="0600a-106">Du kan skapa ER-format för att skapa elektroniska dokument som uppfyller de krav som anger mottagare av dessa dokument.</span><span class="sxs-lookup"><span data-stu-id="0600a-106">You can design ER formats to generate electronic documents that satisfy the requirements that the recipients of those documents specify.</span></span>

- <span data-ttu-id="0600a-107">För elementet FIL-format kan du definiera en gräns på storleken som ett ER-uttryck.</span><span class="sxs-lookup"><span data-stu-id="0600a-107">For the FILE format element, you can define a limit on the file size as an ER expression.</span></span> <span data-ttu-id="0600a-108">Om den definierade gränsen överskrids när en ER-rapport skapas, slutför ER att skapa den aktuella filen och går sedan vidare till nästa fil.</span><span class="sxs-lookup"><span data-stu-id="0600a-108">If the defined limit is exceeded when an ER report is generated, ER finishes creating the current file and then moves on to create the next file.</span></span>
- <span data-ttu-id="0600a-109">För alla XML ELEMENT-format kan du definiera en gräns på antalet element som ett ER-uttryck.</span><span class="sxs-lookup"><span data-stu-id="0600a-109">For any XML ELEMENT format, you can define a limit on the number of elements as an ER expression.</span></span> <span data-ttu-id="0600a-110">Om antalet XML-noder i filen som skapas överstiger gränsen när en ER-rapport körs, slutför ER att skapa den aktuella filen och går sedan vidare till nästa fil.</span><span class="sxs-lookup"><span data-stu-id="0600a-110">If the number of XML nodes in the file that is generated exceeds the defined limit when an ER report is run, ER finishes creating the current file and then moves on to create the next file.</span></span>
- <span data-ttu-id="0600a-111">För alla XML SEQUENCE-formatelement kan du definiera en gräns på antalet underordnade element som ett ER-uttryck.</span><span class="sxs-lookup"><span data-stu-id="0600a-111">For any XML SEQUENCE format element, you can define a limit on the number of child elements as an ER expression.</span></span> <span data-ttu-id="0600a-112">Om antalet kapslade XML-noder av formatelement i den skapade filen överstiger gränsen när en ER-rapport körs, slutför ER att skapa den aktuella filen och går sedan vidare till nästa fil.</span><span class="sxs-lookup"><span data-stu-id="0600a-112">If the number of nested XML nodes of the format element in the generated file exceeds the defined limit when an ER report is run, ER finishes creating the current file and then moves on to create the next file.</span></span>
- <span data-ttu-id="0600a-113">Du kan markera XML ELEMENT-formatet som fasta</span><span class="sxs-lookup"><span data-stu-id="0600a-113">You can mark any XML ELEMENT format element as non-breakable.</span></span> <span data-ttu-id="0600a-114">På så sätt kan du behålla de kapslade artiklarna med XML-noder som skapas under formatelementet i en enkel skapad fil.</span><span class="sxs-lookup"><span data-stu-id="0600a-114">In this way, you can keep the nested items of XML nodes that are generated under the format element in a single generated file.</span></span>

<span data-ttu-id="0600a-115">Utöver att använda XML ELEMENT- och XML SEQUENCE-formatelement för att lägga till XML-noder till den skapade filen kan du använda RAW XML-formatelementet.</span><span class="sxs-lookup"><span data-stu-id="0600a-115">In addition to using the XML ELEMENT and XML SEQUENCE format elements to add XML nodes to the generated file, you can use the RAW XML format element.</span></span> <span data-ttu-id="0600a-116">Noder som du lägger till med hjälp av RAW XML formatelementet beaktas inte när antalet noder beräknas för att utvärdera gränserna för antalet element.</span><span class="sxs-lookup"><span data-stu-id="0600a-116">However, nodes that you add by using the RAW XML format element aren't considered when the number of nodes is calculated to evaluate the limits on the number of elements.</span></span>

<span data-ttu-id="0600a-117">Om du har konfigurerat filmålet för ett FILE formatelement som har konfigurerats för att dela skapade utdata när specifika gränser överskrids skickas varje del av skapade utdata till det konfigurerade filmålet som en individuell fil.</span><span class="sxs-lookup"><span data-stu-id="0600a-117">If you configured file destinations for a FILE format element that has been configured to split the generated output whenever specific limits are exceeded, each piece of generated output is sent to the configured file destination as an individual file.</span></span> <span data-ttu-id="0600a-118">För att unikt namnge filerna som skapas genom att dela upp utdata, måste du konfigurera ER-uttryck för FILE-formatelementet.</span><span class="sxs-lookup"><span data-stu-id="0600a-118">To uniquely name the files that are created by splitting the output, you must configure an ER expression for the FILE format element.</span></span> <span data-ttu-id="0600a-119">Om du anger en ER-datakälla för NUMMERSERIE-typen ökas nummerserien för varje typ av delad utdata.</span><span class="sxs-lookup"><span data-stu-id="0600a-119">If you include an ER data source of the NUMBER SEQUENCE type, the number sequence will be incremented for each piece of the split output.</span></span>

<span data-ttu-id="0600a-120">Om du vill veta mer om den här funktionen kan du spela upp uppgiftsguiden **ER dela XML-filerna baserat på filstorlek eller innehållsartikelkvantiteten** som är en del av affärsprocessen **7.5.4.3 hämta/utveckla fram IT-tjänst/komponenter (10677)** och kan hämtas från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="0600a-120">To learn more about this feature, play the **ER Split XML files based on the file size or content item quantity** task guide, which is part of the **7.5.4.3 Acquire/Develop IT service/solution components (10677)** business process and can be downloaded from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span> <span data-ttu-id="0600a-121">Uppgiftsguiden ger dig information om processen att konfigurera ett ER-format för att dela skapade filer utifrån gränser om filstorlek och innehållsartikelkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="0600a-121">This task guide walks you through the process of configuring an ER format to split generated files based on limits on the file size and content item quantity.</span></span> <span data-ttu-id="0600a-122">För att slutföra uppgiftsguiden måste du hämta följande filer:</span><span class="sxs-lookup"><span data-stu-id="0600a-122">To complete the task guide, you must download the following files:</span></span>

- [<span data-ttu-id="0600a-123">Konfiguration av ER-datamodell – XmlFilesSplittingModel.xml</span><span class="sxs-lookup"><span data-stu-id="0600a-123">ER model configuration - XmlFilesSplittingModel.xml</span></span>](https://download.microsoft.com/download/e/a/f/eaffe96a-22ec-4a32-898a-f4328c91c387/XmlFilesSplittingModel.xml)
- [<span data-ttu-id="0600a-124">ER-formatkonfiguration – XmlFilesSplittingFormat.xml</span><span class="sxs-lookup"><span data-stu-id="0600a-124">ER format configuration - XmlFilesSplittingFormat.xml</span></span>](https://download.microsoft.com/download/e/9/c/e9c5849b-8254-4cdf-bb00-4c2ebc72ddec/XmlFilesSplittingFormat.xml)

## <a name="additional-resources"></a><span data-ttu-id="0600a-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0600a-125">Additional resources</span></span>
[<span data-ttu-id="0600a-126">Destinationer för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="0600a-126">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)

[<span data-ttu-id="0600a-127">Formeldesigner i elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="0600a-127">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
