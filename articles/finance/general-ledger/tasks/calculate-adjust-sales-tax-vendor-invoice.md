---
title: Beräkna och justera moms på en leverantörsfaktura
description: I det här avsnittet beskriver hur du justerar momsen på en leverantörsfaktura Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a68e0df78516875168d977f78adf023887b2362d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186289"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="a5921-103">Beräkna och justera moms på en leverantörsfaktura</span><span class="sxs-lookup"><span data-stu-id="a5921-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a5921-104">I det här avsnittet beskriver hur du justerar momsen på en leverantörsfaktura.</span><span class="sxs-lookup"><span data-stu-id="a5921-104">This topic explains how to adjust sales tax on a vendor invoice.</span></span> <span data-ttu-id="a5921-105">Om det ursprungliga källdokumentet visar andra momsbelopp än dem som beräknas kan du justera dessa belopp, innan du bokför dem.</span><span class="sxs-lookup"><span data-stu-id="a5921-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="a5921-106">I den här uppgiften används demonstrationsföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="a5921-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="a5921-107">I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturajournal**.</span><span class="sxs-lookup"><span data-stu-id="a5921-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="a5921-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a5921-108">Select **New**.</span></span>
3. <span data-ttu-id="a5921-109">I fältet **Namn** i den nya raden väljer du ett alternativ i listrutemenyn.</span><span class="sxs-lookup"><span data-stu-id="a5921-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="a5921-110">Klicka på **Rader** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a5921-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="a5921-111">Ange önskade värden i fältet **Konto**.</span><span class="sxs-lookup"><span data-stu-id="a5921-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="a5921-112">Ange ett värde i fältet **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="a5921-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="a5921-113">I fältet **Kredit** väljer du ett tal.</span><span class="sxs-lookup"><span data-stu-id="a5921-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="a5921-114">Ange önskade värden i fältet **Motkonto**.</span><span class="sxs-lookup"><span data-stu-id="a5921-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="a5921-115">Välj **Moms**.</span><span class="sxs-lookup"><span data-stu-id="a5921-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="a5921-116">Ange ett tal i fältet **Totalt faktiskt momsbelopp**.</span><span class="sxs-lookup"><span data-stu-id="a5921-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="a5921-117">På fliken **justering** kan momsbeloppen justeras per momskod.</span><span class="sxs-lookup"><span data-stu-id="a5921-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="a5921-118">Välj **Återställ utfall till beräknade belopp**.</span><span class="sxs-lookup"><span data-stu-id="a5921-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="a5921-119">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5921-119">Select **OK**.</span></span>
14. <span data-ttu-id="a5921-120">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a5921-120">Select **Save**.</span></span>

