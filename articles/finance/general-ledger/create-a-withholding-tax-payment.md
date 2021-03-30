---
title: Skapa en källskattbetalning
description: Jobbproceduren för källskatt kvittar källskattssaldon från leverantörsreskontra på källskattskonton, och motbokar dem på kontot för källskattskvittning för en viss period. Detta ämne innehåller en lista med steg för att ställa in en källskattebetalning.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: eae914ccafad12426cadd91c0950bada23548005
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212287"
---
# <a name="create-a-withholding-tax-payment"></a><span data-ttu-id="140a9-104">Skapa en källskattbetalning</span><span class="sxs-lookup"><span data-stu-id="140a9-104">Create a withholding tax payment</span></span>

<span data-ttu-id="140a9-105">Jobbproceduren för källskatt kvittar källskattssaldon från leverantörsreskontra på källskattskonton, och motbokar dem på kontot för källskattskvittning för en viss period.</span><span class="sxs-lookup"><span data-stu-id="140a9-105">The Withholding tax payment job procedure settles withholding tax balances from Accounts payable on withholding tax accounts, and offsets them to the withholding tax settlement account for a given period.</span></span> <span data-ttu-id="140a9-106">Detta ämne innehåller en lista med steg för att ställa in en källskattebetalning.</span><span class="sxs-lookup"><span data-stu-id="140a9-106">This topic lists the steps for setting up a withholding tax payment.</span></span>

> [!NOTE] 
> <span data-ttu-id="140a9-107">Motbokning av källskatt (från kundreskontra) räknas inte med när en källskattebetalning beräknas.</span><span class="sxs-lookup"><span data-stu-id="140a9-107">Withholding tax offset (from accounts receivable) is not taken into account when a withholding tax payment is calculated.</span></span>

1. <span data-ttu-id="140a9-108">Gå till **Navigeringsfönster > Moduler > Skatt > Deklarationer > Källskatt > Källskattebetalning**.</span><span class="sxs-lookup"><span data-stu-id="140a9-108">Go to **Navigation pane > Modules > Tax > Declarations > Withholding tax > Withholding tax payment**.</span></span>
2. <span data-ttu-id="140a9-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kvittningsperiod**.</span><span class="sxs-lookup"><span data-stu-id="140a9-109">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="140a9-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="140a9-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="140a9-111">I fältet **Från datum** anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="140a9-111">In the **From date** field, enter a date.</span></span>
5. <span data-ttu-id="140a9-112">I fältet **Transaktionsdatum**, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="140a9-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="140a9-113">Välj **Uppdatera** om du vill bokföra betalningsverifikationen för källskatt på kvittningskontot för källskatt.</span><span class="sxs-lookup"><span data-stu-id="140a9-113">Select **Update** to post withholding tax payment voucher to the withholding tax settlement account.</span></span>
7. <span data-ttu-id="140a9-114">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="140a9-114">Click **OK**.</span></span>

![Parametrar för betalning av källskatt](media/withholding-tax-payment.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]