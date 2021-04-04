---
title: Planera för att ställa in den globala adressboken och andra adressböcker
description: Det här avsnittet innehåller en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar den globala adressboken och alla ytterligare adressböcker.
author: msftbrking
manager: AnnBe
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a0613b944d0446e339480a71fa890702190ed53
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559975"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a><span data-ttu-id="48717-103">Planera för den globala adressboken och andra adressböcker</span><span class="sxs-lookup"><span data-stu-id="48717-103">Plan for the global address book and other address books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="48717-104">Det här avsnittet innehåller en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar den globala adressboken och alla ytterligare adressböcker.</span><span class="sxs-lookup"><span data-stu-id="48717-104">This topic describes the considerations and decisions that you must make during the planning process, before you set up and configure the global address book and any additional address books.</span></span> <span data-ttu-id="48717-105">Vissa av besluten kräver att du bekräftar besluten som har fattats för andra produktområden såsom organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="48717-105">Some of the decisions will require that you confirm the decisions that have been made for other areas of the product, such as the organization hierarchy.</span></span>

## <a name="global-address-book"></a><span data-ttu-id="48717-106">Global adressbok</span><span class="sxs-lookup"><span data-stu-id="48717-106">Global address book</span></span>

<span data-ttu-id="48717-107">Innan du börjar att arbeta med den globala adressboken måste du bestämma standardvärdena för den.</span><span class="sxs-lookup"><span data-stu-id="48717-107">Before you begin to work with the global address book, you must determine the default values for it.</span></span> <span data-ttu-id="48717-108">Dessa standardvärden används sedan för eventuella ytterligare adressböcker som du skapar.</span><span class="sxs-lookup"><span data-stu-id="48717-108">These default values are then used for any additional address books that you create.</span></span>

<span data-ttu-id="48717-109">**Beslut**</span><span class="sxs-lookup"><span data-stu-id="48717-109">**Decisions**</span></span>

- <span data-ttu-id="48717-110">Med vilken sekvens visas namnen för partposter av typen **Person**?</span><span class="sxs-lookup"><span data-stu-id="48717-110">What sequence should names be displayed in for party records of the **Person** type?</span></span> <span data-ttu-id="48717-111">En sekvens ar till exempel förnamn, mellannamn och efternamn.</span><span class="sxs-lookup"><span data-stu-id="48717-111">For example, one sequence is last name, middle name, first name.</span></span>
- <span data-ttu-id="48717-112">Ska partposter tas bort från adressboken när rollposten tas bort?</span><span class="sxs-lookup"><span data-stu-id="48717-112">Should party records be deleted from the address book when the role record is deleted?</span></span> <span data-ttu-id="48717-113">Om till exempel en kundpost raderas, ska även partposten raderas?</span><span class="sxs-lookup"><span data-stu-id="48717-113">For example, if a customer record is deleted, should the party record also be deleted?</span></span>
- <span data-ttu-id="48717-114">När en ny post skapas får användare ett meddelande om en dublettpost finns i den globala adressboken?</span><span class="sxs-lookup"><span data-stu-id="48717-114">When a new record is created, should users be notified if a duplicate record is found in the global address book?</span></span>
- <span data-ttu-id="48717-115">Ska det universella datanumret i systemet (DUNS) inkluderas i partpostens information?</span><span class="sxs-lookup"><span data-stu-id="48717-115">Should the Data Universal Numbering System (DUNS) number be included in a party record's information?</span></span>
- <span data-ttu-id="48717-116">Om DUNS-numret inkluderas i en partpost, ska numrets unikhet kontrolleras?</span><span class="sxs-lookup"><span data-stu-id="48717-116">If the DUNS number is included in a party record, should the uniqueness of the number be checked?</span></span>
- <span data-ttu-id="48717-117">När en partpost skapas i den globala adressboken, vill du ha en standardparttyp, person eller organisation?</span><span class="sxs-lookup"><span data-stu-id="48717-117">When a party record is created in the global address book, do you want a default party type, person, or organization?</span></span>
- <span data-ttu-id="48717-118">Vilka användarroller får åtkomst till privata adresser och kontaktinformation för partposter?</span><span class="sxs-lookup"><span data-stu-id="48717-118">Which user roles should have access to the private addresses and contact information of party records?</span></span>

## <a name="additional-address-books"></a><span data-ttu-id="48717-119">Ytterligare adressböcker</span><span class="sxs-lookup"><span data-stu-id="48717-119">Additional address books</span></span>

<span data-ttu-id="48717-120">När du har skapat den globala adressboken, kan du skapa ytterligare adressböcker efter behov, till exempel en separat adressbok för varje företag i organisationen eller för varje affärsområde.</span><span class="sxs-lookup"><span data-stu-id="48717-120">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span> <span data-ttu-id="48717-121">Exempelvis är Fabrikam en internationell organisation som har flera företag och flera affärsområden.</span><span class="sxs-lookup"><span data-stu-id="48717-121">For example, Fabrikam is an international organization that has multiple companies and multiple lines of business.</span></span> <span data-ttu-id="48717-122">Fabrikam planerar att skapa en adressbok för varje affärsområde.</span><span class="sxs-lookup"><span data-stu-id="48717-122">Fabrikam plans to create an address book for each line of business.</span></span> <span data-ttu-id="48717-123">För affärsområden som finns på fler än en plats, till exempel det pneumatiska verktygsföretaget, planerar Fabrikam att skapa en adressbok för varje plats.</span><span class="sxs-lookup"><span data-stu-id="48717-123">For lines of business that occur in more than one location, such as the pneumatic tools business, Fabrikam plans to create an address book for each location.</span></span> <span data-ttu-id="48717-124">Chris, IT-chefen på Fabrikam, har skapat följande lista över adressböcker som krävs.</span><span class="sxs-lookup"><span data-stu-id="48717-124">Chris, the IT manager at Fabrikam, has created the following list of address books that are required.</span></span> <span data-ttu-id="48717-125">Listan beskriver även partposterna som varje adressbok måste inkludera.</span><span class="sxs-lookup"><span data-stu-id="48717-125">This list also describes the party records that each address book must include.</span></span>

- <span data-ttu-id="48717-126">**Kontrakt med offentlig sektor (PubSC)** – Partposter för alla parter som ingår i Fabrikams avtal med den offentliga sektorn.</span><span class="sxs-lookup"><span data-stu-id="48717-126">**Public Sector Contracts (PubSC)** – Party records for all parties that are involved in the public sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="48717-127">**Kontrakt med privat sektor (PriSC)** – Partposter för alla parter som ingår i Fabrikams avtal med den privata sektorn.</span><span class="sxs-lookup"><span data-stu-id="48717-127">**Private Sector Contracts (PriSC)** – Party records for all parties that are involved in the private sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="48717-128">**Elektroniska verktyg (ET)** – Partposter för alla parter som ingår i inköp eller försäljning av elektroniska verktyg eller annat som samverkar med de elektroniska verktygen, som tillhandahålls av eller köps in för Fabrikam i företaget Fabrikam-Japan.</span><span class="sxs-lookup"><span data-stu-id="48717-128">**Electronic Tools (ET)** – Party records for all parties that are involved in the purchase or sale of electronic tools, or that otherwise interact with the electronic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="48717-129">**Pneumatiska verktyg (PTJPN)** – Partposter för alla parter som ingår i inköp eller försäljning av pneumatiska verktyg eller annat som samverkar med de pneumatiska verktygen, som tillhandahålls av eller köps in för Fabrikam i företaget Fabrikam-Japan.</span><span class="sxs-lookup"><span data-stu-id="48717-129">**Pneumatic Tools (PTJPN)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="48717-130">**Pneumatiska verktyg (PTUSA)** – Partposter för alla parter som ingår i inköp eller försäljning av pneumatiska verktyg eller annat som samverkar med de pneumatiska verktygen, som tillhandahålls av eller köps in för Fabrikam i företaget Fabrikam-US.</span><span class="sxs-lookup"><span data-stu-id="48717-130">**Pneumatic Tools (PTUSA)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-US company.</span></span>

<span data-ttu-id="48717-131">**Beslut:**</span><span class="sxs-lookup"><span data-stu-id="48717-131">**Decision:**</span></span>

- <span data-ttu-id="48717-132">Hur många ytterligare adressböcker ska du skapa?</span><span class="sxs-lookup"><span data-stu-id="48717-132">How many additional address books will you create?</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]