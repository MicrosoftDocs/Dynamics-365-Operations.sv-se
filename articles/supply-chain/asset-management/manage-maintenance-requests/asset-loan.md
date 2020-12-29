---
title: Tillgångslån
description: Det här avsnittet beskriver hur du registrerar lånetillgångar i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cba680d0ad626e0275539d7478a83639a9d22635
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437732"
---
# <a name="asset-loans"></a><span data-ttu-id="b7726-103">Tillgångslån</span><span class="sxs-lookup"><span data-stu-id="b7726-103">Asset loans</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b7726-104">Om ditt företag tar emot tillgångar för reparations- eller underhållsjobb från antingen interna platser eller kunder, och om du tillfälligt lånar tillgångar till dessa platser eller kunder, kan tillgångshantering spåra tillgångslånen.</span><span class="sxs-lookup"><span data-stu-id="b7726-104">If your company receives assets for repair or maintenance jobs from either internal locations or customers, and if you temporarily loan assets to those locations or customers, Asset Management can track the asset loans.</span></span>

## <a name="register-asset-loans-on-a-maintenance-request"></a><span data-ttu-id="b7726-105">Registrera tillgångslån på en underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="b7726-105">Register asset loans on a maintenance request</span></span>

1. <span data-ttu-id="b7726-106">Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **alla underhållbegäran** eller **aktiva underhållbegäran**.</span><span class="sxs-lookup"><span data-stu-id="b7726-106">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="b7726-107">Välj underhållbegäran för att registrera ett tillgångslån på och välj sedan **redigera**.</span><span class="sxs-lookup"><span data-stu-id="b7726-107">Select the maintenance request to register an asset loan on, and then select **Edit**.</span></span>
3. <span data-ttu-id="b7726-108">På sidan **begäran** väljer du **skicka lånetillgång**.</span><span class="sxs-lookup"><span data-stu-id="b7726-108">On the **Request** page, select **Send loan asset**.</span></span>
4. <span data-ttu-id="b7726-109">Välj tillgången och ange förväntat returdatum.</span><span class="sxs-lookup"><span data-stu-id="b7726-109">Select the asset, and enter the expected return date.</span></span>
5. <span data-ttu-id="b7726-110">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7726-110">Select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="b7726-111">Du kan bara skicka en lånetillgång om en tillgång av samma tillgångstyp är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b7726-111">You can send a loan asset only if an asset of the same asset type is available.</span></span>
> - <span data-ttu-id="b7726-112">Den tillgång som du lånar måste ha en tillgångs livscykeltillstånd som gör att den kan användas som en lånetillgång, t.ex. **InStorage**.</span><span class="sxs-lookup"><span data-stu-id="b7726-112">The asset that you loan must have an asset lifecycle state that allows it to be used as a loan asset, such as **InStorage**.</span></span> <span data-ttu-id="b7726-113">När tillgångslånet registreras uppdateras tillgångens livscykeltillstånd automatiskt till till exempel **OnLoan**.</span><span class="sxs-lookup"><span data-stu-id="b7726-113">When the asset loan is registered, the asset lifecycle state of the asset is automatically updated to, for example, **OnLoan**.</span></span>

<span data-ttu-id="b7726-114">Om du vill visa en lista över alla tillgångar som du har lånat till andra platser eller kunder väljer du **tillgångshantering** \> **allmänt** \> **tillgångslån** \> **alla tillgångslån**.</span><span class="sxs-lookup"><span data-stu-id="b7726-114">To view a list of all the assets that you've loaned to other locations or customers, select **Asset management** \> **Common** \> **Asset loan** \> **All asset loans**.</span></span> <span data-ttu-id="b7726-115">Om kryssrutan **avslutad** markeras för en tillgång har tillgången registrerats som returnerad till ditt företag.</span><span class="sxs-lookup"><span data-stu-id="b7726-115">If the **Ended** check box is selected for an asset, the asset has been registered as returned to your company.</span></span>

![Hantera underhållsbegäranden](media/06-manage-maintenance-requests.png)

<span data-ttu-id="b7726-117">På sidan **aktiva tillgångslån** kan du visa en lista över alla lånetillgångar som ännu inte har returnerats till ditt företag.</span><span class="sxs-lookup"><span data-stu-id="b7726-117">On the **Active asset loans** page, you can view a list of all the loan assets that haven't yet been returned to your company.</span></span>

## <a name="register-loan-assets-as-returned"></a><span data-ttu-id="b7726-118">Registrera lånetillgångar som returnerade</span><span class="sxs-lookup"><span data-stu-id="b7726-118">Register loan assets as returned</span></span>

1. <span data-ttu-id="b7726-119">Välj **tillgångshantering** \> **allmänt** \> **tillgångslån** \> **aktiva tillgångslån**</span><span class="sxs-lookup"><span data-stu-id="b7726-119">Select **Asset management** \> **Common** \> **Asset loan** \> **Active asset loans**.</span></span>
2. <span data-ttu-id="b7726-120">Välj tillgångslånet som ska registreras som returnerat och välj **returnera tillgångslån**.</span><span class="sxs-lookup"><span data-stu-id="b7726-120">Select the asset loan to register as returned, and then select **Return asset loan**.</span></span>
3. <span data-ttu-id="b7726-121">I fältet **Returnerad** ställer du in datum och tid.</span><span class="sxs-lookup"><span data-stu-id="b7726-121">In the **Returned** field, enter the date and time.</span></span>
4. <span data-ttu-id="b7726-122">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7726-122">Select **OK**.</span></span>
5. <span data-ttu-id="b7726-123">Uppdatera listsidan **aktiva tillgångslån** och observera att tillgångslånet inte längre visas i listan.</span><span class="sxs-lookup"><span data-stu-id="b7726-123">Refresh the **Active asset loans** list page, and notice that the asset loan no longer appears in the list.</span></span>
