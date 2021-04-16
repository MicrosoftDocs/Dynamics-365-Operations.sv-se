---
title: Transporthantering diverse avgifter
description: Det här ämnet förklarar hur transportgenererade avgifter måste associeras med en debiteringskod.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 53c25f204e98a911e9697f5bb950706555749a55
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828332"
---
# <a name="transportation-management-miscellaneous-charges"></a><span data-ttu-id="28960-103">Transporthantering diverse avgifter</span><span class="sxs-lookup"><span data-stu-id="28960-103">Transportation management miscellaneous charges</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28960-104">Som med alla andra avgifter måste transportgenererade avgifter associeras med en debiteringskod.</span><span class="sxs-lookup"><span data-stu-id="28960-104">As with all miscellaneous charges, transportation-generated charges must be associated with a charge code.</span></span> <span data-ttu-id="28960-105">Annars kommer de inte att läggas till i ordern som en tilläggsavgift.</span><span class="sxs-lookup"><span data-stu-id="28960-105">Otherwise, they won't be added back to the order as a miscellaneous charge.</span></span> <span data-ttu-id="28960-106">**Avgiftskoden** avgör hur tillägget redovisas i relation till ordern och order raden där den läggs till.</span><span class="sxs-lookup"><span data-stu-id="28960-106">The **Charges code** determines how the charge is accounted for in relation to the order and order line where it is added.</span></span>

<span data-ttu-id="28960-107">Gå till **Transporthantering > inställningar > klassificering > tillägg** för att definiera de kvalificerings kriterier som avgör när en viss **Avgiftskod** tillämpas på en debitering.</span><span class="sxs-lookup"><span data-stu-id="28960-107">Go to **Transportation management > Setup > Rating > Miscellaneous charges** to define the qualifying criteria that determine when a specific **Charges code** is applied to a charge.</span></span>

<span data-ttu-id="28960-108">Du bör ha minst en inställning för varje relevant inställning för **Modulen avgifter** (*kund* och *leverantör*) där **Typen övriga avgifter** anges till *ingen*.</span><span class="sxs-lookup"><span data-stu-id="28960-108">You should have at least one setup for each relevant **Charges module** setting (*Customer* and *Vendor*) where the **Miscellaneous charge type** is set to *None*.</span></span> <span data-ttu-id="28960-109">Om detta saknas kommer tillägget *inte* att läggas till i ordern.</span><span class="sxs-lookup"><span data-stu-id="28960-109">If this is missing, the miscellaneous charge will *not* be added to the order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]