---
title: Ställ in kategorier för huvudkonto
description: Det här avsnittet innehåller information om hur du ställer in kategorier för huvudkonto i Dynamics 365 Finance.
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c2dcaa27f20ca050d278aa378e90946b8cb40449
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815126"
---
# <a name="set-up-main-account-categories"></a><span data-ttu-id="37475-103">Ställ in kategorier för huvudkonto</span><span class="sxs-lookup"><span data-stu-id="37475-103">Set up main account categories</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="37475-104">Det här avsnittet innehåller information om hur du ställer in kategorier för huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="37475-104">This topic explains how to set up main account categories.</span></span> <span data-ttu-id="37475-105">Huvudkontokategorier används för standardrapporterna i ekonomisk rapportering och i Power BI.</span><span class="sxs-lookup"><span data-stu-id="37475-105">Main account categories are used for the default reports in financial reporting and in Power BI.</span></span> <span data-ttu-id="37475-106">DU kan byta namn på men inte ta bort huvudkontokategorier som skapats som standard.</span><span class="sxs-lookup"><span data-stu-id="37475-106">Main account categories that are created by default can be renamed but not deleted.</span></span> <span data-ttu-id="37475-107">Ytterligare kontokategorier kan skapas och användas för rapporterings- och analysändamål.</span><span class="sxs-lookup"><span data-stu-id="37475-107">Additional account categories can be created and used for reporting and analysis purposes.</span></span> <span data-ttu-id="37475-108">I det här avsnittet används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="37475-108">This topic uses the USMF demo company.</span></span>

## <a name="create-a-main-account-category"></a><span data-ttu-id="37475-109">Skapa en huvudkontokategori</span><span class="sxs-lookup"><span data-stu-id="37475-109">Create a main account category</span></span>
1. <span data-ttu-id="37475-110">I Navigeringsfönster gå till **Moduler > Redovisning > Kontoplan > Konton > Huvudkontokategorier**.</span><span class="sxs-lookup"><span data-stu-id="37475-110">In the navigation pane, go to **Modules > General Ledger > Chart of accounts > Accounts > Main account categories**.</span></span>
2. <span data-ttu-id="37475-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="37475-111">Select **New**.</span></span>
3. <span data-ttu-id="37475-112">Ange ett unikt namn i fältet **Huvudkontokategori**.</span><span class="sxs-lookup"><span data-stu-id="37475-112">In the **Main account category** field, enter a unique name.</span></span>
4. <span data-ttu-id="37475-113">I fältet **Beskrivning** anger du en beskrivning av huvudkontokategorin.</span><span class="sxs-lookup"><span data-stu-id="37475-113">In the **Description field**, enter a description for the main account category.</span></span>
5. <span data-ttu-id="37475-114">I fältet **Huvudkontotyp** väljer du den huvudkontotyp som ska länkas till kategorin.</span><span class="sxs-lookup"><span data-stu-id="37475-114">In the **Main account type** field, select the main account type that will be linked to the category.</span></span>

## <a name="link-main-accounts-to-account-category"></a><span data-ttu-id="37475-115">Länka huvudkonton till kontokategori</span><span class="sxs-lookup"><span data-stu-id="37475-115">Link main accounts to account category</span></span>
1. <span data-ttu-id="37475-116">Klicka på **Länka huvudkonton**.</span><span class="sxs-lookup"><span data-stu-id="37475-116">Click **Link main accounts**.</span></span>
2. <span data-ttu-id="37475-117">I listan väljer du de huvudkonton som ska tilldelas huvudkontokategorin genom att markera kryssrutorna i den **Länkade** kolumnen.</span><span class="sxs-lookup"><span data-stu-id="37475-117">In the list, select the main accounts to assign to the main account category by checking the boxes in the **Linked** column.</span></span> <span data-ttu-id="37475-118">När du tilldelar huvudkonton till en huvudkontokategori läggs kontosaldona till när kategorin används för ekonomisk rapportering och analys.</span><span class="sxs-lookup"><span data-stu-id="37475-118">Assigning main accounts to a main account category will aggregate the balances of the accounts when that category is used for financial reporting and analysis.</span></span>  
3. <span data-ttu-id="37475-119">Markera eller avmarkera alternativet **Länkad** för att välja huvudkontona.</span><span class="sxs-lookup"><span data-stu-id="37475-119">Select or clear the **Linked** option to choose the main accounts.</span></span>
4. <span data-ttu-id="37475-120">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="37475-120">Select **OK**.</span></span>
5. <span data-ttu-id="37475-121">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="37475-121">Select **Yes**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]