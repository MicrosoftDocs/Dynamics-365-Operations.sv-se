---
title: Användarsäkerhet för leverantörportal
description: Den här artikeln innehåller information om hur du konfigurerar säkerhet för externa leverantörer som använder leverantörsportalen. Denna information gäller endast Dynamics AX-versionerna från februari 2016 &amp; maj 2016.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2b95d386dd12bb1cb3577c3820b0be82d28df8e
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188498"
---
# <a name="vendor-portal-user-security"></a><span data-ttu-id="520d0-104">Användarsäkerhet på leverantörsportalen</span><span class="sxs-lookup"><span data-stu-id="520d0-104">Vendor portal user security</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="520d0-105">Den här artikeln innehåller information om hur du konfigurerar säkerhet för externa leverantörer som använder leverantörsportalen.</span><span class="sxs-lookup"><span data-stu-id="520d0-105">This article explains how to set up security for external vendors who use the Vendor portal.</span></span> <span data-ttu-id="520d0-106">Denna information gäller endast Dynamics AX-versionerna från februari 2016 &amp; maj 2016.</span><span class="sxs-lookup"><span data-stu-id="520d0-106">This information applies only to the February 2016 &amp; May 2016 versions of Dynamics AX.</span></span>

<span data-ttu-id="520d0-107">Funktionen för leverantörsportal har ersatts med utökade funktioner för leverantörsamarbeten i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="520d0-107">The Vendor portal functionality has been replaced by extended vendor collaboration functionality in Dynamics 365 for Operations version 1611.</span></span> <span data-ttu-id="520d0-108">Mer information om hur du konfigurerar säkerheten för leverantörssamarbeten finns i [Skapa och underhålla leverantörssamarbete](set-up-maintain-vendor-collaboration.md).</span><span class="sxs-lookup"><span data-stu-id="520d0-108">For more information about setting up security for vendor collaboration, see [Set up and maintain vendor collaboration](set-up-maintain-vendor-collaboration.md).</span></span> <span data-ttu-id="520d0-109">Säljaren portal utsätter en begränsad uppsättning information om inköpsorder (POs) till externa leverantörer.</span><span class="sxs-lookup"><span data-stu-id="520d0-109">The Vendor portal exposes a limited set of information about purchase orders (POs) to external vendors.</span></span> <span data-ttu-id="520d0-110">Det är viktigt att du korrekt konfigurera användarbehörigheter för säljaren portal i Microsoft Dynamics AX, så att leverantörerna inte har oavsiktlig åtkomst till ytterligare information i din Dynamics AX-installation.</span><span class="sxs-lookup"><span data-stu-id="520d0-110">It's important that you correctly set up user permissions for the Vendor portal in Microsoft Dynamics AX, so that vendors don't have unintended access to additional information in your Dynamics AX installation.</span></span> <span data-ttu-id="520d0-111">**Viktigt!** Till skillnad från andra användare, externa leverantörer bör inte ha **SystemUser** roll.</span><span class="sxs-lookup"><span data-stu-id="520d0-111">**Important:** Unlike other users, external vendors should not have the **SystemUser** role.</span></span> <span data-ttu-id="520d0-112">Det **SystemUser** roll ger tillgång till en uppsättning rättigheter som inte är lämpliga för externa användare.</span><span class="sxs-lookup"><span data-stu-id="520d0-112">The **SystemUser** role grants access to a set of privileges that aren't suitable for external users.</span></span>

## <a name="setting-up-a-vendor-portal-user"></a><span data-ttu-id="520d0-113">Ställa in en leverantör portal-användare</span><span class="sxs-lookup"><span data-stu-id="520d0-113">Setting up a Vendor portal user</span></span>
<span data-ttu-id="520d0-114">Innan du skapar ett användarkonto för någon som använder säljaren portalen måste du ställa upp säljaren att säljaren portal samarbete.</span><span class="sxs-lookup"><span data-stu-id="520d0-114">Before you create a user account for someone who will use the Vendor portal, you must set up the vendor to allow for Vendor portal collaboration.</span></span> <span data-ttu-id="520d0-115">Använd **inköpsorder samarbete** på **fliken Allmänt** på **leverantörer** .</span><span class="sxs-lookup"><span data-stu-id="520d0-115">Use the **Purchase order collaboration** field on the **General** tab on the **Vendors** page.</span></span> <span data-ttu-id="520d0-116">Externa leverantörer som använder säljaren portal måste ha följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="520d0-116">External vendors that use the Vendor portal must have the following setup:</span></span>

-   <span data-ttu-id="520d0-117">Ett Microsoft Azure Active Directory (AAD) användarkonto måste registreras för säljaren på sidan **användare** i Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="520d0-117">A Microsoft Azure Active Directory (AAD) user account must be registered for the vendor on the **Users** page in Dynamics AX.</span></span>
-   <span data-ttu-id="520d0-118">Säljaren måste **säljaren (extern)** säkerhet roll, inte **SystemUser** roll.</span><span class="sxs-lookup"><span data-stu-id="520d0-118">The vendor must have the **Vendor (external)** security role, not the **SystemUser** role.</span></span> <span data-ttu-id="520d0-119">**Obs!** Rollen **SystemUser** beviljas automatiskt när du skapar ett nytt användarkonto i Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="520d0-119">**Note:** The **SystemUser** role is automatically granted when you create a new user account in Dynamics AX.</span></span> <span data-ttu-id="520d0-120">Därför måste du ta den rollen och bekräfta varningsmeddelandet som du tar emot.</span><span class="sxs-lookup"><span data-stu-id="520d0-120">Therefore, you must remove that role and acknowledge the warning message that you receive.</span></span>
-   <span data-ttu-id="520d0-121">Säljaren bör inte beviljas tillstånd för att lägga till ytterligare fält från PO bord till deras uppfattning av PO.</span><span class="sxs-lookup"><span data-stu-id="520d0-121">The vendor user should not be granted permission to add additional fields from the PO tables to their view of the PO.</span></span> <span data-ttu-id="520d0-122">På **fliken anpassning** , på **fliken Användare** , ange **uttryckliga anpassningen tillåtet** alternativ för användaren till **någon**.</span><span class="sxs-lookup"><span data-stu-id="520d0-122">On the **Personalization** tab, on the **Users** tab, set the **Explicit personalization allowed** option for the user to **No**.</span></span>
-   <span data-ttu-id="520d0-123">Användaren måste vara kopplad till en registrerad kontaktperson.</span><span class="sxs-lookup"><span data-stu-id="520d0-123">The user account must be associated with a registered contact person.</span></span> <span data-ttu-id="520d0-124">Om **användarna** väljer du en kontaktperson i **fältet Namn** .</span><span class="sxs-lookup"><span data-stu-id="520d0-124">On the **Users** page, select a contact person in the **Name** field.</span></span> <span data-ttu-id="520d0-125">Den person som du väljer bör ha **kontakt** roll för respektive leverantör.</span><span class="sxs-lookup"><span data-stu-id="520d0-125">The person that you select should have the **Contact** role for the relevant vendor.</span></span>

<span data-ttu-id="520d0-126">Om samma person kräver tillgång till säljaren portal för flera leverantörer konton (för olika juridiska enheter, kanske), varje personens användarkontona måste vara associerade med samma registrerade kontaktperson.</span><span class="sxs-lookup"><span data-stu-id="520d0-126">If the same person requires access to the Vendor portal for multiple vendor accounts (for different legal entities, perhaps), each of that person's user accounts must be associated with the same registered contact person.</span></span> <span data-ttu-id="520d0-127">**Säljaren (extern)** roll innefattar alla de grundläggande funktioner som krävs för att använda funktionerna som är tillgängliga i säljaren portal.</span><span class="sxs-lookup"><span data-stu-id="520d0-127">The **Vendor (external)** role includes all the basic capabilities that are required in order to use the functionality that is available in the Vendor portal.</span></span> <span data-ttu-id="520d0-128">Den här installationen hjälper till att säkra att användargränssnittet att externa användare ser är fokuserade på den avsedda scenario.</span><span class="sxs-lookup"><span data-stu-id="520d0-128">This setup helps guarantee that the user interface that the external user sees is focused on the intended scenario only.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="520d0-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="520d0-129">Additional resources</span></span>

[<span data-ttu-id="520d0-130">Samarbeta med leverantörer med hjälp av leverantörsportalen</span><span class="sxs-lookup"><span data-stu-id="520d0-130">Collaborate with vendors by using the Vendor portal</span></span>](collaborate-vendors-vendor-portal.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]