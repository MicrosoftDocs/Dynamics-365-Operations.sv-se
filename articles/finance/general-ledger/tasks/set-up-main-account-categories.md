---
title: Ställ in kategorier för huvudkonto
description: Det här avsnittet innehåller information om hur du ställer in kategorier för huvudkonto i Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e0a015283064af2287013bccc065b4467a308c5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144799"
---
# <a name="set-up-main-account-categories"></a><span data-ttu-id="a86ce-103">Ställ in kategorier för huvudkonto</span><span class="sxs-lookup"><span data-stu-id="a86ce-103">Set up main account categories</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a86ce-104">Det här avsnittet innehåller information om hur du ställer in kategorier för huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="a86ce-104">This topic explains how to set up main account categories.</span></span> <span data-ttu-id="a86ce-105">Huvudkontokategorier används för standardrapporterna i ekonomisk rapportering och i Power BI.</span><span class="sxs-lookup"><span data-stu-id="a86ce-105">Main account categories are used for the default reports in financial reporting and in Power BI.</span></span> <span data-ttu-id="a86ce-106">DU kan byta namn på men inte ta bort huvudkontokategorier som skapats som standard.</span><span class="sxs-lookup"><span data-stu-id="a86ce-106">Main account categories that are created by default can be renamed but not deleted.</span></span> <span data-ttu-id="a86ce-107">Ytterligare kontokategorier kan skapas och användas för rapporterings- och analysändamål.</span><span class="sxs-lookup"><span data-stu-id="a86ce-107">Additional account categories can be created and used for reporting and analysis purposes.</span></span> <span data-ttu-id="a86ce-108">I det här avsnittet används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="a86ce-108">This topic uses the USMF demo company.</span></span>

## <a name="create-a-main-account-category"></a><span data-ttu-id="a86ce-109">Skapa en huvudkontokategori</span><span class="sxs-lookup"><span data-stu-id="a86ce-109">Create a main account category</span></span>
1. <span data-ttu-id="a86ce-110">I Navigeringsfönster gå till **Moduler > Redovisning > Kontoplan > Konton > Huvudkontokategorier**.</span><span class="sxs-lookup"><span data-stu-id="a86ce-110">In the navigation pane, go to **Modules > General Ledger > Chart of accounts > Accounts > Main account categories**.</span></span>
2. <span data-ttu-id="a86ce-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a86ce-111">Select **New**.</span></span>
3. <span data-ttu-id="a86ce-112">Ange ett unikt namn i fältet **Huvudkontokategori**.</span><span class="sxs-lookup"><span data-stu-id="a86ce-112">In the **Main account category** field, enter a unique name.</span></span>
4. <span data-ttu-id="a86ce-113">I fältet **Beskrivning** anger du en beskrivning av huvudkontokategorin.</span><span class="sxs-lookup"><span data-stu-id="a86ce-113">In the **Description field**, enter a description for the main account category.</span></span>
5. <span data-ttu-id="a86ce-114">I fältet **Huvudkontotyp** väljer du den huvudkontotyp som ska länkas till kategorin.</span><span class="sxs-lookup"><span data-stu-id="a86ce-114">In the **Main account type** field, select the main account type that will be linked to the category.</span></span>

## <a name="link-main-accounts-to-account-category"></a><span data-ttu-id="a86ce-115">Länka huvudkonton till kontokategori</span><span class="sxs-lookup"><span data-stu-id="a86ce-115">Link main accounts to account category</span></span>
1. <span data-ttu-id="a86ce-116">Klicka på **Länka huvudkonton**.</span><span class="sxs-lookup"><span data-stu-id="a86ce-116">Click **Link main accounts**.</span></span>
2. <span data-ttu-id="a86ce-117">I listan väljer du de huvudkonton som ska tilldelas huvudkontokategorin genom att markera kryssrutorna i den **Länkade** kolumnen.</span><span class="sxs-lookup"><span data-stu-id="a86ce-117">In the list, select the main accounts to assign to the main account category by checking the boxes in the **Linked** column.</span></span> <span data-ttu-id="a86ce-118">När du tilldelar huvudkonton till en huvudkontokategori läggs kontosaldona till när kategorin används för ekonomisk rapportering och analys.</span><span class="sxs-lookup"><span data-stu-id="a86ce-118">Assigning main accounts to a main account category will aggregate the balances of the accounts when that category is used for financial reporting and analysis.</span></span>  
3. <span data-ttu-id="a86ce-119">Markera eller avmarkera alternativet **Länkad** för att välja huvudkontona.</span><span class="sxs-lookup"><span data-stu-id="a86ce-119">Select or clear the **Linked** option to choose the main accounts.</span></span>
4. <span data-ttu-id="a86ce-120">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a86ce-120">Select **OK**.</span></span>
5. <span data-ttu-id="a86ce-121">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a86ce-121">Select **Yes**.</span></span>
