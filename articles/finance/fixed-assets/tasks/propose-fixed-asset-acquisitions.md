---
title: Föreslå förvärv av anläggningstillgång
description: Detta avsnitt beskriver hur du anskaffar en anläggningstillgång med hjälp av anskaffningsförslaget i anläggningstillgångsjournalen.
author: saraschi2
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d529cd53b41827a78b282afd4d2c69d2f2db555e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817182"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="1f1b8-103">Föreslå förvärv av anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="1f1b8-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1f1b8-104">Detta avsnitt beskriver hur du anskaffar en anläggningstillgång med hjälp av anskaffningsförslaget i anläggningstillgångsjournalen.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="1f1b8-105">Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="1f1b8-106">Om du vill skaffa en anläggningstillgång via en förslagsjournal för anläggningstillgångar måste du först skapa anläggningstillgångsposten och sedan definiera anskaffningspriset i tillgångsförteckningen.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

## <a name="create-an-asset-acquisition-proposal"></a><span data-ttu-id="1f1b8-107">Skapa ett förslag för anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="1f1b8-107">Create an asset acquisition proposal</span></span>

<span data-ttu-id="1f1b8-108">Gör på följande sätt om du vill skapa ett förslag för anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-108">Complete the following steps to create an asset acquisition proposal.</span></span> 

1. <span data-ttu-id="1f1b8-109">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-109">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="1f1b8-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-110">Select **New**.</span></span>
3. <span data-ttu-id="1f1b8-111">I fältet **Namn** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="1f1b8-112">Klicka på **Rader** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-112">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="1f1b8-113">Välj **Förslag**.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-113">Select **Proposals**.</span></span>
6. <span data-ttu-id="1f1b8-114">Välj **Anskaffningsförslag**.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-114">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="1f1b8-115">Välj **filter**.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-115">Select **Filter**.</span></span> <span data-ttu-id="1f1b8-116">Välj **Återställ** för att rensa tidigare värden.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-116">Select **Reset** to clear previous values.</span></span>
8. <span data-ttu-id="1f1b8-117">Välj raden med **numret på anläggningstillgången**.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-117">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="1f1b8-118">I fältet **Kriterier** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-118">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="1f1b8-119">Ange återstående kriterier för de anläggningstillgångar som du vill anskaffa med detta förslag.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-119">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="1f1b8-120">Välj **OK** två gånger för att avsluta fönstret.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-120">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="1f1b8-121">Kontrollera de skapade transaktionsraderna.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-121">Verify that the transaction lines are created.</span></span>  
- <span data-ttu-id="1f1b8-122">Endast anläggningstillgångar med anskaffningsdatum och anskaffningspris på räkenskapsboken inkluderas i anskaffningsförslaget.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-122">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="1f1b8-123">På sidan väljer du fliken **Böcker**.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-123">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="1f1b8-124">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="1f1b8-124">Select **Post**.</span></span>

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a><span data-ttu-id="1f1b8-125">Inkludera ekonomiska standarddimensioner i ett anskaffningsförslag</span><span class="sxs-lookup"><span data-stu-id="1f1b8-125">Include default financial dimensions in an acquisition proposal</span></span>

<span data-ttu-id="1f1b8-126">Anskaffningstransaktionen kan skapas med hjälp av Excel-tillägg genom att gå till **Anläggningstillgångar > Journalposter > Anläggningstillgångsjournal**.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-126">The acquisition transaction can be created using Excel add-ins, by going to **Fixed assets > Journal entries > Fixed asset journal**.</span></span> <span data-ttu-id="1f1b8-127">Skapa en ny journal och flytta till området **Rader** på sidan, markera Excel-ikonen och välj sedan en journalrad för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-127">Create a new journal and move to the **Lines** section on the page and select the Excel icon, and then select a Fixed asset journal line.</span></span> <span data-ttu-id="1f1b8-128">Systemet skapar och öppnar en Excel-mall som representerar journalrader.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-128">The system will create and open an Excel template representing journal lines.</span></span> <span data-ttu-id="1f1b8-129">Du kan lägga till data för de journalrader du lägger till i mallen och sedan publicera den informationen igen i systemet.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-129">You can add data for the journal lines you're adding into the template, and then publish that information back into the system.</span></span> 

<span data-ttu-id="1f1b8-130">Om standarddimensioner har ställts in för den valda tillgångsboken och motsvarande anläggningstillgångar som angetts i Excel-mallen, anropas de ekonomiska standarddimensionerna från huvuddata i tillgångsboken när journalen publiceras från Excel i systemet.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-130">If default dimensions have been set up for the selected asset book and the corresponding fixed assets that were entered in the Excel template, the default financial dimensions will be called from the asset book master data when the journal is published from the Excel to the system.</span></span> <span data-ttu-id="1f1b8-131">Om du vill att ekonomiska dimensioner ska inkluderas automatiskt i en tillgångsbok när du publicerar anläggningstillgångsjournalen från Excel-tillägget, måste standarddimensionerna ställas in i förväg.</span><span class="sxs-lookup"><span data-stu-id="1f1b8-131">To include financial dimensions on an asset book automatically while publishing the fixed asset journal from the Excel add-in, the default dimensions must be set up in advance.</span></span>  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
