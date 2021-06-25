---
title: 'Guide: Ändra en efterfrågeprognos manuellt'
description: Detta ämne beskriver hur du ändrar prognosen för en artikel
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e12ccf90b9971379e8931bd48d6243a855bb795
ms.sourcegitcommit: 15aacd0e109b05c7281407b5bba4e6cd99116c28
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "6224020"
---
# <a name="guide-modify-a-demand-forecast-manually"></a><span data-ttu-id="69a15-103">Guide: Ändra en efterfrågeprognos manuellt</span><span class="sxs-lookup"><span data-stu-id="69a15-103">Guide: Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="69a15-104">I den här proceduren visas hur du ändrar prognosen för en artikel.</span><span class="sxs-lookup"><span data-stu-id="69a15-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="69a15-105">Den här proceduren är avsedd för produktionsplaneraren.</span><span class="sxs-lookup"><span data-stu-id="69a15-105">This procedure is intended for the production planner.</span></span>

## <a name="modify-the-forecast-for-a-selected-item"></a><span data-ttu-id="69a15-106">Ändra en prognosen för en vald artikel</span><span class="sxs-lookup"><span data-stu-id="69a15-106">Modify the forecast for a selected item</span></span>

<span data-ttu-id="69a15-107">För att ändra prognosen för en vald artikel:</span><span class="sxs-lookup"><span data-stu-id="69a15-107">To modify the forecast for a selected item:</span></span>

1. <span data-ttu-id="69a15-108">Gå till **Moduler \> Hantering av produktinformation \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="69a15-108">Go to **Modules \> Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="69a15-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="69a15-109">In the list, find and select the desired record.</span></span> <span data-ttu-id="69a15-110">Välj den artikel om du vill ändra prognosen för.</span><span class="sxs-lookup"><span data-stu-id="69a15-110">Select the item for which you want to modify the forecast.</span></span>
1. <span data-ttu-id="69a15-111">I åtgärdsfönstret öppnar du fliken **Plan** och väljer **Efterfrågeprognos**.</span><span class="sxs-lookup"><span data-stu-id="69a15-111">On the Action Pane, open the **Plan** tab and select **Demand forecast**.</span></span>
1. <span data-ttu-id="69a15-112">Välj en rad i listan.</span><span class="sxs-lookup"><span data-stu-id="69a15-112">In the list, select a row.</span></span> <span data-ttu-id="69a15-113">Om det inte finns några prognosrader skapar du en ny rad genom att välja **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="69a15-113">If there are no forecast lines, create a new line by selecting **New** on the Action Pane.</span></span>  
1. <span data-ttu-id="69a15-114">I fältet **Försäljningskvantitet** anger du ett positivt värde.</span><span class="sxs-lookup"><span data-stu-id="69a15-114">In the **Sales quantity** field, enter a positive number.</span></span> <span data-ttu-id="69a15-115">Det här numret representerar den prognosticerade kvantiteten för artikeln.</span><span class="sxs-lookup"><span data-stu-id="69a15-115">This number represents the forecasted quantity for the item.</span></span> <span data-ttu-id="69a15-116">Ett fel visas om du anger ett negativt tal.</span><span class="sxs-lookup"><span data-stu-id="69a15-116">An error will be shown if you enter a negative number.</span></span>
1. <span data-ttu-id="69a15-117">Fyll i övriga fält efter behov.</span><span class="sxs-lookup"><span data-stu-id="69a15-117">Fill out the other fields as needed.</span></span>
1. <span data-ttu-id="69a15-118">Välj **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="69a15-118">Select **Save** on the Action Pane.</span></span>

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a><span data-ttu-id="69a15-119">Ändra prognosen för en eller flera artiklar med Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="69a15-119">Modify the forecast for one or more items with Microsoft Excel</span></span>

<span data-ttu-id="69a15-120">För att ändra prognosen för en eller flera artiklar med Microsoft Excel:</span><span class="sxs-lookup"><span data-stu-id="69a15-120">To modify the forecast for one or more items with Microsoft Excel:</span></span>

1. <span data-ttu-id="69a15-121">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="69a15-121">Do one of the following:</span></span>
    - <span data-ttu-id="69a15-122">Öppna sidan **Efterfrågeprognos** för valfri artikel (det spelar ingen roll vilken) som beskrivs i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="69a15-122">Open the **Demand forecast** page for any item (it doesn't matter which one) as described in the previous section.</span></span>
    - <span data-ttu-id="69a15-123">Gå till **Huvudplanering \> Prognosticering \> Manuell prognosangivelse \> Rader för efterfrågeprognos**.</span><span class="sxs-lookup"><span data-stu-id="69a15-123">Go to **Master planning \> Forecasting \> Manual forecast entry \> Demand forecast lines**.</span></span>
1. <span data-ttu-id="69a15-124">I åtgärdsfönstret väljer du **Öppna i Microsoft Office \> Poster för efterfrågeprognos**.</span><span class="sxs-lookup"><span data-stu-id="69a15-124">On the Action Pane, select **Open in Microsoft Office \> Demand forecast entries**.</span></span>
1. <span data-ttu-id="69a15-125">Välj en hämtningsplats, spara och öppna sedan den hämtade filen i Excel.</span><span class="sxs-lookup"><span data-stu-id="69a15-125">Select a download location, save, and then open the downloaded file in Excel.</span></span>
1. <span data-ttu-id="69a15-126">Om en varning visas väljer du **Aktivera redigering**.</span><span class="sxs-lookup"><span data-stu-id="69a15-126">If you see a warning, choose to **Enable editing**.</span></span>
1. <span data-ttu-id="69a15-127">Logga in i Supply Chain Management med hjälp av Microsoft Dynamics-åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="69a15-127">In Excel, sign in to Supply Chain Management using the Microsoft Dynamics task pane.</span></span> <span data-ttu-id="69a15-128">Du måste logga in med alternativet **Håll mig inloggad** aktiverat, och du måste lita på programmet för dataanslutning.</span><span class="sxs-lookup"><span data-stu-id="69a15-128">You must sign in with the **Keep me signed in** option enabled and you must trust the data connection app.</span></span>
1. <span data-ttu-id="69a15-129">I Excel-kalkylbladet visas nu alla aktuella rader i efterfrågeprognosen för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="69a15-129">The Excel spreadsheet now shows all the current demand forecast lines for your company.</span></span>  <span data-ttu-id="69a15-130">Lägg till, ta bort och redigera efterfrågeprognosrader efter behov.</span><span class="sxs-lookup"><span data-stu-id="69a15-130">Add, delete, and edit demand forecast lines as needed.</span></span>
1. <span data-ttu-id="69a15-131">Välj **Publicera** i Microsoft Dynamics-åtgärdsfönstret om du vill föra över ändringarna tillbaka till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="69a15-131">Select **Publish** on the Microsoft Dynamics task pane to upload your changes back to Supply Chain Management.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
