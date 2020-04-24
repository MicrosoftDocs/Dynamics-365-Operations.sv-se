---
title: Aktivera Azure Active Directory-autentisering för kassainloggning
description: I det här avsnittet beskrivs hur du konfigurerar inloggnings upplevelsen för Microsoft Dynamics 365 Commerce kassa (POS) så att den använder Azure Active Directory-autentisering.
author: boycezhu
manager: annbe
ms.date: 03/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: dfc49585434383385b6b993893d93b95ef888384
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "3248950"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a><span data-ttu-id="f6f6b-103">Aktivera Azure Active Directory-autentisering för kassainloggning</span><span class="sxs-lookup"><span data-stu-id="f6f6b-103">Enable Azure Active Directory authentication for POS sign-in</span></span>
[!include [banner](includes/banner.md)]


<span data-ttu-id="f6f6b-104">Många kunder som använder Microsoft Dynamics 365 Commerce använder också andra Microsoft Cloud Service och de kan använda Azure Active Directory (Azure AD) för att hantera användarbehörigheter för dessa tjänster.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-104">Many customers who use Microsoft Dynamics 365 Commerce also use other Microsoft cloud services, and they might use Azure Active Directory (Azure AD) to manage user credentials for those services.</span></span> <span data-ttu-id="f6f6b-105">I dessa fall kanske kunderna vill använda samma Azure AD-konto i olika program.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-105">In those cases, the customers might want to use the same Azure AD account across applications.</span></span> <span data-ttu-id="f6f6b-106">I det här avsnittet beskrivs hur du konfigurerar inloggnings upplevelsen för Commerce-kassa (POS) så att den använder Azure AD-autentisering.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-106">This topic explains how to configure the Commerce point of sale (POS) sign-in experience to use Azure AD authentication.</span></span>

## <a name="configure-azure-ad-authentication"></a><span data-ttu-id="f6f6b-107">Konfigurera Azure AD-autentisering</span><span class="sxs-lookup"><span data-stu-id="f6f6b-107">Configure Azure AD authentication</span></span>

<span data-ttu-id="f6f6b-108">Om du vill göra Azure AD tillgänglig som autentiseringsmetod för kassainloggning för en butik måste du konfigurera inställningarna för butikens funktionsprofil och sedan tillämpa dessa inställningar på kassaklienter.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-108">To make Azure AD available as the authentication method for POS sign-in for a store, you must configure the settings of the store's functionality profile and then apply those setting to POS clients.</span></span>

<span data-ttu-id="f6f6b-109">Följ dessa steg för att konfigurera en ny funktionsprofil.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-109">To configure a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="f6f6b-110">Gå till **Butik och handel** \> **Kanalinställningar** \> **Kassainställningar** \> **Kassaprofiler** \> **Funktionsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-110">Go to **Retail and Commerce** \> **Channel setup** \> **POS setup** \> **POS profiles** \> **Functionality profiles**.</span></span>
1. <span data-ttu-id="f6f6b-111">Välj den funktionsprofil som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-111">Select the functionality profile to change.</span></span>
1. <span data-ttu-id="f6f6b-112">På snabbfliken **funktioner** i avsnittet **kassapersonalinloggning**, ändra värdet i fältet **Autentiseringsmetod för inloggning** från **Personal-ID och lösenord** till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-112">On the **Functions** FastTab, in the **POS staff logon** section, change the value of the **Logon Authentication Method** field from **Personnel ID and Password** to **Azure Active Directory**.</span></span>

<span data-ttu-id="f6f6b-113">Som standard använder alla funktionsprofiler **Personal-ID och lösenord** som autentiseringsmetod för kassan.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-113">By default, all functionality profiles use **Personnel ID and Password** as the POS authentication method.</span></span> <span data-ttu-id="f6f6b-114">Därför måste du ändra värdet för **Autentiseringsmetod för inloggning** om du vill använda Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-114">Therefore, you must change the value of the **Logon Authentication Method** field if you want to use Azure AD.</span></span> <span data-ttu-id="f6f6b-115">Alla butiker som är kopplade till den valda funktionsprofilen påverkas av den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-115">Every retail store that is linked to the selected functionality profile will be affected by this change.</span></span>

<span data-ttu-id="f6f6b-116">För att tillämpa inställningarna till kassaklienter, följ dessa steg instruktioner.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-116">To apply the settings to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="f6f6b-117">Gå till **Butik och handel** \> **Butik och handel-IT** \> **Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-117">Go to **Retail and Commerce** \> **Retail and Commerce IT** \> **Distribution schedule**.</span></span>
1. <span data-ttu-id="f6f6b-118">Kör distributionsschemat **1070** (**Kanalkonfiguration**).</span><span class="sxs-lookup"><span data-stu-id="f6f6b-118">Run the **1070** (**Channel configuration**) distribution schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="f6f6b-119">Azure AD autentisering kräver en Internetanslutning.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-119">Azure AD authentication requires an internet connection.</span></span> <span data-ttu-id="f6f6b-120">Det fungerar inte när kassan är i offline-läge.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-120">It won't work when POS is in offline mode.</span></span>

## <a name="associate-an-azure-ad-account-with-a-worker"></a><span data-ttu-id="f6f6b-121">Associera ett Azure AD-konto med en arbetare</span><span class="sxs-lookup"><span data-stu-id="f6f6b-121">Associate an Azure AD account with a worker</span></span>

<span data-ttu-id="f6f6b-122">Innan en butiksarbetare kan använda ett Azure AD-konto för att logga in på kassaprogrammet måste Azure AD-kontot vara kopplat till den personen.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-122">Before a store worker can use an Azure AD account to sign in to the POS application, the Azure AD account must be associated with that worker.</span></span>

<span data-ttu-id="f6f6b-123">Om du vill associera ett Azure AD-konto med en arbetare följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-123">To associate an Azure AD account with a worker, follow these steps.</span></span>

1. <span data-ttu-id="f6f6b-124">Gå till **Retail och Commerce** \> **Anställda** \> **Arbetare**.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-124">Go to **Retail and Commerce** \> **Employees** \> **Workers**.</span></span>
1. <span data-ttu-id="f6f6b-125">Öppna informationssidan för en arbetare.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-125">Open the details page for a worker.</span></span>
1. <span data-ttu-id="f6f6b-126">I åtgärdsfönstret, på fliken **Commerce** i gruppen **Extern identitet** markerar du **Associera befintlig identitet**.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-126">On the Action Pane, on the **Commerce** tab, in the **External identity** group, select **Associate existing identity**.</span></span>
1. <span data-ttu-id="f6f6b-127">I dialogrutan **Använd befintlig extern identitet**, välj **Sök med e-post**, ange en Azure AD e-postadress och välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-127">In the **Use existing external identity** dialog box, select **Search using email**, enter an Azure AD email address, and then select **Search**.</span></span>
1. <span data-ttu-id="f6f6b-128">Markera Azure AD-kontot som returneras och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-128">Select the Azure AD account that is returned, and then select **OK**.</span></span>

<span data-ttu-id="f6f6b-129">Fälten **Alias**, **UPN** och **Extern underidentifierare** på fliken **Commerce** på arbetarens detaljsida fylls i.</span><span class="sxs-lookup"><span data-stu-id="f6f6b-129">The **Alias**, **UPN**, and **External sub identifier** fields on the **Commerce** tab of the worker's details page will be filled in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f6f6b-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f6f6b-130">Additional resources</span></span>

[<span data-ttu-id="f6f6b-131">Ställa in utökad inloggningsfunktion för MPOS och molnbaserad kassa</span><span class="sxs-lookup"><span data-stu-id="f6f6b-131">Set up extended logon functionality for MPOS and Cloud POS</span></span>](extended-logon.md)

[<span data-ttu-id="f6f6b-132">Skapa en Retail-funktionsprofil</span><span class="sxs-lookup"><span data-stu-id="f6f6b-132">Create a retail functionality profile</span></span>](retail-functionality-profile.md)

[<span data-ttu-id="f6f6b-133"> Konfigurera en arbetare</span><span class="sxs-lookup"><span data-stu-id="f6f6b-133">Configure a worker</span></span>](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)
