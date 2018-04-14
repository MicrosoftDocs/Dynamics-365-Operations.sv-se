--- 
title: "Skapa en anbudsförfrågan"
description: "Den här proceduren visar hur du skapar en anbudsförfrågan."
author: mkirknel
manager: AnnBe
ms.date: 11/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d6e7c8884c0fa29b5c6efc053f2ad8171581b946
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-request-for-quotation"></a><span data-ttu-id="49483-103">Skapa en anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="49483-103">Create a request for quotation</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="49483-104">Den här proceduren visar hur du skapar en anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="49483-104">This procedure shows you how to create a request for quotation.</span></span> <span data-ttu-id="49483-105">Detta görs normalt av en inköpsagent.</span><span class="sxs-lookup"><span data-stu-id="49483-105">This would typically be done by a purchasing agent.</span></span> <span data-ttu-id="49483-106">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="49483-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="49483-107">Du måste ha ställt in begäranstyper innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="49483-107">You need to have set up solicitation types before you start.</span></span> <span data-ttu-id="49483-108">När du har slutfört den här uppgiften och du har skapat och har skickat en anbudsförfrågan kan du sedan ange svarstyper per leverantör, jämföra dem och tilldela kontraktet.</span><span class="sxs-lookup"><span data-stu-id="49483-108">Once you’ve completed this task and you’ve created and sent an RFQ you can then enter the replies per vendor, compare them, and award the contract.</span></span>


## <a name="prepare-a-new-rfq"></a><span data-ttu-id="49483-109">Förbered en ny anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="49483-109">Prepare a new RFQ</span></span>
1. <span data-ttu-id="49483-110">Gå till Anskaffning och källa > Anbudsförfrågningar > Alla anbudsförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="49483-110">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="49483-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="49483-111">Click New.</span></span>
    * <span data-ttu-id="49483-112">Följande inköpstyper finns: Inköpsorder (inställt som standard): ett dokument som bekräftar erbjudandet att köpa produkter eller godkännande av ett erbjudande att sälja produkter i utbyte mot betalning.</span><span class="sxs-lookup"><span data-stu-id="49483-112">The following purchase types are available: Purchase order (this is the default): a document that confirms the offer to buy products, or the acceptance of an offer to sell products in exchange for payment.</span></span> <span data-ttu-id="49483-113">Inköpsrekvisition: den här typen väljs automatiskt, om du skapar en anbudsförfrågan direkt från en inköpsrekvisition.</span><span class="sxs-lookup"><span data-stu-id="49483-113">Purchase requisition: this type is automatically selected if you create an RFQ directly from a purchase requisition.</span></span> <span data-ttu-id="49483-114">Om du väljer det här alternativet manuellt får du ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="49483-114">If you manually select this option, you’ll get an error.</span></span> <span data-ttu-id="49483-115">Inköpsavtal: ett avtal att köpa ett visst kvantitet eller värde av produkt över tid.</span><span class="sxs-lookup"><span data-stu-id="49483-115">Purchase agreement: an agreement to purchase a specific quantity or value of product over time.</span></span> <span data-ttu-id="49483-116">Om du markerar det här alternativet måste du välja det datumintervall som gäller för inköpsavtalet.</span><span class="sxs-lookup"><span data-stu-id="49483-116">If you select this option, you must select the date range that applies to the purchase agreement.</span></span>  
3. <span data-ttu-id="49483-117">Skriv in ett värde i fältet Dokumenttitel.</span><span class="sxs-lookup"><span data-stu-id="49483-117">In the Document title field, type a value.</span></span>
4. <span data-ttu-id="49483-118">Ange eller välj ett värde i fältet Typ av begäran.</span><span class="sxs-lookup"><span data-stu-id="49483-118">In the Solicitation type field, enter or select a value.</span></span>
    * <span data-ttu-id="49483-119">Om en poängsättningsmetod associeras med typ av begäran kommer detta att bli standardpoängmetoden för den anbudsförfrågan som du skapar.</span><span class="sxs-lookup"><span data-stu-id="49483-119">If a scoring method is associated with the solicitation type, this will be the default scoring method for the RFQ that you’re creating.</span></span> <span data-ttu-id="49483-120">Det går det att ändra poängmetod senare.</span><span class="sxs-lookup"><span data-stu-id="49483-120">It is possible to change the scoring method later.</span></span>  
    * <span data-ttu-id="49483-121">I fältet Leveransdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="49483-121">In the Delivery date field, enter a date.</span></span>  
    * <span data-ttu-id="49483-122">Välj det datum då du vill få artiklarna.</span><span class="sxs-lookup"><span data-stu-id="49483-122">Select the date by which you want to receive the items.</span></span>  
    * <span data-ttu-id="49483-123">I fältet Utgångsdatum och tid anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="49483-123">In the Expiration date and time field, enter a date and time.</span></span>  
    * <span data-ttu-id="49483-124">Ange datum och tid då leverantörerna senast måste svara på anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="49483-124">Specify the date and time by which vendors must respond to the RFQ.</span></span>  
5. <span data-ttu-id="49483-125">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="49483-125">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="49483-126">Leveransadressen ska anpassas till lageradressen.</span><span class="sxs-lookup"><span data-stu-id="49483-126">The delivery address will default to the warehouse address.</span></span>  
6. <span data-ttu-id="49483-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="49483-127">Click OK.</span></span>

## <a name="add-lines"></a><span data-ttu-id="49483-128">Lägg till rader</span><span class="sxs-lookup"><span data-stu-id="49483-128">Add lines</span></span>
    * <span data-ttu-id="49483-129">När du har angett grundläggande information om anbudsförfrågan anger du de varor eller tjänster som du vill att leverantörerna ska bjuda på.</span><span class="sxs-lookup"><span data-stu-id="49483-129">After you’ve specified the basic information about your RFQ, you specify the goods or services that you want vendors to bid on.</span></span> <span data-ttu-id="49483-130">Artikel är standardradtypen.</span><span class="sxs-lookup"><span data-stu-id="49483-130">Item is the default line type.</span></span>   
1. <span data-ttu-id="49483-131">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="49483-131">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="49483-132">Om du använder USMF kan du välja T0020.</span><span class="sxs-lookup"><span data-stu-id="49483-132">If you're using USMF, you can select T0020.</span></span>  
2. <span data-ttu-id="49483-133">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="49483-133">In the Quantity field, enter a number.</span></span>
3. <span data-ttu-id="49483-134">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="49483-134">Click Add line.</span></span>
4. <span data-ttu-id="49483-135">Välj "Kategori" i fältet Radtyp.</span><span class="sxs-lookup"><span data-stu-id="49483-135">In the Line type field, select 'Category'.</span></span>
    * <span data-ttu-id="49483-136">Du kan använda kategoriradtypen om du vill skapa anbudsförfrågan för lagervaror eller tjänster som inte finns i lager.</span><span class="sxs-lookup"><span data-stu-id="49483-136">You can use the Category line type to create RFQs for non-inventory goods or services.</span></span> <span data-ttu-id="49483-137">Sedan måste du välja vilken typ av varor eller tjänster från en hierarki med anskaffningkategorier.</span><span class="sxs-lookup"><span data-stu-id="49483-137">You then need to select the type of goods or services from a hierarchy of procurement categories.</span></span>  
5. <span data-ttu-id="49483-138">Ange eller välj ett värde i fältet Anskaffningskategori.</span><span class="sxs-lookup"><span data-stu-id="49483-138">In the Procurement category field, enter or select a value.</span></span>
6. <span data-ttu-id="49483-139">Skriv ett värde i fältet Produktnamn.</span><span class="sxs-lookup"><span data-stu-id="49483-139">In the Product name field, type a value.</span></span>
7. <span data-ttu-id="49483-140">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="49483-140">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="49483-141">Ange eller välj ett värde i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="49483-141">In the Unit field, enter or select a value.</span></span>

## <a name="add-vendors"></a><span data-ttu-id="49483-142">Lägg till leverantörer</span><span class="sxs-lookup"><span data-stu-id="49483-142">Add vendors</span></span>
1. <span data-ttu-id="49483-143">Klicka på Rubrik för att ändra från radvyn till rubrikvyn.</span><span class="sxs-lookup"><span data-stu-id="49483-143">Click Header to change from the Lines view to the Header view.</span></span> 
2. <span data-ttu-id="49483-144">Visa avsnittet Leverantör.</span><span class="sxs-lookup"><span data-stu-id="49483-144">Expand the Vendor section.</span></span>
3. <span data-ttu-id="49483-145">Klicka på Lägg till säljare automatiskt.</span><span class="sxs-lookup"><span data-stu-id="49483-145">Click Auto-add vendors.</span></span>
    * <span data-ttu-id="49483-146">Du kan lägga till leverantörer i en anbudsförfrågan automatiskt, baserat på anskaffningkategorin för de begärda artiklarna.</span><span class="sxs-lookup"><span data-stu-id="49483-146">You can add vendors to the RFQ automatically, based on the procurement category of the items requested.</span></span> <span data-ttu-id="49483-147">Om det inte finns några leverantörer som har godkänts för de kategorier som ingår i raderna kan du lägga till leverantörer manuellt.</span><span class="sxs-lookup"><span data-stu-id="49483-147">If there are no vendors approved for the categories included in the lines you can add vendors manually.</span></span>  
4. <span data-ttu-id="49483-148">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="49483-148">Click Add.</span></span>
5. <span data-ttu-id="49483-149">Ange eller välj ett värde i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="49483-149">In the Vendor account field, enter or select a value.</span></span>
6. <span data-ttu-id="49483-150">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="49483-150">Click Add.</span></span>
7. <span data-ttu-id="49483-151">Ange eller välj ett värde i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="49483-151">In the Vendor account field, enter or select a value.</span></span>
    * <span data-ttu-id="49483-152">När du har valt en leverantör, skapas statusen.</span><span class="sxs-lookup"><span data-stu-id="49483-152">Once you’ve selected a vendor, the status is Created.</span></span> <span data-ttu-id="49483-153">Detta innebär att leverantörsinformationen har sparats i anbudsförfrågan, men du har inte skickat anbudsförfrågan till leverantören.</span><span class="sxs-lookup"><span data-stu-id="49483-153">This means that the vendor information has been saved in the RFQ, but you have not sent the RFQ to the vendor.</span></span> <span data-ttu-id="49483-154">Du kan lägga till en leverantör i en anbudsförfrågan oavsett leverantörstatusen.</span><span class="sxs-lookup"><span data-stu-id="49483-154">You can add a vendor to an RFQ regardless of the vendor status.</span></span>  

## <a name="send-the-rfq-to-vendors"></a><span data-ttu-id="49483-155">Skicka anbudsförfrågan till leverantörer</span><span class="sxs-lookup"><span data-stu-id="49483-155">Send the RFQ to vendors</span></span>
1. <span data-ttu-id="49483-156">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="49483-156">Click Send.</span></span>
    * <span data-ttu-id="49483-157">På sidan Skickar anbudsförfrågan kontrollerar du att leverantörerna i listan är de leverantörer som du vill få anbudsförfrågan från.</span><span class="sxs-lookup"><span data-stu-id="49483-157">In the Sending request for quotation page, check that the vendors in the list are the ones that you want to receive the RFQ.</span></span>  
2. <span data-ttu-id="49483-158">Klicka på Skriv ut.</span><span class="sxs-lookup"><span data-stu-id="49483-158">Click Print.</span></span>
    * <span data-ttu-id="49483-159">Denna dialogruta låter dig skriva ut anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="49483-159">This dialog allows you to print the RFQ.</span></span> <span data-ttu-id="49483-160">Om du väljer att skriva ut ett svarsblad, anges i innehållet i detta i Anskaffnings- och källparametrar.</span><span class="sxs-lookup"><span data-stu-id="49483-160">If you choose to print a reply sheet, the contents of this are defined in Procurement and Sourcing parameters.</span></span> <span data-ttu-id="49483-161">Om du väljer hur du skriver ut svarsblad, klickar du på Avancerade utskriftsalternativ när du har öppnat dialogrutan Skriv ut.</span><span class="sxs-lookup"><span data-stu-id="49483-161">To choose how to print reply sheets, once you’ve opened the Print dialog, click Advanced printing options.</span></span> <span data-ttu-id="49483-162">En anbudsförfrågan ska skrivas ut för varje leverantör som innehåller de rader som har statusen Skapad eller Skickad.</span><span class="sxs-lookup"><span data-stu-id="49483-162">One RFQ will be printed for each vendor containing the lines that have the status of Created or Sent.</span></span> <span data-ttu-id="49483-163">Annullerade rader och rader med registrerade svar skrivs inte ut.</span><span class="sxs-lookup"><span data-stu-id="49483-163">Canceled lines and lines with registered replies will not be printed.</span></span>   
3. <span data-ttu-id="49483-164">Klicka på Avbryt.</span><span class="sxs-lookup"><span data-stu-id="49483-164">Click Cancel.</span></span>
4. <span data-ttu-id="49483-165">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="49483-165">Click OK.</span></span>
5. <span data-ttu-id="49483-166">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="49483-166">Close the page.</span></span>
6. <span data-ttu-id="49483-167">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="49483-167">Close the page.</span></span>

## <a name="view-the-rfq-journal"></a><span data-ttu-id="49483-168">Visa anbudsförfråganjournalen</span><span class="sxs-lookup"><span data-stu-id="49483-168">View the RFQ journal</span></span>
1. <span data-ttu-id="49483-169">Gå till Anskaffning och källa > Anbudsförfrågningar > Uppföljning av anbudsförfrågning > Journaler för anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="49483-169">Go to Procurement and sourcing > Requests for quotations > Request for quotations follow-up > Request for quotation journals.</span></span>
2. <span data-ttu-id="49483-170">Klicka på Förhandsgranska/Skriv ut.</span><span class="sxs-lookup"><span data-stu-id="49483-170">Click Preview/Print.</span></span>
3. <span data-ttu-id="49483-171">Klicka på Ursprunglig förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="49483-171">Click Original preview.</span></span>
4. <span data-ttu-id="49483-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="49483-172">Close the page.</span></span>
5. <span data-ttu-id="49483-173">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="49483-173">Close the page.</span></span>


