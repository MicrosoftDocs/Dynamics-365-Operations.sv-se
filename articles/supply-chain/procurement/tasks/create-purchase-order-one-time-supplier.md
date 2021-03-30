---
title: Skapa en inköpsorder för en engångsleverantör
description: Den här proceduren visar hur du skapar en inköpsorder för en engångsleverantör.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1abd942da608bc221a7a66e03b5269fa30e2c20
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212040"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="94363-103">Skapa en inköpsorder för en engångsleverantör</span><span class="sxs-lookup"><span data-stu-id="94363-103">Create a purchase order for a one-time supplier</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="94363-104">Den här proceduren visar hur du skapar en inköpsorder för en engångsleverantör.</span><span class="sxs-lookup"><span data-stu-id="94363-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="94363-105">Leverantören skapas automatiskt med inköpsordern, snarare än att du måste skapa leverantörskontot manuellt.</span><span class="sxs-lookup"><span data-stu-id="94363-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="94363-106">Inköpsorder används vanligtvis av inköpsagenter.</span><span class="sxs-lookup"><span data-stu-id="94363-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="94363-107">De exempel som visas i den här handboken kan användas i demoföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="94363-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="94363-108">Det är en förutsättning att ett konto för engångsleverantör har ställts in på sidan Obetalda parametrar för konto.</span><span class="sxs-lookup"><span data-stu-id="94363-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="94363-109">Skapa en inköpsorder för en engångsleverantör</span><span class="sxs-lookup"><span data-stu-id="94363-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="94363-110">Gå till Anskaffning och källa > Inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="94363-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="94363-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="94363-111">Click New.</span></span>
3. <span data-ttu-id="94363-112">Välj Ja i fältet Engångsleverantör.</span><span class="sxs-lookup"><span data-stu-id="94363-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="94363-113">Ett leverantörskonto skapas automatiskt och tilldelas inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="94363-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="94363-114">Leverantörskontot är baserat på mallen som visas på fliken Allmänt på sidan Parametrar för leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="94363-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="94363-115">Ange ett namn för leverantören i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="94363-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="94363-116">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="94363-116">Click OK.</span></span>
    * <span data-ttu-id="94363-117">Inköpsordern kan nu slutföras och bearbetas som alla andra order.</span><span class="sxs-lookup"><span data-stu-id="94363-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="94363-118">Det finns inga särskilda resursegenskaper som är relaterade till hur detta ska göras.</span><span class="sxs-lookup"><span data-stu-id="94363-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="94363-119">Fakturan tar hänsyn en transaktion som förfaller på leverantörskontot som skapades med ordern och betalningen bearbetas därefter.</span><span class="sxs-lookup"><span data-stu-id="94363-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]