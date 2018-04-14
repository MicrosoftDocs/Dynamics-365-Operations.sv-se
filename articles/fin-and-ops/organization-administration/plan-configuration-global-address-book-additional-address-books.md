---
title: "Planera hur du ska ställa in den globala adressboken och ytterligare adressböcker"
description: "Det här ämnet innehåller en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar den globala adressboken och alla ytterligare adressböcker i Microsoft Dynamics 365 for Finance and Operations. Vissa av besluten kräver att du bekräftar besluten som har fattats för andra produktområden såsom organisationshierarkin."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6919e2bf8555ac49e086fc9aa46ae6a25099ede4
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="plan-how-to-configure-the-global-address-book-and-additional-address-books"></a><span data-ttu-id="f64e4-104">Planera hur du ska ställa in den globala adressboken och ytterligare adressböcker</span><span class="sxs-lookup"><span data-stu-id="f64e4-104">Plan how to configure the global address book and additional address books</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="f64e4-105">Det här ämnet innehåller en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar den globala adressboken och alla ytterligare adressböcker i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f64e4-105">This topic describes the considerations and decisions that you must make during the planning process, before you set up and configure the global address book and any additional address books in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="f64e4-106">Vissa av besluten kräver att du bekräftar besluten som har fattats för andra produktområden såsom organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="f64e4-106">Some of the decisions will require that you confirm the decisions that have been made for other areas of the product, such as the organization hierarchy.</span></span>

<a name="global-address-book"></a><span data-ttu-id="f64e4-107">Global adressbok</span><span class="sxs-lookup"><span data-stu-id="f64e4-107">Global address book</span></span>
-------------------

<span data-ttu-id="f64e4-108">Innan du börjar att arbeta med den globala adressboken måste du bestämma standardvärdena för den.</span><span class="sxs-lookup"><span data-stu-id="f64e4-108">Before you begin to work with the global address book, you must determine the default values for it.</span></span> <span data-ttu-id="f64e4-109">Dessa standardvärden används sedan för eventuella ytterligare adressböcker som du skapar.</span><span class="sxs-lookup"><span data-stu-id="f64e4-109">These default values are then used for any additional address books that you create.</span></span> 

<span data-ttu-id="f64e4-110">**Beslut:**</span><span class="sxs-lookup"><span data-stu-id="f64e4-110">**Decisions:**</span></span>

-   <span data-ttu-id="f64e4-111">Med vilken sekvens visas namnen för partposter av typen **Person**?</span><span class="sxs-lookup"><span data-stu-id="f64e4-111">What sequence should names be displayed in for party records of the **Person** type?</span></span> <span data-ttu-id="f64e4-112">En sekvens ar till exempel förnamn, mellannamn och efternamn.</span><span class="sxs-lookup"><span data-stu-id="f64e4-112">For example, one sequence is last name, middle name, first name.</span></span>
-   <span data-ttu-id="f64e4-113">Ska partposter tas bort från adressboken när rollposten tas bort?</span><span class="sxs-lookup"><span data-stu-id="f64e4-113">Should party records be deleted from the address book when the role record is deleted?</span></span> <span data-ttu-id="f64e4-114">Om till exempel en kundpost raderas, ska även partposten raderas?</span><span class="sxs-lookup"><span data-stu-id="f64e4-114">For example, if a customer record is deleted, should the party record also be deleted?</span></span>
-   <span data-ttu-id="f64e4-115">När en ny post skapas får användare ett meddelande om en dublettpost finns i den globala adressboken?</span><span class="sxs-lookup"><span data-stu-id="f64e4-115">When a new record is created, should users be notified if a duplicate record is found in the global address book?</span></span>
-   <span data-ttu-id="f64e4-116">Ska det universella datanumret i systemet (DUNS) inkluderas i partpostens information?</span><span class="sxs-lookup"><span data-stu-id="f64e4-116">Should the Data Universal Numbering System (DUNS) number be included in a party record’s information?</span></span>
-   <span data-ttu-id="f64e4-117">Om DUNS-numret inkluderas i en partpost, ska numrets unikhet kontrolleras?</span><span class="sxs-lookup"><span data-stu-id="f64e4-117">If the DUNS number is included in a party record, should the uniqueness of the number be checked?</span></span>
-   <span data-ttu-id="f64e4-118">När en partpost skapas i den globala adressboken, vill du ha en standardparttyp, person eller organisation?</span><span class="sxs-lookup"><span data-stu-id="f64e4-118">When a party record is created in the global address book, do you want a default party type, person, or organization?</span></span>
-   <span data-ttu-id="f64e4-119">Vilka användarroller får åtkomst till privata adresser och kontaktinformation för partposter?</span><span class="sxs-lookup"><span data-stu-id="f64e4-119">Which user roles should have access to the private addresses and contact information of party records?</span></span>

## <a name="additional-address-books"></a><span data-ttu-id="f64e4-120">Ytterligare adressböcker</span><span class="sxs-lookup"><span data-stu-id="f64e4-120">Additional address books</span></span>
<span data-ttu-id="f64e4-121">När du har skapat den globala adressboken, kan du skapa ytterligare adressböcker efter behov, till exempel en separat adressbok för varje företag i organisationen eller för varje affärsområde.</span><span class="sxs-lookup"><span data-stu-id="f64e4-121">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span> <span data-ttu-id="f64e4-122">Exempelvis är Fabrikam en internationell organisation som har flera företag och flera affärsområden.</span><span class="sxs-lookup"><span data-stu-id="f64e4-122">For example, Fabrikam is an international organization that has multiple companies and multiple lines of business.</span></span> <span data-ttu-id="f64e4-123">Fabrikam planerar att skapa en adressbok för varje affärsområde.</span><span class="sxs-lookup"><span data-stu-id="f64e4-123">Fabrikam plans to create an address book for each line of business.</span></span> <span data-ttu-id="f64e4-124">För affärsområden som finns på fler än en plats, till exempel det pneumatiska verktygsföretaget, planerar Fabrikam att skapa en adressbok för varje plats.</span><span class="sxs-lookup"><span data-stu-id="f64e4-124">For lines of business that occur in more than one location, such as the pneumatic tools business, Fabrikam plans to create an address book for each location.</span></span> <span data-ttu-id="f64e4-125">Chris, IT-chefen på Fabrikam, har skapat följande lista över adressböcker som krävs.</span><span class="sxs-lookup"><span data-stu-id="f64e4-125">Chris, the IT manager at Fabrikam, has created the following list of address books that are required.</span></span> <span data-ttu-id="f64e4-126">Listan beskriver även partposterna som varje adressbok måste inkludera.</span><span class="sxs-lookup"><span data-stu-id="f64e4-126">This list also describes the party records that each address book must include.</span></span>

-   <span data-ttu-id="f64e4-127">**Kontrakt med offentlig sektor (PubSC)** – Partposter för alla parter som ingår i Fabrikams avtal med den offentliga sektorn.</span><span class="sxs-lookup"><span data-stu-id="f64e4-127">**Public Sector Contracts (PubSC)** – Party records for all parties that are involved in the public sector contracts that Fabrikam holds.</span></span>
-   <span data-ttu-id="f64e4-128">**Kontrakt med privat sektor (PriSC)** – Partposter för alla parter som ingår i Fabrikams avtal med den privata sektorn.</span><span class="sxs-lookup"><span data-stu-id="f64e4-128">**Private Sector Contracts (PriSC)** – Party records for all parties that are involved in the private sector contracts that Fabrikam holds.</span></span>
-   <span data-ttu-id="f64e4-129">**Elektroniska verktyg (ET)** – Partposter för alla parter som ingår i inköp eller försäljning av elektroniska verktyg eller annat som samverkar med de elektroniska verktygen, som tillhandahålls av eller köps in för Fabrikam i företaget Fabrikam-Japan.</span><span class="sxs-lookup"><span data-stu-id="f64e4-129">**Electronic Tools (ET)** – Party records for all parties that are involved in the purchase or sale of electronic tools, or that otherwise interact with the electronic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
-   <span data-ttu-id="f64e4-130">**Pneumatiska verktyg (PTJPN)** – Partposter för alla parter som ingår i inköp eller försäljning av pneumatiska verktyg eller annat som samverkar med de pneumatiska verktygen, som tillhandahålls av eller köps in för Fabrikam i företaget Fabrikam-Japan.</span><span class="sxs-lookup"><span data-stu-id="f64e4-130">**Pneumatic Tools (PTJPN)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
-   <span data-ttu-id="f64e4-131">**Pneumatiska verktyg (PTUSA)** – Partposter för alla parter som ingår i inköp eller försäljning av pneumatiska verktyg eller annat som samverkar med de pneumatiska verktygen, som tillhandahålls av eller köps in för Fabrikam i företaget Fabrikam-US.</span><span class="sxs-lookup"><span data-stu-id="f64e4-131">**Pneumatic Tools (PTUSA)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-US company.</span></span>

<span data-ttu-id="f64e4-132">**Beslut:**</span><span class="sxs-lookup"><span data-stu-id="f64e4-132">**Decision:**</span></span>

-   <span data-ttu-id="f64e4-133">Hur många ytterligare adressböcker ska du skapa?</span><span class="sxs-lookup"><span data-stu-id="f64e4-133">How many additional address books will you create?</span></span>

### <a name="address-book-security"></a><span data-ttu-id="f64e4-134">Adressbokssäkerhet</span><span class="sxs-lookup"><span data-stu-id="f64e4-134">Address book security</span></span>

<span data-ttu-id="f64e4-135">Du kan skapa adressböcker när som helst och du kan även ange säkerhetsparametrar för adressböckerna när som helst.</span><span class="sxs-lookup"><span data-stu-id="f64e4-135">You can create address books at any time, and you can also set security parameters for the address books at any time.</span></span> <span data-ttu-id="f64e4-136">Du måste inte att ange säkerhetsprivilegier för en adressbok, men om du inte gör det kan alla anställda i organisationen den visa alla partposter i den adressboken.</span><span class="sxs-lookup"><span data-stu-id="f64e4-136">You aren't required to set security privileges for an address book, but if you don't, all workers in your organization can view all party records in that address book.</span></span> <span data-ttu-id="f64e4-137">Du kan ange säkerhetsprivilegier för partposter med adressböcker.</span><span class="sxs-lookup"><span data-stu-id="f64e4-137">You can set security privileges to party records through address books.</span></span> <span data-ttu-id="f64e4-138">Säkerhetsprivilegier baseras på team.</span><span class="sxs-lookup"><span data-stu-id="f64e4-138">Security privileges are based on teams.</span></span> <span data-ttu-id="f64e4-139">Det här garanterar att endast anställda som tilldelas till en grupp har åtkomst till en adressbok kan visa partposterna i den adressboken.</span><span class="sxs-lookup"><span data-stu-id="f64e4-139">This approach guarantees that only workers who are assigned to a team that has access to an address book can view the party records in that address book.</span></span> <span data-ttu-id="f64e4-140">Du måste du välja team som har åtkomst till varje adressbok.</span><span class="sxs-lookup"><span data-stu-id="f64e4-140">You must select the teams that have access to each address book.</span></span> <span data-ttu-id="f64e4-141">För varje adressbok kan du ange säkerhetsprivilegier som tillåter eller förhindrar åtkomst för specifika team.</span><span class="sxs-lookup"><span data-stu-id="f64e4-141">For each address book, you can set security privileges that allow or deny access to specific teams.</span></span> <span data-ttu-id="f64e4-142">Om du beviljar ett team åtkomst till en adressbok kan alla medlemmarna i teamet visa posterna i den adressboken.</span><span class="sxs-lookup"><span data-stu-id="f64e4-142">If you grant a team privileges to an address book, all members of that team can view the records in the address book.</span></span> <span data-ttu-id="f64e4-143">Om du inte beviljar ett team åtkomst till en adressbok kan inga medlemmar i teamet visa posterna eller innehållet i den adressboken.</span><span class="sxs-lookup"><span data-stu-id="f64e4-143">If you don't grant a team access to an address book, the members of that team can't view the address book or its contents.</span></span> 

<span data-ttu-id="f64e4-144">**Beslut:**</span><span class="sxs-lookup"><span data-stu-id="f64e4-144">**Decision:**</span></span>

-   <span data-ttu-id="f64e4-145">Vilka team ska ha åtkomst till varje ny adressbok som du skapar?</span><span class="sxs-lookup"><span data-stu-id="f64e4-145">Which teams should have access to each new address book that you will create?</span></span>





