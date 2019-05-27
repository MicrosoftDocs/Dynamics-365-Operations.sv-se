---
title: Skapa en inköpsorder för en engångsleverantör
description: Den här proceduren visar hur du skapar en inköpsorder för en engångsleverantör.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: beaf6bcbc870e11e74289375611c631306545633
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547589"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="bd500-103">Skapa en inköpsorder för en engångsleverantör</span><span class="sxs-lookup"><span data-stu-id="bd500-103">Create a purchase order for a one-time supplier</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd500-104">Den här proceduren visar hur du skapar en inköpsorder för en engångsleverantör.</span><span class="sxs-lookup"><span data-stu-id="bd500-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="bd500-105">Leverantören skapas automatiskt med inköpsordern, snarare än att du måste skapa leverantörskontot manuellt.</span><span class="sxs-lookup"><span data-stu-id="bd500-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="bd500-106">Inköpsorder används vanligtvis av inköpsagenter.</span><span class="sxs-lookup"><span data-stu-id="bd500-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="bd500-107">De exempel som visas i den här handboken kan användas i demoföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="bd500-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="bd500-108">Det är en förutsättning att ett konto för engångsleverantör har ställts in på sidan Obetalda parametrar för konto.</span><span class="sxs-lookup"><span data-stu-id="bd500-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="bd500-109">Skapa en inköpsorder för en engångsleverantör</span><span class="sxs-lookup"><span data-stu-id="bd500-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="bd500-110">Gå till Anskaffning och källa > Inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="bd500-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="bd500-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="bd500-111">Click New.</span></span>
3. <span data-ttu-id="bd500-112">Välj Ja i fältet Engångsleverantör.</span><span class="sxs-lookup"><span data-stu-id="bd500-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="bd500-113">Ett leverantörskonto skapas automatiskt och tilldelas inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="bd500-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="bd500-114">Leverantörskontot är baserat på mallen som visas på fliken Allmänt på sidan Parametrar för leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="bd500-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="bd500-115">Ange ett namn för leverantören i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="bd500-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="bd500-116">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bd500-116">Click OK.</span></span>
    * <span data-ttu-id="bd500-117">Inköpsordern kan nu slutföras och bearbetas som alla andra order.</span><span class="sxs-lookup"><span data-stu-id="bd500-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="bd500-118">Det finns inga särskilda resursegenskaper som är relaterade till hur detta ska göras.</span><span class="sxs-lookup"><span data-stu-id="bd500-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="bd500-119">Fakturan tar hänsyn en transaktion som förfaller på leverantörskontot som skapades med ordern och betalningen bearbetas därefter.</span><span class="sxs-lookup"><span data-stu-id="bd500-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span> <span data-ttu-id="bd500-120">När detta är slutfört kan leverantörskontot tas bort.</span><span class="sxs-lookup"><span data-stu-id="bd500-120">When this is completed, the vendor account can be deleted.</span></span> <span data-ttu-id="bd500-121">Detta görs normalt av leverantörsreskontraavdelningen.</span><span class="sxs-lookup"><span data-stu-id="bd500-121">This is typically done by the accounts payable department.</span></span>  

