---
title: Felsök försäljningsorder
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med försäljningsorder.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6e51723915892f465ce09d09ee9ed622bab9451e
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889467"
---
# <a name="troubleshoot-sales-orders"></a><span data-ttu-id="c72a1-103">Felsök försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="c72a1-103">Troubleshoot sales orders</span></span>

<span data-ttu-id="c72a1-104">I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c72a1-104">This topic describes how to fix issues that you might encounter while you work with sales orders.</span></span>

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a><span data-ttu-id="c72a1-105">Skatteinformationen uppdateras inte om jag ändrar en plats i en försäljningsorderrubrik.</span><span class="sxs-lookup"><span data-stu-id="c72a1-105">The tax information isn't updated if I change the location on a sales order header.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c72a1-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="c72a1-106">Issue description</span></span>

<span data-ttu-id="c72a1-107">Om webbplatsen, lagerstället eller leveransadressen ändras antingen i ett försäljningsorderrubrik eller på radnivå uppdateras inte fall skatteinformationen för raderna automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c72a1-107">If the site, warehouse, or delivery address is changed either on a sales order header or at the line level, the case tax information isn't automatically updated for the lines.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c72a1-108">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="c72a1-108">Issue resolution</span></span>

<span data-ttu-id="c72a1-109">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="c72a1-109">This behavior is by design.</span></span> <span data-ttu-id="c72a1-110">Problemet beror på att leveransadressen, webbplatsen och lagerstället inte ändras automatiskt på radnivå.</span><span class="sxs-lookup"><span data-stu-id="c72a1-110">The issue occurs because the delivery address, site, and warehouse aren't automatically changed at the line level either.</span></span> <span data-ttu-id="c72a1-111">Du måste uppdatera dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="c72a1-111">You must update them manually.</span></span>

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a><span data-ttu-id="c72a1-112">Om det finns två handelsavtal för samma period eller överlappande perioder väljs alltid samma avtalsrad.</span><span class="sxs-lookup"><span data-stu-id="c72a1-112">If there are two trade agreements for the same period or overlapping periods, the same agreement line is always selected.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c72a1-113">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="c72a1-113">Issue description</span></span>

<span data-ttu-id="c72a1-114">Om två handelsavtal har definierats för samma period eller överlappande perioder verkar samma handelsavtal väljas varje gång du skapar försäljningsorderrader som innehåller dessa artiklar.</span><span class="sxs-lookup"><span data-stu-id="c72a1-114">If two trade agreements are defined for the same period or overlapping periods, the same trade agreement seems to be selected every time when you create sales order lines that contain those items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c72a1-115">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="c72a1-115">Issue resolution</span></span>

<span data-ttu-id="c72a1-116">Om det finns fler än ett handelsavtal för ett givet datum väljs alltid handelsavtalet med det lägsta priset.</span><span class="sxs-lookup"><span data-stu-id="c72a1-116">If there is more than one trade agreement for a given date, the trade agreement that has the lowest price is always selected.</span></span> <span data-ttu-id="c72a1-117">Om du vill ha mer information hämtar du följande faktablad: [handelsavtal i Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span><span class="sxs-lookup"><span data-stu-id="c72a1-117">For more information, download the following white paper: [Trade agreements in Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span></span>

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a><span data-ttu-id="c72a1-118">Kan jag koppla en inköpsorder till en försäljningsorder för att tillfredsställa efterfrågan?</span><span class="sxs-lookup"><span data-stu-id="c72a1-118">Can I link a purchase order to a sales order to fulfill demand?</span></span>

<span data-ttu-id="c72a1-119">Du kan skapa en inköpsorder från en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c72a1-119">You can create a purchase order from a sales order.</span></span> <span data-ttu-id="c72a1-120">För mer information, se [Skapa en inköpsorder från en försäljningsorder](tasks/create-purchase-order-sales-order.md).</span><span class="sxs-lookup"><span data-stu-id="c72a1-120">For more information, see [Create a purchase order from a sales order](tasks/create-purchase-order-sales-order.md).</span></span>

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a><span data-ttu-id="c72a1-121">Jag kan inte avbryta eller ta bort en returorder eller en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c72a1-121">I can't cancel or delete a return order or a sales order.</span></span>

<span data-ttu-id="c72a1-122">Du kan endast annullera försäljningsorder och returorder som har statusen *skapad*.</span><span class="sxs-lookup"><span data-stu-id="c72a1-122">You can cancel only sales orders and return orders that are in a *Created* state.</span></span> <span data-ttu-id="c72a1-123">Mer information finns i [Avbryt returorder](../service-management/cancel-return-order.md).</span><span class="sxs-lookup"><span data-stu-id="c72a1-123">For more information, see [Cancel a return order](../service-management/cancel-return-order.md).</span></span>

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a><span data-ttu-id="c72a1-124">När jag försöker annullera en försäljningsorder får jag felet "reservationer kan inte tas bort eftersom det finns ett arbete skapat som använder reservationerna".</span><span class="sxs-lookup"><span data-stu-id="c72a1-124">When I try to cancel a sales order, I receive a "Reservations cannot be removed because there is work created which relies on the reservations" error.</span></span>

<span data-ttu-id="c72a1-125">Om arbete associeras med en försäljningsorder kan du inte annullera försäljningsordern förrän arbetet har annullerats och återförts.</span><span class="sxs-lookup"><span data-stu-id="c72a1-125">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="c72a1-126">Detta krav gäller även om det arbete som är kopplat till försäljningsordern stängs.</span><span class="sxs-lookup"><span data-stu-id="c72a1-126">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

<span data-ttu-id="c72a1-127">Gör så här om du vill åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="c72a1-127">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="c72a1-128">Avbryt arbetet och sätt tillbaka lagret på önskad plats.</span><span class="sxs-lookup"><span data-stu-id="c72a1-128">Cancel the work, and put inventory back into the desired location.</span></span> <span data-ttu-id="c72a1-129">Gå till relevant inläsning av försäljningsordern och välj antingen **minska plockad kvantitet** på lastraden eller **återför arbete** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c72a1-129">Go to the relevant load of the sales order, and select either **Reduce picked quantity** on the load line or **Reverse work** on the Action Pane.</span></span>

    <span data-ttu-id="c72a1-130">Arbetet har nu statusen *Annullerat* och nytt lagerrörelsearbete skapas och bearbetas automatiskt för att placera lagret på den plats som beskrivs vid tidpunkten för återföringen.</span><span class="sxs-lookup"><span data-stu-id="c72a1-130">The work now has a status of *Canceled*, and new inventory movement work is automatically created and processed to put inventory back into the location that was described at the time of reversal.</span></span>

2. <span data-ttu-id="c72a1-131">Ta bort lasten.</span><span class="sxs-lookup"><span data-stu-id="c72a1-131">Delete the load.</span></span> <span data-ttu-id="c72a1-132">Även leveransen tas bort.</span><span class="sxs-lookup"><span data-stu-id="c72a1-132">The shipment is also deleted.</span></span>
3. <span data-ttu-id="c72a1-133">Du bör nu kunna gå till försäljningsordern och annullera den.</span><span class="sxs-lookup"><span data-stu-id="c72a1-133">You should now be able to go to the sales order and cancel it.</span></span>

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a><span data-ttu-id="c72a1-134">Jag kan inte annullera en koncernintern inköpsorder som är kopplad till en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c72a1-134">I can't cancel an intercompany purchase order that is linked to a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c72a1-135">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="c72a1-135">Issue description</span></span>

<span data-ttu-id="c72a1-136">Om du försöker avbryta en koncernintern inköpsorder som är kopplad till en försäljningsorder, kan det hända att följande felmeddelande visas: "kvantiteten kan inte minskas eftersom återstående uppdateringsantal ändrar tecken."</span><span class="sxs-lookup"><span data-stu-id="c72a1-136">If you try to cancel an intercompany purchase order that is linked to a sales order, you might receive the following error message: "Quantity cannot be reduced because the remaining update quantity changes sign."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c72a1-137">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="c72a1-137">Issue resolution</span></span>

<span data-ttu-id="c72a1-138">Det här problemet har åtgärdats i Microsoft Dynamics 365 Supply Chain Management version 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="c72a1-138">This issue was fixed in Microsoft Dynamics 365 Supply Chain Management version 10.0.13.</span></span> <span data-ttu-id="c72a1-139">I den versionen och senare versioner kan du nu avbryta en koncernintern inköpsorder som är kopplad till en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c72a1-139">In that version and later versions, you can now cancel an intercompany purchase order that is linked to a sales order.</span></span>

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a><span data-ttu-id="c72a1-140">Kan jag återställa en fakturerad försäljningsorder som har tagits bort?</span><span class="sxs-lookup"><span data-stu-id="c72a1-140">Can I restore an invoiced sales order that was deleted?</span></span>

### <a name="issue-description"></a><span data-ttu-id="c72a1-141">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="c72a1-141">Issue description</span></span>

<span data-ttu-id="c72a1-142">En fakturerad försäljningsorder har tagits bort av misstag och du vill återställa den eller visa information om den.</span><span class="sxs-lookup"><span data-stu-id="c72a1-142">An invoiced sales order was deleted by mistake, and you want to restore it or view its details.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c72a1-143">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="c72a1-143">Issue resolution</span></span>

<span data-ttu-id="c72a1-144">Om den borttagna försäljningsordern redan har fakturerats går du till **kundkonto \> transaktioner \> originaldokument \> visningsinformation**.</span><span class="sxs-lookup"><span data-stu-id="c72a1-144">If the deleted sales order has already been invoiced, go to **Customer account \> Transactions \> Original document \> View details**.</span></span> <span data-ttu-id="c72a1-145">Hitta den faktura du söker och markera den om du vill visa information om den.</span><span class="sxs-lookup"><span data-stu-id="c72a1-145">Find the invoice that you're looking for, and select it to view its details.</span></span> <span data-ttu-id="c72a1-146">Informationen omfattar försäljningsorder referensen.</span><span class="sxs-lookup"><span data-stu-id="c72a1-146">These details include the sales order reference.</span></span> <span data-ttu-id="c72a1-147">Du bör också kunna komma åt försäljningsorder information från den sidan.</span><span class="sxs-lookup"><span data-stu-id="c72a1-147">You should also be able to access the sales order details from that page.</span></span>

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a><span data-ttu-id="c72a1-148">Det går inte att hitta en deadline för en försäljningsorderrubrik i dataentiteten SalesOrderHeaderV2Entity.</span><span class="sxs-lookup"><span data-stu-id="c72a1-148">The deadline of a sales order header can't be found in the SalesOrderHeaderV2Entity data entity.</span></span>

<span data-ttu-id="c72a1-149">Fältet för tidsgräns finns inte i entiteten *SalesOrderHeaderV2Entity*.</span><span class="sxs-lookup"><span data-stu-id="c72a1-149">The deadline field doesn't exist on the *SalesOrderHeaderV2Entity* entity.</span></span>

## <a name="i-must-delete-orphaned-sales-order-records"></a><span data-ttu-id="c72a1-150">Jag måste ta bort överblivna försäljningsorderposter.</span><span class="sxs-lookup"><span data-stu-id="c72a1-150">I must delete orphaned sales order records.</span></span>

<span data-ttu-id="c72a1-151">Om du vill rensa överblivna försäljningsorder poster kör du det *periodiska jobbet för borttagning av försäljningsorder* genom att gå till någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="c72a1-151">To clean up orphaned sales order records, run the *Sales order deletion* periodic job by going to either of the following places:</span></span>

- <span data-ttu-id="c72a1-152">Försäljning och marknadsföring \> Periodiska uppgifter \> Rensa \> Ta bort försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="c72a1-152">Sales and marketing \> Periodic tasks \> Clean up \> Delete sales orders</span></span>
- <span data-ttu-id="c72a1-153">Butik och handel \> Butik och handels-IT \> Rensa \> Ta bort försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="c72a1-153">Retail and commerce \> Retail and commerce IT \> Clean up \> Delete sales orders</span></span>

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a><span data-ttu-id="c72a1-154">Finns det något sätt att beräkna provisioner på fakturor som redan har bokförts?</span><span class="sxs-lookup"><span data-stu-id="c72a1-154">Is there a way to calculate commissions on invoices that have already been posted?</span></span>

<span data-ttu-id="c72a1-155">Supply Chain Management stöder för närvarande inte beräkningen av provisioner för bokförda fakturor.</span><span class="sxs-lookup"><span data-stu-id="c72a1-155">Supply Chain Management doesn't currently support the calculation of commissions for posted invoices.</span></span>

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a><span data-ttu-id="c72a1-156">En buntad artikel stöds inte i en koncernintern process.</span><span class="sxs-lookup"><span data-stu-id="c72a1-156">A bundle item isn't supported in an intercompany process.</span></span>

<span data-ttu-id="c72a1-157">Buntad artikel är inte tillgänglig för inköpsordern eftersom du, om du granskar försäljningsorderraderna för buntad artikel ser du att kvantiteten är *0* (noll) och statusvärdet *annullerad*.</span><span class="sxs-lookup"><span data-stu-id="c72a1-157">The bundle item isn't available for the purchase order because, if you examine the sales order lines for the bundle item, you will notice that the quantity is *0* (zero) and the status is *Cancelled*.</span></span> <span data-ttu-id="c72a1-158">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="c72a1-158">This behavior is by design.</span></span> <span data-ttu-id="c72a1-159">Försäljningsordern köper endast komponenterna i buntad artikel.</span><span class="sxs-lookup"><span data-stu-id="c72a1-159">The sales order buys only the components of the bundle item.</span></span> <span data-ttu-id="c72a1-160">Den handlar inte om själva buntade artikeln.</span><span class="sxs-lookup"><span data-stu-id="c72a1-160">It doesn't buy the bundle item itself.</span></span>

<span data-ttu-id="c72a1-161">Om du måste köpa en buntad bör du fundera över om du måste markera det som buntad artikel, eftersom denna funktion verkligen är utformad för scenarier för intäktsredovisning.</span><span class="sxs-lookup"><span data-stu-id="c72a1-161">If you must buy a bundle, consider whether you have to mark it as bundle item, because this functionality is actually designed for revenue recognition scenarios.</span></span> <span data-ttu-id="c72a1-162">Mer information om buntad artikel, se [buntade](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span><span class="sxs-lookup"><span data-stu-id="c72a1-162">For more information about bundle items, see [Bundles](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span></span>
