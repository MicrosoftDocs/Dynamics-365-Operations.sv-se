---
title: Skapa en fraktsedel
description: I det här avsnittet beskrivs hur du skapar en fraktsedel när du använder lagerstyrningsprocesser.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench, WHSBillOfLadingCarrier, WHSBillOfLadingOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b001ef8936e7e35db89163683c023211f79b24c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996485"
---
# <a name="create-a-bill-of-lading"></a><span data-ttu-id="82982-103">Skapa en fraktsedel</span><span class="sxs-lookup"><span data-stu-id="82982-103">Create a bill of lading</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82982-104">I det här avsnittet beskrivs hur du skapar en fraktsedel när du använder lagerstyrningsprocesser.</span><span class="sxs-lookup"><span data-stu-id="82982-104">This topic describes how to create a bill of lading when using warehouse management processes.</span></span>  

<span data-ttu-id="82982-105">En fraktsedel är ett juridiskt dokument mellan företaget som skeppar artiklarna och transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="82982-105">A bill of lading is a legal document between the company that ships the items and the carrier.</span></span> <span data-ttu-id="82982-106">Dokumentet medföljer de levererade artiklarna och fungerar som ett leveranskvitto när artiklarna levereras till målet.</span><span class="sxs-lookup"><span data-stu-id="82982-106">The document accompanies the shipped items, and it serves as a receipt of shipment when the items are delivered at the destination.</span></span> <span data-ttu-id="82982-107">Om du använder lagerstyrning finns det två sätt att skapa en fraktsedel:</span><span class="sxs-lookup"><span data-stu-id="82982-107">If you're using warehouse management, there are two ways to generate a bill of lading:</span></span>

  -   <span data-ttu-id="82982-108">Skapa rapporten manuellt med hjälp av sidan **Fraktsedel**.</span><span class="sxs-lookup"><span data-stu-id="82982-108">Create the report manually, using the **Bill of lading** page.</span></span>
  -   <span data-ttu-id="82982-109">Generera rapporten från **Workbench för lastplanering**.</span><span class="sxs-lookup"><span data-stu-id="82982-109">Generate the report from the **Load planning workbench**.</span></span>

<span data-ttu-id="82982-110">Om du genererar fraktsedeln från **Workbench för lastplanering** måste beläggningsstatusen vara **Levererad.**</span><span class="sxs-lookup"><span data-stu-id="82982-110">If you generate the bill of lading from the **Load planning workbench**, the load status must be **Shipped.**</span></span> <span data-ttu-id="82982-111">Om det finns mer än en leverans i beläggningen, skapas en fraktsedel för varje leverans.</span><span class="sxs-lookup"><span data-stu-id="82982-111">If there's more than one shipment in the load, a bill of lading is created for each shipment.</span></span> <span data-ttu-id="82982-112">När en fraktsedel skapats kan du ändra den på sidan **Ffraktsedel**.</span><span class="sxs-lookup"><span data-stu-id="82982-112">After a bill of lading has been created you can make changes to it on the **Bill of lading** page.</span></span>

## <a name="master-bill-of-lading"></a><span data-ttu-id="82982-113">Huvudfraktsedel</span><span class="sxs-lookup"><span data-stu-id="82982-113">Master bill of lading</span></span>
<span data-ttu-id="82982-114">Om det finns mer än en leverans i en last kan du skapa en huvudfraktsedel.</span><span class="sxs-lookup"><span data-stu-id="82982-114">If there's more than one shipment in the load, you can generate a master bill of lading.</span></span> <span data-ttu-id="82982-115">Denna har samma layout och information som en fraktsedel, men innehåller det sammanfattade innehållet för alla leveranser.</span><span class="sxs-lookup"><span data-stu-id="82982-115">This has the same layout and information as a bill of lading, but contains the summarized content for all the shipments.</span></span> <span data-ttu-id="82982-116">Om alternativet **Skapa en huvudfraktsedel när det finns mer än en leverans på en beläggning** anges som **Ja** på sidan **Transportledningsparametrar**, genereras en huvudfraktsedel automatiskt om du skapar en fraktsedel från **Workbench för lastplanering** och det finns mer än en leverans.</span><span class="sxs-lookup"><span data-stu-id="82982-116">If the **Create a master bill of lading when there's more than one shipment on a load** option is set to **Yes** on the **Transportation management parameters** page, a master bill of lading is automatically generated if you create a bill of lading from the **Load planning workbench**, and there's more than one shipment.</span></span> <span data-ttu-id="82982-117">Du kan också få en lista över fraktsedlarna genom att klicka på **Relaterad information** &gt; **Fraktsedel**.</span><span class="sxs-lookup"><span data-stu-id="82982-117">You can also get a list of the bills of lading by clicking **Related information** &gt; **Bill of lading**.</span></span> <span data-ttu-id="82982-118">Om du skapar fraktsedlar manuellt kan du skapa en huvudfraktsedel på sidan **Fraktsedel**.</span><span class="sxs-lookup"><span data-stu-id="82982-118">If you're creating bills of lading manually, you can create a master bill of lading on the **Bill of lading** page.</span></span>



