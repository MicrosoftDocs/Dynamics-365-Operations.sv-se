---
title: Skapa en källskattbetalning
description: Jobbproceduren för källskatt kvittar källskattssaldon från leverantörsreskontra på källskattskonton, och motbokar dem på kontot för källskattskvittning för en viss period. Detta ämne innehåller en lista med steg för att ställa in en källskattebetalning.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 72d80fbb3b2448f4b89fa7d7fa580387e1a3621c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832956"
---
# <a name="create-a-withholding-tax-payment"></a><span data-ttu-id="f41ff-104">Skapa en källskattbetalning</span><span class="sxs-lookup"><span data-stu-id="f41ff-104">Create a withholding tax payment</span></span>

<span data-ttu-id="f41ff-105">Jobbproceduren för källskatt kvittar källskattssaldon från leverantörsreskontra på källskattskonton, och motbokar dem på kontot för källskattskvittning för en viss period.</span><span class="sxs-lookup"><span data-stu-id="f41ff-105">The Withholding tax payment job procedure settles withholding tax balances from Accounts payable on withholding tax accounts, and offsets them to the withholding tax settlement account for a given period.</span></span> <span data-ttu-id="f41ff-106">Detta ämne innehåller en lista med steg för att ställa in en källskattebetalning.</span><span class="sxs-lookup"><span data-stu-id="f41ff-106">This topic lists the steps for setting up a withholding tax payment.</span></span>

> [!NOTE] 
> <span data-ttu-id="f41ff-107">Motbokning av källskatt (från kundreskontra) räknas inte med när en källskattebetalning beräknas.</span><span class="sxs-lookup"><span data-stu-id="f41ff-107">Withholding tax offset (from accounts receivable) is not taken into account when a withholding tax payment is calculated.</span></span>

1. <span data-ttu-id="f41ff-108">Gå till **Navigeringsfönster > Moduler > Skatt > Deklarationer > Källskatt > Källskattebetalning**.</span><span class="sxs-lookup"><span data-stu-id="f41ff-108">Go to **Navigation pane > Modules > Tax > Declarations > Withholding tax > Withholding tax payment**.</span></span>
2. <span data-ttu-id="f41ff-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kvittningsperiod**.</span><span class="sxs-lookup"><span data-stu-id="f41ff-109">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="f41ff-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f41ff-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f41ff-111">I fältet **Från datum** anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="f41ff-111">In the **From date** field, enter a date.</span></span>
5. <span data-ttu-id="f41ff-112">I fältet **Transaktionsdatum**, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="f41ff-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="f41ff-113">Välj **Uppdatera** om du vill bokföra betalningsverifikationen för källskatt på kvittningskontot för källskatt.</span><span class="sxs-lookup"><span data-stu-id="f41ff-113">Select **Update** to post withholding tax payment voucher to the withholding tax settlement account.</span></span>
7. <span data-ttu-id="f41ff-114">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f41ff-114">Click **OK**.</span></span>

![Parametrar för betalning av källskatt](media/withholding-tax-payment.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]