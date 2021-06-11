---
title: Anpassa och använda kundportalen
description: I det här avsnittet beskrivs hur du anpassar kundportalen efter att den har lagts till i systemet.
author: dasani-madipalli
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: ea1fe6ba374c77784c88cf8202bff2eace217b6a
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2021
ms.locfileid: "6102720"
---
# <a name="customize-and-use-the-customer-portal"></a><span data-ttu-id="bfa88-103">Anpassa och använda kundportalen</span><span class="sxs-lookup"><span data-stu-id="bfa88-103">Customize and use the Customer portal</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="bfa88-104">I det här avsnittet beskrivs de olika sidor som medföljer kundportalen.</span><span class="sxs-lookup"><span data-stu-id="bfa88-104">This topic describes the different pages that available in the Customer portal out of the box.</span></span> <span data-ttu-id="bfa88-105">Den förklarar vad sidorna gör och hur du kan anpassa dem.</span><span class="sxs-lookup"><span data-stu-id="bfa88-105">It explains what the pages do and how you can customize them.</span></span>

<span data-ttu-id="bfa88-106">Kundportalen erbjuder några medföljande webbsidor och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="bfa88-106">The Customer portal offers a few webpages and actions out of the box.</span></span> <span data-ttu-id="bfa88-107">I följande webbplatsöversikt finns en översikt över de webbsidor och åtgärder och vilka roller som kan utföra åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="bfa88-107">The following site map provides an overview of those webpages and actions, and the roles that can perform the actions.</span></span>

<span data-ttu-id="bfa88-108">![Översikt över kundportal webbplats](media/customer-portal-site-map.png "Översikt över kundportal webbplats")</span><span class="sxs-lookup"><span data-stu-id="bfa88-108">![Customer portal site map](media/customer-portal-site-map.png "Customer portal site map")</span></span>

## <a name="typical-customizations"></a><span data-ttu-id="bfa88-109">Typiska anpassningar</span><span class="sxs-lookup"><span data-stu-id="bfa88-109">Typical customizations</span></span>

<span data-ttu-id="bfa88-110">Följande avsnitt innehåller information om grunderna i Power Apps-portaler och hur du kan anpassa portaler:</span><span class="sxs-lookup"><span data-stu-id="bfa88-110">The following topics will help you learn the basics about Power Apps portals and how you can customize portals:</span></span>

- <span data-ttu-id="bfa88-111">[Arbeta med mallar](/powerapps/maker/portals/work-with-templates) – i det här avsnittet finns en allmän översikt över hur Power Apps-portaler fungerar och hur du kan göra enkla anpassningar av portaler.</span><span class="sxs-lookup"><span data-stu-id="bfa88-111">[Work with templates](/powerapps/maker/portals/work-with-templates) – This topic provides a general overview of how Power Apps portals works and how you can do simple customizations of portals.</span></span>
- <span data-ttu-id="bfa88-112">[Hantera portalinnehåll](/dynamics365/portals/manage-portal-content) – i det här avsnittet beskrivs hur du kan hantera och anpassa innehållet som ligger på en portal.</span><span class="sxs-lookup"><span data-stu-id="bfa88-112">[Manage portal content](/dynamics365/portals/manage-portal-content) – This topic explains how you can manage and customize the content that you surface in your portal.</span></span>
- <span data-ttu-id="bfa88-113">[Redigera CSS](/powerapps/maker/portals/edit-css) – i det här avsnittet får du hjälp med att göra mer komplexa anpassningar av portalens användargränssnitt.</span><span class="sxs-lookup"><span data-stu-id="bfa88-113">[Edit CSS](/powerapps/maker/portals/edit-css) – This topic helps you make more complex customizations to the user interface (UI) of your portal.</span></span>
- <span data-ttu-id="bfa88-114">[Skapa ett tema för portalen](/dynamics365/portals/create-theme) – i det här avsnittet får du hjälp med att skapa ett användargränssnittstema för portalen.</span><span class="sxs-lookup"><span data-stu-id="bfa88-114">[Create a theme for your portal](/dynamics365/portals/create-theme) – This topic helps you create a UI theme for your portal.</span></span>
- <span data-ttu-id="bfa88-115">[Skapa och exponera portalinnehåll enkelt](/dynamics365/portals/create-expose-portal-content) – i det här avsnittet får du hjälp med att hantera underliggande data och tabeller som du använder för portalen.</span><span class="sxs-lookup"><span data-stu-id="bfa88-115">[Create and expose portal content easily](/dynamics365/portals/create-expose-portal-content) – This topic helps you manage the underlying data and tables that you use for your portal.</span></span>
- <span data-ttu-id="bfa88-116">[Konfigurera en kontakt som ska användas på en portal](/powerapps/maker/portals/configure/configure-contacts) – i det här avsnittet beskrivs hur du skapar och anpassar användarroller och hur du arbetar med säkerhet och autentisering i Power Apps-portaler.</span><span class="sxs-lookup"><span data-stu-id="bfa88-116">[Configure a contact for use on a portal](/powerapps/maker/portals/configure/configure-contacts) – This topic explains how to create and customize user roles, and how security and authentication work in Power Apps portals.</span></span>
- <span data-ttu-id="bfa88-117">[Konfigurera noteringar för tabellformulär och webbformulär på portaler](/powerapps/maker/portals/configure-notes) – i det här avsnittet beskrivs hur du lägger till dokument och ytterligare lagringsutrymme på portalen.</span><span class="sxs-lookup"><span data-stu-id="bfa88-117">[Configure notes for table forms and web forms on portals](/powerapps/maker/portals/configure-notes) – This topic explains how to add documents and additional storage to your portal.</span></span>
- <span data-ttu-id="bfa88-118">[Felhantering för portalens webbplats](/powerapps/maker/portals/admin/view-portal-error-log) – i det här avsnittet beskrivs hur du visar portalens felloggar och lagrar dem i Microsoft Azure Blob Storage-kontot.</span><span class="sxs-lookup"><span data-stu-id="bfa88-118">[Error handling for portal website](/powerapps/maker/portals/admin/view-portal-error-log) – This topic explains how to view portal error logs and store them in your Microsoft Azure Blob storage account.</span></span>

## <a name="customize-the-order-creation-process"></a><span data-ttu-id="bfa88-119">Anpassa processen för att skapa order</span><span class="sxs-lookup"><span data-stu-id="bfa88-119">Customize the order creation process</span></span>

<span data-ttu-id="bfa88-120">När en användare skickar en order med hjälp av kundportalen, synkroniseras ordern automatiskt till motsvarande Dynamics 365 Supply Chain Management-miljö.</span><span class="sxs-lookup"><span data-stu-id="bfa88-120">When a user submits an order by using the Customer portal, the order is automatically synced to the corresponding Dynamics 365 Supply Chain Management environment.</span></span> <span data-ttu-id="bfa88-121">Eftersom användaren är en extern kund, döljs vissa nödvändiga uppgifter avsiktligt från dem.</span><span class="sxs-lookup"><span data-stu-id="bfa88-121">Because the user is an external customer, some required information is intentionally hidden from them.</span></span> <span data-ttu-id="bfa88-122">Denna information fylls i automatiskt när formuläret skickas.</span><span class="sxs-lookup"><span data-stu-id="bfa88-122">This information will automatically be filled in when the form is submitted.</span></span>

<span data-ttu-id="bfa88-123">I det här avsnittet visas hur du bör ställa in kontakter för att undvika fel.</span><span class="sxs-lookup"><span data-stu-id="bfa88-123">This section shows how you should set up contacts to avoid errors.</span></span> <span data-ttu-id="bfa88-124">Den förklarar fält som ställs in automatiskt och hur du kan ändra värdet på dessa fält om du måste.</span><span class="sxs-lookup"><span data-stu-id="bfa88-124">It explains fields that are automatically set and how you can modify the value of those fields if you must.</span></span>

### <a name="the-out-of-box-order-creation-process"></a><span data-ttu-id="bfa88-125">Den medföljande processen för att skapa order</span><span class="sxs-lookup"><span data-stu-id="bfa88-125">The out-of-box order creation process</span></span>

<span data-ttu-id="bfa88-126">Här följer de här standardstegen för att skicka en order från kundportalen.</span><span class="sxs-lookup"><span data-stu-id="bfa88-126">Here are the standard steps for submitting an order from the Customer portal.</span></span>

1. <span data-ttu-id="bfa88-127">På startsidan väljer du panelen **skapa order** för att öppna guiden **Skapa order**.</span><span class="sxs-lookup"><span data-stu-id="bfa88-127">On the home page, select the **Create order** tile to open the **Create Order** wizard.</span></span>
1. <span data-ttu-id="bfa88-128">På sidan **Orderinformation** anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="bfa88-128">On the **Order Information** page, set the following fields:</span></span>

    - <span data-ttu-id="bfa88-129">**Begärt inleveransdatum** – Ange leveransdatum.</span><span class="sxs-lookup"><span data-stu-id="bfa88-129">**Requested receipt date** – Specify the date of delivery.</span></span>
    - <span data-ttu-id="bfa88-130">**Leveransadress** – Ange den adress som ordern ska levereras till.</span><span class="sxs-lookup"><span data-stu-id="bfa88-130">**Delivery address** – Enter the address that the order should be delivered to.</span></span>
    - <span data-ttu-id="bfa88-131">**Företag** – Välj namnet på kundföretaget.</span><span class="sxs-lookup"><span data-stu-id="bfa88-131">**Company** – Select the name of the customer company.</span></span> <span data-ttu-id="bfa88-132">Det här fältet ställs automatiskt in för användare som inte är administratörer.</span><span class="sxs-lookup"><span data-stu-id="bfa88-132">This field is automatically set for non-admin users.</span></span>
    - <span data-ttu-id="bfa88-133">**Rekvisitionsnummer** – Ange orderns rekvisitionsnummer.</span><span class="sxs-lookup"><span data-stu-id="bfa88-133">**Requisition number** – Enter the requisition number of the order.</span></span> <span data-ttu-id="bfa88-134">Detta fält krävs inte.</span><span class="sxs-lookup"><span data-stu-id="bfa88-134">This field isn't required.</span></span>
    - <span data-ttu-id="bfa88-135">**Leverera till land/region** – ange landet eller regionen som artiklarna ska levereras till.</span><span class="sxs-lookup"><span data-stu-id="bfa88-135">**Ship to country/region** – Enter the country or region that the items will be delivered to.</span></span> <span data-ttu-id="bfa88-136">Det här fältet ställs automatiskt in för användare som inte är administratörer.</span><span class="sxs-lookup"><span data-stu-id="bfa88-136">This field is automatically set for non-admin users.</span></span>

    <span data-ttu-id="bfa88-137">![Sidan orderinformation](media/customer-portal-order-information.png "Sidan orderinformation")</span><span class="sxs-lookup"><span data-stu-id="bfa88-137">![Order information page](media/customer-portal-order-information.png "Order information page")</span></span>

1. <span data-ttu-id="bfa88-138">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="bfa88-138">Select **Next**.</span></span>
1. <span data-ttu-id="bfa88-139">På sidan **Artiklar** markerar du **Lägg till artikel**.</span><span class="sxs-lookup"><span data-stu-id="bfa88-139">On the **Items** page, select **Add Item**.</span></span>

    <span data-ttu-id="bfa88-140">![Sidan artiklar](media/customer-portal-items.png "Sidan artiklar")</span><span class="sxs-lookup"><span data-stu-id="bfa88-140">![Items page](media/customer-portal-items.png "Items page")</span></span>

1. <span data-ttu-id="bfa88-141">I dialogrutan **Artikelinformation** anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="bfa88-141">In the **Item Information** dialog box, set the following fields:</span></span>

    - <span data-ttu-id="bfa88-142">**Produktnamn** – Sök och välj en produkt som du vill lägga till i ordern.</span><span class="sxs-lookup"><span data-stu-id="bfa88-142">**Product Name** – Find and select a product to add to the order.</span></span>
    - <span data-ttu-id="bfa88-143">**Kvantitet** – Ange kvantiteten för den valda produkten.</span><span class="sxs-lookup"><span data-stu-id="bfa88-143">**Quantity** – Enter the quantity of the selected product.</span></span>
    - <span data-ttu-id="bfa88-144">**Enhet** – Ange måttenheten (t.ex. **styck**, **kgs** eller **box**).</span><span class="sxs-lookup"><span data-stu-id="bfa88-144">**Unit** – Specify the unit of measure (for example, **ea.**, **kgs**, or **box**).</span></span>
    - <span data-ttu-id="bfa88-145">**Uppskattat nettobelopp** – värdet beräknas som det uppskattade priset för artikeln × kvantiteten för den valda enheten.</span><span class="sxs-lookup"><span data-stu-id="bfa88-145">**Estimated net amount** – The value is calculated as the estimated price of the item × the quantity for the selected unit.</span></span>

    <span data-ttu-id="bfa88-146">![Dialogruta för artikelinformation](media/customer-portal-item-information.png "Dialogruta för artikelinformation")</span><span class="sxs-lookup"><span data-stu-id="bfa88-146">![Item Information dialog box](media/customer-portal-item-information.png "Item Information dialog box")</span></span>

1. <span data-ttu-id="bfa88-147">Välj **Skicka** för att lägga till artikeln till ordern.</span><span class="sxs-lookup"><span data-stu-id="bfa88-147">Select **Submit** to add the item to the order.</span></span>
1. <span data-ttu-id="bfa88-148">Upprepa steg 4 till och med 6 tills du har lagt till alla artiklar som du vill beställa.</span><span class="sxs-lookup"><span data-stu-id="bfa88-148">Repeat steps 4 through 6 until you've added all the items that you want to order.</span></span>
1. <span data-ttu-id="bfa88-149">När du har lagt till alla artiklar väljer du **Nästa** på sidan **Artiklar**.</span><span class="sxs-lookup"><span data-stu-id="bfa88-149">When you've finished adding items, select **Next** on the **Items** page.</span></span>
1. <span data-ttu-id="bfa88-150">På sidan **Orderinformation** finns en sammanfattning av ordern.</span><span class="sxs-lookup"><span data-stu-id="bfa88-150">The **Order Information** page provides a summary of the order.</span></span> <span data-ttu-id="bfa88-151">Granska orderinnehåll och leveransinformation.</span><span class="sxs-lookup"><span data-stu-id="bfa88-151">Review the order contents and delivery details.</span></span> <span data-ttu-id="bfa88-152">Om allting ser korrekt ut väljer du **Skicka** för att skicka ordern.</span><span class="sxs-lookup"><span data-stu-id="bfa88-152">If everything looks correct, select **Submit** to submit the order.</span></span>

    <span data-ttu-id="bfa88-153">![Sidan slutförd orderinformation](media/customer-portal-order-submit.png "Sidan slutförd orderinformation")</span><span class="sxs-lookup"><span data-stu-id="bfa88-153">![Completed order information page](media/customer-portal-order-submit.png "Completed order information page")</span></span>

### <a name="standard-data-setup"></a><span data-ttu-id="bfa88-154">Ställa in standarddata</span><span class="sxs-lookup"><span data-stu-id="bfa88-154">Standard data setup</span></span>

<span data-ttu-id="bfa88-155">För att säkerställa en smidig användarupplevelse fyller kundportalen automatiskt i värden för flera obligatoriska fält.</span><span class="sxs-lookup"><span data-stu-id="bfa88-155">To help ensure a smooth user experience, the Customer portal automatically fills in values for several required fields.</span></span> <span data-ttu-id="bfa88-156">Dessa värden baseras på informationen i kontaktposten för den kund som skickar ordern.</span><span class="sxs-lookup"><span data-stu-id="bfa88-156">These values are based on information in the contact record of the customer who is submitting the order.</span></span>

<span data-ttu-id="bfa88-157">För varje [kontaktrad](/powerapps/maker/portals/configure/configure-contacts) som tillhör en kund som kommer att använda kundportalen för att skicka order måste värden anges för följande obligatoriska fält.</span><span class="sxs-lookup"><span data-stu-id="bfa88-157">For each [contact row](/powerapps/maker/portals/configure/configure-contacts) that belongs to a customer who will use the Customer portal to submit orders, values must be specified for the following required fields.</span></span> <span data-ttu-id="bfa88-158">Annars kommer fel att uppstå.</span><span class="sxs-lookup"><span data-stu-id="bfa88-158">Otherwise, errors will occur.</span></span>

- <span data-ttu-id="bfa88-159">**Företag** – Den juridiska personen som ordern tillhör</span><span class="sxs-lookup"><span data-stu-id="bfa88-159">**Company** – The legal entity that the order belongs to</span></span>
- <span data-ttu-id="bfa88-160">**Potentiell kund** – Det kundkonto som är associerat med ordern.</span><span class="sxs-lookup"><span data-stu-id="bfa88-160">**Potential customer** – The customer account that is associated with the order</span></span>
- <span data-ttu-id="bfa88-161">**Prislista** – den anpassade prislistan för kunden</span><span class="sxs-lookup"><span data-stu-id="bfa88-161">**Price list** – The custom price list for the customer</span></span>
- <span data-ttu-id="bfa88-162">**Valuta** – valutan för priset</span><span class="sxs-lookup"><span data-stu-id="bfa88-162">**Currency** – The currency of the price</span></span>
- <span data-ttu-id="bfa88-163">**Leverera till land/region** – landet eller regionen som artiklarna ska levereras till</span><span class="sxs-lookup"><span data-stu-id="bfa88-163">**Ship to country/region** – The country or region that the items will be delivered to</span></span>

<span data-ttu-id="bfa88-164">Följande fält ställs automatiskt in för tabellen för försäljningsorder:</span><span class="sxs-lookup"><span data-stu-id="bfa88-164">The following fields are automatically set for the sales order table:</span></span>

- <span data-ttu-id="bfa88-165">**Språk** – språket för ordern (som standard hämtas värdet från kontaktposten.)</span><span class="sxs-lookup"><span data-stu-id="bfa88-165">**Language** – The language of the order (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bfa88-166">**Leverera till land/region** – landet eller regionen som artiklarna ska levereras till (som standard hämtas värdet från kontaktposten.)</span><span class="sxs-lookup"><span data-stu-id="bfa88-166">**Ship to country/region** – The country or region that the items will be delivered to (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bfa88-167">**Kontaktperson** – användaren som kan kontaktas för information om ordern (som standard hämtas värdet från kontaktposten.)</span><span class="sxs-lookup"><span data-stu-id="bfa88-167">**Contact person** – The user who can be contacted for information about the order (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bfa88-168">**Företag** – den juridiska person som ordern tillhör (som standard hämtas värdet från kontaktposten.)</span><span class="sxs-lookup"><span data-stu-id="bfa88-168">**Company** – The legal entity that the order belongs to (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bfa88-169">**Potentiell kund** – det kundkonto som är kopplat till ordern (som standard hämtas värdet från kontaktposten.)</span><span class="sxs-lookup"><span data-stu-id="bfa88-169">**Potential customer** – The customer account that is associated with the order (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bfa88-170">**Fakturakund** – Orderns faktureringskonto (standardvärdet är den potentiella kunden från kontaktposten.)</span><span class="sxs-lookup"><span data-stu-id="bfa88-170">**Invoice customer** – The billing account of the order (The default value is the potential customer from the contact record.)</span></span>
- <span data-ttu-id="bfa88-171">**Namn på försäljningsorder** – namnet på försäljningsordern (standardvärdet är **försäljningsorder** .)</span><span class="sxs-lookup"><span data-stu-id="bfa88-171">**Sales order name** – The name of the sales order (The default value is **sales order**.)</span></span>
- <span data-ttu-id="bfa88-172">**Valuta** – Valutan för priset (som standard hämtas värdet från kontaktposten.)</span><span class="sxs-lookup"><span data-stu-id="bfa88-172">**Currency** – The currency of the price (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bfa88-173">**Prislista** – den anpassade prislistan för kunden (som standard hämtas värdet från kontaktposten.)</span><span class="sxs-lookup"><span data-stu-id="bfa88-173">**Price list** – The custom price list for the customer (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bfa88-174">**Beskrivning av leveransadress** – leveransadressen för försäljningsordern (Standardvärdet är **Beskrivning av leveransadress**).</span><span class="sxs-lookup"><span data-stu-id="bfa88-174">**Delivery address description** – The delivery address of the sales order (The default value is **delivery address description**.)</span></span>

### <a name="modify-the-order-creation-process"></a><span data-ttu-id="bfa88-175">Ändra processen för att skapa order</span><span class="sxs-lookup"><span data-stu-id="bfa88-175">Modify the order creation process</span></span>

<span data-ttu-id="bfa88-176">Du kan fritt ändra utseende och användargränssnitt för kundportalen om du inte ändrar den grundläggande processen för att skapa order.</span><span class="sxs-lookup"><span data-stu-id="bfa88-176">You can freely modify the appearance and UI of the Customer portal if you don't change the basic order creation process.</span></span> <span data-ttu-id="bfa88-177">Om du vill ändra processen för att skapa order måste du ha några poäng i åtanke.</span><span class="sxs-lookup"><span data-stu-id="bfa88-177">If you want to change the order creation process, there are a few points that you must keep in mind.</span></span>

<span data-ttu-id="bfa88-178">Ta inte bort följande kolumner från tabellen för försäljningsorder i Microsoft Dataverse eftersom de krävs för att skapa en försäljningsorder i dubbelriktad skrivning:</span><span class="sxs-lookup"><span data-stu-id="bfa88-178">Don't remove the following columns from the sales order table in Microsoft Dataverse, because they are required to create a sales order in dual-write:</span></span>

- <span data-ttu-id="bfa88-179">**Företag** – Den juridiska personen som ordern tillhör</span><span class="sxs-lookup"><span data-stu-id="bfa88-179">**Company** – The legal entity that the order belongs to</span></span>
- <span data-ttu-id="bfa88-180">**Namn** – Namnet på försäljningsordern</span><span class="sxs-lookup"><span data-stu-id="bfa88-180">**Name** – The name of the sales order</span></span>
- <span data-ttu-id="bfa88-181">**Valuta** – valutan för priset</span><span class="sxs-lookup"><span data-stu-id="bfa88-181">**Currency** – The currency of the price</span></span>
- <span data-ttu-id="bfa88-182">**Prislista** – den anpassade prislistan för kunden</span><span class="sxs-lookup"><span data-stu-id="bfa88-182">**Price list** – The custom price list for the customer</span></span>
- <span data-ttu-id="bfa88-183">**Leverera till land/region** – landet eller regionen som artiklarna ska levereras till</span><span class="sxs-lookup"><span data-stu-id="bfa88-183">**Ship to country/region** – The country or region that the items will be delivered to</span></span>
- <span data-ttu-id="bfa88-184">**Potentiell kund** – Det kundkonto som är associerat med ordern.</span><span class="sxs-lookup"><span data-stu-id="bfa88-184">**Potential customer** – The customer account that is associated with the order</span></span>
- <span data-ttu-id="bfa88-185">**Språk** – språket för ordern (vanligtvis är språket den potentiella kundens språk.)</span><span class="sxs-lookup"><span data-stu-id="bfa88-185">**Language** – The language of the order (Typically, this language is the language of the potential customer.)</span></span>
- <span data-ttu-id="bfa88-186">**Beskrivning av leveransadress** – leveransadressen för försäljningsordern</span><span class="sxs-lookup"><span data-stu-id="bfa88-186">**Delivery address description** – The delivery address of the sales order</span></span>

<span data-ttu-id="bfa88-187">För artiklar krävs följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="bfa88-187">For items, the following columns are required:</span></span>

- <span data-ttu-id="bfa88-188">**Produkt** – produkten som ska beställas</span><span class="sxs-lookup"><span data-stu-id="bfa88-188">**Product** – The product to order</span></span>
- <span data-ttu-id="bfa88-189">**Kvantitet** – kvantiteten för den valda produkten</span><span class="sxs-lookup"><span data-stu-id="bfa88-189">**Quantity** – The quantity of the selected product</span></span>
- <span data-ttu-id="bfa88-190">**Enhet** – måttenheten (t.ex. **styck**, **kgs** eller **box**)</span><span class="sxs-lookup"><span data-stu-id="bfa88-190">**Unit** – The unit of measure (for example, **ea.**, **kgs**, or **box**)</span></span>
- <span data-ttu-id="bfa88-191">**Leverera till land/region** – landet eller regionen för leveransen</span><span class="sxs-lookup"><span data-stu-id="bfa88-191">**Ship to country/region** – The country or region of delivery</span></span>
- <span data-ttu-id="bfa88-192">**Beskrivning av leveransadress** – leveransadressen för ordern</span><span class="sxs-lookup"><span data-stu-id="bfa88-192">**Delivery address description** – The delivery address of the order</span></span>

<span data-ttu-id="bfa88-193">Du måste se till att kundportalen inte skickar värden för alla dessa kolumner.</span><span class="sxs-lookup"><span data-stu-id="bfa88-193">You must make sure that your Customer portal somehow submits values for all these columns.</span></span>

<span data-ttu-id="bfa88-194">Om du vill lägga till kolumner på sidan eller ta bort kolumner, se [skapa eller redigera snabbregistreringsformulär för en rationaliserad datainmatningsupplevelse](/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms).</span><span class="sxs-lookup"><span data-stu-id="bfa88-194">If you want to add columns to the page, or remove columns, see [Create or edit quick create forms for a streamlined data entry experience](/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms).</span></span>

<span data-ttu-id="bfa88-195">Om du vill ändra hur kolumnerna är förinställda och hur värden ställs in när sidan sparas, kan du läsa följande information i dokumentationen för Power Apps-portalen:</span><span class="sxs-lookup"><span data-stu-id="bfa88-195">If you want to change how columns are preset and how values are set when the page is saved, see the following information in the Power Apps portals documentation:</span></span>

- [<span data-ttu-id="bfa88-196">Förifyllt fält</span><span class="sxs-lookup"><span data-stu-id="bfa88-196">Prepopulate field</span></span>](/powerapps/maker/portals/configure/configure-web-form-metadata#prepopulate-field)
- [<span data-ttu-id="bfa88-197">Ange värde vid sparande</span><span class="sxs-lookup"><span data-stu-id="bfa88-197">Set Value On Save</span></span>](/powerapps/maker/portals/configure/configure-web-form-metadata#set-value-on-save)

## <a name="customize-the-home-page"></a><span data-ttu-id="bfa88-198">Anpassa startsidan</span><span class="sxs-lookup"><span data-stu-id="bfa88-198">Customize the home page</span></span>

<span data-ttu-id="bfa88-199">Alla kontrollerna i kundportalen är inbyggda i Power Apps-portalkontroller.</span><span class="sxs-lookup"><span data-stu-id="bfa88-199">All the controls in the Customer portal are built-in Power Apps portals controls.</span></span> <span data-ttu-id="bfa88-200">Du kan anpassa dem genom att följa stegen i dokumentationen [Sammanställ en sida](/powerapps/maker/portals/compose-page)Power Apps-portaler.</span><span class="sxs-lookup"><span data-stu-id="bfa88-200">You can customize them by following the steps in [Compose a page](/powerapps/maker/portals/compose-page) in the Power Apps portals documentation.</span></span>

<span data-ttu-id="bfa88-201">Den enda anpassade kontrollen som ingår i kundportalmallen används för att skapa panelerna på startsidan.</span><span class="sxs-lookup"><span data-stu-id="bfa88-201">The only custom control that is included in the Customer portal template is used to create the tiles on the home page.</span></span>

<span data-ttu-id="bfa88-202">![Paneler på startsidan](media/customer-portal-home-page-tiles.png "Paneler på startsidan")</span><span class="sxs-lookup"><span data-stu-id="bfa88-202">![Tiles on the home page](media/customer-portal-home-page-tiles.png "Tiles on the home page")</span></span>

<span data-ttu-id="bfa88-203">Gör så här om du vill ändra paneler.</span><span class="sxs-lookup"><span data-stu-id="bfa88-203">To modify the tiles, follow these steps.</span></span>

1. <span data-ttu-id="bfa88-204">Öppna [Portalhanteringsapp](/powerapps/maker/portals/configure/configure-portal).</span><span class="sxs-lookup"><span data-stu-id="bfa88-204">Open the [Portal Management app](/powerapps/maker/portals/configure/configure-portal).</span></span>
1. <span data-ttu-id="bfa88-205">I navigeringsfönstret till vänster, välj **Sidmallar**.</span><span class="sxs-lookup"><span data-stu-id="bfa88-205">In the navigation pane on the left, select **Page Templates**.</span></span>

    <span data-ttu-id="bfa88-206">![Navigeringsfönster för portalhantering](media/customer-portal-nav.png "Navigeringsfönster för portalhantering")</span><span class="sxs-lookup"><span data-stu-id="bfa88-206">![Portal Management navigation pane](media/customer-portal-nav.png "Portal Management navigation pane")</span></span>

1. <span data-ttu-id="bfa88-207">Markera den sidmall som heter **Start**.</span><span class="sxs-lookup"><span data-stu-id="bfa88-207">Select the page template that is named **Home**.</span></span>
1. <span data-ttu-id="bfa88-208">I fältet **webbmall** väljer du **start**-länken för att öppna källkoden för den sidan.</span><span class="sxs-lookup"><span data-stu-id="bfa88-208">In the **Web Template** field, select the **Home** link to open the source code for that page.</span></span>

    <span data-ttu-id="bfa88-209">![Fältet webbmall](media/customer-portal-web-template.png "Fältet webbmall")</span><span class="sxs-lookup"><span data-stu-id="bfa88-209">![Web Template field](media/customer-portal-web-template.png "Web Template field")</span></span>

1. <span data-ttu-id="bfa88-210">Du bör nu se alla källkoder för startsidan och kan ändra den efter behov.</span><span class="sxs-lookup"><span data-stu-id="bfa88-210">You should now see all the source code for the home page and can modify it as you require.</span></span>

## <a name="resources"></a><span data-ttu-id="bfa88-211">Resurser</span><span class="sxs-lookup"><span data-stu-id="bfa88-211">Resources</span></span>

<span data-ttu-id="bfa88-212">Mer information om hur du kan ställa in och anpassa kundportalen finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="bfa88-212">To learn more about how you can set up and customize the Customer portal, see the following resources:</span></span>

- [<span data-ttu-id="bfa88-213">Power Apps-portaldokumentation</span><span class="sxs-lookup"><span data-stu-id="bfa88-213">Power Apps portals documentation</span></span>](/powerapps/maker/portals/overview)
- [<span data-ttu-id="bfa88-214">Dokumentation för dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="bfa88-214">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)
- [<span data-ttu-id="bfa88-215">Om portalens livscykel</span><span class="sxs-lookup"><span data-stu-id="bfa88-215">About portal lifecycle</span></span>](/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="bfa88-216">Uppgradera en portal</span><span class="sxs-lookup"><span data-stu-id="bfa88-216">Upgrade a portal</span></span>](/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="bfa88-217">Migrera portalkonfiguration</span><span class="sxs-lookup"><span data-stu-id="bfa88-217">Migrate portal configuration</span></span>](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="bfa88-218">Hantering av lösningens livscykel: Dynamics 365 for Customer Engagement-appar</span><span class="sxs-lookup"><span data-stu-id="bfa88-218">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]