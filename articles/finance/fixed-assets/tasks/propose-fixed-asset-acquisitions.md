---
title: Föreslå förvärv av anläggningstillgång
description: Detta avsnitt beskriver hur du anskaffar en anläggningstillgång med hjälp av anskaffningsförslaget i anläggningstillgångsjournalen.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0997af638c141661afb677e2407a90a883168aed
ms.sourcegitcommit: a8201e0b9033c2afc2b1702b0337facaf7ad4b92
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "3628895"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="9b29e-103">Föreslå förvärv av anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="9b29e-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9b29e-104">Detta avsnitt beskriver hur du anskaffar en anläggningstillgång med hjälp av anskaffningsförslaget i anläggningstillgångsjournalen.</span><span class="sxs-lookup"><span data-stu-id="9b29e-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="9b29e-105">Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen.</span><span class="sxs-lookup"><span data-stu-id="9b29e-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="9b29e-106">Om du vill skaffa en anläggningstillgång via en förslagsjournal för anläggningstillgångar måste du först skapa anläggningstillgångsposten och sedan definiera anskaffningspriset i tillgångsförteckningen.</span><span class="sxs-lookup"><span data-stu-id="9b29e-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

1. <span data-ttu-id="9b29e-107">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="9b29e-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="9b29e-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9b29e-108">Select **New**.</span></span>
3. <span data-ttu-id="9b29e-109">I fältet **Namn**anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="9b29e-109">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="9b29e-110">Klicka på **Rader** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9b29e-110">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="9b29e-111">Välj **Förslag**.</span><span class="sxs-lookup"><span data-stu-id="9b29e-111">Select **Proposals**.</span></span>
6. <span data-ttu-id="9b29e-112">Välj **Anskaffningsförslag**.</span><span class="sxs-lookup"><span data-stu-id="9b29e-112">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="9b29e-113">Välj **filter**.</span><span class="sxs-lookup"><span data-stu-id="9b29e-113">Select **Filter**.</span></span> <span data-ttu-id="9b29e-114">Välj **Återställ** för att rensa tidigare värden.</span><span class="sxs-lookup"><span data-stu-id="9b29e-114">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="9b29e-115">Välj raden med **numret på anläggningstillgången**.</span><span class="sxs-lookup"><span data-stu-id="9b29e-115">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="9b29e-116">I fältet **Kriterier** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="9b29e-116">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="9b29e-117">Ange återstående kriterier för de anläggningstillgångar som du vill anskaffa med detta förslag.</span><span class="sxs-lookup"><span data-stu-id="9b29e-117">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="9b29e-118">Välj **OK** två gånger för att avsluta fönstret.</span><span class="sxs-lookup"><span data-stu-id="9b29e-118">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="9b29e-119">Kontrollera de skapade transaktionsraderna.</span><span class="sxs-lookup"><span data-stu-id="9b29e-119">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="9b29e-120">Endast anläggningstillgångar med anskaffningsdatum och anskaffningspris på räkenskapsboken inkluderas i anskaffningsförslaget.</span><span class="sxs-lookup"><span data-stu-id="9b29e-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="9b29e-121">På sidan väljer du fliken **Böcker**.</span><span class="sxs-lookup"><span data-stu-id="9b29e-121">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="9b29e-122">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="9b29e-122">Select **Post**.</span></span>
