---
title: Skapa nya användare
description: Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.
author: peakerbl
ms.date: 01/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 88d3f1fba05d944e78e4595018d190c3dc41e076
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907921"
---
# <a name="create-new-users"></a><span data-ttu-id="e955c-103">Skapa nya användare</span><span class="sxs-lookup"><span data-stu-id="e955c-103">Create new users</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e955c-104">Innan du får åtkomst till Finance and Operations-appar måste du först lägga till på sidan **Användare** (**Systemadministration \> Användare \> Användare**).</span><span class="sxs-lookup"><span data-stu-id="e955c-104">Before you can access Finance and Operations apps, you must first be added to the **Users** page (**System administration \> Users \> Users**).</span></span> <span data-ttu-id="e955c-105">Användare inkluderar interna medarbetare inom organisationen eller externa kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="e955c-105">Users include internal employees of your organization, or external customers and vendors.</span></span> <span data-ttu-id="e955c-106">Användare kan importeras eller läggas till manuellt.</span><span class="sxs-lookup"><span data-stu-id="e955c-106">Users can be imported or added manually.</span></span> <span data-ttu-id="e955c-107">Alla användare måste ha rätt licens för kompatibel användning.</span><span class="sxs-lookup"><span data-stu-id="e955c-107">All users must be correctly licensed for compliant use.</span></span>

<span data-ttu-id="e955c-108">Mer information om hur du köper och licens för Finance and Operations-appar, se [Microsoft Dynamics 365 licenshandboken](https://go.microsoft.com/fwlink/?LinkId=866544&amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="e955c-108">For information about how to buy and license for Finance and Operations apps, see [Microsoft Dynamics 365 Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=866544&amp;clcid=0x409).</span></span>

## <a name="assign-a-license-to-a-user"></a><span data-ttu-id="e955c-109">Tilldela en licens till en användare.</span><span class="sxs-lookup"><span data-stu-id="e955c-109">Assign a license to a user</span></span>
<span data-ttu-id="e955c-110">Systemadministratörer kan [tilldela licenser till användare](/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) i [Microsoft 365 administrationscenter](/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="e955c-110">System admins can [assign licenses to users](/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="add-an-external-user-in-azure-ad-and-assign-a-license"></a><span data-ttu-id="e955c-111">Lägg till en extern användare i Azure AD och tilldela en licens</span><span class="sxs-lookup"><span data-stu-id="e955c-111">Add an external user in Azure AD and assign a license</span></span> 
<span data-ttu-id="e955c-112">Externa användare måste finnas med i klientkatalogen (Azure Active Directory (Azure AD)) så att de kan tilldelas licenser.</span><span class="sxs-lookup"><span data-stu-id="e955c-112">External users must be represented in your tenant directory (Azure Active Directory (Azure AD)) so that they can be assigned licenses.</span></span> <span data-ttu-id="e955c-113">Dessa externa användare ska läggas till i innehavaren av Azure AD som gästanvändare och sedan tilldelas de lämpliga licenserna.</span><span class="sxs-lookup"><span data-stu-id="e955c-113">Those external users should be added to the tenant in Azure AD as guest users and then assigned the appropriate licenses.</span></span> <span data-ttu-id="e955c-114">Ett krav för Finance and Operations-appar är att gästanvändarens företag måste använda Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e955c-114">A requirement for Finance and Operations apps is that the guest user's company must use Azure AD.</span></span> <span data-ttu-id="e955c-115">Mer information finns i [lägga till Azure Active Directory B2B samarbetsanvändare i Azure-portalen](/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="e955c-115">For more information, see [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

## <a name="import-new-users-from-azure-ad"></a><span data-ttu-id="e955c-116">Importera ny användare från Azure AD</span><span class="sxs-lookup"><span data-stu-id="e955c-116">Import new users from Azure AD</span></span> 
1. <span data-ttu-id="e955c-117">Gå till **Systemadministration** \> **Användare** \> **Användare**.</span><span class="sxs-lookup"><span data-stu-id="e955c-117">Go to **System administration** \> **User** \> **Users**.</span></span>
2. <span data-ttu-id="e955c-118">Välj **Importera användare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e955c-118">On the Action Pane, select **Import users**.</span></span>
3. <span data-ttu-id="e955c-119">Välj den användare du vill importera.</span><span class="sxs-lookup"><span data-stu-id="e955c-119">Select the users to be imported.</span></span> <span data-ttu-id="e955c-120">Listan omfattar användare av Azure AD som för närvarande inte är användare i den här miljön.</span><span class="sxs-lookup"><span data-stu-id="e955c-120">The list includes Azure AD users that are currently not users in this environment.</span></span>
4. <span data-ttu-id="e955c-121">Välj **Importera användare**.</span><span class="sxs-lookup"><span data-stu-id="e955c-121">Select **Import users**.</span></span>
5. <span data-ttu-id="e955c-122">Välj **Nära**.</span><span class="sxs-lookup"><span data-stu-id="e955c-122">Select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="e955c-123">Värdet för fältet **Företag** ställs in baserat på det aktuella sessionsföretaget för administratören. Efter importen måste du tilldela roller och organisationer, enligt vad som är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="e955c-123">The value for the **Company** field will be set based on the current session company for the admin. After import, you must assign roles and organizations as applicable.</span></span> <span data-ttu-id="e955c-124">För mer information, se [Tilldela användare till säkerhetsroller](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e955c-124">For more information, see [Assign users to security roles](assign-users-security-roles.md).</span></span> <span data-ttu-id="e955c-125">Enligt vissa villkor kan det även vara obligatoriskt att koppla användaren till en **person** och uppdatera användaralternativ, till exempel språk.</span><span class="sxs-lookup"><span data-stu-id="e955c-125">Conditionally, it might also be required to associate the user with a **Person** and to update user options such as language.</span></span>

## <a name="manually-add-a-new-user"></a><span data-ttu-id="e955c-126">Lägg manuellt till ny användare</span><span class="sxs-lookup"><span data-stu-id="e955c-126">Manually add a new user</span></span>
1. <span data-ttu-id="e955c-127">Gå till **Systemadministration** \> **Användare** \> **Användare**.</span><span class="sxs-lookup"><span data-stu-id="e955c-127">Go to **System administration** \> **Users** \> **Users**.</span></span>
2. <span data-ttu-id="e955c-128">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e955c-128">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="e955c-129">I fältet **Användar-ID** anger du en unik identifierare för användaren.</span><span class="sxs-lookup"><span data-stu-id="e955c-129">In the **User ID** field, enter a unique identifier for the user.</span></span>   
4. <span data-ttu-id="e955c-130">Ange användarens namn fältet **Användarnamn**.</span><span class="sxs-lookup"><span data-stu-id="e955c-130">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="e955c-131">I fältet **Leverantör**:</span><span class="sxs-lookup"><span data-stu-id="e955c-131">In the **Provider** field:</span></span>
 - <span data-ttu-id="e955c-132">Använd standardvärdet för interna användare.</span><span class="sxs-lookup"><span data-stu-id="e955c-132">For internal users, use the defaulted value.</span></span> <span data-ttu-id="e955c-133">Till exempel får Azure AD innehavare prefix med https://sts.windows.net/.</span><span class="sxs-lookup"><span data-stu-id="e955c-133">For example, your Azure AD tenant prefixed with https://sts.windows.net/.</span></span>  
 - <span data-ttu-id="e955c-134">För icke-Azure AD-användare som tjänst-2-tjänst konton anger du ett grundläggande textvärde.</span><span class="sxs-lookup"><span data-stu-id="e955c-134">For non-Azure AD users, such as Service-2-Service accounts, enter a basic text value.</span></span> <span data-ttu-id="e955c-135">Till exempel NA.</span><span class="sxs-lookup"><span data-stu-id="e955c-135">For example, NA.</span></span> <span data-ttu-id="e955c-136">Det här värdet hjälper dig att undvika felaktiga autentiseringssamtal som kan leda till fel om ett giltigt ID-leverantörsvärde används.</span><span class="sxs-lookup"><span data-stu-id="e955c-136">This value will help avoid incorrect authentication calls that might result in errors if a valid identity provider value is used.</span></span>  
 - <span data-ttu-id="e955c-137">För externa eller gästanvändare, lägg till deras Azure AD innehavarnamn efter https://sts.windows.net/.</span><span class="sxs-lookup"><span data-stu-id="e955c-137">For external or guest users, add their Azure AD tenant name after https://sts.windows.net/.</span></span>
6. <span data-ttu-id="e955c-138">I fältet **E-post** ange användarens fullständiga e-post/användarens huvudnamn.</span><span class="sxs-lookup"><span data-stu-id="e955c-138">In the **Email** field, enter the user's full Email/User Principle Name.</span></span>  
7. <span data-ttu-id="e955c-139">I fältet **Företag** välj standardstartföretag för användaren.</span><span class="sxs-lookup"><span data-stu-id="e955c-139">In the **Company** field, select the default startup company for the user.</span></span> 
8. <span data-ttu-id="e955c-140">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e955c-140">Select **Save**.</span></span>

<span data-ttu-id="e955c-141">Värdena för identitetsleverantör och telemetri-ID kommer att uppdateras baserat på en [Microsoft Graph](/graph/overview)-samtal när användarposten sparas.</span><span class="sxs-lookup"><span data-stu-id="e955c-141">The values for Identity provider and Telemetry ID will be updated based on a [Microsoft graph](/graph/overview) call, when the user record is saved.</span></span> <span data-ttu-id="e955c-142">Telemetr-ID:t baseras på användarens objekt-ID/säkerhetsidentifierare (SID) i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e955c-142">The Telemetry ID is based on the user's Object ID/Security Identifier (SID) in Azure AD.</span></span>

> [!NOTE]
> <span data-ttu-id="e955c-143">När du har lagt till en användare måste du tilldela roller och organisationer, enligt vad som är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="e955c-143">After you add a user, you must assign roles and organizations as applicable.</span></span> <span data-ttu-id="e955c-144">För mer information, se [Tilldela användare till säkerhetsroller](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e955c-144">For more information, see [Assign users to security roles](assign-users-security-roles.md).</span></span> <span data-ttu-id="e955c-145">Enligt vissa villkor kan det även vara obligatoriskt att koppla användaren till en **person** och uppdatera **användaralternativ**, till exempel språk.</span><span class="sxs-lookup"><span data-stu-id="e955c-145">Conditionally, it might also be required to associate the user with a **Person** and to update **User options** such as language.</span></span>

## <a name="change-a-user-id"></a><span data-ttu-id="e955c-146">Ändra ett användar-ID</span><span class="sxs-lookup"><span data-stu-id="e955c-146">Change a user ID</span></span>
<span data-ttu-id="e955c-147">Om du vill ändra ett användar-ID måste du byta namn på nyckeln i databasen.</span><span class="sxs-lookup"><span data-stu-id="e955c-147">To change a user ID, you must rename the key in the database.</span></span> <span data-ttu-id="e955c-148">När du ändrar ett användar-ID genom att använda den här proceduren ändras alla relaterade användarinställningar så att de använder det nya användar-ID:t.</span><span class="sxs-lookup"><span data-stu-id="e955c-148">When you change a user ID by using this procedure, all related user settings are modified to use the new user ID.</span></span> <span data-ttu-id="e955c-149">Till exempel användarinformationen i tabellen **SysLastValue** uppdateras till att referera till det nya användar-ID:t.</span><span class="sxs-lookup"><span data-stu-id="e955c-149">For example, the usage information in the **SysLastValue** table is updated to reference the new user ID.</span></span>

> [!NOTE]
> <span data-ttu-id="e955c-150">Användar-ID är den primära nyckeln i tabellen för användarinformation.</span><span class="sxs-lookup"><span data-stu-id="e955c-150">The user ID is the primary key of the user information table.</span></span> <span data-ttu-id="e955c-151">Att byta namn på primärnyckeln kan ta lite tid för befintliga användare eftersom alla referenser till nyckeln också uppdateras i databasen.</span><span class="sxs-lookup"><span data-stu-id="e955c-151">Renaming the primary key can take some time for existing users because all references to the key are also updated in the database.</span></span> 

1. <span data-ttu-id="e955c-152">Gå till **Systemadministration \> Användare \> Användare**.</span><span class="sxs-lookup"><span data-stu-id="e955c-152">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="e955c-153">Markera en användare i listan och välj **Alternativ\> Postinformation**.</span><span class="sxs-lookup"><span data-stu-id="e955c-153">Select a user in the list and select **Options\> Record info**.</span></span>
3. <span data-ttu-id="e955c-154">Välj **Byt namn**.</span><span class="sxs-lookup"><span data-stu-id="e955c-154">Select **Rename**.</span></span>
4. <span data-ttu-id="e955c-155">Ange ett nytt och unikt värde för användar-ID och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="e955c-155">Enter a new and unique value for the User ID, and then select **OK**.</span></span> 
5. <span data-ttu-id="e955c-156">Klicka på **Ja** för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="e955c-156">Select **Yes** to confirm.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e955c-157">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e955c-157">Additional resources</span></span>

<span data-ttu-id="e955c-158">Fler alternativ för att implementera B2B-användare finns i [Exportera B2B-användare till Azure AD](../implement-b2b.md).</span><span class="sxs-lookup"><span data-stu-id="e955c-158">For more options to implement B2B users, see [Export B2B users to Azure AD](../implement-b2b.md).</span></span>

<span data-ttu-id="e955c-159">Mer information om förkonfigurerade systemkonton finns i [Förkonfigurerade systemkonton](../pre-configured-system-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="e955c-159">For information about preconfigured system accounts, see [Preconfigured system accounts](../pre-configured-system-accounts.md)</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]