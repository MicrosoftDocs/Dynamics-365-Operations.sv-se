---
title: Konfigurera Azure Active Directory-autentisering för kassainloggning
description: I det här ämnet beskrivs hur du konfigurerar Azure Active Directory som autentiseringsmetod i Microsoft Dynamics 365 Commerce-kassan.
author: boycezhu
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: e271bbae84605b4adace1809b53b7cbdb6932da0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020021"
---
# <a name="configure-azure-active-directory-authentication-for-pos-sign-in"></a><span data-ttu-id="fbc05-103">Konfigurera Azure Active Directory-autentisering för kassainloggning</span><span class="sxs-lookup"><span data-stu-id="fbc05-103">Configure Azure Active Directory authentication for POS sign-in</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="fbc05-104">I detta ämne förklaras hur du konfigurerar Azure Active Directory (Azure AD) som autentiseringsmetod i Microsoft Dynamics 365 Commerce-kassan (POS).</span><span class="sxs-lookup"><span data-stu-id="fbc05-104">This topic explains how to configure Azure Active Directory (Azure AD) as the authentication method in Microsoft Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="fbc05-105">Återförsäljare som använder Dynamics 365 Commerce tillsammans med andra Microsoft-molnbaserade tjänster som exempelvis Microsoft Azure, Microsoft 365 och Microsoft Teams vill vanligtvis använda Azure AD för central hantering av användarreferenser för en säker och sömlös inloggningsupplevelse för alla program.</span><span class="sxs-lookup"><span data-stu-id="fbc05-105">Retailers who use Dynamics 365 Commerce along with other Microsoft cloud services such as Microsoft Azure, Microsoft 365, and Microsoft Teams typically want to use Azure AD for centralized management of user credentials for a secure and seamless sign-in experience across applications.</span></span> <span data-ttu-id="fbc05-106">Om du vill använda Azure AD-autentisering för Commerce POS måste du först konfigurera Azure AD som autentiseringsmetod i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="fbc05-106">To use Azure AD authentication for Commerce POS, you must first configure Azure AD as the authentication method in Commerce headquarters.</span></span>

## <a name="configure-pos-authentication-method"></a><span data-ttu-id="fbc05-107">Konfigurera metod för kassaautentisering</span><span class="sxs-lookup"><span data-stu-id="fbc05-107">Configure POS authentication method</span></span>

<span data-ttu-id="fbc05-108">Följ dessa steg för att konfigurera metoden för kassaautentisering i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="fbc05-108">To configure the POS authentication method in Commerce headquarters, follow these steps.</span></span>
    
1. <span data-ttu-id="fbc05-109">Öppna **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler** och välj en funktionsprofil som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="fbc05-109">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS profiles \> Functionality profiles**, and select a functionality profile to change.</span></span>
1. <span data-ttu-id="fbc05-110">I avsnittet **Inloggning för butikspersonal** i snabbfliken **Funktioner** väljer du ett alternativ för autentiseringsmetod i listrutan **Metod för inloggningsmetod**.</span><span class="sxs-lookup"><span data-stu-id="fbc05-110">In the **POS staff logon** section of the **Functions** FastTab, select a desired authentication method option from the **Logon authentication method** drop-down list.</span></span>

    <span data-ttu-id="fbc05-111">**Metoden för inloggningsautentisering** har tre alternativ:</span><span class="sxs-lookup"><span data-stu-id="fbc05-111">The **Logon authentication method** has three options:</span></span>
    
    - <span data-ttu-id="fbc05-112">**Personal-ID och lösenord** – För det här standardalternativet måste kassaanvändarna ange ett personal-ID och ett lösenord för att logga in i kassan och för att få åtkomst till åsidosättningsfunktionen för hanterare.</span><span class="sxs-lookup"><span data-stu-id="fbc05-112">**Personnel ID and Password** - This default option requires POS users to enter a personnel ID and password to sign in to the POS and to access manager override functionality.</span></span>
    - <span data-ttu-id="fbc05-113">**Azure AD utan enkel inloggning** – Det här alternativet kräver att kassaanvändarna använder Azure AD-autentiseringsuppgifter för att logga in i kassan och få åtkomst till åsidosättningsfunktionen för hanterare.</span><span class="sxs-lookup"><span data-stu-id="fbc05-113">**Azure AD without single sign-on** - This option requires POS users to use Azure AD credentials to sign in to the POS and access manager override functionality.</span></span> <span data-ttu-id="fbc05-114">När kassaklienten uppdateras eller öppnas igen måste kassaanvändaren ange autentiseringsuppgifter för Azure AD för att kunna logga in igen.</span><span class="sxs-lookup"><span data-stu-id="fbc05-114">When the POS client is refreshed or reopened, the POS user must provide Azure AD credentials to sign in again.</span></span>
    - <span data-ttu-id="fbc05-115">**Azure AD med enkel inloggning** – När det här alternativet har valts kan POS-användare logga in i Molnbaserad pos (CPOS) med aktiva Azure AD-autentiseringsuppgifter som används av andra webbprogram i samma webbläsare, eller logga in på Modern POS (MPOS) med hjälp av Azure AD-autentiseringsuppgifter registrerade i Windows.</span><span class="sxs-lookup"><span data-stu-id="fbc05-115">**Azure AD with single sign-on** - When this option is selected, POS users are able to sign in to Cloud POS (CPOS) using active Azure AD credentials that are being used by other web applications in the same web browser, or sign in to Modern POS (MPOS) using Azure AD credentials signed in to Windows.</span></span> <span data-ttu-id="fbc05-116">Båda metoder gör att du kan logga in utan att ange Azure AD-autentiseringsuppgifter på inloggningsskärmen för kassa.</span><span class="sxs-lookup"><span data-stu-id="fbc05-116">Both methods allow sign-in without needing to enter Azure AD credentials on the POS sign-in screen.</span></span> <span data-ttu-id="fbc05-117">Åtkomst till funktionen för åsidosättning för kassahanterare kräver dock fortfarande inloggning med Azure AD-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fbc05-117">However, accessing the POS manager override functionality will still require sign-in using Azure AD credentials.</span></span>

1. <span data-ttu-id="fbc05-118">Gå till **Retail och Commerce > Retail och Commerce IT > Distributionsschema** och kör jobbet **1070 (kanalkonfiguration)** för att synkronisera de senaste funktionsprofilinställningarna med kassaklienter.</span><span class="sxs-lookup"><span data-stu-id="fbc05-118">Go to **Retail and Commerce > Retail and Commerce IT > Distribution schedule** and run the **1070 (Channel configuration)** job to synchronize the latest functionality profile settings to POS clients.</span></span>

> [!NOTE]
> - <span data-ttu-id="fbc05-119">Autentiseringen **Azure AD utan enkel inloggning** ersätter alternativet **Azure Active Directory** i Commerce version 10.0.18 och tidigare.</span><span class="sxs-lookup"><span data-stu-id="fbc05-119">The **Azure AD without single sign-on** authentication method option replaces the **Azure Active Directory** option in Commerce version 10.0.18 and earlier.</span></span>
> - <span data-ttu-id="fbc05-120">Azure AD-autentisering kräver en aktiv Internetanslutning och fungerar inte när kassan är offline.</span><span class="sxs-lookup"><span data-stu-id="fbc05-120">Azure AD authentication requires an active internet connection, and won't function when the POS is offline.</span></span>

## <a name="associate-azure-ad-accounts-with-pos-users"></a><span data-ttu-id="fbc05-121">Associera Azure AD-konton med kassaanvändare</span><span class="sxs-lookup"><span data-stu-id="fbc05-121">Associate Azure AD accounts with POS users</span></span>

<span data-ttu-id="fbc05-122">Om du vill använda Azure AD som autentiseringsmetod för kassa måste du koppla Azure AD-konton med kassaanvändare i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="fbc05-122">To use Azure AD as the POS authentication method, you must associate Azure AD accounts with POS users in Commerce headquarters.</span></span> 

<span data-ttu-id="fbc05-123">Om du vill koppla Azure AD-konton till kassaanvändare i Commerce-administrationen följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="fbc05-123">To associate Azure AD accounts with POS users in Commerce headquarters, follow these steps.</span></span>
    
1. <span data-ttu-id="fbc05-124">Gå till **Retail och Commerce > Medarbetare > Arbetare** och öppna en medarbetarpost.</span><span class="sxs-lookup"><span data-stu-id="fbc05-124">Go to **Retail and Commerce > Employees > Workers** and open a worker record.</span></span>
1. <span data-ttu-id="fbc05-125">I åtgärdsfönstret väljer du fliken **Commerce** och sedan, under **Extern identitet**, markerar du **Associera befintlig identitet**.</span><span class="sxs-lookup"><span data-stu-id="fbc05-125">On the Action Pane, select the **Commerce** tab, then under **External identity** select **Associate existing identity**.</span></span> 
1. <span data-ttu-id="fbc05-126">I dialogrutan **Använd befintlig extern identitet**, välj **Sök med e-post**, ange en Azure AD e-postadress och välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="fbc05-126">In the **Use existing external identity** dialog box, select **Search using email**, enter an Azure AD email address, and then select **Search**.</span></span>
1. <span data-ttu-id="fbc05-127">Markera Azure AD-kontot som returneras och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbc05-127">Select the Azure AD account that is returned, then select **OK**.</span></span>

<span data-ttu-id="fbc05-128">Efter konfigureringsstegen ovan kommer fälten **Alias**, **UPN** och **Extern underidentifierare** på fliken **Commerce** på medarbetarens informationssida att fyllas i.</span><span class="sxs-lookup"><span data-stu-id="fbc05-128">After the configuration steps above, the **Alias**, **UPN**, and **External sub identifier** fields on the **Commerce** tab of the worker's details page will be filled in.</span></span>

<span data-ttu-id="fbc05-129">Du måste köra **1060-jobbet (Personal)** i **Retail och Commerce > Retail och Commerce IT > Distributionsschema** för att synkronisera den senaste kassaanvändaren och Azure AD-kontodata till kanalen.</span><span class="sxs-lookup"><span data-stu-id="fbc05-129">You must run the **1060 (Staff)** job in **Retail and Commerce > Retail and Commerce IT > Distribution schedule** to synchronize the latest POS user and Azure AD account data to the channel.</span></span>

> [!NOTE]
> <span data-ttu-id="fbc05-130">När medarbetarinformation som exempelvis lösenord, kassabehörighet, associerat Azure AD-konto eller medarbetarens adressbok har uppdaterats i Commerce-administrationen rekommenderas det starkt att köra jobbet **1060 (personal)** för att synkronisera den senaste medarbetarinformationen med kanalen.</span><span class="sxs-lookup"><span data-stu-id="fbc05-130">As a best practice, after worker information such as password, POS permission, associated Azure AD account, or employee address book is updated in Commerce headquarters, it is highly recommended to run the **1060 (Staff)** job to synchronize the latest worker information to the channel.</span></span> <span data-ttu-id="fbc05-131">Kassaklienten kan sedan hämta korrekta data för kontroll av användarautentisering och behörighet.</span><span class="sxs-lookup"><span data-stu-id="fbc05-131">The POS client can then fetch the correct data for user authentication and authorization checks.</span></span>

## <a name="pos-lock-register-and-sign-out-with-azure-ad-authentication"></a><span data-ttu-id="fbc05-132">Kassalåsregister och utloggning med Azure AD-autentisering</span><span class="sxs-lookup"><span data-stu-id="fbc05-132">POS lock register and sign-out with Azure AD authentication</span></span>

<span data-ttu-id="fbc05-133">Följande inträffar när kassan (POS) konfigureras till att använda autentiseringsmetoden för Azure AD:</span><span class="sxs-lookup"><span data-stu-id="fbc05-133">The following occurs when POS is configured to use the Azure AD authentication method:</span></span>

- <span data-ttu-id="fbc05-134">Funktionen **Lås register** finns inte i kassaprogrammet (POS).</span><span class="sxs-lookup"><span data-stu-id="fbc05-134">The **Lock register** function will not be available in the POS application.</span></span> 
- <span data-ttu-id="fbc05-135">Den **automatiska låsfunktionen** fungerar på samma sätt som den **automatiska utloggningsfunktionen**.</span><span class="sxs-lookup"><span data-stu-id="fbc05-135">The **Automatically lock** function will behave the same as the **Automatically logoff** function.</span></span>
- <span data-ttu-id="fbc05-136">Om kassaanvändaren väljer **Logga ut** kommer användaren att ombedjas logga in med Azure AD-autentiseringsuppgifter nästa gång kassan (POS) körs, oavsett om enkel inloggning har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="fbc05-136">If the POS user selects **Log off**, the user will be asked to sign in with Azure AD credentials the next time the POS launches, regardless of whether single sign-in is enabled.</span></span>

## <a name="manager-override-functionality-with-azure-ad-authentication"></a><span data-ttu-id="fbc05-137">Åsidosättningsfunktioner för chef med Azure AD-autentisering</span><span class="sxs-lookup"><span data-stu-id="fbc05-137">Manager override functionality with Azure AD authentication</span></span>

<span data-ttu-id="fbc05-138">När kassan (POS) har konfigurerats för Azure AD-autentisering öppnar chefsfunktionen för åsidosättning en dialogruta som efterfrågar chefsanvändarens Azure AD-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fbc05-138">When the POS is configured to use Azure AD authentication, the manager override functionality will open a dialog box that prompts for the manager user's Azure AD credentials.</span></span> <span data-ttu-id="fbc05-139">När chefsinloggningen har godkänts tas chefens Azure AD-autentiseringsuppgifter bort och den tidigare användarens Azure AD-autentiseringsuppgifter används för efterföljande kassafunktioner.</span><span class="sxs-lookup"><span data-stu-id="fbc05-139">After manager sign-in is approved, the manager's Azure AD credentials will be dropped and the previous user's Azure AD credentials will be used for subsequent POS operations.</span></span>

> [!NOTE]
> - <span data-ttu-id="fbc05-140">I Commerce-versionerna 10.0.18 och tidigare har åsidosättningsfunktionen för chefer inte stöd för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fbc05-140">In Commerce versions 10.0.18 and earlier, the manager override function does not support Azure AD.</span></span> <span data-ttu-id="fbc05-141">Ett personals-ID och ett lösenord måste anges även om kassan (POS) har konfigurerats att använda Azure AD-autentiseringsmetoden.</span><span class="sxs-lookup"><span data-stu-id="fbc05-141">A personnel ID and password are required even if the POS is configured to use the Azure AD authentication method.</span></span>
> - <span data-ttu-id="fbc05-142">När du använder CPOS med webbläsaren Safari på en Apple iOS-enhet måste du först stänga av **Blockera popup-fönster** i Safari-inställningarna för att åsidosättningsfunktionen för chefer ska kunna fungera tillsammans med Azure AD-autentisering.</span><span class="sxs-lookup"><span data-stu-id="fbc05-142">When using CPOS with the Safari web browser on an Apple iOS device, you must first turn off **Block Pop-ups** in Safari settings for the manager override functionality to work with Azure AD authentication.</span></span> 

## <a name="security-best-practices-for-azure-ad-based-pos-authentication-on-shared-devices"></a><span data-ttu-id="fbc05-143">Metodtips för säkerhet för Azure AD-baserad kassaautentisering på delade enheter</span><span class="sxs-lookup"><span data-stu-id="fbc05-143">Security best practices for Azure AD-based POS authentication on shared devices</span></span>

<span data-ttu-id="fbc05-144">Många återförsäljare ställer in sin butiksmiljö på ett sätt som gör att flera användare behöver få åtkomst till kassaprogrammet från en delad fysisk enhet.</span><span class="sxs-lookup"><span data-stu-id="fbc05-144">Many retailers set up their retail store environment in a way that multiple users need to access the POS application from a shared physical device.</span></span> <span data-ttu-id="fbc05-145">Även om en enskild inloggning ger en praktisk och sömlös autentiseringsupplevelse kan den här även skapa ett säkerhetskryphål där den aktuella kassaanvändaren kanske inte inser att en annan användares autentiseringsuppgifter används för att utföra transaktioner eller funktioner i kassan (POS).</span><span class="sxs-lookup"><span data-stu-id="fbc05-145">In that context, while single sign-in provides a convenient and seamless authentication experience, it may also create a security loophole where the current POS user may not realize that another user's credentials are being used to perform transactions or operations in the POS.</span></span> <span data-ttu-id="fbc05-146">Innan du konfigurerar POS för att använda autentiseringsmetoden för Azure AD bör du granska din säkerhetspolicy och den delade enhetens inloggningsinställningar för att avgöra vilket alternativ som passar bäst.</span><span class="sxs-lookup"><span data-stu-id="fbc05-146">Before you configure the POS to use the Azure AD authentication method, it is highly recommended to review your security policy and the shared device's sign-in settings to decide which option is the best fit.</span></span>

- <span data-ttu-id="fbc05-147">Om din butiksmiljö använder ett delat konto (till exempel ett lokalt konto) för inloggning på den fysiska enheten rekommenderas att använda **Azure AD utan alternativet för enkel inloggning**.</span><span class="sxs-lookup"><span data-stu-id="fbc05-147">If your retail environment uses a shared account (for example, a local account) for physical device sign-in, it's recommended to use the **Azure AD without single sign-on** option.</span></span> <span data-ttu-id="fbc05-148">På så sätt ser du till att varje kassaanvändare explicit anger Azure AD-autentiseringsuppgifter för att logga in i kassan (POS).</span><span class="sxs-lookup"><span data-stu-id="fbc05-148">This ensures that each POS user explicitly provides Azure AD credentials to sign in to the POS.</span></span>
- <span data-ttu-id="fbc05-149">Om din butiksmiljö kräver att medarbetarna använder sina egna Azure AD-konton för att logga in i kassan (POS) och på den fysiska enhet som är kassans värd, rekommenderas du att använda alternativet **Azure AD med enkel inloggning**.</span><span class="sxs-lookup"><span data-stu-id="fbc05-149">If your retail environment requires employees to use their own Azure AD accounts to sign in to the POS and its hosting physical device, it's recommended to use the **Azure AD with single sign-on** option.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fbc05-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fbc05-150">Additional resources</span></span>

[<span data-ttu-id="fbc05-151"> Konfigurera en arbetare</span><span class="sxs-lookup"><span data-stu-id="fbc05-151">Configure a worker</span></span>](tasks/worker.md)

[<span data-ttu-id="fbc05-152">Skapa en Retail-funktionsprofil</span><span class="sxs-lookup"><span data-stu-id="fbc05-152">Create a retail functionality profile</span></span>](retail-functionality-profile.md)


[<span data-ttu-id="fbc05-153">Ställa in utökad inloggningsfunktion för MPOS och Cloud POS</span><span class="sxs-lookup"><span data-stu-id="fbc05-153">Set up extended logon functionality for MPOS and Cloud POS</span></span>](extended-logon.md)

[<span data-ttu-id="fbc05-154">Metodtips för säkerhet för molnbaserad kassa i delade miljöer</span><span class="sxs-lookup"><span data-stu-id="fbc05-154">Security best practices for Cloud POS in shared environments</span></span>](dev-itpro/secure-retail-cloud-pos.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
