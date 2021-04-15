---
title: Lägga till en QR-kod eller streckkod i transaktions- och kvittomeddelanden
description: Det här avsnittet förklarar hur man infogar QR-koder och streckkoder som representerar order-ID i transaktions- och kvittomeddelanden i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: f8d9408090846799c1bb421c4b6e5e248d37fa07
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797513"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a><span data-ttu-id="656ef-103">Lägga till en QR-kod eller streckkod i transaktions- och kvittomeddelanden</span><span class="sxs-lookup"><span data-stu-id="656ef-103">Add a QR code or bar code to transactional and receipt emails</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="656ef-104">Det här avsnittet förklarar hur man infogar QR-koder och streckkoder som representerar order-ID i transaktions- och kvittomeddelanden i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="656ef-104">This topic explains how to insert QR codes and bar codes that represent order IDs into transactional and receipt emails in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="656ef-105">Du kan enkelt ta med QR-koder och streckkoder i transaktionsmeddelanden om du vill påskynda orderprocessen i en butiksmiljö.</span><span class="sxs-lookup"><span data-stu-id="656ef-105">You can easily include QR codes and bar codes in transactional emails to help speed up the order lookup process in a retail environment.</span></span> <span data-ttu-id="656ef-106">För att infoga QR-koder och streckkoder i e-postmeddelanden använder du en HTML **\<img\>** tagg som begär en QR-kod eller streckkodsbild från en generation och återgivningstjänster.</span><span class="sxs-lookup"><span data-stu-id="656ef-106">To insert QR codes and bar codes into emails, you use an HTML **\<img\>** tag that requests a QR code or bar code image from a generation and rendering service.</span></span> <span data-ttu-id="656ef-107">Microsoft tillhandahåller inte denna tjänst.</span><span class="sxs-lookup"><span data-stu-id="656ef-107">Microsoft doesn't provide this service.</span></span> <span data-ttu-id="656ef-108">Det finns emellertid många gratis- eller tjänstservicetjänster som kan servera QR-koder eller streckkoder som är dynamiskt genererade baserat på ett värde som överförs i en frågesträng.</span><span class="sxs-lookup"><span data-stu-id="656ef-108">However, there are many free or inexpensive services that can serve QR codes or bar codes that are dynamically generated based on a value that is passed in a query string.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a><span data-ttu-id="656ef-109">Lägga till en QR-kod eller streckkod i transaktionsmeddelande via e-post</span><span class="sxs-lookup"><span data-stu-id="656ef-109">Add a QR code or bar code to a transactional email</span></span>

<span data-ttu-id="656ef-110">Om du vill infoga en QR-kod eller streckkod i ett transaktionsmeddelande via e-post som skickas som en del av ett e-handelsinköp, följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="656ef-110">To insert a QR code or bar code into a transactional email that is sent as part of an e-commerce purchase, follow these steps.</span></span>

1. <span data-ttu-id="656ef-111">Öppna käll-HTML-koden för transaktionsmeddelande via e-post och lägg till en HTML-tagg **\<img\>** som pekar på din QR-kod eller streckkodstjänst.</span><span class="sxs-lookup"><span data-stu-id="656ef-111">Open the source HTML for the transactional email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="656ef-112">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="656ef-112">Here is an example.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    <span data-ttu-id="656ef-113">Här är en förklaring av föregående exempel:</span><span class="sxs-lookup"><span data-stu-id="656ef-113">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="656ef-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** representerar domänen för din QR-kod eller din streckkodstjänst.</span><span class="sxs-lookup"><span data-stu-id="656ef-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="656ef-115">**data** representerar parametern som QR-koden eller streckkodstjänsten använder för att ta emot innehållet som ska återges som en QR-kod eller streckkod.</span><span class="sxs-lookup"><span data-stu-id="656ef-115">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="656ef-116">Värdet **%salesid%** måste tilldelas den här parametern.</span><span class="sxs-lookup"><span data-stu-id="656ef-116">The value **%salesid%** must be assigned to this parameter.</span></span> <span data-ttu-id="656ef-117">Lägg märke till i det här exemplet att värdet även används som alt-text för bilden.</span><span class="sxs-lookup"><span data-stu-id="656ef-117">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="656ef-118">**param1** och **param2** representerar ytterligare valfria parametrar.</span><span class="sxs-lookup"><span data-stu-id="656ef-118">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="656ef-119">Gå till **Retail och Commerce \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar** och ladda upp den uppdaterade HTML-filen till lämplig transaktionsmall.</span><span class="sxs-lookup"><span data-stu-id="656ef-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the appropriate transactional email template.</span></span>

> [!NOTE]
> <span data-ttu-id="656ef-120">Parametrarna kan skilja sig mellan leverantörer av QR-kod och streckkodstjänster.</span><span class="sxs-lookup"><span data-stu-id="656ef-120">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="656ef-121">Kontakta därför din serviceleverantör för att bekräfta de parametrar som du måste tilldela värden till.</span><span class="sxs-lookup"><span data-stu-id="656ef-121">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a><span data-ttu-id="656ef-122">Lägga till en QR-kod eller streckkod i kvittomeddelande</span><span class="sxs-lookup"><span data-stu-id="656ef-122">Add a QR code or bar code to a receipt email</span></span> 

<span data-ttu-id="656ef-123">Om du vill infoga en QR-kod eller streckkod i ett kvittomeddelande som kan skickas efter att ett inköp har gjorts i kassan (POS) följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="656ef-123">To insert a QR code or bar code into a receipt email that can be sent after a purchase is made at the point of sale (POS), follow these steps.</span></span>

1. <span data-ttu-id="656ef-124">Öppna käll-HTML-koden för kvittomeddelande via e-post och lägg till en HTML-tagg **\<img\>** som pekar på din QR-kod eller streckkodstjänst.</span><span class="sxs-lookup"><span data-stu-id="656ef-124">Open the source HTML for the receipt email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="656ef-125">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="656ef-125">Here is an example below.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    <span data-ttu-id="656ef-126">Här är en förklaring av föregående exempel:</span><span class="sxs-lookup"><span data-stu-id="656ef-126">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="656ef-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** representerar domänen för din QR-kod eller din streckkodstjänst.</span><span class="sxs-lookup"><span data-stu-id="656ef-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="656ef-128">**data** representerar parametern som QR-koden eller streckkodstjänsten använder för att ta emot innehållet som ska återges som en QR-kod eller streckkod.</span><span class="sxs-lookup"><span data-stu-id="656ef-128">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="656ef-129">Värdet **%receiptid%** måste tilldelas den här parametern.</span><span class="sxs-lookup"><span data-stu-id="656ef-129">The value **%receiptid%** must be assigned to this parameter.</span></span> <span data-ttu-id="656ef-130">Lägg märke till i det här exemplet att värdet även används som alt-text för bilden.</span><span class="sxs-lookup"><span data-stu-id="656ef-130">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="656ef-131">**param1** och **param2** representerar ytterligare valfria parametrar.</span><span class="sxs-lookup"><span data-stu-id="656ef-131">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="656ef-132">Gå till **Retail och Commerce \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar** och ladda upp den uppdaterade HTML till e-postmallen som har e-post-ID **emailrecpt**.</span><span class="sxs-lookup"><span data-stu-id="656ef-132">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the email template that has the email ID **emailrecpt**.</span></span>

> [!NOTE]
> <span data-ttu-id="656ef-133">Parametrarna kan skilja sig mellan leverantörer av QR-kod och streckkodstjänster.</span><span class="sxs-lookup"><span data-stu-id="656ef-133">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="656ef-134">Kontakta därför din serviceleverantör för att bekräfta de parametrar som du måste tilldela värden till.</span><span class="sxs-lookup"><span data-stu-id="656ef-134">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="656ef-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="656ef-135">Additional resources</span></span>

[<span data-ttu-id="656ef-136">Skicka e-postkvitton från Modern POS (MPOS)</span><span class="sxs-lookup"><span data-stu-id="656ef-136">Send email receipts from Modern POS (MPOS)</span></span>](email-receipts.md)

[<span data-ttu-id="656ef-137">Skapa e-postmallar för transaktionshändelser</span><span class="sxs-lookup"><span data-stu-id="656ef-137">Create email templates for transactional events</span></span>](email-templates-transactions.md)
