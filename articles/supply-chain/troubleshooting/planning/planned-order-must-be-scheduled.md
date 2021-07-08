---
title: Planerad tillverkningsorder måste tidsplaneras innan den kan bekräftas
description: När du försöker bekräfta en planerad order visas ett felmeddelande om att ordern måste tidsplaneras innan den kan bekräftas.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294186"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a><span data-ttu-id="8f0e6-103">Planerad tillverkningsorder måste tidsplaneras innan den kan bekräftas</span><span class="sxs-lookup"><span data-stu-id="8f0e6-103">Planned production order must be scheduled before it can be firmed</span></span>

<span data-ttu-id="8f0e6-104">Felkod: SYS309802</span><span class="sxs-lookup"><span data-stu-id="8f0e6-104">Error code: SYS309802</span></span>

## <a name="symptoms"></a><span data-ttu-id="8f0e6-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="8f0e6-105">Symptoms</span></span>

<span data-ttu-id="8f0e6-106">När du har bekräftat planerade order visas följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="8f0e6-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="8f0e6-107">Den planerade produktionsordern måste tidsplaneras innan den kan bekräftas.</span><span class="sxs-lookup"><span data-stu-id="8f0e6-107">The planned production order must be scheduled before it can be firmed.</span></span>

## <a name="cause"></a><span data-ttu-id="8f0e6-108">Orsak</span><span class="sxs-lookup"><span data-stu-id="8f0e6-108">Cause</span></span>

<span data-ttu-id="8f0e6-109">De planerade start- och slutdatumen kan inte vara tomma.</span><span class="sxs-lookup"><span data-stu-id="8f0e6-109">The scheduled start and end dates can't be blank.</span></span>

## <a name="resolution"></a><span data-ttu-id="8f0e6-110">Lösning</span><span class="sxs-lookup"><span data-stu-id="8f0e6-110">Resolution</span></span>

<span data-ttu-id="8f0e6-111">Följ de här stegen om du vill ange start- och slutdatum för den planerade ordern.</span><span class="sxs-lookup"><span data-stu-id="8f0e6-111">To specify start and end dates for the planned order, follow these steps.</span></span>

1. <span data-ttu-id="8f0e6-112">Gå till **Huvudplanering \> Huvudplanering \> Planerade order**.</span><span class="sxs-lookup"><span data-stu-id="8f0e6-112">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="8f0e6-113">Öppna relevant planerad ordern.</span><span class="sxs-lookup"><span data-stu-id="8f0e6-113">Open the relevant planned order.</span></span>
1. <span data-ttu-id="8f0e6-114">På snabbflikarna **Allmänt**, i avsnittet **Tidsplanerat**, anger du datum i fälten **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="8f0e6-114">On the **General** FastTab, in the **Scheduled** section, specify dates in the **Start date** and **End date** fields.</span></span>
