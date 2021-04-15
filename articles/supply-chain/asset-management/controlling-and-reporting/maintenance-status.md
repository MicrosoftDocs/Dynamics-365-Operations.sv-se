---
title: Underhållsstatus
description: I det här avsnittet beskrivs hur du beräknar underhållsstatus i Tillgångshantering.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetStatusCalculate, EntAssetStatus
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f3d6f86c5052c845c9c8aad1e4437f4196f78b50
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808626"
---
# <a name="maintenance-status"></a><span data-ttu-id="3f848-103">Underhållsstatus</span><span class="sxs-lookup"><span data-stu-id="3f848-103">Maintenance status</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="3f848-104">I Tillgångshantering kan du göra en översiktsberäkning för en viss period för nya, aktiva och slutförda underhållsbegäranden, arbetsorder och underhållsstopp.</span><span class="sxs-lookup"><span data-stu-id="3f848-104">In Asset Management, you can make an overview calculation for a specific period for new, active, and completed maintenance requests, work orders, and maintenance downtime activities.</span></span> <span data-ttu-id="3f848-105">Du kan också se antalet slutförda tillståndsbedömningar för samma period.</span><span class="sxs-lookup"><span data-stu-id="3f848-105">You can also see the number of completed condition assessments for the same period.</span></span> <span data-ttu-id="3f848-106">Använd beräkningen för att få en översikt över arbetsbelastningen för inkommande och slutförda underhållsbegäranden och arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="3f848-106">Use this calculation to get an overview of workload for incoming and completed maintenance requests and work orders.</span></span>

## <a name="make-a-maintenance-status-calculation"></a><span data-ttu-id="3f848-107">Göra en beräkning av underhållsstatus</span><span class="sxs-lookup"><span data-stu-id="3f848-107">Make a maintenance status calculation</span></span>

1. <span data-ttu-id="3f848-108">Klicka på **Tillgångshantering** > **Förfrågningar** > **Underhållsstatus**.</span><span class="sxs-lookup"><span data-stu-id="3f848-108">Click **Asset management** > **Inquiries** > **Maintenance status**.</span></span>

2. <span data-ttu-id="3f848-109">I dialogrutan **Beräkna status**, välj det tidsintervall för vilket du vill utföra beräkningen i fälten **Från datum** och **Till datum**.</span><span class="sxs-lookup"><span data-stu-id="3f848-109">In the **Calculate status** dialog, select the time range that you want to make the calculation in the **From date** and **To date** fields.</span></span>

3. <span data-ttu-id="3f848-110">Du kan använda fältet **Nivå** för att indikera hur detaljerade underhållsraderna ska vara gällande funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="3f848-110">You can use the **Level** field to indicate how detailed you want the maintenance lines to be regarding functional locations.</span></span> 

  <span data-ttu-id="3f848-111">Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsrader för en funktionsplats på den översta nivån, och därmed kan också den status som finns på en rad läggas till från funktionsplatser på en lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="3f848-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance lines for a functional location will be shown on the top level, and therefore the status on a line may be added up from functional locations located at a lower level.</span></span> 
  
  <span data-ttu-id="3f848-112">Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsrader på alla de funktionsplatsnivåer som de är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="3f848-112">If you insert the number "0" in the **Level** field, you see a detailed result showing all maintenance lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="3f848-113">Klicka på **OK** för att starta beräkningen.</span><span class="sxs-lookup"><span data-stu-id="3f848-113">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="3f848-114">Klicka på knapparna **Gruppera efter...** för att visa den obligatoriska detaljnivån för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="3f848-114">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="3f848-115">De valda knapparna **Gruppera efter** markeras.</span><span class="sxs-lookup"><span data-stu-id="3f848-115">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="3f848-116">Klicka på en knapp för att aktivera och inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="3f848-116">Click on a button to activate or deactivate it.</span></span>

6. <span data-ttu-id="3f848-117">Kom ihåg att klicka på knapparna **Uppdatera** om du vill uppdatera beräkningen varje gång du gör ändringar genom att aktivera eller inaktiverar knapparna **Gruppera efter** eller genom att göra en beräkning för en ny period.</span><span class="sxs-lookup"><span data-stu-id="3f848-117">Remember to click the **Update** button to update the calculation each time you make changes by activating or deactivating **Group by** buttons, or by making a calculation for a new period.</span></span>

7. <span data-ttu-id="3f848-118">Klicka på **Status** om du vill skapa en ny underhållsstatusberäkning.</span><span class="sxs-lookup"><span data-stu-id="3f848-118">Click **Status** if you want to create a new maintenance status calculation.</span></span>

>[!NOTE]
><span data-ttu-id="3f848-119">Resultaten som visas i **Underhållsstatus** omfattar bara underhållsbegäranden och arbetsorder som har ett faktiskt startdatum och en faktisk starttid.</span><span class="sxs-lookup"><span data-stu-id="3f848-119">The results shown in **Maintenance status** only include maintenance requests and work orders that have an actual start date and time.</span></span> <span data-ttu-id="3f848-120">Slutdatum och sluttid kan vara tomma.</span><span class="sxs-lookup"><span data-stu-id="3f848-120">End date and time may be blank.</span></span>

## <a name="example-1"></a><span data-ttu-id="3f848-121">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="3f848-121">Example 1</span></span>

<span data-ttu-id="3f848-122">I bildskärmen nedan har knapparna **År** och **Månad** aktiverats.</span><span class="sxs-lookup"><span data-stu-id="3f848-122">In the screenshot below, the **Year** and **Month** buttons have been activated.</span></span> <span data-ttu-id="3f848-123">Med dessa val för **Gruppera efter** markerade får du en allmän översikt på basis av månadsvis arbetsbelastning och genomflöde som är relaterat till underhållsbegäranden och arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="3f848-123">With these **Group by** options selected, you get a general overview on a monthly basis of workload and throughput related to maintenance requests and work orders.</span></span> 

![Exempel på månatlig arbetsbelastning](media/13-controlling-and-reporting.png)

## <a name="example-2"></a><span data-ttu-id="3f848-125">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="3f848-125">Example 2</span></span>

<span data-ttu-id="3f848-126">I bildskärmen nedan har information om funktionsplatser lagts till.</span><span class="sxs-lookup"><span data-stu-id="3f848-126">In the screenshot below, information about functional locations has been added.</span></span> <span data-ttu-id="3f848-127">Nu är det möjligt att jämföra arbetsbelastning och genomflöde på funktionsplatser, vilket kan representera geografiska platser, fabriker eller arbetsområden.</span><span class="sxs-lookup"><span data-stu-id="3f848-127">Now it is possible to compare workload and throughput across functional locations, which may represent geographical locations, factories, or work areas.</span></span> 

![Exempel på en månatlig arbetsbörda med funktionella platser](media/14-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]