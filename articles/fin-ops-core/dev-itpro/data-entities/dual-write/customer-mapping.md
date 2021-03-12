---
title: Integrerat kundhuvud
description: I det här avsnittet beskrivs integreringen av kunddata mellan Finance and Operations och Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b7e9cd27bb918dc3a6088b45803329deb01a864e
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744412"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="11fdb-103">Integrerad kundmaster</span><span class="sxs-lookup"><span data-stu-id="11fdb-103">Integrated customer master</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


<span data-ttu-id="11fdb-104">Kunddata kan hanteras i fler än ett Dynamics 365-program.</span><span class="sxs-lookup"><span data-stu-id="11fdb-104">Customer data can be mastered in more than one Dynamics 365 application.</span></span> <span data-ttu-id="11fdb-105">En kundrad kan till exempel ha sitt ursprung trots att det finns försäljningsaktiviteter i Dynamics 365 Sales (en modellstyrd app i Dynamics 365), eller så kan en rad ha sitt ursprung i detaljhandelsaktivitet i Dynamics 365 Commerce (Finance and Operations-app).</span><span class="sxs-lookup"><span data-stu-id="11fdb-105">For example, a customer row can originate though sales activity in Dynamics 365 Sales (a model-driven app in Dynamics 365), or a row can originate through retail activity in Dynamics 365 Commerce (a Finance and Operations app).</span></span> <span data-ttu-id="11fdb-106">Oavsett var informationen kommer från kunden integreras den bakom kulisserna.</span><span class="sxs-lookup"><span data-stu-id="11fdb-106">No matter where where the customer data originates, it is integrated behind the scenes.</span></span> <span data-ttu-id="11fdb-107">Integrerad kund huvud ger dig flexibiliteten att hantera kunddata i alla Dynamics 365-program och ger en omfattande översikt över kunden över Dynamics 365-programpaketet.</span><span class="sxs-lookup"><span data-stu-id="11fdb-107">Integrated customer master gives you the flexibility to master customer data in any Dynamics 365 application and provides a comprehensive view of the customer across the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="11fdb-108">Kunddataflöde</span><span class="sxs-lookup"><span data-stu-id="11fdb-108">Customer data flow</span></span>

<span data-ttu-id="11fdb-109">*Kunden* är ett väldefinierat begrepp i program.</span><span class="sxs-lookup"><span data-stu-id="11fdb-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="11fdb-110">Därför innebär integreringen av kunddata bara harmonisering av kundkonceptet mellan de två programmen.</span><span class="sxs-lookup"><span data-stu-id="11fdb-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="11fdb-111">Illustrationen som följer visar kunddataflödet.</span><span class="sxs-lookup"><span data-stu-id="11fdb-111">The following illustration shows the customer data flow.</span></span>

![Kunddataflöde](media/dual-write-customer-data-flow.png)

<span data-ttu-id="11fdb-113">Kunder kan i stort sett delas in i två typer: kommersiella/organisatoriska kunder och konsumenter/slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="11fdb-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="11fdb-114">Dessa två typer av kunder lagras och hanteras på olika sätt i Finance and Operations och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11fdb-114">These two types of customers are stored and handled differently in Finance and Operations and Dataverse.</span></span>

<span data-ttu-id="11fdb-115">I Finance and Operations hanteras både kommersiella/organisatoriska kunder och konsumenter/slutanvändare i en enda tabell som kallas **CustTable** (CustCustomerV3Entity) och de klassificeras baserat på attributet **Typ**.</span><span class="sxs-lookup"><span data-stu-id="11fdb-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="11fdb-116">(Om **typ** är inställd på **organisation** är kunden en kommersiell/organisatorisk kund och om **typ** är inställd på **person** är kunden en konsument/slutanvändare.) Den primära kontaktpersonens information hanteras via tabellen SMMContactPersonEntity.</span><span class="sxs-lookup"><span data-stu-id="11fdb-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity table.</span></span>

<span data-ttu-id="11fdb-117">I Dataverse hanteras kommersiella/organisatoriska kunder i kontotabellen och identifieras som kunder när attributet **RelationshipType** är inställt på **kund**.</span><span class="sxs-lookup"><span data-stu-id="11fdb-117">In Dataverse, commercial/organizational customers are mastered in the Account table and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="11fdb-118">Både konsumenter/slutanvändare och kontaktpersonen representeras av kontakttabellen.</span><span class="sxs-lookup"><span data-stu-id="11fdb-118">Both consumers/end users and the contact person are represented by the Contact table.</span></span> <span data-ttu-id="11fdb-119">För att ge en tydlig åtskillnad mellan en konsument/slutanvändare och en kontaktperson har tabellen **kontakt** en boolesk flagga som heter **säljbar**.</span><span class="sxs-lookup"><span data-stu-id="11fdb-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** table has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="11fdb-120">När **säljbar** är **sant** är kontakten en konsument/slutanvändare och offerter och order kan skapas för den kontakten.</span><span class="sxs-lookup"><span data-stu-id="11fdb-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="11fdb-121">När **säljbar** är **falskt** är kontakten bara en primär kontaktperson för en kund.</span><span class="sxs-lookup"><span data-stu-id="11fdb-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="11fdb-122">När en icke-säljbar kontakt deltar i en offert eller orderprocess är **säljbart** inställt på **sant** för att flagga kontakten som en säljbar kontakt.</span><span class="sxs-lookup"><span data-stu-id="11fdb-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="11fdb-123">En kontakt som har blivit en säljbar kontakt förblir en säljbar kontakt.</span><span class="sxs-lookup"><span data-stu-id="11fdb-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="11fdb-124">Mallar</span><span class="sxs-lookup"><span data-stu-id="11fdb-124">Templates</span></span>

<span data-ttu-id="11fdb-125">Kunddata innehåller all information om kunden, till exempel kundgruppen, adresser, kontaktinformation, betalningsprofil, fakturaprofil och förmånsstatus.</span><span class="sxs-lookup"><span data-stu-id="11fdb-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="11fdb-126">En samling tabellmappningar fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="11fdb-126">A collection of table maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="11fdb-127">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="11fdb-127">Finance and Operations apps</span></span> | <span data-ttu-id="11fdb-128">Andra Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="11fdb-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="11fdb-129">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="11fdb-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="11fdb-130">CDS-kontakter V2</span><span class="sxs-lookup"><span data-stu-id="11fdb-130">CDS Contacts V2</span></span>             | <span data-ttu-id="11fdb-131">kontakter</span><span class="sxs-lookup"><span data-stu-id="11fdb-131">contacts</span></span>                        | <span data-ttu-id="11fdb-132">Den här mallen synkroniserar all primär, sekundär och tertiär kontaktinformation för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="11fdb-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="11fdb-133">Kundgrupper</span><span class="sxs-lookup"><span data-stu-id="11fdb-133">Customer groups</span></span>             | <span data-ttu-id="11fdb-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="11fdb-134">msdyn_customergroups</span></span>            | <span data-ttu-id="11fdb-135">Den här mallen synkroniserar kundgruppinformation.</span><span class="sxs-lookup"><span data-stu-id="11fdb-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="11fdb-136">Kundbetalningsmetod</span><span class="sxs-lookup"><span data-stu-id="11fdb-136">Customer payment method</span></span>     | <span data-ttu-id="11fdb-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="11fdb-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="11fdb-138">Den här mallen synkroniserar information om kundbetalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="11fdb-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="11fdb-139">Kunder V3</span><span class="sxs-lookup"><span data-stu-id="11fdb-139">Customers V3</span></span>                | <span data-ttu-id="11fdb-140">konton</span><span class="sxs-lookup"><span data-stu-id="11fdb-140">accounts</span></span>                        | <span data-ttu-id="11fdb-141">Den här mallen synkroniserar kundhuvudinformation för kommersiella och organisatoriska kunder.</span><span class="sxs-lookup"><span data-stu-id="11fdb-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="11fdb-142">Kunder V3</span><span class="sxs-lookup"><span data-stu-id="11fdb-142">Customers V3</span></span>                | <span data-ttu-id="11fdb-143">kontakter</span><span class="sxs-lookup"><span data-stu-id="11fdb-143">contacts</span></span>                        | <span data-ttu-id="11fdb-144">Den här mallen synkroniserar kundhuvuddata för användare och slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="11fdb-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="11fdb-145">Namnaffix</span><span class="sxs-lookup"><span data-stu-id="11fdb-145">Name affixes</span></span>                | <span data-ttu-id="11fdb-146">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="11fdb-146">msdyn_nameaffixes</span></span>               | <span data-ttu-id="11fdb-147">Mallen synkroniserar referensdata för namnaffix för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="11fdb-147">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="11fdb-148">Betalningsdagsrader – CDS V2</span><span class="sxs-lookup"><span data-stu-id="11fdb-148">Payment day lines CDS V2</span></span>    | <span data-ttu-id="11fdb-149">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="11fdb-149">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="11fdb-150">Mallen synkroniserar referensdata för betalningsplanrader för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="11fdb-150">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="11fdb-151">Betalningsdagar – CDS</span><span class="sxs-lookup"><span data-stu-id="11fdb-151">Payment days CDS</span></span>            | <span data-ttu-id="11fdb-152">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="11fdb-152">msdyn_paymentdays</span></span>               | <span data-ttu-id="11fdb-153">Mallen synkroniserar referensdata för betalningsdagar för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="11fdb-153">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="11fdb-154">Betalningsplanrader</span><span class="sxs-lookup"><span data-stu-id="11fdb-154">Payment schedule lines</span></span>      | <span data-ttu-id="11fdb-155">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="11fdb-155">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="11fdb-156">Synkronisera referensdata för betalningsplanrader för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="11fdb-156">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="11fdb-157">Betalningsplan</span><span class="sxs-lookup"><span data-stu-id="11fdb-157">Payment schedule</span></span>            | <span data-ttu-id="11fdb-158">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="11fdb-158">msdyn_paymentschedules</span></span>          | <span data-ttu-id="11fdb-159">Mallen synkroniserar referensdata för betalningsplan för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="11fdb-159">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="11fdb-160">Betalningsvillkor</span><span class="sxs-lookup"><span data-stu-id="11fdb-160">Terms of payment</span></span>            | <span data-ttu-id="11fdb-161">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="11fdb-161">msdyn_paymentterms</span></span>              | <span data-ttu-id="11fdb-162">Mallen synkroniserar referensdata för betalningsvillkor för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="11fdb-162">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]
