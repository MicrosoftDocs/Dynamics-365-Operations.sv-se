---
title: Ändra en efterfrågeprognos manuellt
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
ms.openlocfilehash: 5da1d5b1fbd91964e695a704681b1c9ee513a2f1
ms.sourcegitcommit: 4016c223a985c46e33f9941bf91ba5e1583e1cfd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889034"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="401d1-103">Ändra en efterfrågeprognos manuellt</span><span class="sxs-lookup"><span data-stu-id="401d1-103">Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="401d1-104">I den här proceduren visas hur du ändrar prognosen för en artikel.</span><span class="sxs-lookup"><span data-stu-id="401d1-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="401d1-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="401d1-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="401d1-106">Den här proceduren är avsedd för produktionsplaneraren.</span><span class="sxs-lookup"><span data-stu-id="401d1-106">This procedure is intended for the production planner.</span></span>

## <a name="modify-the-forecast-for-a-selected-item"></a><span data-ttu-id="401d1-107">Ändra en prognosen för en vald artikel</span><span class="sxs-lookup"><span data-stu-id="401d1-107">Modify the forecast for a selected item</span></span>

<span data-ttu-id="401d1-108">För att ändra prognosen för en vald artikel:</span><span class="sxs-lookup"><span data-stu-id="401d1-108">To modify the forecast for a selected item:</span></span>

1. <span data-ttu-id="401d1-109">Gå till **Moduler \> Hantering av produktinformation \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="401d1-109">Go to **Modules \> Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="401d1-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="401d1-110">In the list, find and select the desired record.</span></span> <span data-ttu-id="401d1-111">Välj den artikel om du vill ändra prognosen för.</span><span class="sxs-lookup"><span data-stu-id="401d1-111">Select the item for which you want to modify the forecast.</span></span>
1. <span data-ttu-id="401d1-112">I åtgärdsfönstret öppnar du fliken **Plan** och väljer **Efterfrågeprognos**.</span><span class="sxs-lookup"><span data-stu-id="401d1-112">On the Action Pane, open the **Plan** tab and select **Demand forecast**.</span></span>
1. <span data-ttu-id="401d1-113">Välj en rad i listan.</span><span class="sxs-lookup"><span data-stu-id="401d1-113">In the list, select a row.</span></span> <span data-ttu-id="401d1-114">Om det inte finns några prognosrader skapar du en ny rad genom att välja **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="401d1-114">If there are no forecast lines, create a new line by selecting **New** on the Action Pane.</span></span>  
1. <span data-ttu-id="401d1-115">I fältet **Försäljningskvantitet** anger du ett positivt värde.</span><span class="sxs-lookup"><span data-stu-id="401d1-115">In the **Sales quantity** field, enter a positive number.</span></span> <span data-ttu-id="401d1-116">Det här numret representerar den prognosticerade kvantiteten för artikeln.</span><span class="sxs-lookup"><span data-stu-id="401d1-116">This number represents the forecasted quantity for the item.</span></span> <span data-ttu-id="401d1-117">Ett fel visas om du anger ett negativt tal.</span><span class="sxs-lookup"><span data-stu-id="401d1-117">An error will be shown if you enter a negative number.</span></span>
1. <span data-ttu-id="401d1-118">Fyll i övriga fält efter behov.</span><span class="sxs-lookup"><span data-stu-id="401d1-118">Fill out the other fields as needed.</span></span>
1. <span data-ttu-id="401d1-119">Välj **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="401d1-119">Select **Save** on the Action Pane.</span></span>

## <a name="modify-the-forecast-for-one-or-more-items-microsoft-excel"></a><span data-ttu-id="401d1-120">Ändra prognosen för en eller flera artiklar i Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="401d1-120">Modify the forecast for one or more items Microsoft Excel</span></span>

<span data-ttu-id="401d1-121">För att ändra prognosen för en eller flera artiklar i Microsoft Excel:</span><span class="sxs-lookup"><span data-stu-id="401d1-121">To modify the forecast for one or more items Microsoft Excel:</span></span>

1. <span data-ttu-id="401d1-122">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="401d1-122">Do one of the following:</span></span>
    - <span data-ttu-id="401d1-123">Öppna sidan **Efterfrågeprognos** för valfri artikel (det spelar ingen roll vilken) som beskrivs i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="401d1-123">Open the **Demand forecast** page for any item (it doesn't matter which one) as described in the previous section.</span></span>
    - <span data-ttu-id="401d1-124">Gå till **Huvudplanering \> Prognosticering \> Manuell prognosangivelse \> Rader för efterfrågeprognos**.</span><span class="sxs-lookup"><span data-stu-id="401d1-124">Go to **Master planning \> Forecasting \> Manual forecast entry \> Demand forecast lines**.</span></span>
1. <span data-ttu-id="401d1-125">I åtgärdsfönstret väljer du **Öppna i Microsoft Office \> Poster för efterfrågeprognos**.</span><span class="sxs-lookup"><span data-stu-id="401d1-125">On the Action Pane, select **Open in Microsoft Office \> Demand forecast entries**.</span></span>
1. <span data-ttu-id="401d1-126">Välj en hämtningsplats, spara och öppna sedan den hämtade filen i Excel.</span><span class="sxs-lookup"><span data-stu-id="401d1-126">Select a download location, save, and then open the downloaded file in Excel.</span></span>
1. <span data-ttu-id="401d1-127">Om en varning visas väljer du **Aktivera redigering**.</span><span class="sxs-lookup"><span data-stu-id="401d1-127">If you see a warning, choose to **Enable editing**.</span></span>
1. <span data-ttu-id="401d1-128">Logga in i Supply Chain Management med hjälp av Microsoft Dynamics-åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="401d1-128">In Excel, sign in to Supply Chain Management using the Microsoft Dynamics task pane.</span></span> <span data-ttu-id="401d1-129">Du måste logga in med alternativet **Håll mig inloggad** aktiverat, och du måste lita på programmet för dataanslutning.</span><span class="sxs-lookup"><span data-stu-id="401d1-129">You must sign in with the **Keep me signed in** option enabled and you must trust the data connection app.</span></span>
1. <span data-ttu-id="401d1-130">I Excel-kalkylbladet visas nu alla aktuella rader i efterfrågeprognosen för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="401d1-130">The Excel spreadsheet now shows all the current demand forecast lines for your company.</span></span>  <span data-ttu-id="401d1-131">Lägg till, ta bort och redigera efterfrågeprognosrader efter behov.</span><span class="sxs-lookup"><span data-stu-id="401d1-131">Add, delete, and edit demand forecast lines as needed.</span></span>
1. <span data-ttu-id="401d1-132">Välj **Publicera** i Microsoft Dynamics-åtgärdsfönstret om du vill föra över ändringarna tillbaka till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="401d1-132">Select **Publish** on the Microsoft Dynamics task pane to upload your changes back to Supply Chain Management.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
