---
title: Valt formelnummer som inte godkänts för en batchorder
description: När du försöker bekräfta en planerad order visas ett felmeddelande där det står att det valda formelnumret inte är godkänt för en batchorder.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294178"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a><span data-ttu-id="99859-103">Valt formelnummer som inte godkänts för en batchorder</span><span class="sxs-lookup"><span data-stu-id="99859-103">Selected formula number isn't approved for a batch order</span></span>

<span data-ttu-id="99859-104">Felkod: PRO2614</span><span class="sxs-lookup"><span data-stu-id="99859-104">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="99859-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="99859-105">Symptoms</span></span>

<span data-ttu-id="99859-106">När du har bekräftat planerade order visas följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="99859-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="99859-107">Det valda formelnumret är inte godkänt för en batchorder.</span><span class="sxs-lookup"><span data-stu-id="99859-107">The selected formula number is not approved for a batch order.</span></span>

## <a name="cause"></a><span data-ttu-id="99859-108">Orsak</span><span class="sxs-lookup"><span data-stu-id="99859-108">Cause</span></span>

<span data-ttu-id="99859-109">Systemet validerar bekräftad operation för att se till att ett godkänt recept är tillgängligt för den aktiva artikeln.</span><span class="sxs-lookup"><span data-stu-id="99859-109">The system validates the firming operation to make sure that an approved formula is available for the active item.</span></span> <span data-ttu-id="99859-110">Du måste troligen godkänna formel.</span><span class="sxs-lookup"><span data-stu-id="99859-110">You must probably approve the formula.</span></span>

## <a name="resolution"></a><span data-ttu-id="99859-111">Lösning</span><span class="sxs-lookup"><span data-stu-id="99859-111">Resolution</span></span>

<span data-ttu-id="99859-112">Följ anvisningarna nedan om du vill godkänna en formel.</span><span class="sxs-lookup"><span data-stu-id="99859-112">To approve a formula, follow these steps.</span></span>

1. <span data-ttu-id="99859-113">Gå till **Produktinformationshantering \> Strukturlistor och formler \> Formler**.</span><span class="sxs-lookup"><span data-stu-id="99859-113">Go to **Product information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="99859-114">Välj relevant formel.</span><span class="sxs-lookup"><span data-stu-id="99859-114">Select the relevant formula.</span></span>
1. <span data-ttu-id="99859-115">I Åtgärdsfönstret, på fliken **formel**, i gruppen **underhåll**, markerar du **godkänn formel**.</span><span class="sxs-lookup"><span data-stu-id="99859-115">On the Action Pane, on the **Formula** tab, in the **Maintain** group, select **Approve formula**.</span></span>
1. <span data-ttu-id="99859-116">Välj en godkännare i dialogrutan **Godkänn strukturlista** eller recept och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="99859-116">In the **Approve BOM or formula** dialog box, select an approver, and then select **OK**.</span></span>
