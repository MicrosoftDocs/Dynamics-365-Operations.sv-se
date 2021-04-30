---
title: Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integration
description: Det här avsnittet finns svar på vanliga frågeställningar som rör Microsoft Dynamics 365 Commerce och Microsoft Teams-integration.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bf9aebb1c8ba7cf4fee3f0471a10872de1e23ce6
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908866"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a><span data-ttu-id="6f7c2-103">Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="6f7c2-103">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6f7c2-104">Det här avsnittet finns svar på vanliga frågeställningar som rör Microsoft Dynamics 365 Commerce och Microsoft Teams-integration.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-104">This topic provides answers to frequently asked questions regarding Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a><span data-ttu-id="6f7c2-105">Vem i butiken blir ägare till ett team när Teams etableras från Commerce?</span><span class="sxs-lookup"><span data-stu-id="6f7c2-105">Who in the store becomes an owner of a team while provisioning Teams from Commerce?</span></span> 

<span data-ttu-id="6f7c2-106">Alla butikschefer läggs automatiskt till som ägare till motsvarande grupp så att de kan utföra åtgärder som till exempel att lägga till en privat kanal och lägga till eller ta bort medlemmar.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-106">All store managers are automatically added as owners to the corresponding team group so that they can perform operations such as adding a private channel and adding or deleting members.</span></span> 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a><span data-ttu-id="6f7c2-107">Hur tilldelar jag rollen "kommunikationsansvarig" till en medarbetare i Commerce-administration?</span><span class="sxs-lookup"><span data-stu-id="6f7c2-107">How do I assign the "communications manager" role to an employee in Commerce headquarters?</span></span> 

<span data-ttu-id="6f7c2-108">Kommunikationschefer i Microsoft Teams har förmågan att skapa och publicera uppgiftslistor.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-108">Communication managers in Microsoft Teams have the ability to create and publish task lists.</span></span> <span data-ttu-id="6f7c2-109">Organisationsanställda som måste bli kommunikationsansvariga måste ha rollen "butiksuppgiftschef" tilldelad till sig i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-109">Organization employees who need to become communication managers must have the "retail task manager" role assigned to them in Commerce headquarters.</span></span>

<span data-ttu-id="6f7c2-110">Om du vill tilldela en medarbetare rollen som butiksuppgiftschef i Commerce-administration följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-110">To assign the retail task manager role to an employee in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6f7c2-111">Gå till **Butik och handel \> Anställda \> Användare**.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-111">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="6f7c2-112">Välj en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-112">Select an employee.</span></span>
1. <span data-ttu-id="6f7c2-113">På snabbfliken **Användarens roller** klicka på **Tilldela roller**.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-113">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="6f7c2-114">I dialogrutan **Tilldela roller till användare**, välj rollen **butikshanterarens roll** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-114">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a><span data-ttu-id="6f7c2-115">Hur gör jag en specifik organisationshierarki tillgänglig för överföring till Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="6f7c2-115">How do I make a specific organization hierarchy available to upload into Microsoft Teams?</span></span>

<span data-ttu-id="6f7c2-116">I Commerce-administration är varje organisationshierarki kopplad till ett eller flera syften.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-116">In Commerce headquarters, every organization's hierarchy is associated with one or more purposes.</span></span> <span data-ttu-id="6f7c2-117">Se till att den hierarki som du vill tillhandahålla Microsoft Teams har **Butiksrapportering** syfte associerat med det, som visas i följande exempelbild.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-117">Make sure the hierarchy that you want to provision into Microsoft Teams has the **Retail reporting** purpose associated with it, as shown in the following example image.</span></span> 

![Exempel på ett organisationshierarkisyfte i Commerce-administration](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a><span data-ttu-id="6f7c2-119">Hur aktiverar jag att butiksarbetare ska logga in i Commerce kassa med hjälp av Azure Active Directory (Azure AD)?</span><span class="sxs-lookup"><span data-stu-id="6f7c2-119">How do I enable retail store workers to sign in to Commerce point of sale (POS) using Azure Active Directory (Azure AD)?</span></span>

<span data-ttu-id="6f7c2-120">För information om hur du konfigurerar Commerce POS inloggningsupplevelse för att använda Azure AD autentisering finns i [Aktivera Azure Active Directory autentisering för kassainloggning](aad-pos-logon.md).</span><span class="sxs-lookup"><span data-stu-id="6f7c2-120">For information about how to configure the Commerce POS sign-in experience to use Azure AD authentication, see [Enable Azure Active Directory authentication for POS sign-in](aad-pos-logon.md).</span></span>

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a><span data-ttu-id="6f7c2-121">Hur mappar jag butiker och motsvarande team i Commerce-administration om min organisation redan har skapat team i Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="6f7c2-121">How do I map stores and corresponding teams in Commerce headquarters if my organization has already created teams in Microsoft Teams?</span></span>

<span data-ttu-id="6f7c2-122">Information om hur du mappar butiker och team om det finns befintliga team finns i [Kartlägg butiker och motsvarande team om din organisation har befintliga team i Microsoft Teams](map-stores-existing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6f7c2-122">For information on how to map stores and teams if there are pre-existing teams, see [Map stores and corresponding teams if your organization has pre-existing teams in Microsoft Teams](map-stores-existing-teams.md).</span></span>

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a><span data-ttu-id="6f7c2-123">Hur tar jag bort den Microsoft Graph API-token som lagrats i sessionslagringen?</span><span class="sxs-lookup"><span data-stu-id="6f7c2-123">How do I clear the Microsoft Graph API token stored in the session storage?</span></span>

<span data-ttu-id="6f7c2-124">En användare som har loggat in på kassan med ett Azure Active Directory (Azure AD) konto ska logga ut från kassan eller stänga appen för att rensa sessionslagring.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-124">A user who has signed in to the point of sale (POS) with an Azure Active Directory (Azure AD) account should sign out from the POS or close the application to clear the session storage.</span></span> 

> [!TIP]
> <span data-ttu-id="6f7c2-125">Vi rekommenderar att butiksarbetare alltid låser kassaterminalen eller loggar ut från en session när de inte använder terminalen.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-125">A recommended best practice is to always have store workers lock the POS terminal or sign out from a session when not using the terminal.</span></span> 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a><span data-ttu-id="6f7c2-126">Vad händer om en butik inte har butikschefer?</span><span class="sxs-lookup"><span data-stu-id="6f7c2-126">What happens if a store doesn't have store managers?</span></span>

<span data-ttu-id="6f7c2-127">Om en butik inte har några chefer skapas ingen teamgrupp för butiken eller i Teams.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-127">If a store doesn't have managers, a team group will not be created for the store or in Teams.</span></span> 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a><span data-ttu-id="6f7c2-128">Vad händer om en butikschef lämnar företaget?</span><span class="sxs-lookup"><span data-stu-id="6f7c2-128">What happens if a store manager leaves the company?</span></span>

<span data-ttu-id="6f7c2-129">Alla med ägarrollen kan lägga till en ny butikschef i Commerce-administration och ometablera Teams så att den nya chefen får de behörigheter som den nya chefen behöver i Teams för gruppen.</span><span class="sxs-lookup"><span data-stu-id="6f7c2-129">Anyone with the owner role can add a new store manager in Commerce headquarters and reprovision Teams so that the new manager will have the necessary privileges in Teams for the group.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="6f7c2-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6f7c2-130">Additional resources</span></span>

[<span data-ttu-id="6f7c2-131">Dynamics 365 Commerce och Microsoft Teams-integrering, översikt</span><span class="sxs-lookup"><span data-stu-id="6f7c2-131">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="6f7c2-132">Aktivera Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="6f7c2-132">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="6f7c2-133">Provision Microsoft Teams från Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6f7c2-133">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="6f7c2-134">Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="6f7c2-134">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="6f7c2-135">Hantera användarroller i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f7c2-135">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="6f7c2-136">Mappa butiker och team om det finns befintliga team i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f7c2-136">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)
