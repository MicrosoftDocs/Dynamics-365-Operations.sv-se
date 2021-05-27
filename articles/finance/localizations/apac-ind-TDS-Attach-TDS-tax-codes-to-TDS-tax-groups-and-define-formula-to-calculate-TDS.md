---
title: Koppla TDS-momskoder till TDS-momsgrupper och definiera formeln för att beräkna TDS
description: I det här avsnittet beskrivs hur du ställer in TDS-momsgrupper (Tax Deducted at Source) och kopplar TDS-momskoder till TDS-momsgrupper. Om du vill beräkna TDS för en TDS-momsgrupp måste du definiera formeln för TDS-momskoder som är kopplade till den.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: ec0d683153bd5ab731035159d32881fbdb352d70
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023607"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a><span data-ttu-id="e407c-104">Koppla TDS-momskoder till TDS-momsgrupper och definiera formeln för att beräkna TDS</span><span class="sxs-lookup"><span data-stu-id="e407c-104">Attach TDS tax codes to TDS tax groups and define the formula for calculating TDS</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e407c-105">I det här avsnittet beskrivs hur du ställer in TDS-momsgrupper (Tax Deducted at Source) och kopplar TDS-momskoder till TDS-momsgrupper.</span><span class="sxs-lookup"><span data-stu-id="e407c-105">This topic explains how to set up Tax Deducted at Source (TDS) tax groups and attach TDS tax codes to TDS tax groups.</span></span> <span data-ttu-id="e407c-106">Om du vill beräkna TDS för en TDS-momsgrupp måste du definiera formeln för TDS-momskoder som är kopplade till den.</span><span class="sxs-lookup"><span data-stu-id="e407c-106">To calculate TDS for a TDS tax group, you must define the formula for TDS tax codes that are attached to it.</span></span>

<span data-ttu-id="e407c-107">Följ dessa steg om du vill ställa in en TDS-momsgrupp, koppla TDS-momskoder till den och definiera formeln för beräkning av TDS.</span><span class="sxs-lookup"><span data-stu-id="e407c-107">Follow these steps to set up a TDS tax group, attach TDS tax codes to it, and define the formula for calculating TDS.</span></span>

1. <span data-ttu-id="e407c-108">Gå till **Skatt \> Indirekta skatter \> Källskatt \> Källskattegrupper**.</span><span class="sxs-lookup"><span data-stu-id="e407c-108">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax groups**.</span></span>

    <span data-ttu-id="e407c-109">[![Sidan Källskattegrupper](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span><span class="sxs-lookup"><span data-stu-id="e407c-109">[![Withholding tax groups page](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span></span>

2. <span data-ttu-id="e407c-110">I åtgärdsfönstret väljer du **Ny** för att skapa en källskattegrupp för TDS och anger den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="e407c-110">On the Action Pane, select **New** to create a withholding tax group for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="e407c-111">I fältet **Momstyp**, välj **TDS**.</span><span class="sxs-lookup"><span data-stu-id="e407c-111">In the **Tax type** field, select **TDS**.</span></span>
4. <span data-ttu-id="e407c-112">På snabbfliken **Konfigurera**, klicka på **Lägg till** för att skapa en rad.</span><span class="sxs-lookup"><span data-stu-id="e407c-112">On the **Setup** FastTab, select **Add** to create a line.</span></span>
5. <span data-ttu-id="e407c-113">I fältet **Källskattekod** väljer du TDS-skattekoden för TDS-skattegruppen.</span><span class="sxs-lookup"><span data-stu-id="e407c-113">In the **Withholding tax code** field, select the TDS tax code for the TDS tax group.</span></span> <span data-ttu-id="e407c-114">Fältet **Namn på källskatt** visar namnet på TDS-skattekoden, och fältet **Värde** visar värdet.</span><span class="sxs-lookup"><span data-stu-id="e407c-114">The **Withholding tax name** field shows the name of the TDS tax code, and the **Value** field shows the value.</span></span>
6. <span data-ttu-id="e407c-115">Om du vill ignorera det tröskelvärde och undantagströskelvärde som har definierats för TDS-momskomponenten som är kopplad till TDS-momskoden i TDS-transaktioner markerar du kryssrutan **Förbigå tröskelvärde**.</span><span class="sxs-lookup"><span data-stu-id="e407c-115">To ignore the threshold limit and exception threshold limit that are defined for the TDS tax component that is attached to the TDS tax code in TDS transactions, select the **Overlook threshold** check box.</span></span>
7. <span data-ttu-id="e407c-116">För att förhindra momsgruppen från att beräknas i transaktioner markerar du kryssrutan **Undantagen**.</span><span class="sxs-lookup"><span data-stu-id="e407c-116">To prevent the tax group from being calculated in transactions, select the **Exempt** check box.</span></span>
8. <span data-ttu-id="e407c-117">I åtgärdsfönstret väljer du **Designer** för att öppna formeldesignern, så att du kan definiera formeln för beräkning av TDS för TDS-momsgruppen.</span><span class="sxs-lookup"><span data-stu-id="e407c-117">On the Action Pane, select **Designer** to open the formula designer, so that you can define the formula for calculating TDS for the TDS tax group.</span></span> <span data-ttu-id="e407c-118">På sidan **Designer** visar fliken **Skatter** TDS-momskoder som har valts för TDS-momsgruppen.</span><span class="sxs-lookup"><span data-stu-id="e407c-118">On the **Designer** page, the **Taxes** tab shows the TDS tax codes that have been selected for the TDS tax group.</span></span>

    <span data-ttu-id="e407c-119">[![Designersida](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span><span class="sxs-lookup"><span data-stu-id="e407c-119">[![Designer page](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span></span>

9. <span data-ttu-id="e407c-120">På fliken **Beräkning** väljer du **Alt+N** för att skapa en rad.</span><span class="sxs-lookup"><span data-stu-id="e407c-120">On the **Calculation** tab, select **Alt+N** to create a line.</span></span> <span data-ttu-id="e407c-121">Fältet **ID** visar det automatiskt genererade prioritets-ID för TDS-beräkning.</span><span class="sxs-lookup"><span data-stu-id="e407c-121">The **ID** field shows the automatically generated priority ID for TDS calculation.</span></span>
10. <span data-ttu-id="e407c-122">I fältet **Momskod** väljer du TDS-momskoden som formeln ska definieras för.</span><span class="sxs-lookup"><span data-stu-id="e407c-122">In the **Tax code** field, select the TDS tax code to define the formula for.</span></span> <span data-ttu-id="e407c-123">Alla TDS-momskoder som har valts för TDS-momsgruppen går att välja i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="e407c-123">All the TDS tax codes that have been selected for the TDS tax group are available for selection in this field.</span></span>
11. <span data-ttu-id="e407c-124">I fältet **Momsunderlag** väljer du bas för beräkning av TDS:</span><span class="sxs-lookup"><span data-stu-id="e407c-124">In the **Taxable basis** field, select the basis for calculating TDS:</span></span>

    - <span data-ttu-id="e407c-125">**Bruttobelopp** – Beräkna TDS baserat på bruttotransaktionsbeloppet (det vill säga fakturabeloppet) med hjälp av beräkningsuttrycket som definieras för momskoden.</span><span class="sxs-lookup"><span data-stu-id="e407c-125">**Gross amount** – Calculate TDS based on the gross transaction amount (that is, the invoice amount) by using the calculation expression that is defined for the tax code.</span></span>
    - <span data-ttu-id="e407c-126">**Exkl. bruttobelopp** – Beräkna TDS baserat på det beräkningsuttryck som är definierat för momskoden.</span><span class="sxs-lookup"><span data-stu-id="e407c-126">**Excl Gross amount** – Calculate TDS based on the calculation expression that is defined for the tax code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e407c-127">Fältet **Momsunderlag** kan inte ställas in på **Exkl. bruttobelopp** för TDS-momskoden med prioritets-ID **1**.</span><span class="sxs-lookup"><span data-stu-id="e407c-127">The **Taxable basis** field can't be set to **Excl Gross amount** for the TDS tax code that has a priority ID of **1**.</span></span>

12. <span data-ttu-id="e407c-128">TDS-beräkningen baseras på formeln som definieras i fältet **Beräkningsuttryck** för varje momskod som är kopplad till TDS-momsgruppen.</span><span class="sxs-lookup"><span data-stu-id="e407c-128">The TDS calculation is based on the formula that is defined in the **Calculation expression** field for each tax code that is attached to the TDS tax group.</span></span> <span data-ttu-id="e407c-129">Välj plustecknet (**+**), minustecknet (**-**), multiplikationstecknet (**\**_) eller divisionstecknet (_*/**) för att ange beräkningsuttrycket för den valda TDS-momskoden i fältet **Beräkningsuttryck**.</span><span class="sxs-lookup"><span data-stu-id="e407c-129">Select the plus sign (**+**), minus sign (**-**), multiplication sign (**\**_), or division sign (_*/**) button to enter the calculation expression for the selected TDS tax code in the **Calculation expression** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e407c-130">Inget beräkningsuttryck kan definieras för TDS-momskoden som har prioritets-ID **1**.</span><span class="sxs-lookup"><span data-stu-id="e407c-130">No calculation expression can be defined for the TDS tax code that has a priority ID of **1**.</span></span>

13. <span data-ttu-id="e407c-131">Om du vill definiera beräkningsuttrycket för TDS-momskoden i fältet **Beräkningsuttryck** lägger du till TDS-momskoder som är tillgängliga under fliken **Skatter**. Om du vill lägga till TDS-momskoder i fältet **Beräkningsuttryck** kan du använda någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="e407c-131">To define the calculation expression for the TDS tax code in the **Calculation expression** field, add TDS tax codes that are available on the **Taxes** tab. To add TDS tax codes in the **Calculation expression** field, you can use any of the following methods:</span></span>

    - <span data-ttu-id="e407c-132">Dra den nödvändiga momskoden från fliken **Skatter** till fältet **Beräkningsuttryck**.</span><span class="sxs-lookup"><span data-stu-id="e407c-132">Drag the required tax code from the **Taxes** tab to the **Calculation expression** field.</span></span>
    - <span data-ttu-id="e407c-133">Dubbelklicka på momskoden på fliken **Skatter**.</span><span class="sxs-lookup"><span data-stu-id="e407c-133">Double-tap (or double-click) the required tax code on the **Taxes** tab.</span></span>
    - <span data-ttu-id="e407c-134">Tryck på och håll inne (eller högerklicka) momskoden på fliken **Skatter** och välj sedan **Lägg till momskod**.</span><span class="sxs-lookup"><span data-stu-id="e407c-134">Select and hold (or right-click) the required tax code on the **Taxes** tab, and then select **Add tax code**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e407c-135">Infoga ett beräkningsuttryck före varje TDS-momskod.</span><span class="sxs-lookup"><span data-stu-id="e407c-135">Insert a calculation expression before each TDS tax code.</span></span> <span data-ttu-id="e407c-136">De TDS-momskoder som har lagts till i beräkningsuttrycket visas inom hakparenteser (\[...\]).</span><span class="sxs-lookup"><span data-stu-id="e407c-136">The TDS tax codes that have been added to the calculation expression appear in brackets (\[...\]).</span></span>

14. <span data-ttu-id="e407c-137">Om du vill rensa beräkningsuttrycket som har definierats för en momskod i fältet **Beräkningsuttryck** väljer du knappen **C**.</span><span class="sxs-lookup"><span data-stu-id="e407c-137">To clear the calculation expression that is defined for a tax code in the **Calculation expression** field, select the **C** button.</span></span>
15. <span data-ttu-id="e407c-138">Om du vill ta bort en post på fliken **Beräkning** väljer du **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="e407c-138">To delete a record on the **Calculation** tab, select **Delete**.</span></span>
16. <span data-ttu-id="e407c-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e407c-139">Close the page.</span></span>
