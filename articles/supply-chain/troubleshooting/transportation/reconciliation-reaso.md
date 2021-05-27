---
title: Du kan bara lägga till huvudkontot som kreditkonto av avstämningsskäl
description: När du ställer in en avstämningsorsak i transporthantering kan du bara lägga till huvudkontot som kreditkonto.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026901"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a><span data-ttu-id="07b52-103">Du kan bara lägga till huvudkontot som kreditkonto av avstämningsskäl</span><span class="sxs-lookup"><span data-stu-id="07b52-103">You can add only the main account as the credit account for reconciliation reasons</span></span>

<span data-ttu-id="07b52-104">KB-nummer: 4603538</span><span class="sxs-lookup"><span data-stu-id="07b52-104">KB number: 4603538</span></span>

## <a name="symptoms"></a><span data-ttu-id="07b52-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="07b52-105">Symptoms</span></span>

<span data-ttu-id="07b52-106">När du ställer in en avstämningsorsak i transporthantering kan du bara lägga till huvudkontot som kreditkonto.</span><span class="sxs-lookup"><span data-stu-id="07b52-106">When you set up a reconciliation reason in Transportation management, you can add only the main account as the credit account.</span></span> <span data-ttu-id="07b52-107">Du kan inte lägga till ett kostnadsställe eller någon annan dimension som kreditkonto.</span><span class="sxs-lookup"><span data-stu-id="07b52-107">You can't add a cost center or any other dimension as the credit account.</span></span> <span data-ttu-id="07b52-108">Med debetkontot kan du dock välja andra dimensioner.</span><span class="sxs-lookup"><span data-stu-id="07b52-108">However, the debit account lets you select other dimensions.</span></span>

## <a name="resolution"></a><span data-ttu-id="07b52-109">Upplösning</span><span class="sxs-lookup"><span data-stu-id="07b52-109">Resolution</span></span>

<span data-ttu-id="07b52-110">Om avstämningen inte görs för att betala leverantören men för att kreditera ett visst huvudkonto, tillåter systemet inte att du väljer en ekonomisk dimension för kreditkontot när du ställer in avstämningsorsaken.</span><span class="sxs-lookup"><span data-stu-id="07b52-110">If the reconciliation isn't done to pay the vendor but to credit a specific main account, the system doesn't allow you to select a financial dimension for the credit account when you set up the reconciliation reason.</span></span>

<span data-ttu-id="07b52-111">Om kontostrukturen kräver ett specifikt ekonomiskt dimensionsvärde för kredithuvudkontot kan den resulterande leverantörsjournalen inte bokföras automatiskt, eftersom värdet för den ekonomiska dimensionen saknas.</span><span class="sxs-lookup"><span data-stu-id="07b52-111">If the account structure requires a specific financial dimension value for the credit main account, the resulting vendor journal can't be posted automatically, because the financial dimension value is missing.</span></span> <span data-ttu-id="07b52-112">Därför måste du först ange kreditkontot manuellt med hjälp av sidan **Fakturajournal**.</span><span class="sxs-lookup"><span data-stu-id="07b52-112">Therefore, you must first manually specify the credit account by using the **Invoice journal** page.</span></span>

<span data-ttu-id="07b52-113">Eftersom ett dimensionsvärde krävs för kreditkontot kan leverantörsfakturajournalen inte bokföras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="07b52-113">Because a dimension value is required for the credit account, the vendor invoice journal can't be automatically posted.</span></span> <span data-ttu-id="07b52-114">Du måste bokföra det manuellt när du har lagt till dimensionsvärdet manuellt på huvudkontot för kreditraden.</span><span class="sxs-lookup"><span data-stu-id="07b52-114">You must manually post it after you manually add the dimension value to the main account for the credit line.</span></span>
