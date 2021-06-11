---
title: Du uppmanas att spara inställningarna för artikeldisponering även om du inte gör några ändringar
description: Du uppmanas att spara inställningarna för artikeldisponering även om du inte gör några ändringar.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dfa974740420433af1e1b37630b22509510c91b
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049490"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a><span data-ttu-id="f293a-103">Du uppmanas att spara inställningarna för artikeldisponering även om du inte gör några ändringar</span><span class="sxs-lookup"><span data-stu-id="f293a-103">You're prompted to save item coverage settings even though you made no changes</span></span>

<span data-ttu-id="f293a-104">KB-nummer: 4615588</span><span class="sxs-lookup"><span data-stu-id="f293a-104">KB number: 4615588</span></span>

## <a name="symptoms"></a><span data-ttu-id="f293a-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="f293a-105">Symptoms</span></span>

<span data-ttu-id="f293a-106">I vissa situationer kanske du får följande meddelande när du öppnar sidan **Artikeldisponering** efter att du importerat artiklar via enheten *Artikeldisponering V2*:</span><span class="sxs-lookup"><span data-stu-id="f293a-106">In some scenarios, you might receive the following message when you open the **Item coverage** page after you import items through the *Item coverage V2* entity:</span></span>

> <span data-ttu-id="f293a-107">Vill du spara ändringarna innan du stänger?</span><span class="sxs-lookup"><span data-stu-id="f293a-107">Do you want to save your changes before closing?</span></span>

<span data-ttu-id="f293a-108">Du får det här meddelandet även om du inte har gjort några ändringar.</span><span class="sxs-lookup"><span data-stu-id="f293a-108">You receive this message even though you haven't made any changes.</span></span>

## <a name="resolution"></a><span data-ttu-id="f293a-109">Lösning</span><span class="sxs-lookup"><span data-stu-id="f293a-109">Resolution</span></span>

<span data-ttu-id="f293a-110">Sidan **Artikeldisponering** innehåller komplex standardlogik som kan medföra att meddelandet visas när direkta ändringar nyligen har gjorts i databasen, t.ex. genom enhetsimport.</span><span class="sxs-lookup"><span data-stu-id="f293a-110">The **Item coverage** page includes complex defaulting logic that might cause the message to be shown after direct changes have recently been made in the database, such as through entity import.</span></span> <span data-ttu-id="f293a-111">Till exempel ställs entitetsfältet `AREGENERALSETTINGSOVERRIDDEN` anges till *Nej*, men du importerar en fil som innehåller nya eller modifierade värden för fält som `PRODUCTCOVERAGEGROUPID` och/eller `VENDORACCOUNTNUMBER`.</span><span class="sxs-lookup"><span data-stu-id="f293a-111">For example, the `AREGENERALSETTINGSOVERRIDDEN` entity field is set to *No*, but you import a file that provides new or modified values for fields such as `PRODUCTCOVERAGEGROUPID` and/or `VENDORACCOUNTNUMBER`.</span></span> <span data-ttu-id="f293a-112">Eftersom fältet är inställt på `AREGENERALSETTINGSOVERRIDDEN` anges till *Nej*, värdena rensas automatiskt från fälten när du öppnar sidan **Artikeldisponering** för första gången efter importen.</span><span class="sxs-lookup"><span data-stu-id="f293a-112">In this case, because the `AREGENERALSETTINGSOVERRIDDEN` field is set to *No*, the values are automatically cleared from the fields when you open the **Item coverage** page for the first time after the import.</span></span> <span data-ttu-id="f293a-113">Om du sparar ändringarna så som meddelanderutan uppmanas, lagras de i databasen.</span><span class="sxs-lookup"><span data-stu-id="f293a-113">If you save the changes as the message box prompts, they are stored in the database.</span></span> <span data-ttu-id="f293a-114">I annat fall visas samma meddelande nästa gång du öppnar sidan.</span><span class="sxs-lookup"><span data-stu-id="f293a-114">Otherwise, you will receive the same message the next time that you open the page.</span></span>

<span data-ttu-id="f293a-115">Om du vill förhindra detta beteende, men även inkludera värden för fält som `PRODUCTCOVERAGEGROUPID`via enhetsimport, ställer du in `AREGENERALSETTINGSOVERRIDDEN` på *Ja* när du importerar.</span><span class="sxs-lookup"><span data-stu-id="f293a-115">To prevent this behavior but also include values for fields such as `PRODUCTCOVERAGEGROUPID` through entity import, set `AREGENERALSETTINGSOVERRIDDEN` to *Yes* when you import.</span></span>
