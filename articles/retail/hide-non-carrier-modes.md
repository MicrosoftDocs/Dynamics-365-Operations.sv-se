---
title: Dölj leveranslägen som inte är transportsätt från leveransalternativen i kassan
description: Det här ämnet beskriver ett konfigurationsalternativ som gör det möjligt att förhindra att leveranssätt som inte är transportsätt för val när en leveransorder skapas i kassan (POS).
author: hhainesms
manager: annbe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 09ea83b3336b208f8af0a91025c2e6c50d64c385
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2019
ms.locfileid: "2659031"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a><span data-ttu-id="98046-103">Dölj leveranslägen som inte är transportsätt från leveransalternativen i kassan</span><span class="sxs-lookup"><span data-stu-id="98046-103">Hide non-carrier delivery modes from the shipping options in POS</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="98046-104">Det här ämnet beskriver ett konfigurationsalternativ som är tillgängligt för kassaprogrammet (POS).</span><span class="sxs-lookup"><span data-stu-id="98046-104">This topic describes a configuration option that is available for the point of sale (POS) application.</span></span> <span data-ttu-id="98046-105">Det här konfigurationsalternativet ändrar beteendet för valet av leveranssätt när en leveransorder skapas i POS.</span><span class="sxs-lookup"><span data-stu-id="98046-105">This configuration option changes the behavior for the selection of a mode of delivery when shipment orders are created in POS.</span></span>

<span data-ttu-id="98046-106">När användarna skapar kundleveransorder i kassan kan de välja ett leveranssätt för försändelsen.</span><span class="sxs-lookup"><span data-stu-id="98046-106">When users create customer shipment orders in POS, they can select a mode of delivery for the shipment.</span></span> <span data-ttu-id="98046-107">Den här funktionen är tillgänglig oavsett om hela ordern levereras eller endast är valda rader.</span><span class="sxs-lookup"><span data-stu-id="98046-107">This functionality is available regardless of whether the whole order is being shipped or only selected lines.</span></span>

<span data-ttu-id="98046-108">Som standard visas alla giltiga leveranssätt för kombinationen av en kanal, en artikel och en leveransadress i dialogrutan där leveranssättet väljs.</span><span class="sxs-lookup"><span data-stu-id="98046-108">By default, the dialog box where a mode of delivery is selected shows all the valid modes of delivery for the combination of a channel, an item, and a delivery address.</span></span> <span data-ttu-id="98046-109">Dessa leveranssätt definieras på sidan **Leveranssätt** i Retail Headquarters (**Försäljning och marknadsföring \> Inställning \> Distribution \> Leveranssätt**).</span><span class="sxs-lookup"><span data-stu-id="98046-109">These modes of delivery are defined on the **Modes of delivery** page in Retail Headquarters (**Sales and marketing \> Setup \> Distribution \> Modes of delivery**).</span></span> <span data-ttu-id="98046-110">Leveranslägen som inte är transportsätt, t.ex. **Utför** eller **Upphämtning** kan också visas för val i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="98046-110">"Non-carrier" modes of delivery, such as **Carryout** or **Pickup**, might also appear for selection in the dialog box.</span></span>

<span data-ttu-id="98046-111">En funktion har dock lagts till som gör att du kan dölja leveranslägen som inte är transportsätt i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="98046-111">However, a feature has been added that lets you hide non-carrier modes of delivery in the dialog box.</span></span> <span data-ttu-id="98046-112">Om du vill aktivera den här funktionen går du till sidan **butiksparametrar** på fliken **kundorder** och anger alternativet **Visa endast alternativ där leveranslägen är transportsätt** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="98046-112">To turn on this feature, on the **Retail parameters** page, on the **Customer orders** tab, set the **Show only carrier mode options for ship orders** option to **Yes**.</span></span> <span data-ttu-id="98046-113">När du har aktiverat den här funktionen och kört lämpliga distributionsjobb för att synkronisera informationen med kanaldatabasen visas inte leveranssätt för andra företag för val under processen med att skapa leveransorder i kassan.</span><span class="sxs-lookup"><span data-stu-id="98046-113">After you turn on this feature and run the appropriate distribution jobs to sync the information to the channel database, non-carrier modes of delivery won't appear for selection during the process of creating shipment orders in POS.</span></span>
