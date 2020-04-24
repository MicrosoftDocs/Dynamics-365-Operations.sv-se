---
title: Bearbetning av utgiftskvitto
description: Det här ämnet ger information om optisk teckenläsning (OCR) av kvitton. Den här funktionen är utformad för att förbättra användarupplevelsen när utgiftsrapporter skapas i Microsoft Dynamics 365 Finance.
author: stsporen
manager: AnnBe
ms.date: 11/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: efba2faf9428d9b556d74273bc7daadba7211c48
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "3248973"
---
# <a name="expense-receipt-processing"></a><span data-ttu-id="8414b-104">Bearbetning av utgiftskvitto</span><span class="sxs-lookup"><span data-stu-id="8414b-104">Expense receipt processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8414b-105">Utgiftsregistrering har förbättrats genom introduktion av OCR (optisk teckenläsning) för kvitton.</span><span class="sxs-lookup"><span data-stu-id="8414b-105">Expense entry has been enhanced through the introduction of optical character recognition (OCR) processing for receipts.</span></span> <span data-ttu-id="8414b-106">Den här funktionen är utformad för att förbättra användarupplevelsen när utgiftsrapporter skapas.</span><span class="sxs-lookup"><span data-stu-id="8414b-106">This feature is designed to improve the user experience when expense reports are created.</span></span>

## <a name="key-features"></a><span data-ttu-id="8414b-107">Nyckelfunktioner</span><span class="sxs-lookup"><span data-stu-id="8414b-107">Key features</span></span>

- <span data-ttu-id="8414b-108">Handelsnamn, datum och totalbelopp hämtas från kvitton.</span><span class="sxs-lookup"><span data-stu-id="8414b-108">The merchant name, date, and total amount are extracted from receipts.</span></span>
- <span data-ttu-id="8414b-109">Funktionen försöker matcha ej kopplade kvitton till ej kopplade utgiftstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="8414b-109">The feature tries to match unattached receipts to unattached expense transactions.</span></span>
- <span data-ttu-id="8414b-110">Användare kan skapa manuellt registrerade utgiftstransaktioner från kvitton.</span><span class="sxs-lookup"><span data-stu-id="8414b-110">Users can create manually entered expense transactions from receipts.</span></span>

## <a name="usage-examples"></a><span data-ttu-id="8414b-111">Exempel på användning</span><span class="sxs-lookup"><span data-stu-id="8414b-111">Usage examples</span></span>

- <span data-ttu-id="8414b-112">**Koppla automatiskt kvitton som inkluderar kreditkortstransaktioner när en utgiftsrapport skapas.**</span><span class="sxs-lookup"><span data-stu-id="8414b-112">**Automatically attach receipts that include credit card transactions when an expense report is created.**</span></span>

    1. <span data-ttu-id="8414b-113">Öppna arbetsytan **utgiftshantering**.</span><span class="sxs-lookup"><span data-stu-id="8414b-113">Open the **Expense management** workspace.</span></span>
    2. <span data-ttu-id="8414b-114">På fliken **kvitton** kontrollerar du att det inte finns några kopplade kvitton.</span><span class="sxs-lookup"><span data-stu-id="8414b-114">On the **Receipts** tab, verify that unattached receipts exist.</span></span> <span data-ttu-id="8414b-115">Du kan även överföra kvitton på fliken **kvitton**.</span><span class="sxs-lookup"><span data-stu-id="8414b-115">You can also upload receipts on the **Receipts** tab.</span></span>
    3. <span data-ttu-id="8414b-116">På fliken **utgifter** kontrollerar du att det inte finns några kopplade utgifter.</span><span class="sxs-lookup"><span data-stu-id="8414b-116">On the **Expenses** tab, verify that unattached expenses exist.</span></span> <span data-ttu-id="8414b-117">Vanligtvis importerar utgiftsadministratören dessa utgifter från kreditkortsutfärdaren.</span><span class="sxs-lookup"><span data-stu-id="8414b-117">Typically, the expense administrator imports these expenses from the credit card provider.</span></span>
    4. <span data-ttu-id="8414b-118">Välj **Ny utgiftsrapport**.</span><span class="sxs-lookup"><span data-stu-id="8414b-118">Select **New expense report**.</span></span> <span data-ttu-id="8414b-119">Observera att du kan inkludera utgifter och kvitton även när du skapar en utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="8414b-119">Notice that you can include expenses, and receipts, now as well, when you create an expense report.</span></span> <span data-ttu-id="8414b-120">Om du lägger till både utgifter och kvitton utlöses automatisk matchning av kvitton mot utgifterna.</span><span class="sxs-lookup"><span data-stu-id="8414b-120">If you add both expenses and receipts, automatic matching of the receipts against the expenses is triggered.</span></span>

- <span data-ttu-id="8414b-121">**Skapa en utgift eller matcha en utgift från ett kvitto.**</span><span class="sxs-lookup"><span data-stu-id="8414b-121">**Create an expense, or match an expense from a receipt.**</span></span>

    1. <span data-ttu-id="8414b-122">På en utgiftsrapport på fliken **kvitton** bifogar du ett kvitto genom att välja **Lägg kvitton**.</span><span class="sxs-lookup"><span data-stu-id="8414b-122">On an expense report, on the **Receipts** tab, attach a receipt by selecting **Add receipts**.</span></span>
    2. <span data-ttu-id="8414b-123">Lägg märke till under den uppladdade bilden av kvittot, observera alternativet **Skapa** och **Matcha**.</span><span class="sxs-lookup"><span data-stu-id="8414b-123">Under the uploaded image of the receipt, notice the **Create** and **Match** options.</span></span>

        - <span data-ttu-id="8414b-124">Välj **skapa** om du vill skapa en manuellt angiven utgiftstransaktion och fyll i de värden som hämtas från kvittot.</span><span class="sxs-lookup"><span data-stu-id="8414b-124">Select **Create** to create a manually entered expense transaction and fill in the values that are extracted from the receipt.</span></span>
        - <span data-ttu-id="8414b-125">Om du väljer **matcha** kommer systemet att försöka matcha en befintlig utgift mot kvittot.</span><span class="sxs-lookup"><span data-stu-id="8414b-125">If you select **Match**, the system tries to match an existing expense to the receipt.</span></span>

## <a name="installation"></a><span data-ttu-id="8414b-126">Installation</span><span class="sxs-lookup"><span data-stu-id="8414b-126">Installation</span></span>

<span data-ttu-id="8414b-127">Den här funktionen fungerar tillsammans med **Utgiftsrapporter på nytt sätt**, så att utgiftsupplevelsen blir enklare att använda.</span><span class="sxs-lookup"><span data-stu-id="8414b-127">This feature works in combination with the **Expense reports re-imagined** feature to help simplify the expense experience.</span></span>

<span data-ttu-id="8414b-128">Om du vill använda de avancerade utgiftsfunktionerna installerar du tillägget utgiftshanteringstjänst för Microsoft Dynamics 365 Finance och aktiverar funktionerna i din instans.</span><span class="sxs-lookup"><span data-stu-id="8414b-128">To use these advanced expense capabilities, install the Expense Management Service add-in for Microsoft Dynamics 365 Finance, and turn on the features in your instance.</span></span> <span data-ttu-id="8414b-129">Du kan komma åt tillägget från ditt projekt i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8414b-129">You can access the add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="8414b-130">Logga in på LCS och öppna den önskade miljön.</span><span class="sxs-lookup"><span data-stu-id="8414b-130">Sign in to LCS, and open the desired environment.</span></span>
2. <span data-ttu-id="8414b-131">Gå till **Fullständiga detaljer**.</span><span class="sxs-lookup"><span data-stu-id="8414b-131">Go to **Full details**.</span></span>
3. <span data-ttu-id="8414b-132">Välj **underhåll** eller rulla ned till snabbfliken **miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="8414b-132">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
4. <span data-ttu-id="8414b-133">Välj **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="8414b-133">Select **Install a new add-in**.</span></span>
5. <span data-ttu-id="8414b-134">Välj **utgiftshanteringstjänst**.</span><span class="sxs-lookup"><span data-stu-id="8414b-134">Select **Expense Management Service**.</span></span>
6. <span data-ttu-id="8414b-135">Följ installationsguiden och godkänn villkoren.</span><span class="sxs-lookup"><span data-stu-id="8414b-135">Follow the installation guide, and agree to the terms and conditions.</span></span>
7. <span data-ttu-id="8414b-136">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="8414b-136">Select **Install**.</span></span>

<span data-ttu-id="8414b-137">I arbetsytan **utgiftshantering** aktiverar du följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="8414b-137">In the **Feature management** workspace, turn on the following features:</span></span>

- <span data-ttu-id="8414b-138">Utgiftsrapporter på nytt sätt</span><span class="sxs-lookup"><span data-stu-id="8414b-138">Expense reports re-imagined</span></span>
- <span data-ttu-id="8414b-139">Matcha automatiskt och skapa utgift från kvitto</span><span class="sxs-lookup"><span data-stu-id="8414b-139">Auto-match and create expense from receipt</span></span>

<span data-ttu-id="8414b-140">När du aktiverar dessa funktioner utförs följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="8414b-140">When you turn on these features the following actions occur:</span></span>

- <span data-ttu-id="8414b-141">Den befintliga arbetsytan för **utgiftshantering** ersätts med den nya arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="8414b-141">The existing **Expense management** workspace is replaced with the new workspace.</span></span>
- <span data-ttu-id="8414b-142">Ett nytt menyalternativ för utgiftsfältets synlighet läggs till.</span><span class="sxs-lookup"><span data-stu-id="8414b-142">A new menu item for expense field visibility is added.</span></span>
- <span data-ttu-id="8414b-143">Du kan fortfarande öppna den tidigare sidan **utgiftsrapporter** genom att gå till **utgiftshantering > mina utgifter > utgiftsrapporter**.</span><span class="sxs-lookup"><span data-stu-id="8414b-143">You can still open the former **Expense reports** page by going to **Expense management > My expenses > Expense reports**.</span></span>
- <span data-ttu-id="8414b-144">Arbetsflöden och eventuella godkännanden leder fortfarande till sidan för befintliga utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="8414b-144">Workflows and any approvals still take you to the existing expense reports page.</span></span>
- <span data-ttu-id="8414b-145">Kvitton kommer att bearbetas via Microsoft Azure Cognitive Services och metadata extraheras och läggs till.</span><span class="sxs-lookup"><span data-stu-id="8414b-145">Receipts will be processed through Microsoft Azure Cognitive Services, and metadata will be extracted and added.</span></span>
- <span data-ttu-id="8414b-146">Ett alternativ läggs till som gör att du kan skapa en utgiftsrapport som innehåller matchade ej kopplade kvitton.</span><span class="sxs-lookup"><span data-stu-id="8414b-146">An option is added that lets you create an expense report that includes matched unattached receipts.</span></span>
- <span data-ttu-id="8414b-147">Ett alternativ som läggs till i utgiftsrapporter gör att du kan skapa en utgiftsrad från ett kvitto eller ett försök att matcha en befintlig inleverans till en befintlig utgiftsrad.</span><span class="sxs-lookup"><span data-stu-id="8414b-147">An option that is added to expense reports lets you create an expense line from a receipt, or attempts to match an existing receipt to an existing expense line.</span></span>

<span data-ttu-id="8414b-148">Mer information om hur utgiftsrapporter är förväntat finns i [Utgiftsrapporter på nytt sätt](ExpenseWorkspaceNew.md).</span><span class="sxs-lookup"><span data-stu-id="8414b-148">For more information about the Expense reports re-imagined feature, see [Expense reports reimagined](ExpenseWorkspaceNew.md).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8414b-149">Vanliga frågor</span><span class="sxs-lookup"><span data-stu-id="8414b-149">Frequently asked questions</span></span>

<span data-ttu-id="8414b-150">**Används mina data för modellerna i Microsoft?**</span><span class="sxs-lookup"><span data-stu-id="8414b-150">**Does Microsoft use my data for its models?**</span></span>

<span data-ttu-id="8414b-151">Nej, Microsoft har skapat en allmän modell för maskininlärning för den mottagande bearbetningstjänsten.</span><span class="sxs-lookup"><span data-stu-id="8414b-151">No, Microsoft has built a general machine learning model for its receipt processing service.</span></span> <span data-ttu-id="8414b-152">Den här modellen är inte baserad på kvitton som du har överfört.</span><span class="sxs-lookup"><span data-stu-id="8414b-152">This model isn't based on the receipts that you upload.</span></span>

<span data-ttu-id="8414b-153">**Var är den här funktionen tillgänglig och bearbetad?**</span><span class="sxs-lookup"><span data-stu-id="8414b-153">**Where is this feature available and processed?**</span></span>

<span data-ttu-id="8414b-154">USA stöds för närvarande.</span><span class="sxs-lookup"><span data-stu-id="8414b-154">Currently, the United States is supported.</span></span>

<span data-ttu-id="8414b-155">**Var hamnar mina kvitton?**</span><span class="sxs-lookup"><span data-stu-id="8414b-155">**Where do my receipts go?**</span></span>

<span data-ttu-id="8414b-156">Finance kommer att kontakta Cognitive Services för att extrahera fältdata.</span><span class="sxs-lookup"><span data-stu-id="8414b-156">Finance will contact Cognitive Services to extract the field data.</span></span> <span data-ttu-id="8414b-157">Cognitive Services behåller en kopia av ditt kvitto i upp till 24 timmar under bearbetningen.</span><span class="sxs-lookup"><span data-stu-id="8414b-157">Cognitive Services will retain a copy of your receipt for up to 24 hours while processing occurs.</span></span> <span data-ttu-id="8414b-158">När bearbetningen är klar kommer Cognitive Services att ta bort kvittot.</span><span class="sxs-lookup"><span data-stu-id="8414b-158">After processing is completed, Cognitive Services will remove the receipt.</span></span> <span data-ttu-id="8414b-159">Kvitton lagras fortfarande i Finance.</span><span class="sxs-lookup"><span data-stu-id="8414b-159">Receipts are still stored in Finance.</span></span>

<span data-ttu-id="8414b-160">Mer information finns i [aktivera kvittoförståelse med formulärtolkens nya förmåga](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span><span class="sxs-lookup"><span data-stu-id="8414b-160">For more information, see [Enable receipt understanding with Form Recognizer's new capability](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span></span>
