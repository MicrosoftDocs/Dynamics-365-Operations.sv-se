---
title: Funktion för att dela upp faktura
description: I det här avsnittet beskrivs inställning och funktionalitet för uppdelning av fakturor efter leveransadress och skattekontonummer (TAN).
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7dddbb9f69a9735c2a03d2b23928f5cb92d4e0fd
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023603"
---
# <a name="split-invoice-functionality"></a><span data-ttu-id="cdf16-103">Funktion för att dela upp faktura</span><span class="sxs-lookup"><span data-stu-id="cdf16-103">Split invoice functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cdf16-104">I det här avsnittet beskrivs inställning och funktionalitet för uppdelning av fakturor efter leveransadress och skattekontonummer (TAN).</span><span class="sxs-lookup"><span data-stu-id="cdf16-104">This topic describes the setup and functionality for splitting invoices by delivery address and tax account number (TAN).</span></span>

<span data-ttu-id="cdf16-105">På sidan **Leverantörsreskontraparametrar**, under fliken **Allmänt**, markerar du kryssrutan **Produktkvitto** eller **Faktura** för att bokföra och dela upp ett produktkvitto eller en faktura som har olika leveransadresser och TAN på sidan **Inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="cdf16-105">On the **Accounts payable parameters** page, on the **General** tab, select the **Product receipt** or **Invoice** checkbox to post and split a product receipt or invoice that has different delivery addresses and TANs on the **Purchase order** page.</span></span> <span data-ttu-id="cdf16-106">Den bokförda fakturan delas sedan upp efter leveransadress och TAN.</span><span class="sxs-lookup"><span data-stu-id="cdf16-106">The posted invoice will then be split by delivery address and TAN.</span></span>

<span data-ttu-id="cdf16-107">Under fliken **Sammanfattningsuppdatering**, under snabbfliken **Dela upp baserat på**, i raden **Leveransinformation**, ställer du in alternativet **Bekräftelse**, **Plocklista**, **Följesedel** eller **Faktura** på **Ja** för att bokföra och dela upp en bekräftelse, plocklista, följesedel eller faktura där olika leveransadressen och TAN har definierats för olika fakturarader på sidan **Försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="cdf16-107">On the **Summary update** tab, on the **Split based on** FastTab, in the **Delivery information** row, set the **Confirmation**, **Picking list**, **Packing slip**, or **Invoice** option to **Yes** to post and split a confirmation, picking list, packing slip, or invoice where different delivery addresses and TANs are defined for different invoice lines on the **Sales order** page.</span></span> <span data-ttu-id="cdf16-108">Fakturan delas upp först efter leveransadress och sedan efter TAN.</span><span class="sxs-lookup"><span data-stu-id="cdf16-108">The invoice will be split first by delivery address and then by TAN.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="cdf16-109">Om inga alternativ för **Leveransinformation** har ställts in på **Ja**, bokförs fakturan som en enkel faktura.</span><span class="sxs-lookup"><span data-stu-id="cdf16-109">If no options for **Delivery information** are set to **Yes**, the invoice will be posted as a single invoice.</span></span> <span data-ttu-id="cdf16-110">Ingen fakturadelning sker.</span><span class="sxs-lookup"><span data-stu-id="cdf16-110">No invoice splitting will occur.</span></span>
> - <span data-ttu-id="cdf16-111">Om du vill dela upp och bokföra en följesedel där fakturaraderna har olika leveransadresser och TAN måste du ställa in alternativet **Följesedel** för **Leveransinformation** på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="cdf16-111">To split and post a packing slip where the invoice lines have different delivery addresses and TANs, you must set the **Packing slip** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="cdf16-112">Om du vill dela upp och bokföra en faktura där fakturaraderna har olika leveransadresser och TAN måste du ställa in alternativet **Faktura** för **Leveransinformation** på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="cdf16-112">To split and post an invoice where the invoice lines have different delivery addresses and TANs, you must set the **Invoice** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="cdf16-113">Om du vill bokföra en faktura där fakturaraderna har olika leveransadresser men samma TAN ställer du in alternativet **Faktura** för **Leveransinformation** på **Nej**.</span><span class="sxs-lookup"><span data-stu-id="cdf16-113">To post an invoice where the invoice lines have different delivery addresses but the same TAN, set the **Invoice** option for **Delivery information** to **No**.</span></span> <span data-ttu-id="cdf16-114">Fakturan delas upp efter leveransadress.</span><span class="sxs-lookup"><span data-stu-id="cdf16-114">The invoice will be split by delivery address.</span></span>

## <a name="example"></a><span data-ttu-id="cdf16-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="cdf16-115">Example</span></span>

<span data-ttu-id="cdf16-116">I det här exemplet har alternativet **Faktura** för **Leveransinformation** ställts in på **Ja** under fliken **Sammanfattningsuppdatering** på sidan **Leverantörsreskontraparametrar**.</span><span class="sxs-lookup"><span data-stu-id="cdf16-116">In this example, the **Invoice** option for **Delivery information** is set to **Yes** on the **Summary update** tab of the **Accounts payable parameters** page.</span></span> <span data-ttu-id="cdf16-117">En inköpsfaktura bokförs med följande inställningar för leveransadresser och TAN på raderna:</span><span class="sxs-lookup"><span data-stu-id="cdf16-117">A purchase invoice is posted that has the following setup for delivery addresses and TANs on the lines:</span></span>

- <span data-ttu-id="cdf16-118">**Artikelrad 1:** Leveransadress 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="cdf16-118">**Item line 1:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="cdf16-119">**Artikelrad 2:** Leveransadress 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="cdf16-119">**Item line 2:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="cdf16-120">**Artikelrad 3:** Leveransadress 2, TAN-ABCE12345B</span><span class="sxs-lookup"><span data-stu-id="cdf16-120">**Item line 3:** Delivery address 2, TAN-ABCE12345B</span></span>
- <span data-ttu-id="cdf16-121">**Artikelrad 4:** Leveransadress 3, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="cdf16-121">**Item line 4:** Delivery address 3, TAN-ABCD12345A</span></span>

<span data-ttu-id="cdf16-122">I det här fallet delas den ursprungliga fakturan upp i två fakturor och bokförs på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="cdf16-122">In this case, the original invoice is split into two invoices and posted in the following way:</span></span>

- <span data-ttu-id="cdf16-123">Faktura 1 bokförs för artikelrad 1 och artikelrad 2 eftersom båda raderna har samma leveransadress och TAN.</span><span class="sxs-lookup"><span data-stu-id="cdf16-123">Invoice 1 is posted for item line 1 and item line 2, because both lines have the same delivery address and TAN.</span></span>
- <span data-ttu-id="cdf16-124">Faktura 2 bokförs för artikelrad 3.</span><span class="sxs-lookup"><span data-stu-id="cdf16-124">Invoice 2 is posted for item line 3.</span></span>
- <span data-ttu-id="cdf16-125">Faktura 3 bokförs för artikelrad 4.</span><span class="sxs-lookup"><span data-stu-id="cdf16-125">Invoice 3 is posted for item line 4.</span></span>
