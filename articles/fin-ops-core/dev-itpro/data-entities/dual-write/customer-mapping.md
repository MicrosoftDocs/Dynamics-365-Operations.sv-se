---
title: Integrerat kundhuvud
description: I det här avsnittet beskrivs integreringen av kunddata mellan Finance and Operations och Common Data Service.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 269346d38eeb3812c352d16f9d50fbcd09307c12
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020023"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="179e4-103">Integrerat kundhuvud</span><span class="sxs-lookup"><span data-stu-id="179e4-103">Integrated customer master</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="179e4-104">Det är typiskt för kundposter som ska hanteras i mer än ett program.</span><span class="sxs-lookup"><span data-stu-id="179e4-104">It's typical for customer records to be mastered in more than one application.</span></span> <span data-ttu-id="179e4-105">Försäljningsaktivitet kan till exempel föra in kommersiella kundposter via ett Sales-program och e-handels- eller butiksförsäljning kan ta in kundposter via en Finance and Operations-app.</span><span class="sxs-lookup"><span data-stu-id="179e4-105">For example, sales activity can bring in commercial customer records through a Sales application, and e-Commerce or retail sales can bring in customer records through a Finance and Operations application.</span></span> <span data-ttu-id="179e4-106">Oavsett var kundposten har sitt ursprung integreras den bakom kulisserna i programgränser och infrastrukturskillnader.</span><span class="sxs-lookup"><span data-stu-id="179e4-106">Regardless of where the customer record originates, it's integrated behind the scenes across application boundaries and infrastructure differences.</span></span> <span data-ttu-id="179e4-107">Integrerad kundhantering hjälper till att hantera scenarier med flera hanteringar och ger en heltäckande vy av kunden till Dynamics 365 programsvit.</span><span class="sxs-lookup"><span data-stu-id="179e4-107">Integrated customer mastering helps handle multi-mastering scenarios and provides a comprehensive view of the customer to the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="179e4-108">Kunddataflöde</span><span class="sxs-lookup"><span data-stu-id="179e4-108">Customer data flow</span></span>

<span data-ttu-id="179e4-109">*Kunden* är ett väldefinierat begrepp i program.</span><span class="sxs-lookup"><span data-stu-id="179e4-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="179e4-110">Därför innebär integreringen av kunddata bara harmonisering av kundkonceptet mellan de två programmen.</span><span class="sxs-lookup"><span data-stu-id="179e4-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="179e4-111">Illustrationen som följer visar kunddataflödet.</span><span class="sxs-lookup"><span data-stu-id="179e4-111">The following illustration shows the customer data flow.</span></span>

![Kunddataflöde](media/dual-write-customer-data-flow.png)

<span data-ttu-id="179e4-113">Kunder kan i stort sett delas in i två typer: kommersiella/organisatoriska kunder och konsumenter/slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="179e4-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="179e4-114">Dessa två typer av kunder lagras och hanteras på olika sätt i Finance and Operations och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="179e4-114">These two types of customers are stored and handled differently in Finance and Operations and Common Data Service.</span></span>

<span data-ttu-id="179e4-115">I Finance and Operations hanteras både kommersiella/organisatoriska kunder och konsumenter/slutanvändare i en enda tabell som kallas **CustTable** (CustomerCustomerV3Entity) och de klassificeras baserat på attributet **Typ**.</span><span class="sxs-lookup"><span data-stu-id="179e4-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustomerCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="179e4-116">(Om **typ** är inställd på **organisation** är kunden en kommersiell/organisatorisk kund och om **typ** är inställd på **person** är kunden en konsument/slutanvändare.) Den primära kontaktpersonens information hanteras via entiteten SMMContactPersonEntity.</span><span class="sxs-lookup"><span data-stu-id="179e4-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity entity.</span></span>

<span data-ttu-id="179e4-117">I Common Data Service hanteras kommersiella/organisatoriska kunder i kontoentiteten och identifieras som kunder när attributet **RelationshipType** är inställt på **kund**.</span><span class="sxs-lookup"><span data-stu-id="179e4-117">In Common Data Service, commercial/organizational customers are mastered in the Account entity and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="179e4-118">Både konsumenter/slutanvändare och kontaktpersonen representeras av kontaktentiteten.</span><span class="sxs-lookup"><span data-stu-id="179e4-118">Both consumers/end users and the contact person are represented by the Contact entity.</span></span> <span data-ttu-id="179e4-119">För att ge en tydlig åtskillnad mellan en konsument/slutanvändare och en kontaktperson har entiteten **kontakt** en boolesk flagga som heter **säljbar**.</span><span class="sxs-lookup"><span data-stu-id="179e4-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** entity has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="179e4-120">När **säljbar** är **sant** är kontakten en konsument/slutanvändare och offerter och order kan skapas för den kontakten.</span><span class="sxs-lookup"><span data-stu-id="179e4-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="179e4-121">När **säljbar** är **falskt** är kontakten bara en primär kontaktperson för en kund.</span><span class="sxs-lookup"><span data-stu-id="179e4-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="179e4-122">När en icke-säljbar kontakt deltar i en offert eller orderprocess är **säljbart** inställt på **sant** för att flagga kontakten som en säljbar kontakt.</span><span class="sxs-lookup"><span data-stu-id="179e4-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="179e4-123">En kontakt som har blivit en säljbar kontakt förblir en säljbar kontakt.</span><span class="sxs-lookup"><span data-stu-id="179e4-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="179e4-124">Mallar</span><span class="sxs-lookup"><span data-stu-id="179e4-124">Templates</span></span>

<span data-ttu-id="179e4-125">Kunddata innehåller all information om kunden, till exempel kundgruppen, adresser, kontaktinformation, betalningsprofil, fakturaprofil och förmånsstatus.</span><span class="sxs-lookup"><span data-stu-id="179e4-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="179e4-126">En samling entitetsmappningar fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="179e4-126">A collection of entity maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="179e4-127">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="179e4-127">Finance and Operations apps</span></span> | <span data-ttu-id="179e4-128">Andra Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="179e4-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="179e4-129">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="179e4-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="179e4-130">CDS-kontakter V2</span><span class="sxs-lookup"><span data-stu-id="179e4-130">CDS Contacts V2</span></span>             | <span data-ttu-id="179e4-131">kontakter</span><span class="sxs-lookup"><span data-stu-id="179e4-131">contacts</span></span>                        | <span data-ttu-id="179e4-132">Den här mallen synkroniserar all primär, sekundär och tertiär kontaktinformation för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="179e4-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="179e4-133">Kundgrupper</span><span class="sxs-lookup"><span data-stu-id="179e4-133">Customer groups</span></span>             | <span data-ttu-id="179e4-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="179e4-134">msdyn_customergroups</span></span>            | <span data-ttu-id="179e4-135">Den här mallen synkroniserar kundgruppinformation.</span><span class="sxs-lookup"><span data-stu-id="179e4-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="179e4-136">Kundbetalningsmetod</span><span class="sxs-lookup"><span data-stu-id="179e4-136">Customer payment method</span></span>     | <span data-ttu-id="179e4-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="179e4-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="179e4-138">Den här mallen synkroniserar information om kundbetalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="179e4-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="179e4-139">Kunder V3</span><span class="sxs-lookup"><span data-stu-id="179e4-139">Customers V3</span></span>                | <span data-ttu-id="179e4-140">konton</span><span class="sxs-lookup"><span data-stu-id="179e4-140">accounts</span></span>                        | <span data-ttu-id="179e4-141">Den här mallen synkroniserar kundhuvudinformation för kommersiella och organisatoriska kunder.</span><span class="sxs-lookup"><span data-stu-id="179e4-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="179e4-142">Kunder V3</span><span class="sxs-lookup"><span data-stu-id="179e4-142">Customers V3</span></span>                | <span data-ttu-id="179e4-143">kontakter</span><span class="sxs-lookup"><span data-stu-id="179e4-143">contacts</span></span>                        | <span data-ttu-id="179e4-144">Den här mallen synkroniserar kundhuvuddata för användare och slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="179e4-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="179e4-145">Förmånskort</span><span class="sxs-lookup"><span data-stu-id="179e4-145">Loyalty card</span></span>                | <span data-ttu-id="179e4-146">msdyn_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="179e4-146">msdyn_loyaltycards</span></span>              | <span data-ttu-id="179e4-147">Den här mallen synkroniserar information om förmånskort.</span><span class="sxs-lookup"><span data-stu-id="179e4-147">This template synchronizes customer loyalty card information.</span></span>
<span data-ttu-id="179e4-148">Namnaffix</span><span class="sxs-lookup"><span data-stu-id="179e4-148">Name affixes</span></span>                | <span data-ttu-id="179e4-149">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="179e4-149">msdyn_nameaffixes</span></span>               | <span data-ttu-id="179e4-150">Mallen synkroniserar referensdata för namnaffix för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="179e4-150">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="179e4-151">Betalningsdagsrader – CDS V2</span><span class="sxs-lookup"><span data-stu-id="179e4-151">Payment day lines CDS V2</span></span>    | <span data-ttu-id="179e4-152">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="179e4-152">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="179e4-153">Mallen synkroniserar referensdata för betalningsplanrader för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="179e4-153">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="179e4-154">Betalningsdagar – CDS</span><span class="sxs-lookup"><span data-stu-id="179e4-154">Payment days CDS</span></span>            | <span data-ttu-id="179e4-155">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="179e4-155">msdyn_paymentdays</span></span>               | <span data-ttu-id="179e4-156">Mallen synkroniserar referensdata för betalningsdagar för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="179e4-156">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="179e4-157">Betalningsplanrader</span><span class="sxs-lookup"><span data-stu-id="179e4-157">Payment schedule lines</span></span>      | <span data-ttu-id="179e4-158">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="179e4-158">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="179e4-159">Synkronisera referensdata för betalningsplanrader för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="179e4-159">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="179e4-160">Betalningsplan</span><span class="sxs-lookup"><span data-stu-id="179e4-160">Payment schedule</span></span>            | <span data-ttu-id="179e4-161">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="179e4-161">msdyn_paymentschedules</span></span>          | <span data-ttu-id="179e4-162">Mallen synkroniserar referensdata för betalningsplan för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="179e4-162">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="179e4-163">Betalningsvillkor</span><span class="sxs-lookup"><span data-stu-id="179e4-163">Terms of payment</span></span>            | <span data-ttu-id="179e4-164">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="179e4-164">msdyn_paymentterms</span></span>              | <span data-ttu-id="179e4-165">Mallen synkroniserar referensdata för betalningsvillkor för både kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="179e4-165">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]
