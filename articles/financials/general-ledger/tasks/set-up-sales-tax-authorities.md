---
title: Ställ in momsmyndigheter
description: Skattemyndigheter är enheter dit den insamlade momsen måste rapporteras och betalas.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb0b30be91e33cb50af0ae5c2e4dcd75bd12599b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846329"
---
# <a name="set-up-sales-tax-authorities"></a><span data-ttu-id="5b475-103">Ställ in momsmyndigheter</span><span class="sxs-lookup"><span data-stu-id="5b475-103">Set up sales tax authorities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5b475-104">Skattemyndigheter är enheter dit den insamlade momsen måste rapporteras och betalas.</span><span class="sxs-lookup"><span data-stu-id="5b475-104">Sales tax authorities are entities to which collected sales tax needs to be reported and paid.</span></span> <span data-ttu-id="5b475-105">Du kan betala moms direkt till myndigheten eller via ett leverantörskonto som du skapar för skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="5b475-105">You can pay sales taxes to the authority directly or through a vendor account that you create for the sales tax authority.</span></span> <span data-ttu-id="5b475-106">Om du gör detta kan företaget använda sina vanliga betalningsrutiner för att betala skattemyndigheten i tid.</span><span class="sxs-lookup"><span data-stu-id="5b475-106">If you do this, the company can use its usual payment routines to pay the sales tax authority on time.</span></span> <span data-ttu-id="5b475-107">Om du inte registrerar skattemyndigheten som en leverantör måste någon förbereda en manuell betalning till skattemyndigheten på relevant förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="5b475-107">If you do not set up the tax authority as a vendor, someone must prepare a manual payment to the tax authority on the appropriate due date.</span></span> <span data-ttu-id="5b475-108">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="5b475-108">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="5b475-109">Gå till Skatt > Indirekta skatter > Moms > Skattemyndigheter.</span><span class="sxs-lookup"><span data-stu-id="5b475-109">Go to Tax > Indirect taxes > Sales tax > Sales tax authorities.</span></span>
2. <span data-ttu-id="5b475-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5b475-110">Click New.</span></span>
3. <span data-ttu-id="5b475-111">Ange ett värde i fältet Myndighet.</span><span class="sxs-lookup"><span data-stu-id="5b475-111">In the Authority field, type a value.</span></span>
4. <span data-ttu-id="5b475-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5b475-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="5b475-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="5b475-113">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="5b475-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5b475-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="5b475-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5b475-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="5b475-116">Välj rapportlayout för ditt land/region, om det finns tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="5b475-116">Select the report layout for your country/region, if one is available.</span></span> <span data-ttu-id="5b475-117">Om rapportlayouterna inte motsvarar kraven från skattemyndigheten, ska du använda standardlayouten.</span><span class="sxs-lookup"><span data-stu-id="5b475-117">If the report layouts do not correspond to the requirements of the sales tax authority, use default layout.</span></span>
9. <span data-ttu-id="5b475-118">Ange värden i avrundningformuläret och avrundningsfälten för att ange hur det totala momsbeloppet för betalning ska avrundas.</span><span class="sxs-lookup"><span data-stu-id="5b475-118">Enter values in the Rounding form and the Round-off fields to specify how the tax total amount to be paid should be rounded.</span></span> <span data-ttu-id="5b475-119">Alla avrundningsdifferenser bokförs på konton för automatiska transaktioner som ställts in i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="5b475-119">Any rounding differences will be posted to Accounts for automatic transactions set up in General ledger.</span></span>
10. <span data-ttu-id="5b475-120">Välj ett tal i fältet Avrundning.</span><span class="sxs-lookup"><span data-stu-id="5b475-120">In the Round-off field, enter a number.</span></span>
11. <span data-ttu-id="5b475-121">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5b475-121">Click Save.</span></span>

