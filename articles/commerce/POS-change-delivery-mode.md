---
title: Ändra Leveranssätt i kassan
description: I det här avsnittet beskrivs hur du konfigurerar och använder ändringsläget för leverans i kassan.
author: hhainesms
manager: annbe
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 26e798c664844b575de6f019ad8f5349ed92be98
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2020
ms.locfileid: "3114414"
---
# <a name="change-mode-of-delivery-in-pos"></a><span data-ttu-id="18c84-103">Ändra Leveranssätt i kassan</span><span class="sxs-lookup"><span data-stu-id="18c84-103">Change mode of delivery in POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="18c84-104">I det här avsnittet beskrivs hur du ställer in och använder funktionen "ändra leveranssätt" i ditt försäljnings- eller kassamiljöläge.</span><span class="sxs-lookup"><span data-stu-id="18c84-104">This topic describes how to set up and use the "change mode of delivery" functionality in your point of sale (POS) environment.</span></span> 

<span data-ttu-id="18c84-105">I Dynamics 365 Commerce versioner 10.0.10 och senare är **Leveransläget** operation (647) tillgängligt för att läggas till i dina layouter för kassaskärmen.</span><span class="sxs-lookup"><span data-stu-id="18c84-105">In Dynamics 365 Commerce versions 10.0.10 and later, the **Change mode of delivery** operation (647) is available to add to your POS screen layouts.</span></span>

<span data-ttu-id="18c84-106">Funktionen ändra leveransläge ger dig möjlighet att ändra leveranssättet för en eller flera försändelse konfigurerade försäljningsrader i kassatransaktionen.</span><span class="sxs-lookup"><span data-stu-id="18c84-106">The change mode of delivery feature provides you with the option to change the mode of delivery for one or more shipment-configured sales lines on the POS transaction.</span></span> <span data-ttu-id="18c84-107">I tidigare versions versioner av Commerce var du tvungen att gå igenom hela konfigurationsflöden **Leverera allt** eller **Leverera utvalda** om du vill ändra leveranssättet på en befintlig rad som har konfigurerats för leverans.</span><span class="sxs-lookup"><span data-stu-id="18c84-107">In previous versions of Commerce, you had to go through the full **Ship all** or **Ship selected** configuration flows if you wanted to change the mode of delivery on an existing line that was configured for shipment.</span></span> <span data-ttu-id="18c84-108">Den här processen tar lång tid och skulle kunna leda till att den ursprungliga leveransdagen eller leveransdatumen ändras av raden.</span><span class="sxs-lookup"><span data-stu-id="18c84-108">This process was time consuming and could result in accidental changes to the delivery origin or delivery dates for the line.</span></span> <span data-ttu-id="18c84-109">Den nya funktionen ger en alternativ metod för att effektivt uppdatera leveranssättet på dessa försäljningsrader.</span><span class="sxs-lookup"><span data-stu-id="18c84-109">The new functionality provides an alternative method for efficiently updating the mode of delivery on these sales lines.</span></span>

<span data-ttu-id="18c84-110">Mer information om hur du lägger till en operation i en knapp på kassaknappens rutnät finns it [Skärmlayouter för kassan](https://docs.microsoft.com/dynamics365/commerce/pos-screen-layouts).</span><span class="sxs-lookup"><span data-stu-id="18c84-110">For more information about how to add an operation to a button on your POS button grid, see [Screen layouts for the point of sale](https://docs.microsoft.com/dynamics365/commerce/pos-screen-layouts).</span></span>

<span data-ttu-id="18c84-111">När den här funktionen har konfigurerats i kassan när du väljer **Ändra leverans** visas en listsida där du kan välja rader för den transaktion som du vill ändra leveranssättet för.</span><span class="sxs-lookup"><span data-stu-id="18c84-111">After this feature is configured in POS, when you select **Change mode of delivery**, you will be presented with a list page that allows you to choose the lines of the transaction that you want to change the mode of delivery for.</span></span> <span data-ttu-id="18c84-112">Du kan välja några eller alla av raderna eller avsluta utan att göra några ändringar.</span><span class="sxs-lookup"><span data-stu-id="18c84-112">You can choose some or all of the lines, or exit without making any changes.</span></span> <span data-ttu-id="18c84-113">De försäljningsrader som tidigare konfigurerades för leverans är de enda raderna i listan som du kan ändra.</span><span class="sxs-lookup"><span data-stu-id="18c84-113">The sales lines that were previously configured for shipment are the only lines in the list that you can change.</span></span> <span data-ttu-id="18c84-114">Om du vill ändra en rad som är avsedd för upphämtning eller utföra leverans, måste du använda operationen **leverera alla** eller **leverera utvalda**.</span><span class="sxs-lookup"><span data-stu-id="18c84-114">If you want to change a line designated for pickup or carryout to ship, you must use the **Ship all** or **Ship selected** operations.</span></span> <span data-ttu-id="18c84-115">Om du vill ändra en rad som angivits som en försändelse till en upphämtning eller utför måste du använda åtgärderna **Avhämta**, **Avhämtning vald**, **Utför alla** eller **Utför valda**.</span><span class="sxs-lookup"><span data-stu-id="18c84-115">Conversely, if you want to change a line designated as a shipment to a pickup or carryout, you must use the  **Pickup all**, **Pickup selected**, **Carryout all**, or **Carryout selected** operations.</span></span>

<span data-ttu-id="18c84-116">När du har valt de rader som du vill ändra klickar du på **Ändra leveranssätt** för att uppmanas att välja alternativ för leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="18c84-116">After you select the lines that you want to change, click **Change mode of delivery** to be prompted to select the delivery mode options.</span></span> <span data-ttu-id="18c84-117">Om du har valt flera rader att ändra, visar kassan endast leveranssätt som har konfigurerats som tillåtna för alla valda produkter.</span><span class="sxs-lookup"><span data-stu-id="18c84-117">If you selected multiple lines to change, POS will only display modes of delivery that have been configured as allowable for all of the selected products.</span></span> <span data-ttu-id="18c84-118">Leveranssätten kan konfigureras till att stödja specifika produkter och leveransadresser.</span><span class="sxs-lookup"><span data-stu-id="18c84-118">Modes of delivery can be configured to support specific products and delivery addresses.</span></span> <span data-ttu-id="18c84-119">Om det finns ett leveranssätt som är acceptabelt för en produkt- och adresskombination, men inte accepteras för någon annan produkt- och adresskombination, är leveranssättet inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="18c84-119">If there is a mode of delivery that is acceptable for one product and address combination but is not acceptable for another selected product and address combination, the mode of delivery is not available.</span></span> <span data-ttu-id="18c84-120">Du kan behöva välja rader en och en och ändra leveranssättet för varje rad separat om du vill välja ett leveranssätt för en produkt som inte stöds av en annan produkt.</span><span class="sxs-lookup"><span data-stu-id="18c84-120">You may need to select lines one by one and change the mode of delivery for each line separately if you want to select a mode of delivery for one product that is not supported by another product.</span></span>  

<span data-ttu-id="18c84-121">När du har valt det nya leveranssättet visas transaktionssidan.</span><span class="sxs-lookup"><span data-stu-id="18c84-121">After you select the new mode of delivery, the transaction page is displayed.</span></span> <span data-ttu-id="18c84-122">Om du vill granska dina nya val för leveranssätt väljer du **leverans** i transaktionslistan.</span><span class="sxs-lookup"><span data-stu-id="18c84-122">To review your new delivery mode selections, select the **Delivery** tab on the transaction list.</span></span>   
