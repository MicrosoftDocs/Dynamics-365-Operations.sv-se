---
title: En artikel kan inte ha en strukturlista eller en formel
description: När du försöker bekräfta en order visas ett felmeddelande under artikelvalidering. Den visar att artikeln inte kan ha någon strukturlista eller en formel.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294182"
---
# <a name="item-cant-have-a-bom-or-formula"></a><span data-ttu-id="0a363-104">En artikel kan inte ha en strukturlista eller en formel</span><span class="sxs-lookup"><span data-stu-id="0a363-104">Item can't have a BOM or formula</span></span>

<span data-ttu-id="0a363-105">Felkod: PRO2614</span><span class="sxs-lookup"><span data-stu-id="0a363-105">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="0a363-106">Symtom</span><span class="sxs-lookup"><span data-stu-id="0a363-106">Symptoms</span></span>

<span data-ttu-id="0a363-107">När du försöker bekräfta en order visas ett felmeddelande under artikelvalidering:</span><span class="sxs-lookup"><span data-stu-id="0a363-107">When you try to firm an order, you receive the following error message during item validation:</span></span>

> <span data-ttu-id="0a363-108">Ingen strukturlista eller formel kan användas för artikeln</span><span class="sxs-lookup"><span data-stu-id="0a363-108">Item cannot have a BOM or formula</span></span>

## <a name="resolution"></a><span data-ttu-id="0a363-109">Lösning</span><span class="sxs-lookup"><span data-stu-id="0a363-109">Resolution</span></span>

<span data-ttu-id="0a363-110">Artiklar som har en strukturlista eller en formel måste vara av typen *Planeringsartikel*, *Strukturlista* eller *Formel*.</span><span class="sxs-lookup"><span data-stu-id="0a363-110">Items that have a bill of materials (BOM) or formula must be of the *Planning item*, *BOM*, or *formula* type.</span></span> <span data-ttu-id="0a363-111">Följ dessa steg för att ändra typen av ett objekt.</span><span class="sxs-lookup"><span data-stu-id="0a363-111">To change the type of an item, follow these steps.</span></span>

1. <span data-ttu-id="0a363-112">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="0a363-112">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="0a363-113">Öppna relevanta produkt.</span><span class="sxs-lookup"><span data-stu-id="0a363-113">Open the relevant product.</span></span>
1. <span data-ttu-id="0a363-114">På snabbfliken **Konstruera** ange fältet **Produktionstyp** till *Planera artikel*, *strukturlista* eller *formel*.</span><span class="sxs-lookup"><span data-stu-id="0a363-114">On the **Engineer** FastTab, set the **Production type** field to *Planning item*, *BOM*, or *formula*.</span></span>
