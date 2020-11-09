---
title: Skapa en anläggningstillgång
description: I det här avsnittet beskrivs hur du skapar en ny anläggningstillgångspost från listsidan för anläggningstillgångar.
author: saraschi2
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b7d65a047251fa036242fb456725bc8cba957b9
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000253"
---
# <a name="create-a-fixed-asset"></a><span data-ttu-id="9645c-103">Skapa en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="9645c-103">Create a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9645c-104">I det här avsnittet beskrivs hur du skapar en ny anläggningstillgångspost från listsidan för **anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="9645c-104">This topic explains how to create a new fixed asset record from the **Fixed asset** list page.</span></span>

<span data-ttu-id="9645c-105">Systemet tilldelar tillgångsnumret baserat på den nummer serie som har tilldelats anläggningstillgångsgruppen.</span><span class="sxs-lookup"><span data-stu-id="9645c-105">The system assigns the asset number, based on the number sequence that is assigned to the fixed asset group.</span></span> <span data-ttu-id="9645c-106">Om du använder mallen för anläggningstillgångar för att importera till gångar via Microsoft Excel-tillägget, eller om du använder ett annat importjobb, skapar systemet automatiskt anläggningstillgångsposter och ökar tillgångsnumret.</span><span class="sxs-lookup"><span data-stu-id="9645c-106">If you use the fixed asset template to import assets via the Microsoft Excel add-in, or if you use another import job, the system automatically creates fixed asset records and increments the asset number.</span></span>

<span data-ttu-id="9645c-107">Om du vill skapa en tillgångspost manuellt följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="9645c-107">To manually create an asset record, follow these steps.</span></span>

1. <span data-ttu-id="9645c-108">Gå till **Navigeringsfönstret \> Moduler \> Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="9645c-108">Go to **Navigation pane \> Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="9645c-109">Klicka på **Ny** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="9645c-109">On the **Action pane** , select **New**.</span></span>
3. <span data-ttu-id="9645c-110">Ange eller välj ett värde i fältet **Anläggningstillgångsgrupp.**</span><span class="sxs-lookup"><span data-stu-id="9645c-110">In **the Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="9645c-111">Fältet **Nummer** får sin standard om du har aktiverat funktionen **Autonummer för anläggningstillgångar** i **Parametrar för anläggningstillgångar** och **Anläggningstillgångsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="9645c-111">The **Number** field will default if you have enabled **Autonumber fixed assets functionality** in the **Fixed assets parameters** and the **Fixed asset group**.</span></span> <span data-ttu-id="9645c-112">Om inte måste du ange ett unikt nummer som identifierar anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="9645c-112">If not, you must enter a unique number to identify the fixed asset.</span></span>
4. <span data-ttu-id="9645c-113">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="9645c-113">In the **Name** field, enter a value.</span></span> <span data-ttu-id="9645c-114">Ange ytterligare information som verksamheten kräver för tillgången.</span><span class="sxs-lookup"><span data-stu-id="9645c-114">Enter the additional information that your business needs for this asset.</span></span>
5. <span data-ttu-id="9645c-115">Klicka på **Räkenskapsböcker** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="9645c-115">On the **Action pane** , select **Books**.</span></span>
6. <span data-ttu-id="9645c-116">Ange ett datum i fältet **Anskaffningsdatum.**</span><span class="sxs-lookup"><span data-stu-id="9645c-116">In the **Acquisition date** field, enter a date.</span></span>
7. <span data-ttu-id="9645c-117">Ange ett tal i fältet **Anskaffningspris.**</span><span class="sxs-lookup"><span data-stu-id="9645c-117">In the **Acquisition price** field, enter a number.</span></span>

    - <span data-ttu-id="9645c-118">Ange den ytterligare information som din verksamhet kräver för denna bok.</span><span class="sxs-lookup"><span data-stu-id="9645c-118">Enter the additional information that your business needs for this book.</span></span>
    - <span data-ttu-id="9645c-119">Ange den ytterligare information som verksamheten kräver för återstående böcker.</span><span class="sxs-lookup"><span data-stu-id="9645c-119">Enter the additional information that your business needs for the remaining books.</span></span>

8. <span data-ttu-id="9645c-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9645c-120">Close the page.</span></span>

<span data-ttu-id="9645c-121">Du kan även importera anläggningstillgångar genom att använda Excel-tillägget eller genom att köra ett importjobb från arbetsytan **Datahantering**.</span><span class="sxs-lookup"><span data-stu-id="9645c-121">You can also import fixed assets by using the Excel add-in or by running an import job from the **Data management** workspace.</span></span> <span data-ttu-id="9645c-122">Innan du kör importen anger du värdena för de obligatoriska fälten i mallen.</span><span class="sxs-lookup"><span data-stu-id="9645c-122">Before you run the import, enter the values for required fields in the template.</span></span>

<span data-ttu-id="9645c-123">Om du inte har definierat numret för anläggningstillgången i mallen för Excel-tillägget, eller i datahantering, skapar systemet ett anläggningstillgångsnummer för varje importerad tillgång och ökar nummer serien automatiskt för varje.</span><span class="sxs-lookup"><span data-stu-id="9645c-123">If you didn't define the fixed asset number in the template of the Excel add-in, or in Data management, the system creates a fixed asset number for each imported asset and automatically increments the number sequence for each.</span></span> <span data-ttu-id="9645c-124">Om du däremot importerar resurser och definierar tillgångsnummer i mallen ökar **inte** nummerserien automatiskt.</span><span class="sxs-lookup"><span data-stu-id="9645c-124">However, if you import assets and define asset numbers in the template, the system does **not** automatically increment the number sequence.</span></span> <span data-ttu-id="9645c-125">I det här fallet kan en administratör behöva uppdatera nummerserien manuellt.</span><span class="sxs-lookup"><span data-stu-id="9645c-125">In this case, an admin might have to manually update the number sequence.</span></span> <span data-ttu-id="9645c-126">Om du har definierat anläggningstillgångsnumret i mallen för Excel-tillägget använder systemet det definierade anläggningstillgångsnumret och ökar nummerserien.</span><span class="sxs-lookup"><span data-stu-id="9645c-126">If you defined the fixed asset number in the template of the Excel add-in, the system uses the defined fixed asset number and increments the number sequence.</span></span>
