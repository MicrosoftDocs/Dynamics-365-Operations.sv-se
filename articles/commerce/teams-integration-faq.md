---
title: Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integration
description: Det här avsnittet finns svar på vanliga frågeställningar som rör Microsoft Dynamics 365 Commerce och Microsoft Teams-integration.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3fc7cff0a3f8d0fbfb196ec5951b138088afece7
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019480"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a><span data-ttu-id="3b32b-103">Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="3b32b-103">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3b32b-104">Det här avsnittet finns svar på vanliga frågeställningar som rör Microsoft Dynamics 365 Commerce och Microsoft Teams-integration.</span><span class="sxs-lookup"><span data-stu-id="3b32b-104">This topic provides answers to frequently asked questions regarding Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a><span data-ttu-id="3b32b-105">Vem i butiken blir ägare till ett team när Teams etableras från Commerce?</span><span class="sxs-lookup"><span data-stu-id="3b32b-105">Who in the store becomes an owner of a team while provisioning Teams from Commerce?</span></span> 

<span data-ttu-id="3b32b-106">Alla butikschefer läggs automatiskt till som ägare till motsvarande grupp så att de kan utföra åtgärder som till exempel att lägga till en privat kanal och lägga till eller ta bort medlemmar.</span><span class="sxs-lookup"><span data-stu-id="3b32b-106">All store managers are automatically added as owners to the corresponding team group so that they can perform operations such as adding a private channel and adding or deleting members.</span></span> 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a><span data-ttu-id="3b32b-107">Hur tilldelar jag rollen "kommunikationsansvarig" till en medarbetare i Commerce-administration?</span><span class="sxs-lookup"><span data-stu-id="3b32b-107">How do I assign the "communications manager" role to an employee in Commerce headquarters?</span></span> 

<span data-ttu-id="3b32b-108">Kommunikationschefer i Microsoft Teams har förmågan att skapa och publicera uppgiftslistor.</span><span class="sxs-lookup"><span data-stu-id="3b32b-108">Communication managers in Microsoft Teams have the ability to create and publish task lists.</span></span> <span data-ttu-id="3b32b-109">Organisationsanställda som måste bli kommunikationsansvariga måste ha rollen "butiksuppgiftschef" tilldelad till sig i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="3b32b-109">Organization employees who need to become communication managers must have the "retail task manager" role assigned to them in Commerce headquarters.</span></span>

<span data-ttu-id="3b32b-110">Om du vill tilldela en medarbetare rollen som butiksuppgiftschef i Commerce-administration följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="3b32b-110">To assign the retail task manager role to an employee in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="3b32b-111">Gå till **Butik och handel \> Anställda \> Användare**.</span><span class="sxs-lookup"><span data-stu-id="3b32b-111">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="3b32b-112">Välj en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="3b32b-112">Select an employee.</span></span>
1. <span data-ttu-id="3b32b-113">På snabbfliken **Användarens roller** klicka på **Tilldela roller**.</span><span class="sxs-lookup"><span data-stu-id="3b32b-113">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="3b32b-114">I dialogrutan **Tilldela roller till användare**, välj rollen **butikshanterarens roll** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b32b-114">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a><span data-ttu-id="3b32b-115">Hur gör jag en specifik organisationshierarki tillgänglig för överföring till Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="3b32b-115">How do I make a specific organization hierarchy available to upload into Microsoft Teams?</span></span>

<span data-ttu-id="3b32b-116">I Commerce-administration är varje organisationshierarki kopplad till ett eller flera syften.</span><span class="sxs-lookup"><span data-stu-id="3b32b-116">In Commerce headquarters, every organization's hierarchy is associated with one or more purposes.</span></span> <span data-ttu-id="3b32b-117">Se till att den hierarki som du vill tillhandahålla Microsoft Teams har **Butiksrapportering** syfte associerat med det, som visas i följande exempelbild.</span><span class="sxs-lookup"><span data-stu-id="3b32b-117">Make sure the hierarchy that you want to provision into Microsoft Teams has the **Retail reporting** purpose associated with it, as shown in the following example image.</span></span> 

![Exempel på ett organisationshierarkisyfte i Commerce-administration](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a><span data-ttu-id="3b32b-119">Hur aktiverar jag att butiksarbetare ska logga in i Commerce kassa med hjälp av Azure Active Directory (Azure AD)?</span><span class="sxs-lookup"><span data-stu-id="3b32b-119">How do I enable retail store workers to sign in to Commerce point of sale (POS) using Azure Active Directory (Azure AD)?</span></span>

<span data-ttu-id="3b32b-120">För information om hur du konfigurerar Commerce POS inloggningsupplevelse för att använda Azure AD autentisering finns i [Aktivera Azure Active Directory autentisering för kassainloggning](aad-pos-logon.md).</span><span class="sxs-lookup"><span data-stu-id="3b32b-120">For information about how to configure the Commerce POS sign-in experience to use Azure AD authentication, see [Enable Azure Active Directory authentication for POS sign-in](aad-pos-logon.md).</span></span>

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a><span data-ttu-id="3b32b-121">Hur mappar jag butiker och motsvarande team i Commerce-administration om min organisation redan har skapat team i Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="3b32b-121">How do I map stores and corresponding teams in Commerce headquarters if my organization has already created teams in Microsoft Teams?</span></span>

<span data-ttu-id="3b32b-122">Information om hur du mappar butiker och team om det finns befintliga team finns i [Kartlägg butiker och motsvarande team om din organisation har befintliga team i Microsoft Teams](map-stores-existing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="3b32b-122">For information on how to map stores and teams if there are pre-existing teams, see [Map stores and corresponding teams if your organization has pre-existing teams in Microsoft Teams](map-stores-existing-teams.md).</span></span>

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a><span data-ttu-id="3b32b-123">Hur tar jag bort den Microsoft Graph API-token som lagrats i sessionslagringen?</span><span class="sxs-lookup"><span data-stu-id="3b32b-123">How do I clear the Microsoft Graph API token stored in the session storage?</span></span>

<span data-ttu-id="3b32b-124">En användare som har loggat in på kassan med ett Azure Active Directory (Azure AD) konto ska logga ut från kassan eller stänga appen för att rensa sessionslagring.</span><span class="sxs-lookup"><span data-stu-id="3b32b-124">A user who has signed in to the point of sale (POS) with an Azure Active Directory (Azure AD) account should sign out from the POS or close the application to clear the session storage.</span></span> 

> [!TIP]
> <span data-ttu-id="3b32b-125">Vi rekommenderar att butiksarbetare alltid låser kassaterminalen eller loggar ut från en session när de inte använder terminalen.</span><span class="sxs-lookup"><span data-stu-id="3b32b-125">A recommended best practice is to always have store workers lock the POS terminal or sign out from a session when not using the terminal.</span></span> 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a><span data-ttu-id="3b32b-126">Vad händer om en butik inte har butikschefer?</span><span class="sxs-lookup"><span data-stu-id="3b32b-126">What happens if a store doesn't have store managers?</span></span>

<span data-ttu-id="3b32b-127">Om en butik inte har några chefer skapas ingen teamgrupp för butiken eller i Teams.</span><span class="sxs-lookup"><span data-stu-id="3b32b-127">If a store doesn't have managers, a team group will not be created for the store or in Teams.</span></span> 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a><span data-ttu-id="3b32b-128">Vad händer om en butikschef lämnar företaget?</span><span class="sxs-lookup"><span data-stu-id="3b32b-128">What happens if a store manager leaves the company?</span></span>

<span data-ttu-id="3b32b-129">Alla med ägarrollen kan lägga till en ny butikschef i Commerce-administration och ometablera Teams så att den nya chefen får de behörigheter som den nya chefen behöver i Teams för gruppen.</span><span class="sxs-lookup"><span data-stu-id="3b32b-129">Anyone with the owner role can add a new store manager in Commerce headquarters and reprovision Teams so that the new manager will have the necessary privileges in Teams for the group.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="3b32b-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3b32b-130">Additional resources</span></span>

[<span data-ttu-id="3b32b-131">Dynamics 365 Commerce och Microsoft Teams-integrering, översikt</span><span class="sxs-lookup"><span data-stu-id="3b32b-131">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="3b32b-132">Aktivera Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="3b32b-132">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="3b32b-133">Provision Microsoft Teams från Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3b32b-133">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="3b32b-134">Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="3b32b-134">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="3b32b-135">Hantera användarroller i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b32b-135">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="3b32b-136">Mappa butiker och team om det finns befintliga team i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b32b-136">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)
