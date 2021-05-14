---
title: Verifikation genereras inte
description: Detta ämne tillhandahåller felsökningsinformation som kan vara till hjälp när en verifikation borde genereras men inte gör det.
author: qire
manager: beya
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: eafc9110ec58be5083569188d59b67a62e86c85d
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947712"
---
# <a name="voucher-isnt-generated"></a><span data-ttu-id="336dc-103">Verifikation genereras inte</span><span class="sxs-lookup"><span data-stu-id="336dc-103">Voucher isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="336dc-104">Om en verifikation ska genereras men sidan **Verifikationstransaktioner** inte visar några verifikationer, följer du stegen i följande avsnitt när du felsöker det här problemet.</span><span class="sxs-lookup"><span data-stu-id="336dc-104">If a voucher should be generated, but the **Voucher transactions** page doesn't show any vouchers, follow the steps in the following sections as required to troubleshoot this issue.</span></span>

<span data-ttu-id="336dc-105">[![Sida för Verifikationstransaktioner som inte har några verifikationer](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="336dc-105">[![Voucher transactions page that has no vouchers](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span></span>

## <a name="check-the-tax-applicability"></a><span data-ttu-id="336dc-106">Kontrollera tillämplighet för moms</span><span class="sxs-lookup"><span data-stu-id="336dc-106">Check the tax applicability</span></span>

1. <span data-ttu-id="336dc-107">Gå till **Moms** \> **Periodiska uppgifter** \> **Poster i redovisningsjournal som ännu inte har överförts**.</span><span class="sxs-lookup"><span data-stu-id="336dc-107">Go to **Tax** \> **Periodic tasks** \> **Subledger journal entries not yet transferred**.</span></span>
2. <span data-ttu-id="336dc-108">Om det finns en journalpost väljer du den och sedan **Överför nu**.</span><span class="sxs-lookup"><span data-stu-id="336dc-108">If there is a journal record, select it, and then select **Transfer now**.</span></span>

    <span data-ttu-id="336dc-109">[![Knappen Överför nu på sidan för poster i redovisningsjournal som ännu inte har överförts](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="336dc-109">[![Transfer now button on the Subledger journal entries not yet transferred page](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span></span>

3. <span data-ttu-id="336dc-110">Öppna sidan **Verifikationstransaktioner** igen om du vill se om verifikationen har skapats.</span><span class="sxs-lookup"><span data-stu-id="336dc-110">Open the **Voucher transactions** page again to see whether the voucher was generated.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="336dc-111">Bestäm om anpassning finns</span><span class="sxs-lookup"><span data-stu-id="336dc-111">Determine whether customization exists</span></span>

<span data-ttu-id="336dc-112">Om du har utfört stegen i det föregående avsnittet men inte hittat något problem, ska du fastställa om det finns någon anpassning.</span><span class="sxs-lookup"><span data-stu-id="336dc-112">If you've completed the steps in the previous section but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="336dc-113">Om det inte finns någon anpassning skapar du en Microsoft-servicebegäran för ytterligare support.</span><span class="sxs-lookup"><span data-stu-id="336dc-113">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
