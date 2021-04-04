---
title: Anskaffnings- och källparametrar för hemtagningskostnad
description: Det här ämnet beskriver hur du ställer in relevanta parametrar för Anskaffning och inköp när du använder modulen hemtagningskostnad.
author: sherry-zheng
manager: tfehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 49e046a1437917cfa866f690511789496fac2c53
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500752"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a><span data-ttu-id="12b11-103">Anskaffnings- och källparametrar för hemtagningskostnad</span><span class="sxs-lookup"><span data-stu-id="12b11-103">Procurement and sourcing parameters for Landed cost</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="12b11-104">Sidan **Anskaffnings- och inköpsparametrar** har några inställningar som är särskilt relevanta när du använder modulen **Hemtagningskostnad**.</span><span class="sxs-lookup"><span data-stu-id="12b11-104">The **Procurement and sourcing parameters** page has a few settings that are especially relevant when you use the **Landed cost** module.</span></span> <span data-ttu-id="12b11-105">Använd dialogrutan **Uppdatera orderrader** som öppnas från sidan **Anskaffnings- och källparametrar** om du vill ange om inköpsorderrader ska uppdateras automatiskt när ändringar görs i inköpsorderrubriken.</span><span class="sxs-lookup"><span data-stu-id="12b11-105">Use the **Update order lines** dialog box that is opened from the **Procurement and sourcing parameters** page to specify whether purchase order lines should automatically be updated when changes are made on the purchase order header.</span></span>

<span data-ttu-id="12b11-106">Om du vill slutföra denna inställning, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="12b11-106">To complete this setup, follow these steps.</span></span>

1. <span data-ttu-id="12b11-107">Gå till **Anskaffning och källa \> Inställningar \> Anskaffnings- och källparametrar**.</span><span class="sxs-lookup"><span data-stu-id="12b11-107">Go to **Procurement and sourcing \> Setup \> Procurement and sourcing parameters**.</span></span>
1. <span data-ttu-id="12b11-108">På fliken **Allmänt**, välj länken **Uppdatera orderrader**.</span><span class="sxs-lookup"><span data-stu-id="12b11-108">On the **General** tab, select the **Update order lines** link.</span></span>
1. <span data-ttu-id="12b11-109">Dialogrutan **Uppdatera orderrader** visar fälten i orderrubriken som också kan tillämpa automatiska uppdateringar på relaterade fält på orderraderna.</span><span class="sxs-lookup"><span data-stu-id="12b11-109">The **Update order lines** dialog box lists the fields on the order header that can also apply automatic updates to related fields on the order lines.</span></span> <span data-ttu-id="12b11-110">Ställ in varje fält i listan på ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="12b11-110">Set each field in the list to one of the following values:</span></span>

    - <span data-ttu-id="12b11-111">**Alltid** – Orderraderna uppdateras automatiskt när orderrubriken uppdateras.</span><span class="sxs-lookup"><span data-stu-id="12b11-111">**Always** – The order lines should automatically be updated when the order header is updated.</span></span>
    - <span data-ttu-id="12b11-112">**Aldrig** – Orderraderna uppdateras aldrig när orderrubriken uppdateras.</span><span class="sxs-lookup"><span data-stu-id="12b11-112">**Never** – The order lines should never be updated when the order header is updated.</span></span>
    - <span data-ttu-id="12b11-113">**Uppmaning** – Användaren uppmanas att välja om orderraderna ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="12b11-113">**Prompt** – The user will be prompted to select whether the order lines should be updated.</span></span>
