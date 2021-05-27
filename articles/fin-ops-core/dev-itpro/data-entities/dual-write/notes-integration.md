---
title: Integrering av anteckning
description: I det här avsnittet beskrivs integreringen av anteckningsdata i dubbel skrivning.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: ed068f4264269334babec9acd59d9d58551333b4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018396"
---
# <a name="note-integration"></a><span data-ttu-id="875b3-103">Integrering av anteckning</span><span class="sxs-lookup"><span data-stu-id="875b3-103">Note integration</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="875b3-104">Under affärsprocesser samlar Microsoft Dynamics 365 användare ofta in information om sina kunder.</span><span class="sxs-lookup"><span data-stu-id="875b3-104">During business processes, Microsoft Dynamics 365 users often gather information about their customers.</span></span> <span data-ttu-id="875b3-105">Denna information registreras som aktiviteter och anteckningar.</span><span class="sxs-lookup"><span data-stu-id="875b3-105">This information is recorded as activities and notes.</span></span> <span data-ttu-id="875b3-106">I det här avsnittet beskrivs integreringen av anteckningsdata i dubbel skrivning.</span><span class="sxs-lookup"><span data-stu-id="875b3-106">This topic describes the integration of note data in dual-write.</span></span>

<span data-ttu-id="875b3-107">Kundinformation kan klassificeras på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="875b3-107">Customer information can be classified in the following ways:</span></span>

+ <span data-ttu-id="875b3-108">**Handlingsbar information som en Dynamics 365-användare hanterar för en kunds räkning** – Till exempel Contoso (en Dynamics 365-användare) genomför ett spelprogram.</span><span class="sxs-lookup"><span data-stu-id="875b3-108">**Actionable information that a Dynamics 365 user handles on behalf of a customer** – For example, Contoso (a Dynamics 365 user) is conducting a game show.</span></span> <span data-ttu-id="875b3-109">En av Contosos kunder (en kund) vill delta i programmet.</span><span class="sxs-lookup"><span data-stu-id="875b3-109">One of Contoso's customers (a customer) wants to attend the game show.</span></span> <span data-ttu-id="875b3-110">Kunden ber en Contoso-medarbetare att boka en plats i ett spelprogram för dem.</span><span class="sxs-lookup"><span data-stu-id="875b3-110">The customer asks a Contoso employee to book a slot in the game show for them.</span></span> <span data-ttu-id="875b3-111">Denna reservation sker i Contosos kalender för händelsedeltagaren.</span><span class="sxs-lookup"><span data-stu-id="875b3-111">The booking occurs in Contoso's event attendee's calendar.</span></span>
+ <span data-ttu-id="875b3-112">**Åtgärdsbar information för en Dynamics 365-användare** – En kund som köper en Surface-enhet anger speciella instruktioner som anger att enheten ska vara gift förpackad före leverans.</span><span class="sxs-lookup"><span data-stu-id="875b3-112">**Actionable information for a Dynamics 365 user** – For example, a customer who is purchasing a Surface unit enters special instructions that indicate that the device should be gift wrapped before delivery.</span></span> <span data-ttu-id="875b3-113">Instruktionerna är handlingsbar information som ska hanteras av Contoso-medarbetaren som ansvarar för förpackning.</span><span class="sxs-lookup"><span data-stu-id="875b3-113">These instructions are actionable information that should be handled by the Contoso employee who is responsible for packaging.</span></span>
+ <span data-ttu-id="875b3-114">**Icke-handlingsbar information** – En kund besöker till exempel Contoso-butiken och uttrycker under sin dialog med en butiksrelation, intresse för *Halo*-spel och speltillbehör.</span><span class="sxs-lookup"><span data-stu-id="875b3-114">**Non-actionable information** – For example, a customer visits the Contoso store and, during their conversation with a store associate, expresses interest in *Halo* games and gaming accessories.</span></span> <span data-ttu-id="875b3-115">Butikens personal gör en notering om den här informationen.</span><span class="sxs-lookup"><span data-stu-id="875b3-115">The store associate makes a note of this information.</span></span> <span data-ttu-id="875b3-116">Produktrekommendationsmotorn använder sedan den för att göra rekommendationer till kunden.</span><span class="sxs-lookup"><span data-stu-id="875b3-116">The product recommendations engine then uses it to make recommendations to the customer.</span></span>

<span data-ttu-id="875b3-117">I allmänhet fångas handlingsbar information in som *aktiviteter* i Finance and Operations-appar och kundengagemangsappar.</span><span class="sxs-lookup"><span data-stu-id="875b3-117">In general, actionable information is captured as *activities* in Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="875b3-118">Ej handlingsbar information fångas som *anteckningar* i Finance and Operations-appar *kommentarer* i kundengagemangsappar.</span><span class="sxs-lookup"><span data-stu-id="875b3-118">Non-actionable information is captured as *notes* in Finance and Operations apps, and as *annotations* in customer engagement apps.</span></span>

> [!TIP]
> <span data-ttu-id="875b3-119">Även om noteringar är avsedda för icke-åtgärdsbar information hindrar programmen inte dig från att använda dem för att lagra och hantera åtgärdsbar information om du vill använda dem på det sättet.</span><span class="sxs-lookup"><span data-stu-id="875b3-119">Although notes are intended for non-actionable information, the apps won't prevent you from using them to store and handle actionable information if you want to use them in that way.</span></span>

<span data-ttu-id="875b3-120">Microsoft frisläpper för närvarande funktioner för noteringsintegrering.</span><span class="sxs-lookup"><span data-stu-id="875b3-120">Microsoft is currently releasing functionality for note integration.</span></span> <span data-ttu-id="875b3-121">(Funktioner för aktivitetsintegrering kommer att frisläppas senare.) Noteringsintegreringen är tillgänglig för kunder, leverantörer, försäljningsorder och inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="875b3-121">(Functionality for activity integration will be released later.) Note integration is available for customers, vendors, sales orders, and purchase orders.</span></span>

## <a name="create-a-note-in-a-customer-engagement-app"></a><span data-ttu-id="875b3-122">Skapa en notering i en kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="875b3-122">Create a note in a customer engagement app</span></span>

<span data-ttu-id="875b3-123">Följ de här stegen om du vill skapa en notering i en kundengagemangsapp och synkronisera den i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="875b3-123">To create a note in a customer engagement app and then sync it to a Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="875b3-124">I kundengagemangsapp, öppna kontopostför en kund.</span><span class="sxs-lookup"><span data-stu-id="875b3-124">In the customer engagement app, open the account record for a customer.</span></span>
2. <span data-ttu-id="875b3-125">I fönstret **tidslinje** välj plustecknet (**+**) och välj sedan **Anteckning** för att skapa en anteckning.</span><span class="sxs-lookup"><span data-stu-id="875b3-125">In the **Timeline** pane, select the plus sign (**+**), and then select **Note** to create a note.</span></span>

    ![Skapa en notering i en kundengagemangsapp](media/notes-ce-1.png)

3. <span data-ttu-id="875b3-127">Ange en titel och en beskrivning och välj sedan **Lägg till notering**.</span><span class="sxs-lookup"><span data-stu-id="875b3-127">Enter a title and description, and then select **Add note**.</span></span>

    ![Ange en titel och en beskrivning](media/notes-ce-2.png)

    <span data-ttu-id="875b3-129">Den nya noteringen läggs till kundens tidslinje.</span><span class="sxs-lookup"><span data-stu-id="875b3-129">The new note is added to the customer timeline.</span></span>

    ![Ny notering på kundens tidslinje](media/notes-ce-3.png)

4. <span data-ttu-id="875b3-131">Logga in på Finance and Operations-appen och öppna samma kundpost.</span><span class="sxs-lookup"><span data-stu-id="875b3-131">Sign in to the Finance and Operations app, and open the same customer record.</span></span> <span data-ttu-id="875b3-132">Lägg märke till att knappen **Bilagor** (gemsymbol) i det övre högra hörnet anger att posten har en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="875b3-132">Notice that the **Attachments** button (paperclip symbol) in the upper-right corner indicates that the record has an attachment.</span></span>

    ![Meddelande om en bilaga](media/notes-ce-4.png)

5. <span data-ttu-id="875b3-134">Välj knappen **Bilagor** för att öppna sidan **Bilagor**.</span><span class="sxs-lookup"><span data-stu-id="875b3-134">Select the **Attachments** button to open the **Attachments** page.</span></span> <span data-ttu-id="875b3-135">Du bör hitta noteringen som du skapade i kundengagemangsappen.</span><span class="sxs-lookup"><span data-stu-id="875b3-135">You should find the note that you created in the customer engagement app.</span></span>

    ![Notering från kundengagemangsapp](media/notes-ce-5.png)

<span data-ttu-id="875b3-137">Alla uppdateringar av noteringen synkroniseras fram och tillbaka mellan Finance and Operations-appen och kundengagemangsappen.</span><span class="sxs-lookup"><span data-stu-id="875b3-137">Any updates to the note are synced back and forth between the Finance and Operations app and the customer engagement app.</span></span>

## <a name="create-a-note-in-a-finance-and-operations-app"></a><span data-ttu-id="875b3-138">Skapa en notering i Finance and Operations-appen</span><span class="sxs-lookup"><span data-stu-id="875b3-138">Create a note in a Finance and Operations app</span></span>

<span data-ttu-id="875b3-139">Du kan också skapa en anteckning i en Finance and Operations-app och den kommer att synkroniseras till kundengagemangsappen.</span><span class="sxs-lookup"><span data-stu-id="875b3-139">You can also create a note in a Finance and Operations app, and it will be synced to a customer engagement app.</span></span>

<span data-ttu-id="875b3-140">Följ de här stegen om du vill skapa en notering i Finance and Operations och synkroniserad den sedan till en kundengagemangsapp.</span><span class="sxs-lookup"><span data-stu-id="875b3-140">To create a note in a Finance and Operations app and then sync it to a customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="875b3-141">I Finance and Operations-appen, på sidan **Bilagor**, välj **Ny** \> **notering**.</span><span class="sxs-lookup"><span data-stu-id="875b3-141">In the Finance and Operations app, on the **Attachments** page, select **New** \> **Note**.</span></span>

    ![Skapa en notering i en Finance and Operations-app](media/notes-fo-1.png)

2. <span data-ttu-id="875b3-143">Ange en rubrik och en kort uppsättning instruktioner och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="875b3-143">Enter a title and a brief set of instructions, and then select **Save**.</span></span>

    ![Ange en titel och instruktioner](media/notes-fo-2.png)

3. <span data-ttu-id="875b3-145">Uppdatera posten i kundengagemangsapp.</span><span class="sxs-lookup"><span data-stu-id="875b3-145">In the customer engagement app, update the record.</span></span> <span data-ttu-id="875b3-146">Du bör hitta den nya noteringen under tidslinjen.</span><span class="sxs-lookup"><span data-stu-id="875b3-146">You should find the new note on the timeline.</span></span>

    ![Ny notering på tidslinjen i kundengagemangsapp](media/notes-fo-3.png)

<span data-ttu-id="875b3-148">Du kan klassificera en notering som intern eller extern.</span><span class="sxs-lookup"><span data-stu-id="875b3-148">You can classify a note as either internal or external.</span></span>

- <span data-ttu-id="875b3-149">I Finance and Operations-app, på sidan **Bilagor**, öppna en anteckning och sedan i fältet **Begränsning** välj **Intern** eller **Extern**.</span><span class="sxs-lookup"><span data-stu-id="875b3-149">In the Finance and Operations app, on the **Attachments** page, open the note, and then, in the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Begränsningsfält](media/notes-fo-4.png)

<span data-ttu-id="875b3-151">Du kan även skapa en URL.</span><span class="sxs-lookup"><span data-stu-id="875b3-151">You can also create a URL.</span></span>

1. <span data-ttu-id="875b3-152">I Finance and Operations-appen, på sidan **Bilagor**, välj **Ny** \> **URL**.</span><span class="sxs-lookup"><span data-stu-id="875b3-152">In the Finance and Operations app, on the **Attachments** page, select **New** \> **URL**.</span></span>
2. <span data-ttu-id="875b3-153">Ange en titel och en URL.</span><span class="sxs-lookup"><span data-stu-id="875b3-153">Enter a title and the URL.</span></span>
3. <span data-ttu-id="875b3-154">I fältet **Begränsning**, välj **Intern** eller **Extern**.</span><span class="sxs-lookup"><span data-stu-id="875b3-154">In the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Skapa en URL i en Finance and Operations-app](media/notes-fo-5.png)

4. <span data-ttu-id="875b3-156">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="875b3-156">Select **Save**.</span></span>

    <span data-ttu-id="875b3-157">Eftersom kundengagemangsappar inte har någon URL-typ integreras URL med dubbel skrivning som en notering.</span><span class="sxs-lookup"><span data-stu-id="875b3-157">Because customer engagement apps don't have a URL type, the URL is integrated with dual-write as a note.</span></span>

    ![URL visas som en notering i en kundengagemangsapp](media/notes-ce-6.png)

> [!NOTE]
> <span data-ttu-id="875b3-159">Filbilagor stöds inte.</span><span class="sxs-lookup"><span data-stu-id="875b3-159">File attachments aren't supported.</span></span>

## <a name="templates"></a><span data-ttu-id="875b3-160">Mallar</span><span class="sxs-lookup"><span data-stu-id="875b3-160">Templates</span></span>

<span data-ttu-id="875b3-161">Integrering av anteckning inkluderar en samling tabellmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="875b3-161">Note integration includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="875b3-162">Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="875b3-162">Finance and Operations app</span></span> | <span data-ttu-id="875b3-163">Kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="875b3-163">Customer engagement app</span></span> | <span data-ttu-id="875b3-164">beskrivning</span><span class="sxs-lookup"><span data-stu-id="875b3-164">Description</span></span> |
|----------------------------|-------------------------|-------------|
| [<span data-ttu-id="875b3-165">Kundbilagor</span><span class="sxs-lookup"><span data-stu-id="875b3-165">Customer Attachments</span></span>](mapping-reference.md#230) | <span data-ttu-id="875b3-166">Anteckning</span><span class="sxs-lookup"><span data-stu-id="875b3-166">Annotations</span></span> | <span data-ttu-id="875b3-167">Företag som använder vanlig text och URL-adresser för att samla in kundspecifik information (för både organisationer och personer).</span><span class="sxs-lookup"><span data-stu-id="875b3-167">Businesses that use plain text and URLs to capture customer-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="875b3-168">Bilagor till leverantörsdokument</span><span class="sxs-lookup"><span data-stu-id="875b3-168">Vendor document attachments</span></span>](mapping-reference.md#231) | <span data-ttu-id="875b3-169">Anteckning</span><span class="sxs-lookup"><span data-stu-id="875b3-169">Annotations</span></span> | <span data-ttu-id="875b3-170">Företag som använder vanlig text och URL-adresser för att samla in leverantörsspecifik information (för både organisationer och personer).</span><span class="sxs-lookup"><span data-stu-id="875b3-170">Businesses that use plain text and URLs to capture vendor-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="875b3-171">Försäljningsorderrubrikens dokumentbilagor</span><span class="sxs-lookup"><span data-stu-id="875b3-171">Sales order header document attachments</span></span>](mapping-reference.md#229) | <span data-ttu-id="875b3-172">Anteckning</span><span class="sxs-lookup"><span data-stu-id="875b3-172">Annotations</span></span> | <span data-ttu-id="875b3-173">Företag som använder vanlig text och URL-adresser för att samla in försäljningsorderspecifik information.</span><span class="sxs-lookup"><span data-stu-id="875b3-173">Businesses that use plain text and URLs to capture sales order–specific information.</span></span> |
| [<span data-ttu-id="875b3-174">Inköpsorderhuvudets dokumentbilagor</span><span class="sxs-lookup"><span data-stu-id="875b3-174">Purchase order header document attachments</span></span>](mapping-reference.md#232) | <span data-ttu-id="875b3-175">Anteckning</span><span class="sxs-lookup"><span data-stu-id="875b3-175">Annotations</span></span> | <span data-ttu-id="875b3-176">Företag som använder vanlig text och URL-adresser för att samla in inköpsorderspecifik information.</span><span class="sxs-lookup"><span data-stu-id="875b3-176">Businesses that use plain text and URLs to capture purchase order–specific information.</span></span> |

<span data-ttu-id="875b3-177">Mer information finns i [Mappningsreferens för dubbel skrivning](mapping-reference.md).</span><span class="sxs-lookup"><span data-stu-id="875b3-177">For more information, see [Dual-write mapping reference](mapping-reference.md).</span></span>
