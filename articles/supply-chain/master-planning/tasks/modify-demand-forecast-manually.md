---
title: Ändra en efterfrågeprognos manuellt
description: I den här proceduren visas hur du ändrar prognosen för en artikel.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ca6b881bc094b68d1bbf8c7c20b65418e42b28e3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835890"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="63ee0-103">Ändra en efterfrågeprognos manuellt</span><span class="sxs-lookup"><span data-stu-id="63ee0-103">Modify a demand forecast manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="63ee0-104">I den här proceduren visas hur du ändrar prognosen för en artikel.</span><span class="sxs-lookup"><span data-stu-id="63ee0-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="63ee0-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="63ee0-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="63ee0-106">Registreringen är avsedd för produktionsplaneraren.</span><span class="sxs-lookup"><span data-stu-id="63ee0-106">This recording is intended for the production planner.</span></span> 


## <a name="modify-the-forecast-for-an-item"></a><span data-ttu-id="63ee0-107">Ändra en prognos för en artikel</span><span class="sxs-lookup"><span data-stu-id="63ee0-107">Modify the forecast for an item</span></span>
1. <span data-ttu-id="63ee0-108">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="63ee0-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="63ee0-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="63ee0-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="63ee0-110">Välj den artikel om du vill ändra prognosen för.</span><span class="sxs-lookup"><span data-stu-id="63ee0-110">Select the item for which you want to modify the forecast.</span></span> <span data-ttu-id="63ee0-111">Du kan till exempel välja artikel D0001.</span><span class="sxs-lookup"><span data-stu-id="63ee0-111">For example, you can select item D0001.</span></span>  
3. <span data-ttu-id="63ee0-112">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="63ee0-112">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="63ee0-113">Klicka på Efterfrågeprognos.</span><span class="sxs-lookup"><span data-stu-id="63ee0-113">Click Demand forecast.</span></span>
5. <span data-ttu-id="63ee0-114">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="63ee0-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="63ee0-115">Om det inte finns några rader för inköpsprognoser, skapa en ny rad genom att</span><span class="sxs-lookup"><span data-stu-id="63ee0-115">If there are no forecast lines, create a new line by  .</span></span> <span data-ttu-id="63ee0-116">klicka på Ny i appfältet.</span><span class="sxs-lookup"><span data-stu-id="63ee0-116">clicking New on the app bar.</span></span>  
6. <span data-ttu-id="63ee0-117">Ange ett nummer i fältet Försäljningskvantitet.</span><span class="sxs-lookup"><span data-stu-id="63ee0-117">In the Sales quantity field, enter a number.</span></span>
    * <span data-ttu-id="63ee0-118">Det här numret representerar den prognosticerade kvantiteten för artikeln.</span><span class="sxs-lookup"><span data-stu-id="63ee0-118">This number represents the forecasted quantity for the item.</span></span>  
7. <span data-ttu-id="63ee0-119">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="63ee0-119">Click Save.</span></span>

## <a name="modify-the-forecast-in-excel"></a><span data-ttu-id="63ee0-120">Ändra prognosen i Excel</span><span class="sxs-lookup"><span data-stu-id="63ee0-120">Modify the forecast in Excel</span></span>
1. <span data-ttu-id="63ee0-121">Klicka på Öppna i Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="63ee0-121">Click Open in Microsoft Office.</span></span>
2. <span data-ttu-id="63ee0-122">Klicka på Redigera en efterfrågeprognos i Excel.</span><span class="sxs-lookup"><span data-stu-id="63ee0-122">Click Edit Demand forecast in Excel.</span></span>
    * <span data-ttu-id="63ee0-123">I Excel kan du lägga till, ta bort och redigera efterfrågeprognosrader.</span><span class="sxs-lookup"><span data-stu-id="63ee0-123">In Excel, you can add, delete and edit demand forecast lines.</span></span> <span data-ttu-id="63ee0-124">Om du inte kan se data i Excel måste du logga in i Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition med alternativet "Håll mig inloggad" aktiverat och du måste lita på dataanslutningsappen.</span><span class="sxs-lookup"><span data-stu-id="63ee0-124">If you are not able to see the data in Excel, you need to sign in to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition with the "Keep me signed in" option enabled and you need to trust the data connection app.</span></span>  

