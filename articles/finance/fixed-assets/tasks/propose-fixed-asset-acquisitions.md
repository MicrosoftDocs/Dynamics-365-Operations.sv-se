---
title: Föreslå förvärv av anläggningstillgång
description: Detta avsnitt beskriver hur du anskaffar en anläggningstillgång med hjälp av anskaffningsförslaget i anläggningstillgångsjournalen.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
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
ms.openlocfilehash: 4b35b13dc266fd5bccde437526400832d394b9aa
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179940"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="5208c-103">Föreslå förvärv av anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="5208c-103">Propose fixed asset acquisitions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5208c-104">Detta avsnitt beskriver hur du anskaffar en anläggningstillgång med hjälp av anskaffningsförslaget i anläggningstillgångsjournalen.</span><span class="sxs-lookup"><span data-stu-id="5208c-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="5208c-105">Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen.</span><span class="sxs-lookup"><span data-stu-id="5208c-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="5208c-106">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="5208c-106">In the Navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="5208c-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="5208c-107">Select **New**.</span></span>
3. <span data-ttu-id="5208c-108">I fältet **Namn**anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="5208c-108">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="5208c-109">Klicka på **Rader** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5208c-109">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="5208c-110">Välj **Förslag**.</span><span class="sxs-lookup"><span data-stu-id="5208c-110">Select **Proposals**.</span></span>
6. <span data-ttu-id="5208c-111">Välj **Anskaffningsförslag**.</span><span class="sxs-lookup"><span data-stu-id="5208c-111">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="5208c-112">Välj **filter**.</span><span class="sxs-lookup"><span data-stu-id="5208c-112">Select **Filter**.</span></span> <span data-ttu-id="5208c-113">Välj **Återställ** för att rensa tidigare värden.</span><span class="sxs-lookup"><span data-stu-id="5208c-113">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="5208c-114">Välj raden med **numret på anläggningstillgången**.</span><span class="sxs-lookup"><span data-stu-id="5208c-114">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="5208c-115">I fältet **Kriterier** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="5208c-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="5208c-116">Ange återstående kriterier för de anläggningstillgångar som du vill anskaffa med detta förslag.</span><span class="sxs-lookup"><span data-stu-id="5208c-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="5208c-117">Välj **OK** två gånger för att avsluta fönstret.</span><span class="sxs-lookup"><span data-stu-id="5208c-117">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="5208c-118">Kontrollera de skapade transaktionsraderna.</span><span class="sxs-lookup"><span data-stu-id="5208c-118">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="5208c-119">Endast anläggningstillgångar med anskaffningsdatum och anskaffningspris på räkenskapsboken inkluderas i anskaffningsförslaget.</span><span class="sxs-lookup"><span data-stu-id="5208c-119">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="5208c-120">På sidan väljer du fliken **Böcker**.</span><span class="sxs-lookup"><span data-stu-id="5208c-120">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="5208c-121">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="5208c-121">Select **Post**.</span></span>

