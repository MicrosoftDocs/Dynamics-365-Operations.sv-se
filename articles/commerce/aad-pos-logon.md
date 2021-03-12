---
title: Aktivera Azure Active Directory-autentisering för kassainloggning
description: I det här avsnittet beskrivs hur du konfigurerar inloggnings upplevelsen för Microsoft Dynamics 365 Commerce kassa (POS) så att den använder Azure Active Directory-autentisering.
author: boycezhu
manager: annbe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: d6073a04814adf8237b4caa952b31b011f4b34bf
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982750"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a><span data-ttu-id="c7448-103">Aktivera Azure Active Directory-autentisering för kassainloggning</span><span class="sxs-lookup"><span data-stu-id="c7448-103">Enable Azure Active Directory authentication for POS sign-in</span></span>
[!include [banner](includes/banner.md)]


<span data-ttu-id="c7448-104">Många kunder som använder Microsoft Dynamics 365 Commerce använder också andra Microsoft Cloud Service och de kan använda Azure Active Directory (Azure AD) för att hantera användarbehörigheter för dessa tjänster.</span><span class="sxs-lookup"><span data-stu-id="c7448-104">Many customers who use Microsoft Dynamics 365 Commerce also use other Microsoft cloud services, and they might use Azure Active Directory (Azure AD) to manage user credentials for those services.</span></span> <span data-ttu-id="c7448-105">I dessa fall kanske kunderna vill använda samma Azure AD-konto i olika program.</span><span class="sxs-lookup"><span data-stu-id="c7448-105">In those cases, the customers might want to use the same Azure AD account across applications.</span></span> <span data-ttu-id="c7448-106">I det här avsnittet beskrivs hur du konfigurerar inloggnings upplevelsen för Commerce-kassa (POS) så att den använder Azure AD-autentisering.</span><span class="sxs-lookup"><span data-stu-id="c7448-106">This topic explains how to configure the Commerce point of sale (POS) sign-in experience to use Azure AD authentication.</span></span>

## <a name="configure-azure-ad-authentication"></a><span data-ttu-id="c7448-107">Konfigurera Azure AD-autentisering</span><span class="sxs-lookup"><span data-stu-id="c7448-107">Configure Azure AD authentication</span></span>

<span data-ttu-id="c7448-108">Om du vill göra Azure AD tillgänglig som autentiseringsmetod för kassainloggning för en butik måste du konfigurera inställningarna för butikens funktionsprofil och sedan tillämpa dessa inställningar på kassaklienter.</span><span class="sxs-lookup"><span data-stu-id="c7448-108">To make Azure AD available as the authentication method for POS sign-in for a store, you must configure the settings of the store's functionality profile and then apply those setting to POS clients.</span></span>

<span data-ttu-id="c7448-109">Följ dessa steg för att konfigurera en ny funktionsprofil.</span><span class="sxs-lookup"><span data-stu-id="c7448-109">To configure a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="c7448-110">Gå till **Butik och handel** \> **Kanalinställningar** \> **Kassainställningar** \> **Kassaprofiler** \> **Funktionsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="c7448-110">Go to **Retail and Commerce** \> **Channel setup** \> **POS setup** \> **POS profiles** \> **Functionality profiles**.</span></span>
1. <span data-ttu-id="c7448-111">Välj den funktionsprofil som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="c7448-111">Select the functionality profile to change.</span></span>
1. <span data-ttu-id="c7448-112">På snabbfliken **funktioner** i avsnittet **kassapersonalinloggning**, ändra värdet i fältet **Autentiseringsmetod för inloggning** från **Personal-ID och lösenord** till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c7448-112">On the **Functions** FastTab, in the **POS staff logon** section, change the value of the **Logon Authentication Method** field from **Personnel ID and Password** to **Azure Active Directory**.</span></span>

<span data-ttu-id="c7448-113">Som standard använder alla funktionsprofiler **Personal-ID och lösenord** som autentiseringsmetod för POS.</span><span class="sxs-lookup"><span data-stu-id="c7448-113">By default, all functionality profiles use **Personnel ID and Password** as the POS authentication method.</span></span> <span data-ttu-id="c7448-114">Därför måste du ändra värdet för **Autentiseringsmetod för inloggning** om du vill använda Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c7448-114">Therefore, you must change the value of the **Logon Authentication Method** field if you want to use Azure AD.</span></span> <span data-ttu-id="c7448-115">Alla butiker som är kopplade till den valda funktionsprofilen påverkas av den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="c7448-115">Every retail store that is linked to the selected functionality profile will be affected by this change.</span></span>

<span data-ttu-id="c7448-116">För att tillämpa inställningarna till kassaklienter, följ dessa steg instruktioner.</span><span class="sxs-lookup"><span data-stu-id="c7448-116">To apply the settings to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="c7448-117">Gå till **Butik och handel** \> **Butik och handel-IT** \> **Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="c7448-117">Go to **Retail and Commerce** \> **Retail and Commerce IT** \> **Distribution schedule**.</span></span>
1. <span data-ttu-id="c7448-118">Kör distributionsschemat **1070** (**Kanalkonfiguration**).</span><span class="sxs-lookup"><span data-stu-id="c7448-118">Run the **1070** (**Channel configuration**) distribution schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="c7448-119">Azure AD autentisering kräver en Internetanslutning.</span><span class="sxs-lookup"><span data-stu-id="c7448-119">Azure AD authentication requires an internet connection.</span></span> <span data-ttu-id="c7448-120">Det fungerar inte när POS är i offline-läge.</span><span class="sxs-lookup"><span data-stu-id="c7448-120">It won't work when POS is in offline mode.</span></span>
> 
> <span data-ttu-id="c7448-121">För närvarande stöder inte funktionen **Hantera åsidosättning** Azure AD som autentiseringsmetod.</span><span class="sxs-lookup"><span data-stu-id="c7448-121">Currently, the **Manager override** function doesn't support Azure AD as an authentication method.</span></span> <span data-ttu-id="c7448-122">Ett operatörs-ID och ett lösenord måste anges även om Azure AD har konfigurerats som autentiseringsmetod för kassainloggning.</span><span class="sxs-lookup"><span data-stu-id="c7448-122">An operator ID and password are required even if Azure AD is configured as the authentication method for POS sign-in.</span></span>

## <a name="associate-an-azure-ad-account-with-a-worker"></a><span data-ttu-id="c7448-123">Associera ett Azure AD-konto med en arbetare</span><span class="sxs-lookup"><span data-stu-id="c7448-123">Associate an Azure AD account with a worker</span></span>

<span data-ttu-id="c7448-124">Innan en butiksarbetare kan använda ett Azure AD-konto för att logga in på kassaprogrammet måste Azure AD-kontot vara kopplat till den personen.</span><span class="sxs-lookup"><span data-stu-id="c7448-124">Before a store worker can use an Azure AD account to sign in to the POS application, the Azure AD account must be associated with that worker.</span></span>

<span data-ttu-id="c7448-125">Om du vill associera ett Azure AD-konto med en arbetare följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="c7448-125">To associate an Azure AD account with a worker, follow these steps.</span></span>

1. <span data-ttu-id="c7448-126">Gå till **Retail och Commerce** \> **Anställda** \> **Arbetare**.</span><span class="sxs-lookup"><span data-stu-id="c7448-126">Go to **Retail and Commerce** \> **Employees** \> **Workers**.</span></span>
1. <span data-ttu-id="c7448-127">Öppna informationssidan för en arbetare.</span><span class="sxs-lookup"><span data-stu-id="c7448-127">Open the details page for a worker.</span></span>
1. <span data-ttu-id="c7448-128">I åtgärdsfönstret, på fliken **Commerce** i gruppen **Extern identitet** markerar du **Associera befintlig identitet**.</span><span class="sxs-lookup"><span data-stu-id="c7448-128">On the Action Pane, on the **Commerce** tab, in the **External identity** group, select **Associate existing identity**.</span></span>
1. <span data-ttu-id="c7448-129">I dialogrutan **Använd befintlig extern identitet**, välj **Sök med e-post**, ange en Azure AD e-postadress och välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="c7448-129">In the **Use existing external identity** dialog box, select **Search using email**, enter an Azure AD email address, and then select **Search**.</span></span>
1. <span data-ttu-id="c7448-130">Markera Azure AD-kontot som returneras och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7448-130">Select the Azure AD account that is returned, and then select **OK**.</span></span>

<span data-ttu-id="c7448-131">Fälten **Alias**, **UPN** och **Extern underidentifierare** på fliken **Commerce** på arbetarens detaljsida fylls i.</span><span class="sxs-lookup"><span data-stu-id="c7448-131">The **Alias**, **UPN**, and **External sub identifier** fields on the **Commerce** tab of the worker's details page will be filled in.</span></span>

> [!NOTE]
> <span data-ttu-id="c7448-132">När en arbetarpost har uppdaterats, till exempel om ett nytt Azure AD-konto är associerat, ett lösenord ändras eller en adressbok för medarbetare uppdateras bör du köra distributionsschema **1060** (**personal**) för att synkronisera den senaste informationen om personalen till kanalen.</span><span class="sxs-lookup"><span data-stu-id="c7448-132">After a worker record is updated, for example if a new Azure AD account is associated, a password is changed, or an employee address book is updated, it’s recommended that you run **1060** (**Staff**) distribution schedule to synchronize the latest staff information to the channel.</span></span> <span data-ttu-id="c7448-133">På så sätt kan kassaprogrammet hämta korrekta data för kontroll av användarautentisering och behörighet.</span><span class="sxs-lookup"><span data-stu-id="c7448-133">That way, the POS application can fetch the correct data for user authentication and authorization check.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c7448-134">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c7448-134">Additional resources</span></span>

[<span data-ttu-id="c7448-135">Ställa in utökad inloggningsfunktion för MPOS och Cloud POS</span><span class="sxs-lookup"><span data-stu-id="c7448-135">Set up extended logon functionality for MPOS and Cloud POS</span></span>](extended-logon.md)

[<span data-ttu-id="c7448-136">Skapa en Retail-funktionsprofil</span><span class="sxs-lookup"><span data-stu-id="c7448-136">Create a retail functionality profile</span></span>](retail-functionality-profile.md)

[<span data-ttu-id="c7448-137"> Konfigurera en arbetare</span><span class="sxs-lookup"><span data-stu-id="c7448-137">Configure a worker</span></span>](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)
