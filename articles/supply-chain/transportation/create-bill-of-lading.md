---
title: Skapa en fraktsedel
description: "I det här avsnittet beskrivs hur du skapar en fraktsedel när du använder lagerstyrningsprocesser."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ab5aa60198e442237fd85bb295589ae0ebe9c5f5
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="create-a-bill-of-lading"></a><span data-ttu-id="e75ec-103">Skapa en fraktsedel</span><span class="sxs-lookup"><span data-stu-id="e75ec-103">Create a bill of lading</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e75ec-104">I det här avsnittet beskrivs hur du skapar en fraktsedel när du använder lagerstyrningsprocesser.</span><span class="sxs-lookup"><span data-stu-id="e75ec-104">This topic describes how to create a bill of lading when using warehouse management processes.</span></span>  

<span data-ttu-id="e75ec-105">En fraktsedel är ett juridiskt dokument mellan företaget som skeppar artiklarna och transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="e75ec-105">A bill of lading is a legal document between the company that ships the items and the carrier.</span></span> <span data-ttu-id="e75ec-106">Dokumentet medföljer de levererade artiklarna och fungerar som ett leveranskvitto när artiklarna levereras till målet.</span><span class="sxs-lookup"><span data-stu-id="e75ec-106">The document accompanies the shipped items, and it serves as a receipt of shipment when the items are delivered at the destination.</span></span> <span data-ttu-id="e75ec-107">Om du använder lagerstyrning finns det två sätt att skapa en fraktsedel:</span><span class="sxs-lookup"><span data-stu-id="e75ec-107">If you're using warehouse management, there are two ways to generate a bill of lading:</span></span>

  -   <span data-ttu-id="e75ec-108">Skapa rapporten manuellt med hjälp av sidan **Fraktsedel**.</span><span class="sxs-lookup"><span data-stu-id="e75ec-108">Create the report manually, using the **Bill of lading** page.</span></span>
  -   <span data-ttu-id="e75ec-109">Generera rapporten från **Workbench för lastplanering**.</span><span class="sxs-lookup"><span data-stu-id="e75ec-109">Generate the report from the **Load planning workbench**.</span></span>

<span data-ttu-id="e75ec-110">Om du genererar fraktsedeln från **Workbench för lastplanering** måste beläggningsstatusen vara **Levererad.**</span><span class="sxs-lookup"><span data-stu-id="e75ec-110">If you generate the bill of lading from the **Load planning workbench**, the load status must be **Shipped.**</span></span> <span data-ttu-id="e75ec-111">Om det finns mer än en leverans i beläggningen, skapas en fraktsedel för varje leverans.</span><span class="sxs-lookup"><span data-stu-id="e75ec-111">If there's more than one shipment in the load, a bill of lading is created for each shipment.</span></span> <span data-ttu-id="e75ec-112">När en fraktsedel skapats kan du ändra den på sidan **Ffraktsedel**.</span><span class="sxs-lookup"><span data-stu-id="e75ec-112">After a bill of lading has been created you can make changes to it on the **Bill of lading** page.</span></span>

## <a name="master-bill-of-lading"></a><span data-ttu-id="e75ec-113">Huvudfraktsedel</span><span class="sxs-lookup"><span data-stu-id="e75ec-113">Master bill of lading</span></span>
<span data-ttu-id="e75ec-114">Om det finns mer än en leverans i en last kan du skapa en huvudfraktsedel.</span><span class="sxs-lookup"><span data-stu-id="e75ec-114">If there's more than one shipment in the load, you can generate a master bill of lading.</span></span> <span data-ttu-id="e75ec-115">Denna har samma layout och information som en fraktsedel, men innehåller det sammanfattade innehållet för alla leveranser.</span><span class="sxs-lookup"><span data-stu-id="e75ec-115">This has the same layout and information as a bill of lading, but contains the summarized content for all the shipments.</span></span> <span data-ttu-id="e75ec-116">Om alternativet **Skapa en huvudfraktsedel när det finns mer än en leverans på en beläggning** anges som **Ja** på sidan **Transportledningsparametrar**, genereras en huvudfraktsedel automatiskt om du skapar en fraktsedel från **Workbench för lastplanering** och det finns mer än en leverans.</span><span class="sxs-lookup"><span data-stu-id="e75ec-116">If the **Create a master bill of lading when there's more than one shipment on a load** option is set to **Yes** on the **Transportation management parameters** page, a master bill of lading is automatically generated if you create a bill of lading from the **Load planning workbench**, and there's more than one shipment.</span></span> <span data-ttu-id="e75ec-117">Du kan också få en lista över fraktsedlarna genom att klicka på **Relaterad information** &gt; **Fraktsedel**.</span><span class="sxs-lookup"><span data-stu-id="e75ec-117">You can also get a list of the bills of lading by clicking **Related information** &gt; **Bill of lading**.</span></span> <span data-ttu-id="e75ec-118">Om du skapar fraktsedlar manuellt kan du skapa en huvudfraktsedel på sidan **Fraktsedel**.</span><span class="sxs-lookup"><span data-stu-id="e75ec-118">If you're creating bills of lading manually, you can create a master bill of lading on the **Bill of lading** page.</span></span>




