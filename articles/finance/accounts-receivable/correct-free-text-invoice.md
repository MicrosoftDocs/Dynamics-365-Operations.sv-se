---
title: Korrigera en fritextfaktura
description: Det här avsnittet innehåller information om hur du korrigerar en fritextfaktura som har bokförts och hur du återutfärdar den som en korrigerad faktura.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 71b94e6fa4faafdc5fbe68e89635ec79616164bb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217540"
---
# <a name="correct-a-free-text-invoice"></a><span data-ttu-id="a6f39-103">Korrigera en fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="a6f39-103">Correct a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a6f39-104">Det här avsnittet innehåller information om hur du korrigerar en fritextfaktura som har bokförts och hur du återutfärdar den som en korrigerad faktura.</span><span class="sxs-lookup"><span data-stu-id="a6f39-104">This article explains how to correct a free text invoice that has been posted and reissue it as a corrected invoice.</span></span>

<span data-ttu-id="a6f39-105">Öppna bokförd fritextfaktura för att åtgärda en fritextfaktura som redan har bokförts.</span><span class="sxs-lookup"><span data-stu-id="a6f39-105">To correct a free text invoice that has already been posted, open the posted free text invoice.</span></span> <span data-ttu-id="a6f39-106">På sidan **Faktura**, välj **Avbryt** och sedan **Korrigera faktura**.</span><span class="sxs-lookup"><span data-stu-id="a6f39-106">On the **Invoice** page, select **Cancel**, and then select **Correct invoice**.</span></span> <span data-ttu-id="a6f39-107">Välj en orsakskod, lägg till kommentarer och välj datum för ny korrigerad faktura.</span><span class="sxs-lookup"><span data-stu-id="a6f39-107">Select a reason code, add comments, and select the date for new corrected invoice.</span></span> <span data-ttu-id="a6f39-108">Du kan ändra den korrigerade fakturan och bokföra den.</span><span class="sxs-lookup"><span data-stu-id="a6f39-108">You can modify the corrected invoice, and post it.</span></span> 

<span data-ttu-id="a6f39-109">När du bokför den korrigerade fakturan skapas en annulleringsfaktura för ett kreditbelopp som är lika med det ursprungliga fakturabeloppet.</span><span class="sxs-lookup"><span data-stu-id="a6f39-109">When you post the corrected invoice, a canceling invoice is created for a credit amount that equals the original invoice amount.</span></span> <span data-ttu-id="a6f39-110">Därför är det kombinerade saldot för den ursprungliga fakturan och annulleringsfakturan 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="a6f39-110">Therefore, the combined balance of the original invoice and the canceling invoice is 0 (zero).</span></span> <span data-ttu-id="a6f39-111">Annulleringsfakturan kvittas mot den ursprungliga fakturan.</span><span class="sxs-lookup"><span data-stu-id="a6f39-111">The canceling invoice is settled against the original invoice.</span></span> 

<span data-ttu-id="a6f39-112">När du har bokfört den korrigerade fakturan har du tre fakturor:</span><span class="sxs-lookup"><span data-stu-id="a6f39-112">After you post the corrected invoice, you will have three invoices:</span></span>

-   <span data-ttu-id="a6f39-113">**Ursprunglig faktura** – Fakturan som innehåller informationen som du korrigerar.</span><span class="sxs-lookup"><span data-stu-id="a6f39-113">**Original invoice** – The invoice that includes the information that you're correcting.</span></span>
-   <span data-ttu-id="a6f39-114">**Annulleringsfaktura** – Den systemgenererade kreditfakturan som har skapats för att annullera fakturan som senast korrigerades.</span><span class="sxs-lookup"><span data-stu-id="a6f39-114">**Canceling invoice** – The system-generated credit invoice that was created to cancel the invoice that was most recently corrected.</span></span>
-   <span data-ttu-id="a6f39-115">**Korrigerad faktura** – Fakturan som innehåller den korrigerade fakturainformationen.</span><span class="sxs-lookup"><span data-stu-id="a6f39-115">**Corrected invoice** – The invoice that contains the corrected invoice information.</span></span>

<span data-ttu-id="a6f39-116">Du kan identifiera annullerings- och korrigeringsfakturor på två sätt:</span><span class="sxs-lookup"><span data-stu-id="a6f39-116">You can identify canceling and correcting invoices in two ways:</span></span>

-   <span data-ttu-id="a6f39-117">Sidan **Alla fritextfakturor** innehåller kolumnen **Korrigering** där du ser vilka fakturor som är annulleringsfakturor och korrigerade fakturor.</span><span class="sxs-lookup"><span data-stu-id="a6f39-117">The **All free text invoices** page includes a **Correction** column, where you can see which invoices are canceling invoices and corrected invoices.</span></span>
-   <span data-ttu-id="a6f39-118">Sidhuvudet på fritextfakturan anger statusen **Annullerar faktura "\[fakturanummer\]"'** eller **Korrigerad faktura "\[fakturanummer\]"**.</span><span class="sxs-lookup"><span data-stu-id="a6f39-118">The header of the free text invoice shows a status of **Cancelling invoice '\[invoice number\]'** or **Corrected invoice '\[invoice number\]'**.</span></span>

> [!NOTE]
> <span data-ttu-id="a6f39-119">Den här funktionen är bara tillgänglig om konfigurationsnyckeln **Korrigering av fritextfaktura** markeras.</span><span class="sxs-lookup"><span data-stu-id="a6f39-119">This feature is available only if the **Free text invoice correction** configuration key is selected.</span></span> <span data-ttu-id="a6f39-120">Mer information om hur du aktiverar konfigurationsnycklar finns i avsnittet Aktivera (eller inaktivera) konfigurationsnycklar i avsnittet [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a6f39-120">For more information on how to enable Configuration keys refer to the Enable (or disable) configuration keys section in the [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) topic.</span></span> 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]