---
title: Omvända inställningar i journaler och på rader
description: Det här avsnittet tar upp varför en återföringspost som bokfördes i en allmän journal kanske inte inkluderas i den bokförda transaktionen.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 74020f6fc9b0fa8e05a1e2a09fd13dcd60490dc0
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028586"
---
# <a name="reverse-settings-on-journals-and-lines"></a><span data-ttu-id="acb64-103">Omvända inställningar i journaler och på rader</span><span class="sxs-lookup"><span data-stu-id="acb64-103">Reverse settings on journals and lines</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="acb64-104">Det här avsnittet tar upp varför en återföringspost som bokfördes i en allmän journal kanske inte inkluderas i den bokförda transaktionen.</span><span class="sxs-lookup"><span data-stu-id="acb64-104">This topic addresses why a reversing entry that was entered on a general journal might not be included on the posted transaction.</span></span>  

## <a name="symptom"></a><span data-ttu-id="acb64-105">Symptom</span><span class="sxs-lookup"><span data-stu-id="acb64-105">Symptom</span></span>

<span data-ttu-id="acb64-106">En allmän journal innehåller en återföringspost och ett återföringsdatum i journalen.</span><span class="sxs-lookup"><span data-stu-id="acb64-106">A general journal includes a reversing entry and reversing date on the journal.</span></span> <span data-ttu-id="acb64-107">När du bokför journalen återförs ingen av verifikationerna.</span><span class="sxs-lookup"><span data-stu-id="acb64-107">When you post the journal, none of the vouchers are reversed.</span></span> <span data-ttu-id="acb64-108">Varför inträffar det här?</span><span class="sxs-lookup"><span data-stu-id="acb64-108">Why does this happen?</span></span>

## <a name="resolution"></a><span data-ttu-id="acb64-109">Lösning</span><span class="sxs-lookup"><span data-stu-id="acb64-109">Resolution</span></span>

<span data-ttu-id="acb64-110">När journalen bokförs tittar reverseringsprocessen bara på inställningarna för **Återföringspost** och **Återföringsdatum** i avsnittet **Rader** i verifikationen.</span><span class="sxs-lookup"><span data-stu-id="acb64-110">When the journal is posted, the reversing process looks only at the **Revering entry** and **Reversing date** settings on the **Lines** section of the voucher.</span></span> <span data-ttu-id="acb64-111">Med den här metoden kan en journal att innehålla verifikationer markerade för återföring och andra som inte är det.</span><span class="sxs-lookup"><span data-stu-id="acb64-111">This approach allows a journal to include some vouchers that are marked for reversing, and others that are not.</span></span>

<span data-ttu-id="acb64-112">Värdena från journalen används bara som standard när *nya* rader läggs till.</span><span class="sxs-lookup"><span data-stu-id="acb64-112">The values from the journal are only used as defaults when adding *new* lines.</span></span> <span data-ttu-id="acb64-113">Att ändra värdena i journalen påverkar inte befintliga rader.</span><span class="sxs-lookup"><span data-stu-id="acb64-113">Changing the values on the journal doesn’t affect existing lines.</span></span> <span data-ttu-id="acb64-114">I det här exemplet angavs verifikationsraderna först.</span><span class="sxs-lookup"><span data-stu-id="acb64-114">In this example, the voucher lines were entered first.</span></span> <span data-ttu-id="acb64-115">När du anger radinformationen innan du anger journalen som återföring tillämpas inte beteckningen som en återföringspost och ett återföringsdatum på befintliga rader.</span><span class="sxs-lookup"><span data-stu-id="acb64-115">When you enter the line detail before designating the journal as reversing, the designation as a reversing entry and date won't be applied to any existing lines.</span></span>

<span data-ttu-id="acb64-116">Om du ändrar återföringsposten eller återföringsdatumet på en befintlig rad sprids den ändringen till andra rader i samma verifikation.</span><span class="sxs-lookup"><span data-stu-id="acb64-116">Changing the reversing entry or reversing date on an existing line propagates that change to other lines in the same voucher.</span></span> <span data-ttu-id="acb64-117">Optimera prestanda genom att inte uppdatera rutnätet efter att ändringar har spridits till andra rader.</span><span class="sxs-lookup"><span data-stu-id="acb64-117">To optimize performance, the grid is not refreshed after propagating changes to other Lines.</span></span> <span data-ttu-id="acb64-118">Det går att visa de uppdaterade värdena genom att uppdatera rutnätet.</span><span class="sxs-lookup"><span data-stu-id="acb64-118">You can display the updated values by refreshing the grid.</span></span>


