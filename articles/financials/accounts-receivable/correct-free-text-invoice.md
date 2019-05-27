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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8c1b90b7b2c02a53e53cc13d70445a237b126d4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559789"
---
# <a name="correct-a-free-text-invoice"></a><span data-ttu-id="4183d-103">Korrigera en fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="4183d-103">Correct a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4183d-104">Det här avsnittet innehåller information om hur du korrigerar en fritextfaktura som har bokförts och hur du återutfärdar den som en korrigerad faktura.</span><span class="sxs-lookup"><span data-stu-id="4183d-104">This article explains how to correct a free text invoice that has been posted and reissue it as a corrected invoice.</span></span>

<span data-ttu-id="4183d-105">Öppna bokförd fritextfaktura för att åtgärda en fritextfaktura som redan har bokförts.</span><span class="sxs-lookup"><span data-stu-id="4183d-105">To correct a free text invoice that has already been posted, open the posted free text invoice.</span></span> <span data-ttu-id="4183d-106">På sidan **Faktura**, välj **Avbryt** och sedan **Korrigera faktura**.</span><span class="sxs-lookup"><span data-stu-id="4183d-106">On the **Invoice** page, select **Cancel**, and then select **Correct invoice**.</span></span> <span data-ttu-id="4183d-107">Välj en orsakskod, lägg till kommentarer och välj datum för ny korrigerad faktura.</span><span class="sxs-lookup"><span data-stu-id="4183d-107">Select a reason code, add comments, and select the date for new corrected invoice.</span></span> <span data-ttu-id="4183d-108">Du kan ändra den korrigerade fakturan och bokföra den.</span><span class="sxs-lookup"><span data-stu-id="4183d-108">You can modify the corrected invoice, and post it.</span></span> 

<span data-ttu-id="4183d-109">När du bokför den korrigerade fakturan skapas en annulleringsfaktura för ett kreditbelopp som är lika med det ursprungliga fakturabeloppet.</span><span class="sxs-lookup"><span data-stu-id="4183d-109">When you post the corrected invoice, a canceling invoice is created for a credit amount that equals the original invoice amount.</span></span> <span data-ttu-id="4183d-110">Därför är det kombinerade saldot för den ursprungliga fakturan och annulleringsfakturan 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="4183d-110">Therefore, the combined balance of the original invoice and the canceling invoice is 0 (zero).</span></span> <span data-ttu-id="4183d-111">Annulleringsfakturan kvittas mot den ursprungliga fakturan.</span><span class="sxs-lookup"><span data-stu-id="4183d-111">The canceling invoice is settled against the original invoice.</span></span> 

<span data-ttu-id="4183d-112">När du har bokfört den korrigerade fakturan har du tre fakturor:</span><span class="sxs-lookup"><span data-stu-id="4183d-112">After you post the corrected invoice, you will have three invoices:</span></span>

-   <span data-ttu-id="4183d-113">**Ursprunglig faktura** – Fakturan som innehåller informationen som du korrigerar.</span><span class="sxs-lookup"><span data-stu-id="4183d-113">**Original invoice** – The invoice that includes the information that you're correcting.</span></span>
-   <span data-ttu-id="4183d-114">**Annulleringsfaktura** – Den systemgenererade kreditfakturan som har skapats för att annullera fakturan som senast korrigerades.</span><span class="sxs-lookup"><span data-stu-id="4183d-114">**Canceling invoice** – The system-generated credit invoice that was created to cancel the invoice that was most recently corrected.</span></span>
-   <span data-ttu-id="4183d-115">**Korrigerad faktura** – Fakturan som innehåller den korrigerade fakturainformationen.</span><span class="sxs-lookup"><span data-stu-id="4183d-115">**Corrected invoice** – The invoice that contains the corrected invoice information.</span></span>

<span data-ttu-id="4183d-116">Du kan identifiera annullerings- och korrigeringsfakturor på två sätt:</span><span class="sxs-lookup"><span data-stu-id="4183d-116">You can identify canceling and correcting invoices in two ways:</span></span>

-   <span data-ttu-id="4183d-117">Sidan **Alla fritextfakturor** innehåller kolumnen **Korrigering** där du ser vilka fakturor som är annulleringsfakturor och korrigerade fakturor.</span><span class="sxs-lookup"><span data-stu-id="4183d-117">The **All free text invoices** page includes a **Correction** column, where you can see which invoices are canceling invoices and corrected invoices.</span></span>
-   <span data-ttu-id="4183d-118">Sidhuvudet på fritextfakturan anger statusen **Annullerar faktura "\[fakturanummer\]"'** eller **Korrigerad faktura "\[fakturanummer\]"**.</span><span class="sxs-lookup"><span data-stu-id="4183d-118">The header of the free text invoice shows a status of **Cancelling invoice '\[invoice number\]'** or **Corrected invoice '\[invoice number\]'**.</span></span>

> [!NOTE]
> <span data-ttu-id="4183d-119">Den här funktionen är bara tillgänglig om konfigurationsnyckeln **Korrigering av fritextfaktura** markeras.</span><span class="sxs-lookup"><span data-stu-id="4183d-119">This feature is available only if the **Free text invoice correction** configuration key is selected.</span></span>



