---
title: Kom i gång med Global lagerredovisning
description: I det här avsnittet beskrivs hur du kommer igång med global lagerredovisningen.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 59f9db309312bbbc88b4fa47c12c4c02f09e7c6d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301708"
---
# <a name="get-started-with-global-inventory-accounting"></a><span data-ttu-id="40493-103">Kom i gång med Global lagerredovisning</span><span class="sxs-lookup"><span data-stu-id="40493-103">Get started with Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="40493-104">Global lagerredovisning låter dig utföra flera lagerredovisningar i de globala lagerredovisningar som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="40493-104">Global Inventory Accounting lets you do multiple inventory accountings in the Global Inventory Accounting ledgers that you've set up.</span></span> <span data-ttu-id="40493-105">Du kopplar varje redovisning med en Global lagerredovisning till en *konvention*.</span><span class="sxs-lookup"><span data-stu-id="40493-105">You must associate each Global Inventory Accounting ledger with a *convention*.</span></span> <span data-ttu-id="40493-106">En konvention är en samling av följande typer av redovisningsprinciper:</span><span class="sxs-lookup"><span data-stu-id="40493-106">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="40493-107">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="40493-107">Cost object</span></span>
- <span data-ttu-id="40493-108">Inmatningsmåttbas</span><span class="sxs-lookup"><span data-stu-id="40493-108">Input measurement basis</span></span>
- <span data-ttu-id="40493-109">Antagande för kostnadsflöde</span><span class="sxs-lookup"><span data-stu-id="40493-109">Cost flow assumption</span></span>
- <span data-ttu-id="40493-110">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="40493-110">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="40493-111">Även när du har aktiverat Global lagerredovisning kan du fortfarande göra lagerredovisningen i Microsoft Dynamics 365 Supply Chain Management som vanligt.</span><span class="sxs-lookup"><span data-stu-id="40493-111">Even after you turn on Global Inventory Accounting, you can still do inventory accounting in Microsoft Dynamics 365 Supply Chain Management in the usual way.</span></span>

<span data-ttu-id="40493-112">Global lagerredovisning är ett tillägg.</span><span class="sxs-lookup"><span data-stu-id="40493-112">Global Inventory Accounting is an add-in.</span></span> <span data-ttu-id="40493-113">För att göra funktionerna tillgängliga måste du installera det från Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="40493-113">To make its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="40493-114">Därför kan du välja att utvärdera den i en testmiljö innan du aktiverar den för produktionsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="40493-114">You can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="40493-115">Global lagerredovisning har för närvarande inte stöd för alla kostnadshanteringsfunktioner som är inbyggda i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="40493-115">Global Inventory Accounting doesn't currently support all the cost management features that are built into Supply Chain Management.</span></span> <span data-ttu-id="40493-116">Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen ska uppfylla dina krav.</span><span class="sxs-lookup"><span data-stu-id="40493-116">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a><span data-ttu-id="40493-117">Så här hämtar du offentlig förhandsgranskning av global lagerredovisning</span><span class="sxs-lookup"><span data-stu-id="40493-117">How to get the Global Inventory Accounting public preview</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40493-118">Om du vill använda global lagerredovisning måste du ha en LCS-aktiverad miljö med hög tillgänglighet (inte en OneBox-miljö).</span><span class="sxs-lookup"><span data-stu-id="40493-118">To use Global Inventory Accounting, you must have an LCS-enabled high-availability environment (not a OneBox environment).</span></span> <span data-ttu-id="40493-119">Du måste dessutom köra Supply Chain Management version 10.0.19 eller senare.</span><span class="sxs-lookup"><span data-stu-id="40493-119">Additionally, you must be running Supply Chain Management version 10.0.19 or later.</span></span>

<span data-ttu-id="40493-120">Om du vill registrera dig för offentlig förhandsgranskning av global lagerredovisning skickar du ditt LCS-miljö-ID med e-post till [Global lagerredovisning teamet](mailto:GlobalInventoryAccounting@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="40493-120">To sign up for the Global Inventory Accounting public preview, send your LCS environment ID by email to the [Global Inventory Accounting team](mailto:GlobalInventoryAccounting@service.microsoft.com).</span></span> <span data-ttu-id="40493-121">När du har godkänts för programmet skickar teamet ett uppföljningsmeddelande med en nyckel för Global lagerredovisning och dina tjänsteslutpunkter.</span><span class="sxs-lookup"><span data-stu-id="40493-121">After you're approved for the program, the team will send you a follow-up email that contains a Global Inventory Accounting beta key and your service endpoints.</span></span> <span data-ttu-id="40493-122">När du har fått nyckeln kan du [installera tillägget](#install).</span><span class="sxs-lookup"><span data-stu-id="40493-122">After you receive the beta key, you can [install the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="40493-123">Licensiering</span><span class="sxs-lookup"><span data-stu-id="40493-123">Licensing</span></span>

<span data-ttu-id="40493-124">Global lagerredovisning licensieras tillsammans med de standardfunktioner i lagerredovisningen som är tillgängliga för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="40493-124">Global Inventory Accounting is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="40493-125">Du behöver inte köpa ytterligare en licens för att kunna använda Global lagerredovisning.</span><span class="sxs-lookup"><span data-stu-id="40493-125">You don't have to purchase an additional license to use Global Inventory Accounting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="40493-126">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="40493-126">Prerequisites</span></span>

### <a name="set-up-microsoft-power-platform-integration"></a><span data-ttu-id="40493-127">Ställ in Microsoft Power Platform-integrering</span><span class="sxs-lookup"><span data-stu-id="40493-127">Set up Microsoft Power Platform integration</span></span>

<span data-ttu-id="40493-128">Innan du kan aktivera tilläggsfunktionen måste du integrera Microsoft Power Platform med följande steg.</span><span class="sxs-lookup"><span data-stu-id="40493-128">Before you can enable add-in functionality, you must integrate with Microsoft Power Platform by following these steps.</span></span>

1. <span data-ttu-id="40493-129">Öppna LCS-miljön där du vill lägga till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="40493-129">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="40493-130">Gå till **Fullständiga detaljer**.</span><span class="sxs-lookup"><span data-stu-id="40493-130">Go to **Full details**.</span></span>
1. <span data-ttu-id="40493-131">I avsnittet **Power Platform-integrering** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="40493-131">In the **Power Platform Integration** section, select **Setup**.</span></span>
1. <span data-ttu-id="40493-132">Markera kryssrutan i dialogrutan **Inställning av Power platform miljö** och välj sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="40493-132">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="40493-133">Normalt tar inställningen mellan 60 och 90 minuter.</span><span class="sxs-lookup"><span data-stu-id="40493-133">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="40493-134">När inställningen av Microsoft Power Platform miljön är klar, visar sidan namnet på din miljö.</span><span class="sxs-lookup"><span data-stu-id="40493-134">After setup of the Microsoft Power Platform environment is completed, the page shows the name of your environment.</span></span> <span data-ttu-id="40493-135">Dessutom visar avsnittet **Power Platform-integration** visar instruktionen, "Power Platform miljöinställningen är klar."</span><span class="sxs-lookup"><span data-stu-id="40493-135">Additionally, the **Power Platform Integration** section shows the statement, "Power Platform environment setup is complete."</span></span> <span data-ttu-id="40493-136">Global lagerredovisning behöver inte ha något program för global lagerredovisning.</span><span class="sxs-lookup"><span data-stu-id="40493-136">Global Inventory Accounting doesn't require a dual-write application.</span></span>

<span data-ttu-id="40493-137">Mer information finns i [Ställ in efter utveckling av miljön](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span><span class="sxs-lookup"><span data-stu-id="40493-137">For more information, see [Set up after environment deployment](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span></span>

### <a name="set-up-dataverse"></a><span data-ttu-id="40493-138">Ställ in Dataverse</span><span class="sxs-lookup"><span data-stu-id="40493-138">Set up Dataverse</span></span>

<span data-ttu-id="40493-139">Innan du ställer in Dataverse lägger du till serviceprinciperna för global lagerredovisning till din innehavare genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="40493-139">Before you set up Dataverse, add the Global Inventory Accounting service principles to your tenant by following these steps.</span></span>

1. <span data-ttu-id="40493-140">Installera Azure AD-modul för Windows PowerShell v2 enligt beskrivningen i [Installera Azure Active Directory PowerShell för Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="40493-140">Install Azure AD Module for Windows PowerShell v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
1. <span data-ttu-id="40493-141">Kör följande PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="40493-141">Run the following PowerShell command.</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

<span data-ttu-id="40493-142">Skapa sedan programanvändare för Global lagerredovisning i Dataverse genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="40493-142">Next, create application users for Global Inventory Accounting in Dataverse by following these steps.</span></span>

1. <span data-ttu-id="40493-143">Öppna URL-adressen för din Dataverse miljö.</span><span class="sxs-lookup"><span data-stu-id="40493-143">Open the URL of your Dataverse environment.</span></span>
1. <span data-ttu-id="40493-144">Gå till **Avancerade inställningar \> System \> Säkerhet \> Användare** och skapa en programanvändare.</span><span class="sxs-lookup"><span data-stu-id="40493-144">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="40493-145">Använd fältet **Vy** för att ändra sidvisningen till *appanvändare*.</span><span class="sxs-lookup"><span data-stu-id="40493-145">Use the **View** field to change the page view to *Application users*.</span></span>
1. <span data-ttu-id="40493-146">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="40493-146">Select **New**.</span></span>
1. <span data-ttu-id="40493-147">Ange fältet **App-ID** till *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span><span class="sxs-lookup"><span data-stu-id="40493-147">Set the **Application ID** field to *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span></span>
1. <span data-ttu-id="40493-148">Välj **Tilldela roll** och välj sedan *Systemadministratör*.</span><span class="sxs-lookup"><span data-stu-id="40493-148">Select **Assign Role**, and then select *System Administrator*.</span></span> <span data-ttu-id="40493-149">Om det finns en roll med namnet *Common Data Service Användare* väljer du den också.</span><span class="sxs-lookup"><span data-stu-id="40493-149">If there is a role that is named *Common Data Service User*, select it too.</span></span>
1. <span data-ttu-id="40493-150">Upprepa föregående steg, men ställ in fältet **Program-ID** på *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span><span class="sxs-lookup"><span data-stu-id="40493-150">Repeat the preceding steps, but set the **Application ID** field to *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span></span>

<span data-ttu-id="40493-151">Mer information finns i [Skapa en appanvändare](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="40493-151">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

<span data-ttu-id="40493-152">Om standardspråket i installationen Dataverse inte är engelska följer du dessa anvisningar.</span><span class="sxs-lookup"><span data-stu-id="40493-152">If the default language of your Dataverse installation isn't English, follow these steps.</span></span>

1. <span data-ttu-id="40493-153">Gå till **Avancerad inställning \> Administration \> Språk**.</span><span class="sxs-lookup"><span data-stu-id="40493-153">Go to **Advanced Setting \> Administration \> Languages**.</span></span>
1. <span data-ttu-id="40493-154">Välj *Engelska* (*LanguageCode=1033*) och sedan **Verkställ**.</span><span class="sxs-lookup"><span data-stu-id="40493-154">Select *English* (*LanguageCode=1033*), and then select **Apply**.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="40493-155">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="40493-155">Install the add-in</span></span>

<span data-ttu-id="40493-156">Följ dessa steg för att installera tillägget så att du kan använda global lagerredovisning.</span><span class="sxs-lookup"><span data-stu-id="40493-156">Follow these steps to install the add-in so that you can use Global Inventory Accounting.</span></span>

1. <span data-ttu-id="40493-157">[Logga in](#sign-up) för offentlig förhandsgranskning av global lagerredovisning.</span><span class="sxs-lookup"><span data-stu-id="40493-157">[Sign up](#sign-up) for the Global Inventory Accounting public preview.</span></span>
1. <span data-ttu-id="40493-158">Logga in på [LCS](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="40493-158">Sign in to [LCS](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="40493-159">Gå till **Hantering av förhandsgranskningsfunktioner**.</span><span class="sxs-lookup"><span data-stu-id="40493-159">Go to **Preview feature management**.</span></span>
1. <span data-ttu-id="40493-160">Välj plustecknet (**+**).</span><span class="sxs-lookup"><span data-stu-id="40493-160">Select the plus sign (**+**).</span></span>
1. <span data-ttu-id="40493-161">I fältet **kod** anger du betanyckeln för tillägget för Global lagerredovisning.</span><span class="sxs-lookup"><span data-stu-id="40493-161">In the **Code** field, enter your add-in beta key for Global Inventory Accounting.</span></span> <span data-ttu-id="40493-162">(Du bör ha fått nyckeln via e-post när du har registrerat dig.)</span><span class="sxs-lookup"><span data-stu-id="40493-162">(You should have received your beta key by email when you signed up.)</span></span>
1. <span data-ttu-id="40493-163">Välj **Avblockera**.</span><span class="sxs-lookup"><span data-stu-id="40493-163">Select **Unblock**.</span></span>
1. <span data-ttu-id="40493-164">Öppna LCS-miljön där du vill lägga till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="40493-164">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="40493-165">Gå till **Fullständiga detaljer**.</span><span class="sxs-lookup"><span data-stu-id="40493-165">Go to **Full details**.</span></span>
1. <span data-ttu-id="40493-166">Gå till **Power Platform-integration** och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="40493-166">Go to **Power Platform Integration**, and select **Setup**.</span></span>
1. <span data-ttu-id="40493-167">Markera kryssrutan i dialogrutan **Inställning av Power platform miljö** och välj sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="40493-167">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="40493-168">Normalt tar inställningen mellan 60 och 90 minuter.</span><span class="sxs-lookup"><span data-stu-id="40493-168">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="40493-169">När inställningen av Microsoft Power Platform-miljön är klar väljer du på snabbfliken **Miljötillägg** välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="40493-169">After setup of the Microsoft Power Platform environment is completed, on the **Environment add-ins** FastTab, select **Install a new add-in**.</span></span>
1. <span data-ttu-id="40493-170">Välj **Global lagerredovisning**.</span><span class="sxs-lookup"><span data-stu-id="40493-170">Select **Global inventory accounting**.</span></span>
1. <span data-ttu-id="40493-171">Följ installationsguiden och godkänn villkoren.</span><span class="sxs-lookup"><span data-stu-id="40493-171">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="40493-172">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="40493-172">Select **Install**.</span></span>
1. <span data-ttu-id="40493-173">På snabbfliken **Miljötillägg** bör du se att Global lagerredovisning installeras.</span><span class="sxs-lookup"><span data-stu-id="40493-173">On the **Environment add-ins** FastTab, you should see that Global Inventory Accounting is being installed.</span></span> <span data-ttu-id="40493-174">Efter några minuter bör statusen ändras från *installera* till *installerad*.</span><span class="sxs-lookup"><span data-stu-id="40493-174">After a few minutes, the status should change from *Installing* to *Installed*.</span></span> <span data-ttu-id="40493-175">(Du kan behöva uppdatera sidan för att se ändringen.) Vid den tidpunkten är Global lagerredovisning klar för användning.</span><span class="sxs-lookup"><span data-stu-id="40493-175">(You might have to refresh the page to see this change.) At that point, Global Inventory Accounting is ready to use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="40493-176">Inställning och integrering</span><span class="sxs-lookup"><span data-stu-id="40493-176">Set up the integration</span></span>

<span data-ttu-id="40493-177">Följ anvisningarna nedan och ställ in integreringen mellan Global Lagerredovisning och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="40493-177">Follow these steps to set up the integration between Global Inventory Accounting and Supply Chain Management.</span></span>

1. <span data-ttu-id="40493-178">Logga in på Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="40493-178">Sign in to Supply Chain Management.</span></span>
1. <span data-ttu-id="40493-179">Gå till **Systemadministration \> Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="40493-179">Go to **System administration \> Feature Management**.</span></span>
1. <span data-ttu-id="40493-180">Välj **Sök efter uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="40493-180">Select **Check for updates**.</span></span>
1. <span data-ttu-id="40493-181">Sök på fliken **Alla** efter den funktion som kallas *global lagerredovisning*.</span><span class="sxs-lookup"><span data-stu-id="40493-181">On the **All** tab, search for the feature that is named *Global inventory accounting*.</span></span>
1. <span data-ttu-id="40493-182">Välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="40493-182">Select **Enable now**.</span></span>
1. <span data-ttu-id="40493-183">Gå till **Global lagerredovisning \> Inställningar \> Parametrar för global lagerredovisning \> Integrationsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="40493-183">Go to **Global inventory accounting \> Setup \> Global inventory accounting parameters \> Integrations parameters**.</span></span>
1. <span data-ttu-id="40493-184">I fälten **Datatjänstslutpunkt** och **Slutpunkt för global lagerredovisning** ange webbadresserna från det e-postmeddelande som Global lagerredovisning-teamet skickade när du registrerade dig för förhandsgranskningen.</span><span class="sxs-lookup"><span data-stu-id="40493-184">In the **Data service endpoint** and **Global inventory accounting endpoint** fields, enter the URLs from the email that the Global Inventory Accounting team sent when you signed up for the preview.</span></span>

<span data-ttu-id="40493-185">Global lagerredovisning är nu klar att användas.</span><span class="sxs-lookup"><span data-stu-id="40493-185">Global Inventory Accounting is now ready to use.</span></span>
