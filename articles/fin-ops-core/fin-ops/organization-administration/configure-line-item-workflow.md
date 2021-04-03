---
title: Konfigurera arbetsflöden för radartiklar
description: I det här avsnittet beskrivs hur du konfigurerar ett arbetsflödeselement för radartiklar.
author: ChrisGarty
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 46de2bc3683ed907f1879afc13c60adce261d402
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567025"
---
# <a name="configure-line-item-workflows"></a><span data-ttu-id="02f46-103">Konfigurera arbetsflöden för radartiklar</span><span class="sxs-lookup"><span data-stu-id="02f46-103">Configure line-item workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02f46-104">I det här avsnittet beskrivs hur du konfigurerar ett arbetsflödeselement för radartiklar.</span><span class="sxs-lookup"><span data-stu-id="02f46-104">This topic explains how to configure a line-item workflow element.</span></span>

<span data-ttu-id="02f46-105">Höger klicka på elementet i arbetsflödesredigeraren och klicka sedan på **Properties** för att öppna sidan **Properties**, om du vill konfigurera ett arbetsflöde för radartiklar.</span><span class="sxs-lookup"><span data-stu-id="02f46-105">To configure a line-item workflow element, in the workflow editor, right-click the element, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="02f46-106">Du kan sedan använda följande procedurer för att konfigurera olika egenskaper för arbetsflödet för radartikel.</span><span class="sxs-lookup"><span data-stu-id="02f46-106">Then use the following procedures to configure the properties of the line-item workflow element.</span></span>

## <a name="name-the-line-item-workflow-element"></a><span data-ttu-id="02f46-107">Namnge arbetsflödet för radartikel</span><span class="sxs-lookup"><span data-stu-id="02f46-107">Name the line-item workflow element</span></span>

<span data-ttu-id="02f46-108">Följ dessa steg när du vill ange ett namn för arbetsflödet för radartikel.</span><span class="sxs-lookup"><span data-stu-id="02f46-108">Follow these steps to enter a name for the line-item workflow element.</span></span>

1. <span data-ttu-id="02f46-109">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="02f46-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="02f46-110">I fältet **Namn** anger du ett unikt namn för arbetsflödet för radartikel.</span><span class="sxs-lookup"><span data-stu-id="02f46-110">In the **Name** field, enter a unique name for the line-item workflow element.</span></span>

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a><span data-ttu-id="02f46-111">Ange om samma arbetsflöde används för att bearbeta alla radartiklar</span><span class="sxs-lookup"><span data-stu-id="02f46-111">Specify whether the same workflow is used to process all line items</span></span>

<span data-ttu-id="02f46-112">Gör på följande sätt när du vill ange om samma arbetsflöde används för att bearbeta alla radartiklar i ett dokument.</span><span class="sxs-lookup"><span data-stu-id="02f46-112">Follow these steps to specify whether the same workflow is used to process all the line items on a document.</span></span>

1. <span data-ttu-id="02f46-113">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="02f46-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="02f46-114">Om samma arbetsflöde ska bearbeta alla radartiklar i ett dokument, klicka på **Anropa ett enskilt arbetsflöde för alla radartiklar**.</span><span class="sxs-lookup"><span data-stu-id="02f46-114">If the same workflow should process all the line items on a document, click **Invoke a single workflow for all line-items**.</span></span> <span data-ttu-id="02f46-115">Välj sedan arbetsflödet som ska användas för att bearbeta radartiklarna.</span><span class="sxs-lookup"><span data-stu-id="02f46-115">Then select the workflow to use to process the line items.</span></span>
3. <span data-ttu-id="02f46-116">Om ett specifikt arbetsflöde ska processa radartiklar som uppfyller en viss uppsättning villkor, klicka på **Anropa ett arbetsflöde för varje radartikel**.</span><span class="sxs-lookup"><span data-stu-id="02f46-116">If a specific workflow should process line items that meet a specific set of conditions, click **Invoke a workflow for each line-item**.</span></span> <span data-ttu-id="02f46-117">Följ därefter dessa steg när du vill definiera uppsättningen villkor:</span><span class="sxs-lookup"><span data-stu-id="02f46-117">Then follow these steps to define the set of conditions:</span></span>

    1. <span data-ttu-id="02f46-118">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="02f46-118">Click **Add**.</span></span>
    2. <span data-ttu-id="02f46-119">Välj villkoret i tabellen.</span><span class="sxs-lookup"><span data-stu-id="02f46-119">Select the condition in the table.</span></span>
    3. <span data-ttu-id="02f46-120">I fliken **Villkorsnamn** anger du ett namn på den villkorsuppsättning som du vill definiera.</span><span class="sxs-lookup"><span data-stu-id="02f46-120">On the **Condition name** tab, enter a name for the set of conditions that you're defining.</span></span>
    4. <span data-ttu-id="02f46-121">Klicka på **Lägg till villkor** för att ange ett villkor.</span><span class="sxs-lookup"><span data-stu-id="02f46-121">Click **Add condition** to enter a condition.</span></span>
    5. <span data-ttu-id="02f46-122">Ange eventuellt ytterligare villkor som krävs.</span><span class="sxs-lookup"><span data-stu-id="02f46-122">Enter any additional conditions that are required.</span></span>
    6. <span data-ttu-id="02f46-123">Klicka på **Test** för att bekräfta att den uppsättning villkor som du har angett också har ställts in korrekt.</span><span class="sxs-lookup"><span data-stu-id="02f46-123">To verify that the set of conditions that you entered is configured correctly, click **Test**.</span></span> <span data-ttu-id="02f46-124">På sidan **Testa arbetsflödesvillkor**, i området **Validera villkor**, väljer du en post innan du klickar på **Testa**.</span><span class="sxs-lookup"><span data-stu-id="02f46-124">On the **Test workflow condition** page, in the **Validate condition** area, select a record, and then click **Test**.</span></span> <span data-ttu-id="02f46-125">Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.</span><span class="sxs-lookup"><span data-stu-id="02f46-125">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span> <span data-ttu-id="02f46-126">När du vill återgå till sidan **Egenskaper** klickar du på **OK** eller på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="02f46-126">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

    <span data-ttu-id="02f46-127">I fliken **Workflow** markerar du det arbetsflöde du vill använda för att processa radartiklar som uppfyller den uppsättning villkor som du har angett.</span><span class="sxs-lookup"><span data-stu-id="02f46-127">On the **Workflow** tab, select the workflow select the workflow to use to process line items that meet the set of conditions that you defined.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]