---
title: Använda Power Portal med datamodellen för part
description: I det här avsnittet beskrivs ändringarna av Power Portal-webbrollerna på grund av partens datamodell i nedskrivningen.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: a2ea914344341ee26138e853727c551bdd5d733e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833100"
---
# <a name="using-power-portal-with-the-party-data-model"></a><span data-ttu-id="e76a4-103">Använda Power Portal med datamodellen för part</span><span class="sxs-lookup"><span data-stu-id="e76a4-103">Using Power Portal with the Party data model</span></span>

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e76a4-104">Lösningen för dubbelriktad skrivning för programorkestrering version 2.0.999.0 innehåller senare datamodelländringar av parten och den globala adressboken för konto- och kontaktregistren.</span><span class="sxs-lookup"><span data-stu-id="e76a4-104">The Dual-write application orchestration solution version 2.0.999.0 and later includes data model changes to party and global address book for the Account and Contact tables.</span></span> <span data-ttu-id="e76a4-105">Ändringarna tillåter relationer mellan många som stöder avancerade affärsscenarier.</span><span class="sxs-lookup"><span data-stu-id="e76a4-105">The changes allow many-to-many relationships that support advanced business scenarios.</span></span> <span data-ttu-id="e76a4-106">Dessa ändringar stöds inte av portalwebbrollerna, inklusive kundportalen, som levereras out-of-the-box eller som fanns i din miljö innan du installerade webbplatsskrivning.</span><span class="sxs-lookup"><span data-stu-id="e76a4-106">These changes are not supported by portal web roles, including the customer portal, that are shipped out-of-the-box or that existed in your environment before you installed dual-write.</span></span> <span data-ttu-id="e76a4-107">För att webbrollerna ska fungera som förväntat måste du skapa nya webbroller med hjälp av den nya datamodellen.</span><span class="sxs-lookup"><span data-stu-id="e76a4-107">For the web roles to work as expected, you need to create new web roles using the new data model.</span></span> 

<span data-ttu-id="e76a4-108">Sammanfattningen är att det sätt på vilket register samverkar har ändrats, men registerbehörigheterna i kundportalen har inte ändrats.</span><span class="sxs-lookup"><span data-stu-id="e76a4-108">In summary, the way the tables interact has changed, but the table permissions in the customer portal haven't changed.</span></span> <span data-ttu-id="e76a4-109">I det här avsnittet beskrivs hur du skapar nya webbroller som arbetar med den nya avancerade datamodellen.</span><span class="sxs-lookup"><span data-stu-id="e76a4-109">This topic explains how to create new web roles that work with the new advanced data model.</span></span>

<span data-ttu-id="e76a4-110">Detta diagram visar tabellförhållandet **utan** partiets och den globala adressbokens datamodell:</span><span class="sxs-lookup"><span data-stu-id="e76a4-110">This diagram shows the table relationship **without** the party and global address book data model:</span></span>

   ![utan partmodell](media/without-party-model.PNG)

<span data-ttu-id="e76a4-112">Detta diagram visar tabellförhållandet **med** partiets och den globala adressbokens datamodell:</span><span class="sxs-lookup"><span data-stu-id="e76a4-112">This diagram shows the table relationship **with** the party and global address book data model:</span></span>

   ![med partmodell](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a><span data-ttu-id="e76a4-114">Skapa en ny registerbehörighet</span><span class="sxs-lookup"><span data-stu-id="e76a4-114">Create a new table permission</span></span>

<span data-ttu-id="e76a4-115">Gör på följande sätt om du vill skapa de nya registerbehörigheterna:</span><span class="sxs-lookup"><span data-stu-id="e76a4-115">To create these new table permissions, follow these steps:</span></span>

1. <span data-ttu-id="e76a4-116">Logga in på [Power Apps](https://make.powerapps.com) och gå till programmen.</span><span class="sxs-lookup"><span data-stu-id="e76a4-116">Sign in to [Power Apps](https://make.powerapps.com), and go to your apps.</span></span>
2. <span data-ttu-id="e76a4-117">Välj ett portalhanteringsprogram.</span><span class="sxs-lookup"><span data-stu-id="e76a4-117">Select your Portal Management app.</span></span>
3. <span data-ttu-id="e76a4-118">I sidfältet, välj **Säkerhet > Registerbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="e76a4-118">In the side bar, select **Security > Table permissions**.</span></span>

    <span data-ttu-id="e76a4-119">Du måste skapa tre nya behörigheter:</span><span class="sxs-lookup"><span data-stu-id="e76a4-119">You must create three new permissions:</span></span>

    + <span data-ttu-id="e76a4-120">Kontakt till partanslutning</span><span class="sxs-lookup"><span data-stu-id="e76a4-120">Contact to Party connection</span></span>
    + <span data-ttu-id="e76a4-121">Part till kontoanslutning</span><span class="sxs-lookup"><span data-stu-id="e76a4-121">Party to Account connection</span></span>
    + <span data-ttu-id="e76a4-122">Anslutning mellan konto och beställning</span><span class="sxs-lookup"><span data-stu-id="e76a4-122">Account to Order connection</span></span>

4. <span data-ttu-id="e76a4-123">Skapa och spara en ny behörighet för anslutningen till kontaktpersonen och ange följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="e76a4-123">Create and save a new permission for the Contact to Party connection, setting these parameters:</span></span>

    + <span data-ttu-id="e76a4-124">**Namn**: Part till kontoanslutning (eller ditt val)</span><span class="sxs-lookup"><span data-stu-id="e76a4-124">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="e76a4-125">**Registernamn**: msdyn_contactforparty</span><span class="sxs-lookup"><span data-stu-id="e76a4-125">**Table Name**: msdyn_contactforparty</span></span>
    + <span data-ttu-id="e76a4-126">**Webbplats**: kundportal</span><span class="sxs-lookup"><span data-stu-id="e76a4-126">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="e76a4-127">**Område**: Kontakt</span><span class="sxs-lookup"><span data-stu-id="e76a4-127">**Scope**: Contact</span></span>
    + <span data-ttu-id="e76a4-128">**Behörigheter**: Välj alla</span><span class="sxs-lookup"><span data-stu-id="e76a4-128">**Privileges**: Select all</span></span>
    + <span data-ttu-id="e76a4-129">**Webbroller**: Autentiserade användare, kundrepresentant (eller ditt val)</span><span class="sxs-lookup"><span data-stu-id="e76a4-129">**Web roles**: Authenticated Users, Customer Representative (or your choice)</span></span>

5. <span data-ttu-id="e76a4-130">Skapa och spara en ny behörighet för part till konto-anslutning och ange följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="e76a4-130">Create and save a new permission for the Party to Account connection, setting these parameters:</span></span>

    + <span data-ttu-id="e76a4-131">**Namn**: Part till kontoanslutning (eller ditt val)</span><span class="sxs-lookup"><span data-stu-id="e76a4-131">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="e76a4-132">**Registernamn**: konto</span><span class="sxs-lookup"><span data-stu-id="e76a4-132">**Table Name**: account</span></span>
    + <span data-ttu-id="e76a4-133">**Webbplats**: kundportal</span><span class="sxs-lookup"><span data-stu-id="e76a4-133">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="e76a4-134">**Område**: Överordnad</span><span class="sxs-lookup"><span data-stu-id="e76a4-134">**Scope**: Parent</span></span>
    + <span data-ttu-id="e76a4-135">**Behörigheter**: Välj alla</span><span class="sxs-lookup"><span data-stu-id="e76a4-135">**Privileges**: Select all</span></span>
    + <span data-ttu-id="e76a4-136">**Överordnad registerbehörighet**: kontakt till part-anslutning</span><span class="sxs-lookup"><span data-stu-id="e76a4-136">**Parent Table Permission**: Contact to Party Connection</span></span>

6. <span data-ttu-id="e76a4-137">Skapa och spara en ny behörighet för konto till order-anslutning och ange följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="e76a4-137">Create and save a new permission for the Account to Order connection, setting these parameters:</span></span>

    + <span data-ttu-id="e76a4-138">**Namn**: Konto till order-anslutning (eller ditt val)</span><span class="sxs-lookup"><span data-stu-id="e76a4-138">**Name**: Account to Order Connection (or your choice)</span></span>
    + <span data-ttu-id="e76a4-139">**Registernamn**: försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="e76a4-139">**Table Name**: salesorder</span></span>
    + <span data-ttu-id="e76a4-140">**Webbplats**: kundportal</span><span class="sxs-lookup"><span data-stu-id="e76a4-140">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="e76a4-141">**Område**: Överordnad</span><span class="sxs-lookup"><span data-stu-id="e76a4-141">**Scope**: Parent</span></span>
    + <span data-ttu-id="e76a4-142">**Behörigheter**: Välj alla</span><span class="sxs-lookup"><span data-stu-id="e76a4-142">**Privileges**: Select all</span></span>
    + <span data-ttu-id="e76a4-143">**Överordnad registerbehörighet**: part till konto-anslutning</span><span class="sxs-lookup"><span data-stu-id="e76a4-143">**Parent Table Permission**: Party to Account Connection</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
