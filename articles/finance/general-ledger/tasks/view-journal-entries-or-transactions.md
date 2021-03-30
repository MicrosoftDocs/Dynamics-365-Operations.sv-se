---
title: Visa poster eller transaktioner i redovisningsjournal
description: Detta förfarande anger hur du använder verifikationstransaktionbegäran för att söka efter poster i redovisningsjournaler eller transaktioner.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm, LedgerTransVoucher, LedgerTransBase, Originaldocuments
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: da5979067639834929d10c0a8c1e372b2235a7af
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222081"
---
# <a name="view-journal-entries-or-transactions"></a><span data-ttu-id="b580d-103">Visa poster eller transaktioner i redovisningsjournal</span><span class="sxs-lookup"><span data-stu-id="b580d-103">View journal entries or transactions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b580d-104">Detta förfarande anger hur du använder verifikationstransaktionbegäran för att söka efter poster i redovisningsjournaler eller transaktioner.</span><span class="sxs-lookup"><span data-stu-id="b580d-104">This procedure shows how to use the Voucher transactions inquiry to search for journal entries or transactions.</span></span>

1. <span data-ttu-id="b580d-105">Gå till **navigeringsfönster > Moduler > Redovisning > Förfrågningar och rapporter > Verifikationstransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="b580d-105">Go to **Navigation pane > Modules > General ledger > Inquiries and reports > Voucher transactions**.</span></span>
2. <span data-ttu-id="b580d-106">Ange fältet som du vill ange ett filterkriterium för.</span><span class="sxs-lookup"><span data-stu-id="b580d-106">Select the field for which you want to define a filter criteria.</span></span>
3. <span data-ttu-id="b580d-107">Ange dina filterkriterier för det valda fältet.</span><span class="sxs-lookup"><span data-stu-id="b580d-107">Enter your filter critieria for the selected field.</span></span> <span data-ttu-id="b580d-108">Du kan filtrera efter ett enskilt värde eller ett intervall.</span><span class="sxs-lookup"><span data-stu-id="b580d-108">You could filter on a single value or a range.</span></span> <span data-ttu-id="b580d-109">Kontrollera att korrekt syntax används när du definierar ett intervall.</span><span class="sxs-lookup"><span data-stu-id="b580d-109">When defining a range, make sure the correct syntax is used.</span></span> <span data-ttu-id="b580d-110">Värdena ska separeras med dubbla punkter (.).</span><span class="sxs-lookup"><span data-stu-id="b580d-110">The values should be separated by a double period (..).</span></span>  
4. <span data-ttu-id="b580d-111">Klicka på fliken **Sammanfogningar** om du vill lägga till ytterligare register att filtrera ifrån.</span><span class="sxs-lookup"><span data-stu-id="b580d-111">Click the **Joins** tab to add additional tables from which to filter.</span></span>
5. <span data-ttu-id="b580d-112">Välj **Register/Allmän journalpost** i trädet.</span><span class="sxs-lookup"><span data-stu-id="b580d-112">In the tree, select **Tables/General journal entry**.</span></span>
6. <span data-ttu-id="b580d-113">Klicka på **Lägg till registersammanfogning**.</span><span class="sxs-lookup"><span data-stu-id="b580d-113">Click **Add table join**.</span></span>
7. <span data-ttu-id="b580d-114">Klicka på **Avbryt** om du väljer att inte lägga till ett ytterligare register.</span><span class="sxs-lookup"><span data-stu-id="b580d-114">Click **Cancel** if you decide not to add an additional table.</span></span>
8. <span data-ttu-id="b580d-115">Klicka på fliken **Sortiment**.</span><span class="sxs-lookup"><span data-stu-id="b580d-115">Click the **Range** tab.</span></span>
9. <span data-ttu-id="b580d-116">Klicka på **OK** om du vill köra frågan.</span><span class="sxs-lookup"><span data-stu-id="b580d-116">Click **OK** to run the query.</span></span>
10. <span data-ttu-id="b580d-117">Klicka på **Transaktionsursprung** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b580d-117">On the Action pane, click **Transaction origin**.</span></span> <span data-ttu-id="b580d-118">Olika knappar för rutnätet kan användas för att utforska ytterligare information om den valda verifikationsposten.</span><span class="sxs-lookup"><span data-stu-id="b580d-118">Various buttons about the grid can be used to research additional information about the selected record of the voucher.</span></span> <span data-ttu-id="b580d-119">Vissa knappar kanske inte är tillgängliga, beroende på typen av transaktion och transaktionsegenskaperna.</span><span class="sxs-lookup"><span data-stu-id="b580d-119">Some buttons may not be available, depending on the type of transaction and characteristics of the transaction.</span></span>
11. <span data-ttu-id="b580d-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b580d-120">Close the page.</span></span>
12. <span data-ttu-id="b580d-121">Klicka på **Ursprungsdokument** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b580d-121">On the Action pane, Click **Original document**.</span></span>
13. <span data-ttu-id="b580d-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b580d-122">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]