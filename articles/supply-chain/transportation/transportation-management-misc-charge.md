---
title: Transporthantering diverse avgifter
description: Det här ämnet förklarar hur transportgenererade avgifter måste associeras med en debiteringskod.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2b703d770c7f9ea684716368cf1e7dbe5fec8710
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "4438138"
---
# <a name="transportation-management-miscellaneous-charges"></a><span data-ttu-id="aea1d-103">Transporthantering diverse avgifter</span><span class="sxs-lookup"><span data-stu-id="aea1d-103">Transportation management miscellaneous charges</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aea1d-104">Som med alla andra avgifter måste transportgenererade avgifter associeras med en debiteringskod.</span><span class="sxs-lookup"><span data-stu-id="aea1d-104">As with all miscellaneous charges, transportation-generated charges must be associated with a charge code.</span></span> <span data-ttu-id="aea1d-105">Annars kommer de inte att läggas till i ordern som en tilläggsavgift.</span><span class="sxs-lookup"><span data-stu-id="aea1d-105">Otherwise, they won't be added back to the order as a miscellaneous charge.</span></span> <span data-ttu-id="aea1d-106">**Avgiftskoden** avgör hur tillägget redovisas i relation till ordern och order raden där den läggs till.</span><span class="sxs-lookup"><span data-stu-id="aea1d-106">The **Charges code** determines how the charge is accounted for in relation to the order and order line where it is added.</span></span>

<span data-ttu-id="aea1d-107">Gå till **Transporthantering > inställningar > klassificering > tillägg** för att definiera de kvalificerings kriterier som avgör när en viss **Avgiftskod** tillämpas på en debitering.</span><span class="sxs-lookup"><span data-stu-id="aea1d-107">Go to **Transportation management > Setup > Rating > Miscellaneous charges** to define the qualifying criteria that determine when a specific **Charges code** is applied to a charge.</span></span>

<span data-ttu-id="aea1d-108">Du bör ha minst en inställning för varje relevant inställning för **Modulen avgifter** (*kund* och *leverantör*) där **Typen övriga avgifter** anges till *ingen*.</span><span class="sxs-lookup"><span data-stu-id="aea1d-108">You should have at least one setup for each relevant **Charges module** setting (*Customer* and *Vendor*) where the **Miscellaneous charge type** is set to *None*.</span></span> <span data-ttu-id="aea1d-109">Om detta saknas kommer tillägget *inte* att läggas till i ordern.</span><span class="sxs-lookup"><span data-stu-id="aea1d-109">If this is missing, the miscellaneous charge will *not* be added to the order.</span></span>
