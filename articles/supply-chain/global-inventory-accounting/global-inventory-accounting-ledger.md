---
title: Transaktionsregister för Global lagerredovisning
description: I det här avsnittet beskrivs redovisning för global lagerredovisning, som definieras av en kombination av en valuta, en kalender, en konferens och en koppling till en juridisk person.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea3434675aa3b7f2304be93ef9b489747994fa9d
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273226"
---
# <a name="global-inventory-accounting-ledger"></a><span data-ttu-id="98fed-103">Transaktionsregister för Global lagerredovisning</span><span class="sxs-lookup"><span data-stu-id="98fed-103">Global Inventory Accounting ledger</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="98fed-104">Global lagerredovisning har sin egen uppsättning redovisning.</span><span class="sxs-lookup"><span data-stu-id="98fed-104">Global Inventory Accounting has its own set of ledgers.</span></span> <span data-ttu-id="98fed-105">Varje gång en lagerrelaterad transaktion bearbetas för en relevant juridisk person kan systemet konto för transaktionen i val enskilt antal redovisningar för global lagerredovisning efter behov.</span><span class="sxs-lookup"><span data-stu-id="98fed-105">Each time an inventory-related transaction is processed for a relevant legal entity, the system can account for that transaction in any number of Global Inventory Accounting ledgers, as required.</span></span>

<span data-ttu-id="98fed-106">Redovisningen är ett register för debet- och kreditmått.</span><span class="sxs-lookup"><span data-stu-id="98fed-106">A ledger is a register of debit and credit measures.</span></span> <span data-ttu-id="98fed-107">Dessa mått klassificeras genom användning av kostnadselement och redovisningskonton.</span><span class="sxs-lookup"><span data-stu-id="98fed-107">These measures are classified by using cost elements and subledger accounts.</span></span> <span data-ttu-id="98fed-108">Redovisning för global lagerredovisning, som definieras av en kombination av en valuta, en kalender, en konferens och en koppling till en juridisk person.</span><span class="sxs-lookup"><span data-stu-id="98fed-108">A Global Inventory Accounting ledger is defined by its combination of a currency, a calendar, a convention, and an association with a legal entity.</span></span>

<span data-ttu-id="98fed-109">Om du vill ställa in dina redovisningar för global lagerredovisning går du till **Global lagerredovisning \> Inställningar \> Global lagerredovisning**.</span><span class="sxs-lookup"><span data-stu-id="98fed-109">To set up your Global Inventory Accounting ledgers, go to **Global inventory accounting \> Setup \> Global inventory accounting ledgers**.</span></span> <span data-ttu-id="98fed-110">För varje redovisning anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="98fed-110">For each ledger, set the following fields:</span></span>

- <span data-ttu-id="98fed-111">**Namn** – Ange namnet på redovisning.</span><span class="sxs-lookup"><span data-stu-id="98fed-111">**Name** – Enter the name of the ledger.</span></span>
- <span data-ttu-id="98fed-112">**Beskrivning** – Ange en beskrivning av redovisning.</span><span class="sxs-lookup"><span data-stu-id="98fed-112">**Description** – Enter a description of the ledger.</span></span>
- <span data-ttu-id="98fed-113">**Räkenskapskalender** – Ange räkenskapskalendern för redovisningen.</span><span class="sxs-lookup"><span data-stu-id="98fed-113">**Fiscal calendar** – Specify the fiscal calendar for the ledger.</span></span>
- <span data-ttu-id="98fed-114">**Valuta- och valutakurstyp** – Använd fälten på den här snabbfliken för att välja den redovisningsvaluta som redovisningen använder samt valutakurstypen.</span><span class="sxs-lookup"><span data-stu-id="98fed-114">**Currency and exchange rate type** – Use the fields on this FastTab to select the accounting currency that the ledger uses, and the exchange rate type.</span></span> <span data-ttu-id="98fed-115">Valutan du väljer kan skilja sig från den valuta som den juridiska personen använder.</span><span class="sxs-lookup"><span data-stu-id="98fed-115">The currency that you select can differ from the currency that the legal entity uses.</span></span> <span data-ttu-id="98fed-116">I Global lagerredovisning kan användarna definiera så många kostnadsredovisningar som de behöver.</span><span class="sxs-lookup"><span data-stu-id="98fed-116">In Global Inventory Accounting, users can define as many costing ledgers as they require.</span></span> <span data-ttu-id="98fed-117">Global lagerredovisning stöder lagerredovisning i flera valutor och vid flera värderingar.</span><span class="sxs-lookup"><span data-stu-id="98fed-117">Global Inventory Accounting supports inventory accounting in multiple currencies and in multiple valuations.</span></span> <span data-ttu-id="98fed-118">Ange följande fält.</span><span class="sxs-lookup"><span data-stu-id="98fed-118">Set the following fields:</span></span>

    - <span data-ttu-id="98fed-119">**Valuta** – Välj den kostnadsvaluta som lagerrelaterade värden underhålls i.</span><span class="sxs-lookup"><span data-stu-id="98fed-119">**Currency** – Select the costing currency that inventory-related values are maintained in.</span></span> <span data-ttu-id="98fed-120">Det här värdet inkluderar lagervärde, kostnad för sålda varor, lager under transport och alla typer av avvikelser.</span><span class="sxs-lookup"><span data-stu-id="98fed-120">These values include the inventory value, cost of goods sold, inventory in transit, and all kinds of variance.</span></span>
    - <span data-ttu-id="98fed-121">**Valutakurstyp** – Välj den valutakurs som ska användas för att konvertera transaktionsbeloppet i transaktionsvalutan och standardkostnaden för artiklarna till kostnadsvalutan.</span><span class="sxs-lookup"><span data-stu-id="98fed-121">**Exchange rate type** – Select the exchange rate that the system should use to convert the transaction amount in the transaction currency and the standard cost of the items into the costing currency.</span></span>

- <span data-ttu-id="98fed-122">**Konventionens namn** – Ange en konvention.</span><span class="sxs-lookup"><span data-stu-id="98fed-122">**Convention name** – Specify a convention.</span></span> <span data-ttu-id="98fed-123">En konvention är en samling principer som fastställer hur kostnader ska redovisas i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="98fed-123">A convention is a collection of policies that establish how costs will be accounted in this ledger.</span></span>
- <span data-ttu-id="98fed-124">**Juridisk person** – I redovisningen bokförs dokumenten som bokförs till den valda juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="98fed-124">**Legal entity** – The ledger will account the documents that are posted to the selected legal entity.</span></span>
- <span data-ttu-id="98fed-125">**Priming** – Välj om lagertransaktioner som skapades innan huvudboken skapades ska behandlas enligt valutan och konventionen i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="98fed-125">**Priming** – Select whether inventory transactions that were created before the ledger was created should be processed according to the currency and convention in the ledger.</span></span> <span data-ttu-id="98fed-126">Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="98fed-126">Select one of the following values:</span></span>

    - <span data-ttu-id="98fed-127">**Aktiverat** – Redovisningen ska bearbeta transaktioner som skapades innan redovisningen skapades.</span><span class="sxs-lookup"><span data-stu-id="98fed-127">**Activated** – The ledger should process transactions that were created before the ledger was created.</span></span>
    - <span data-ttu-id="98fed-128">**Inaktiverat** – Redovisningen ska endast bearbeta transaktioner som skapades efter redovisningen skapades.</span><span class="sxs-lookup"><span data-stu-id="98fed-128">**Deactivated** – The ledger should process only transactions that are created after the ledger was created.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="98fed-129">Du kan **inte** komma tillbaka och ställa in detta fält när du har angett nya dokument.</span><span class="sxs-lookup"><span data-stu-id="98fed-129">You will **not** be able to come back and set this field after you enter new documents.</span></span>

- <span data-ttu-id="98fed-130">**Status** – Systemet ställer automatiskt in statusen för nyligen skapade redovisningar att *förbereda*.</span><span class="sxs-lookup"><span data-stu-id="98fed-130">**Status** – The system automatically sets the status of newly created ledgers to *Prepare*.</span></span>
