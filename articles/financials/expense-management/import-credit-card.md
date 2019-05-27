---
title: Importera och underhålla kreditkortstransaktioner
description: Detta avsnitt förklarar hur du importerar och underhåller utgiftsrelaterade kreditkortstransaktioner. Dessa transaktioner kan konfigureras att importeras automatiskt enligt ett återkommande schema, eller också importeras manuellt efter behov.
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPbsMainDataLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 9674cf495b7fdd40d8672580b9d10e9ebe626bb0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565123"
---
# <a name="import-and-maintain-credit-card-transactions"></a><span data-ttu-id="c80f7-104">Importera och underhålla kreditkortstransaktioner</span><span class="sxs-lookup"><span data-stu-id="c80f7-104">Import and maintain credit card transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c80f7-105">Utgiftsrelaterade kreditkortstransaktioner kan konfigureras att importeras automatiskt enligt ett återkommande schema.</span><span class="sxs-lookup"><span data-stu-id="c80f7-105">Expense-related credit card transactions can be set up so that they are automatically imported on a recurring schedule.</span></span> <span data-ttu-id="c80f7-106">Alternativt kan transaktionerna även importeras manuellt efter behov.</span><span class="sxs-lookup"><span data-stu-id="c80f7-106">Alternatively, the transactions can be manually imported as they are required.</span></span> <span data-ttu-id="c80f7-107">Kreditkortstransaktionerna importeras via dataentiteten för kreditkortstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="c80f7-107">The credit card transactions are imported through the Credit card transactions data entity.</span></span>

<span data-ttu-id="c80f7-108">Mer information om dataentiteter finns i [Dataentiteter](../../dev-itpro/data-entities/data-entities.md).</span><span class="sxs-lookup"><span data-stu-id="c80f7-108">For more information about data entities, see [Data entities](../../dev-itpro/data-entities/data-entities.md).</span></span>

## <a name="import-credit-card-transactions"></a><span data-ttu-id="c80f7-109">Importera kreditkortstransaktioner</span><span class="sxs-lookup"><span data-stu-id="c80f7-109">Import credit card transactions</span></span>

1. <span data-ttu-id="c80f7-110">På sidan **Kreditkortstransaktioner** väljer du **Importera transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="c80f7-110">On the **Credit card transactions** page, select **Import transactions**.</span></span> <span data-ttu-id="c80f7-111">Om du öppnar datahanteringen för första gången måste systemet uppdatera listan över dataentiteter innan du kan fortsätta.</span><span class="sxs-lookup"><span data-stu-id="c80f7-111">If you’re opening data management for the first time, the system must update the list of data entities before you can continue.</span></span>
2. <span data-ttu-id="c80f7-112">Ange en unik beskrivning för importjobbet i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="c80f7-112">In the **Name** field, enter a unique description of the import job.</span></span>
3. <span data-ttu-id="c80f7-113">I fältet **Källdataformat** väljer du formatet på den fil som innehåller de kreditkortstransaktioner som du vill importera.</span><span class="sxs-lookup"><span data-stu-id="c80f7-113">In the **Source data format** field, select the format of the file that contains the credit card transactions to import.</span></span>
4. <span data-ttu-id="c80f7-114">Välj **Ladda upp** och leta sedan upp och välj den fil du vill importera.</span><span class="sxs-lookup"><span data-stu-id="c80f7-114">Select **Upload**, and then find and select the file to import.</span></span>
5. <span data-ttu-id="c80f7-115">När filen har laddats upp väljer du länken **Visa karta** i panelen för att validera mappningen av filen för kreditkortstransaktionerna samt kolumnerna för kreditkortstransaktionernas dataentitet.</span><span class="sxs-lookup"><span data-stu-id="c80f7-115">After the file has been uploaded, validate the mapping of the credit card transaction file and the columns of the Credit card transactions data entity by selecting the **View map** link on the tile.</span></span> <span data-ttu-id="c80f7-116">Om mappningsfel uppstår eller du måste ändra mappningen, använder du antingen fliken **Mappningsvisualisering** eller fliken **Mappningsinformation** för att utföra mappningsändringarna.</span><span class="sxs-lookup"><span data-stu-id="c80f7-116">If there are mapping errors, or if you must change the mapping, make the mapping changes from either the **Mapping visualization** tab or the **Mapping details** tab.</span></span>
6. <span data-ttu-id="c80f7-117">Välj **Skapa återkommande datajobb** för att automatisera kreditkortstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="c80f7-117">To automate the credit card transactions, select **Create recurring data job**.</span></span> <span data-ttu-id="c80f7-118">Du kan sedan välja den upprepningsfrekvens som anger hur ofta kreditkortstransaktionerna ska importeras.</span><span class="sxs-lookup"><span data-stu-id="c80f7-118">You can then set the recurrence that defines how often credit card transactions should be imported.</span></span> <span data-ttu-id="c80f7-119">Välj **OK** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="c80f7-119">When you’ve finished, select **OK**.</span></span>
7. <span data-ttu-id="c80f7-120">Välj **Importera** om du vill importera vald fil nu.</span><span class="sxs-lookup"><span data-stu-id="c80f7-120">To import the selected file now, select **Import**.</span></span>
8. <span data-ttu-id="c80f7-121">Om något fel skulle uppstå i samband med import kan du visa körningsloggen eller underliggande data för att se de fel som du måste åtgärda i syfte att säkerställa en lyckad import.</span><span class="sxs-lookup"><span data-stu-id="c80f7-121">If errors occur during the import, you can view the execution log or staging data to see the errors that you must fix to help guarantee a successful import.</span></span>

> [!NOTE]
> <span data-ttu-id="c80f7-122">Om du måste importera mer än ett filformat måste du skapa separata importjobb för respektive formattyp.</span><span class="sxs-lookup"><span data-stu-id="c80f7-122">If you must import more than one file format, you must create separate import jobs for each format type.</span></span>

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a><span data-ttu-id="c80f7-123">Omtilldela kreditkortstransaktioner för uppsagda medarbetare</span><span class="sxs-lookup"><span data-stu-id="c80f7-123">Reassign the credit card transactions for terminated employees</span></span>

<span data-ttu-id="c80f7-124">När en medarbetarpost raderas, avaktiveras medarbetarens Active Directory Domain Services (AD DS)-konto.</span><span class="sxs-lookup"><span data-stu-id="c80f7-124">After an employee record is terminated, the employee’s Active Directory Domain Services (AD DS) account is disabled.</span></span> <span data-ttu-id="c80f7-125">Det kan emellertid fortfarande finnas kreditkortstransaktioner kvar som måste betalas och ersättas.</span><span class="sxs-lookup"><span data-stu-id="c80f7-125">However, there might be active credit card transactions that must still be expensed and reimbursed.</span></span> <span data-ttu-id="c80f7-126">Via sidan **Kreditkortstransaktioner** kan du omtilldela medarbetaren för samtliga kreditkortstransaktioner där tillhörande medarbetare har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="c80f7-126">From the **Credit card transactions** page, you can reassign the employee for any credit card transaction where the associated employee has been terminated.</span></span>

<span data-ttu-id="c80f7-127">Välj en eller flera kreditkortstransaktioner och välj sedan **Omtilldela transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="c80f7-127">Select one or more credit card transactions, and then select **Reassign transactions**.</span></span> <span data-ttu-id="c80f7-128">Du kan sedan välja en annan medarbetare att tilldela kreditkortstransaktionerna till.</span><span class="sxs-lookup"><span data-stu-id="c80f7-128">You can then select another employee to assign the credit card transactions to.</span></span> <span data-ttu-id="c80f7-129">När kreditkortstransaktionerna har omtilldelats kan de väljas ut till en utgiftsrapport och betalas via den sedvanliga processen för ersättning av utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="c80f7-129">After the credit card transactions have been reassigned, they can be selected for an expense report and paid through the usual process for expense report reimbursement.</span></span>
