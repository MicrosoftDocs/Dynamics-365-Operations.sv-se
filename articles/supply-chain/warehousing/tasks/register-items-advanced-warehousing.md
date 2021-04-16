---
title: Registrera artiklar för en artikel som är aktiverad för avancerad distributionslagerhantering med hjälp av en artikelinförseljournal
description: Det här ämnet presenterar ett scenario som visar hur du registrerar artiklar via artikelinförseljournalen när du använder avancerade processer för lagerstyrning.
author: ShylaThompson
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c58aa1cec6c0bfe33fa1ef90267dcd8ac1218157
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830844"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="62bcd-103">Registrera artiklar för en artikel som är aktiverad för avancerad distributionslagerhantering med hjälp av en artikelinförseljournal</span><span class="sxs-lookup"><span data-stu-id="62bcd-103">Register items for an advanced warehousing enabled item using an item arrival journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="62bcd-104">Det här ämnet presenterar ett scenario som visar hur du registrerar artiklar via artikelinförseljournalen när du använder avancerade processer för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="62bcd-104">This topic presents a scenario that shows how to register items using the item arrival journal when you are using advanced warehouse management processes.</span></span> <span data-ttu-id="62bcd-105">Detta görs vanligtvis av en inleveransansvarig.</span><span class="sxs-lookup"><span data-stu-id="62bcd-105">This would usually be done by a receiving clerk.</span></span>

## <a name="enable-sample-data"></a><span data-ttu-id="62bcd-106">Aktivera exempeldata</span><span class="sxs-lookup"><span data-stu-id="62bcd-106">Enable sample data</span></span>

<span data-ttu-id="62bcd-107">Om du vill gå igenom det här scenariot med hjälp av de exempelposter och värden som anges i det här avsnittet måste du använda ett system där standard demodata är installerad och du måste välja den juridiska personen *USMF* innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="62bcd-107">To work through this scenario using the sample records and values specified in this topic, you must be using a system where the standard demo data is installed, and you must select the *USMF* legal entity before you begin.</span></span>

<span data-ttu-id="62bcd-108">Du kan istället arbeta dig igenom det här scenariot genom att använda värderingsvärden från dina egna data under förutsättning att du har följande tillgängliga data:</span><span class="sxs-lookup"><span data-stu-id="62bcd-108">You can instead work through this scenario by substituting values from your own data provided that you have the following data available:</span></span>

- <span data-ttu-id="62bcd-109">Du måste ha en bekräftad inköpsorder med en öppen inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="62bcd-109">You must have a confirmed purchase order with an open purchase order line.</span></span>
- <span data-ttu-id="62bcd-110">Artikeln på raden måste lagras.</span><span class="sxs-lookup"><span data-stu-id="62bcd-110">The item on the line must be stocked.</span></span> <span data-ttu-id="62bcd-111">Den får inte använda produktvarianter och får inte ha spårningsdimensioner.</span><span class="sxs-lookup"><span data-stu-id="62bcd-111">It must not use product variants, and must not have tracking dimensions.</span></span>
- <span data-ttu-id="62bcd-112">Objektet måste associeras med en lagringsdimensionsgrupp som har lagerhanteringsprocessen aktiverad.</span><span class="sxs-lookup"><span data-stu-id="62bcd-112">The item must be associated with a storage dimension group that has warehouse management process enabled.</span></span>
- <span data-ttu-id="62bcd-113">Lagerstället som används måste aktiveras för lagerstyrningsprocesser och lagerplatsen som du använder för inleveranser måste vara id-nummerstyrd.</span><span class="sxs-lookup"><span data-stu-id="62bcd-113">The warehouse that's used must be enabled for warehouse management processes and the location that you use for receiving must be license plate controlled.</span></span>

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a><span data-ttu-id="62bcd-114">Skapa en journalrubrik för artikelinförleverans som använder lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="62bcd-114">Create an item arrival journal header that uses warehouse management</span></span>

<span data-ttu-id="62bcd-115">I följande scenario visas hur du skapar en artikelinföringsjournalrubrik där lagerstyrning används:</span><span class="sxs-lookup"><span data-stu-id="62bcd-115">The following scenario shows how to create an item arrival journal header that uses warehouse management:</span></span>

1. <span data-ttu-id="62bcd-116">Kontrollera att systemet innehåller en bekräftad inköpsorder som uppfyller kraven i det föregående avsnittet.</span><span class="sxs-lookup"><span data-stu-id="62bcd-116">Make sure your system contains a confirmed purchase order that fulfils the requirements outlined in the previous section.</span></span> <span data-ttu-id="62bcd-117">I det här scenariot används en inköpsorder för företaget *USMF*, leverantörskonto *1001*, lagerställe *51* med en orderrad för *10 PL* (10 lastpallar) för artikelnummer *M9200*.</span><span class="sxs-lookup"><span data-stu-id="62bcd-117">This scenario uses a purchase order for company *USMF*, vendor account *1001*, warehouse *51*, with an order line for *10 PL* (10 pallets) of item number *M9200*.</span></span>
1. <span data-ttu-id="62bcd-118">Anteckna inköpsordernumret som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="62bcd-118">Make a note of the purchase order number that you will use.</span></span>
1. <span data-ttu-id="62bcd-119">Gå till **Lagerhantering \> Poster i redovisningsjournal \> Artikelinförsel \> Artikelinförsel**.</span><span class="sxs-lookup"><span data-stu-id="62bcd-119">Go to **Inventory management \> Journal entries \> Item arrival \> Item arrival**.</span></span>
1. <span data-ttu-id="62bcd-120">Välj **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="62bcd-120">Select **New** on the Action Pane.</span></span>
1. <span data-ttu-id="62bcd-121">Dialogrutan **Skapa lagerhanteringsjournal** öppnas.</span><span class="sxs-lookup"><span data-stu-id="62bcd-121">The **Create warehouse management journal** dialog box opens.</span></span> <span data-ttu-id="62bcd-122">Välj ett journalnamn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="62bcd-122">Select a journal name in the **Name** field.</span></span>
    - <span data-ttu-id="62bcd-123">Om du använder exempeldata för *USMF*, välj *WHS*.</span><span class="sxs-lookup"><span data-stu-id="62bcd-123">If you are using *USMF* sample data, select *WHS*.</span></span>
    - <span data-ttu-id="62bcd-124">Om du använder dina egna uppgifter måste den journal du väljer ha **Kontrollera plockplats** inställt på *Nej* och **Karantänhantering** anges till *Nej*.</span><span class="sxs-lookup"><span data-stu-id="62bcd-124">If you're using your own data, the journal you choose must have **Check picking location** set to *No* and **Quarantine management** set to *No*.</span></span>
1. <span data-ttu-id="62bcd-125">Ange **Referens** till *Inköpsorder*.</span><span class="sxs-lookup"><span data-stu-id="62bcd-125">Set **Reference** to *Purchase order*.</span></span>
1. <span data-ttu-id="62bcd-126">Ange **Kontonummer** till *1001*.</span><span class="sxs-lookup"><span data-stu-id="62bcd-126">Set **Account number** to *1001*.</span></span>
1. <span data-ttu-id="62bcd-127">Ange **Nummer** till numret inköpsordern som du identifierade i det här arbetet.</span><span class="sxs-lookup"><span data-stu-id="62bcd-127">Set **Number** to the number of the purchase order that you identified for this exercise.</span></span>

    <span data-ttu-id="62bcd-128">![Artikelinförseljournal](../media/item-arrival-journal-header.png "Artikelinförseljournal")</span><span class="sxs-lookup"><span data-stu-id="62bcd-128">![Item arrival journal](../media/item-arrival-journal-header.png "Item arrival journal")</span></span>

1. <span data-ttu-id="62bcd-129">Välj **OK** för att skapa journalrubriken.</span><span class="sxs-lookup"><span data-stu-id="62bcd-129">Select the **OK** to create the journal header.</span></span>
1. <span data-ttu-id="62bcd-130">I avsnittet **Journalrader**, välj **Lägg till rad** och ange följande data:</span><span class="sxs-lookup"><span data-stu-id="62bcd-130">In the **Journal lines** section, select **Add line** and enter the following data:</span></span>
    - <span data-ttu-id="62bcd-131">**Artikelnummer** – Ange till *M9200*.</span><span class="sxs-lookup"><span data-stu-id="62bcd-131">**Item number** – Set to *M9200*.</span></span> <span data-ttu-id="62bcd-132">**Webbplatsen**, **lagerstället** och **kvantiteten** kommer att ställas in baserat på lagertransaktionsdata för de 10 lastpallar (1000 st).</span><span class="sxs-lookup"><span data-stu-id="62bcd-132">The **Site**, **Warehouse**, and **Quantity** will get set based on the inventory transaction data for the 10 pallets (1000 ea.).</span></span>
    - <span data-ttu-id="62bcd-133">**Plats** – Ställ in på *001*.</span><span class="sxs-lookup"><span data-stu-id="62bcd-133">**Location** – Set to  *001*.</span></span> <span data-ttu-id="62bcd-134">Den här platsen spårar inte licensinnehavare.</span><span class="sxs-lookup"><span data-stu-id="62bcd-134">This specific location does not track license plates.</span></span>

    <span data-ttu-id="62bcd-135">![Artikelinförseljournalrad](../media/item-arrival-journal-line.png "Artikelinförseljournalrad")</span><span class="sxs-lookup"><span data-stu-id="62bcd-135">![Item arrival journal line](../media/item-arrival-journal-line.png "Item arrival journal line")</span></span>

    > [!NOTE]
    > <span data-ttu-id="62bcd-136">Fältet **Datum** bestämmer datumet då lagerbehållningen för artikeln ska registreras i lagret.</span><span class="sxs-lookup"><span data-stu-id="62bcd-136">The **Date** field determines the date on which the on-hand quantity of this item will be registered in the inventory.</span></span>  
    >
    > <span data-ttu-id="62bcd-137">**Parti-ID** fylls i av systemet, om det kan identifieras av den tillhandahållna informationen.</span><span class="sxs-lookup"><span data-stu-id="62bcd-137">The **Lot ID** will be populated by the system if it can be uniquely identified from the information provided.</span></span> <span data-ttu-id="62bcd-138">Annars måste du ange det manuellt.</span><span class="sxs-lookup"><span data-stu-id="62bcd-138">Otherwise you will have to enter this manually.</span></span> <span data-ttu-id="62bcd-139">Detta är ett obligatoriskt fält, som kopplar den här registreringen till en viss källdokumentrad.</span><span class="sxs-lookup"><span data-stu-id="62bcd-139">This is a required field, which links this registration to a specific source document line.</span></span>  

1. <span data-ttu-id="62bcd-140">Välj **Validera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="62bcd-140">Select **Validate** on the Action Pane.</span></span> <span data-ttu-id="62bcd-141">Detta kontrollerar att journalen är klar att bokföras.</span><span class="sxs-lookup"><span data-stu-id="62bcd-141">This checks that the journal is ready to be posted.</span></span> <span data-ttu-id="62bcd-142">Om valideringen misslyckas måste du korrigera felen innan du kan bokföra journalen.</span><span class="sxs-lookup"><span data-stu-id="62bcd-142">If the validation fails you will need to fix the errors before you can post the journal.</span></span>  
1. <span data-ttu-id="62bcd-143">Dialogrutan **Kontrollera journal** öppnas.</span><span class="sxs-lookup"><span data-stu-id="62bcd-143">The **Check journal** dialog box opens.</span></span> <span data-ttu-id="62bcd-144">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="62bcd-144">Select **OK**.</span></span>
1. <span data-ttu-id="62bcd-145">Granska meddelandefältet.</span><span class="sxs-lookup"><span data-stu-id="62bcd-145">Review the message bar.</span></span> <span data-ttu-id="62bcd-146">Det bör visas ett meddelande om att åtgärden lyckades.</span><span class="sxs-lookup"><span data-stu-id="62bcd-146">There should be a message denoting that the operation was completed.</span></span>  
1. <span data-ttu-id="62bcd-147">Klicka på **Bokföra** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="62bcd-147">Select **Post** on the Action Pane.</span></span>
1. <span data-ttu-id="62bcd-148">Dialogrutan **Bokför journal** öppnas.</span><span class="sxs-lookup"><span data-stu-id="62bcd-148">The **Post journal** dialog box opens.</span></span> <span data-ttu-id="62bcd-149">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="62bcd-149">Select **OK**.</span></span>
1. <span data-ttu-id="62bcd-150">Granska meddelandefältet.</span><span class="sxs-lookup"><span data-stu-id="62bcd-150">Review the message bar.</span></span> <span data-ttu-id="62bcd-151">Det bör visas ett meddelande om att åtgärden lyckades.</span><span class="sxs-lookup"><span data-stu-id="62bcd-151">There should be messages denoting that the operation completed.</span></span>
1. <span data-ttu-id="62bcd-152">Välj **Funktioner > Produktinleverans** i åtgärdsfönstret om du vill uppdatera inköpsorderraden och bokföra en produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="62bcd-152">Select **Functions > Product receipt** on the Action Pane to update the purchase order line and post a product receipt.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
