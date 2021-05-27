---
title: Redigera ekonomiska dimensioner för butikstransaktioner
description: Det här ämnet beskriver hur du redigerar ekonomiska dimensioner för butikstransaktioner i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 381d8bb0939f6c4c163477990e49382201487375
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019917"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a><span data-ttu-id="d9727-103">Redigera ekonomiska dimensioner för butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="d9727-103">Edit financial dimensions for retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9727-104">Det här ämnet beskriver hur du redigerar ekonomiska dimensioner för butikstransaktioner i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d9727-104">This topic describes how to edit financial dimensions for retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="edit-financial-dimensions"></a><span data-ttu-id="d9727-105">Redigera ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="d9727-105">Edit financial dimensions</span></span>

<span data-ttu-id="d9727-106">Följ de här stegen om du vill redigera ekonomiska dimensioner för butikstransaktioner i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="d9727-106">To edit financial dimensions for retail transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="d9727-107">Öppna sidan **Konfiguration av ekonomisk dimension för integrering av program**.</span><span class="sxs-lookup"><span data-stu-id="d9727-107">Open the **Financial dimensions configuration for integrating applications** page.</span></span>
1. <span data-ttu-id="d9727-108">Välj den aktiva posten för **Integration med standarddimension**.</span><span class="sxs-lookup"><span data-stu-id="d9727-108">Select the active **Default dimensions integration** record.</span></span>
1. <span data-ttu-id="d9727-109">Gå till snabbfliken **Ekonomiska dimensioner** och se till att alla de dimensioner som du vill redigera i Excel-kalkylbladet finns i listan **Valda**.</span><span class="sxs-lookup"><span data-stu-id="d9727-109">On the **Financial dimensions** FastTab, make sure that all the dimensions that you want to edit in the Excel worksheet are present in the **Selected** list.</span></span> <span data-ttu-id="d9727-110">Mer information finns i [Datatabeller](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities).</span><span class="sxs-lookup"><span data-stu-id="d9727-110">For more information, see [Data entities](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities).</span></span>
1. <span data-ttu-id="d9727-111">Ladda ned och öppna Excel-filen från sidan **Utdrag**, sidan **Butikstransaktioner** eller panelen **Transaktionsvalideringsfel** i arbetsytan **Butiksekonomi**.</span><span class="sxs-lookup"><span data-stu-id="d9727-111">Download and open the Excel file from the **Statements** page, the **Retail transactions** page, or the **Transaction validation failures** tile in the **Store financials** workspace.</span></span>
1. <span data-ttu-id="d9727-112">Om du vill ändra transaktionens ekonomiska dimension väljer **Design** och väljer sedan pennsymbolen bredvid raden **Transaktion (granskningsbar)**.</span><span class="sxs-lookup"><span data-stu-id="d9727-112">To change the transaction financial dimension, select **Design**, and then select the pencil symbol next to the **Transaction (auditable)** row.</span></span>
1. <span data-ttu-id="d9727-113">Sök efter och markera fältet **FinancialDimensionDisplayValue**, markera en cell i huvuddelen i Excel-kalkylbladet och välj sedan **Lägg till etikett**.</span><span class="sxs-lookup"><span data-stu-id="d9727-113">Find and select the **FinancialDimensionDisplayValue** field, select a cell in the header part of the Excel worksheet, and then select **Add label**.</span></span>
1. <span data-ttu-id="d9727-114">Markera en cell nedanför cellen som du markerade i föregående steg, välj **Lägg till värde** och välj sedan **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="d9727-114">Select a cell below the cell that you selected in the previous step, select **Add Value**, and then select **Refresh**.</span></span> <span data-ttu-id="d9727-115">De ekonomiska dimensionerna läggs till i Excel-kalkylbladet och de kan sedan redigeras och publiceras.</span><span class="sxs-lookup"><span data-stu-id="d9727-115">The financial dimensions are added to the Excel worksheet, and they can then be edited and published.</span></span>
1. <span data-ttu-id="d9727-116">Om du vill ändra dimensionerna på transaktionsraderna markerar du raden **Försäljningstransaktioner (granskningsbara)**, väljer pennsymbolen och upprepar sedan steg 6 och 7.</span><span class="sxs-lookup"><span data-stu-id="d9727-116">To change the dimensions on the transaction lines, select the **Sales transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>
1. <span data-ttu-id="d9727-117">Om du vill ändra dimensionerna på betalningsraderna markerar du raden **Betalningstransaktioner (granskningsbara)**, väljer pennsymbolen och upprepar sedan steg 6 och 7.</span><span class="sxs-lookup"><span data-stu-id="d9727-117">To change the dimensions on the payment lines, select the **Payment transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d9727-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d9727-118">Additional resources</span></span>

[<span data-ttu-id="d9727-119">Redigera och granska hämtköpstransaktioner och transaktioner för kassahantering</span><span class="sxs-lookup"><span data-stu-id="d9727-119">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="d9727-120">Redigera och granska onlineorder- och asynkrona kundordertransaktioner</span><span class="sxs-lookup"><span data-stu-id="d9727-120">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="d9727-121">Skapa en Excel-arbetsbok för att redigera butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="d9727-121">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="d9727-122">Lägga till fält i en Excel-arbetsbok för att redigera butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="d9727-122">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]