---
title: Uppgradering av enstaka verifikationsjournaler och valutaomvärderingar
description: Vissa organisationer anger journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de kör också processen Omräkning i utländsk valuta för Kundreskontra eller Leverantörsreskontra. Det här avsnittet beskriver de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 for Operations version 1611.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7c06e54c5be8d0a410b9f15f2a89def3076b4638
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681034"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a><span data-ttu-id="f1c0f-104">Uppgradera journaler med enstaka verifikationer och valutaomvärderingar</span><span class="sxs-lookup"><span data-stu-id="f1c0f-104">Upgrade single-voucher journals and currency revaluations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f1c0f-105">Vissa organisationer anger journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de kör också processen Omräkning i utländsk valuta för Kundreskontra eller Leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="f1c0f-105">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="f1c0f-106">Det här avsnittet beskriver de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="f1c0f-106">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="f1c0f-107">Gör så här när du uppgraderar till Microsoft Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="f1c0f-107">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="f1c0f-108">Innan du uppgraderar till Finance and Operations kör du processerna för omvärdering i utländsk valuta för Kundreskontra och Leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="f1c0f-108">Before you upgrade to Finance and Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="f1c0f-109">Ange fältet **Metod** till **Fakturadatum**.</span><span class="sxs-lookup"><span data-stu-id="f1c0f-109">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="f1c0f-110">En omvärderingstransaktion skapas som återför den senaste omvärderingen i utländsk valuta.</span><span class="sxs-lookup"><span data-stu-id="f1c0f-110">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="f1c0f-111">Därför värderas de öppna transaktionerna till sin ursprungliga redovisningsvaluta.</span><span class="sxs-lookup"><span data-stu-id="f1c0f-111">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="f1c0f-112">Uppgradera till version 1611.</span><span class="sxs-lookup"><span data-stu-id="f1c0f-112">Upgrade to version 1611.</span></span>
3.  <span data-ttu-id="f1c0f-113">Kör processerna för omräkning i utländsk valuta för Leverantörsreskontra och Kundreskontra</span><span class="sxs-lookup"><span data-stu-id="f1c0f-113">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="f1c0f-114">Denna gång ändrar du fältet **Metod** till **Standard**.</span><span class="sxs-lookup"><span data-stu-id="f1c0f-114">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="f1c0f-115">En ny omvärderingstransaktion skapas som baseras på de aktuella valutakurserna.</span><span class="sxs-lookup"><span data-stu-id="f1c0f-115">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="f1c0f-116">Den här transaktionen registrerar orealiserad vinst/förlust och korrekt summeringskonto i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="f1c0f-116">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>
