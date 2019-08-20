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
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839915"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="97fa0-103">Föreslå förvärv av anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="97fa0-103">Propose fixed asset acquisitions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="97fa0-104">Detta avsnitt beskriver hur du anskaffar en anläggningstillgång med hjälp av anskaffningsförslaget i anläggningstillgångsjournalen.</span><span class="sxs-lookup"><span data-stu-id="97fa0-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="97fa0-105">Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen.</span><span class="sxs-lookup"><span data-stu-id="97fa0-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="97fa0-106">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="97fa0-106">In the Navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="97fa0-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="97fa0-107">Select **New**.</span></span>
3. <span data-ttu-id="97fa0-108">I fältet **Namn**anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="97fa0-108">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="97fa0-109">Klicka på **Rader** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="97fa0-109">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="97fa0-110">Välj **Förslag**.</span><span class="sxs-lookup"><span data-stu-id="97fa0-110">Select **Proposals**.</span></span>
6. <span data-ttu-id="97fa0-111">Välj **Anskaffningsförslag**.</span><span class="sxs-lookup"><span data-stu-id="97fa0-111">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="97fa0-112">Välj **filter**.</span><span class="sxs-lookup"><span data-stu-id="97fa0-112">Select **Filter**.</span></span> <span data-ttu-id="97fa0-113">Välj **Återställ** för att rensa tidigare värden.</span><span class="sxs-lookup"><span data-stu-id="97fa0-113">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="97fa0-114">Välj raden med **numret på anläggningstillgången**.</span><span class="sxs-lookup"><span data-stu-id="97fa0-114">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="97fa0-115">I fältet **Kriterier** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="97fa0-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="97fa0-116">Ange återstående kriterier för de anläggningstillgångar som du vill anskaffa med detta förslag.</span><span class="sxs-lookup"><span data-stu-id="97fa0-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="97fa0-117">Välj **OK** två gånger för att avsluta fönstret.</span><span class="sxs-lookup"><span data-stu-id="97fa0-117">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="97fa0-118">Kontrollera de skapade transaktionsraderna.</span><span class="sxs-lookup"><span data-stu-id="97fa0-118">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="97fa0-119">Endast anläggningstillgångar med anskaffningsdatum och anskaffningspris på räkenskapsboken inkluderas i anskaffningsförslaget.</span><span class="sxs-lookup"><span data-stu-id="97fa0-119">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="97fa0-120">På sidan väljer du fliken **Böcker**.</span><span class="sxs-lookup"><span data-stu-id="97fa0-120">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="97fa0-121">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="97fa0-121">Select **Post**.</span></span>

