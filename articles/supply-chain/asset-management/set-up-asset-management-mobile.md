---
title: Ställ in mobil arbetsyta för tillgångshantering
description: I det här avsnittet beskrivs hur du ställer in Microsoft Dynamics 365 Supply Chain Management och Finance and Operations (Dynamics 365) mobilappen för att köra en tillgångshantering mobil arbetsyta som arbetstagare kan använda för att utföra uppgifter för hantering av tillgångar.
author: johanhoffmann
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9c2410c50b5d289792e2cc364674e1e093653590
ms.sourcegitcommit: 995c678b4715be267f1f97148902a6b3dde3bcab
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/20/2021
ms.locfileid: "5033231"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a><span data-ttu-id="4c913-103">Ställ in mobil arbetsyta för tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="4c913-103">Set up the Asset management mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c913-104">I det här avsnittet beskrivs hur du ställer in Microsoft Dynamics 365 Supply Chain Management och Finance and Operations (Dynamics 365) mobilapp för att köra en **Tillgångshantering** mobil arbetsyta som arbetstagare kan använda för att utföra uppgifter för hantering av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="4c913-104">This topic describes how to set up Microsoft Dynamics 365 Supply Chain Management and the Finance and Operations (Dynamics 365) mobile app to run an **Asset management** mobile workspace that workers can use to perform asset management tasks.</span></span>

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a><span data-ttu-id="4c913-105">Ställ in användare av underhållsarbetare i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="4c913-105">Set up maintenance worker users in Supply Chain Management</span></span>

<span data-ttu-id="4c913-106">För varje användare som kräver åtkomst till den mobila arbetsytan för **Hantering av tillgångar** följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="4c913-106">For each user that requires access to the **Asset management** mobile workspace, follow these steps.</span></span>

1. <span data-ttu-id="4c913-107">I Supply Chain Management, gå till **Personal \> Arbetare** och se till att det finns en arbetarpost för den användare som du vill ställa in.</span><span class="sxs-lookup"><span data-stu-id="4c913-107">In Supply Chain Management, go to **Human resources \> Workers**, and make sure that a worker record exists for the user that you want to set up.</span></span> <span data-ttu-id="4c913-108">Skapa en ny arbetarpost som krävs.</span><span class="sxs-lookup"><span data-stu-id="4c913-108">Create a new worker record as required.</span></span>
1. <span data-ttu-id="4c913-109">Gå till **Tillgångshantering \> Inställningar \> Arbetare \> Arbetare**, och se till att den arbetarpost som du identifierade (eller skapade) i föregående steg är mappad till en underhållspost.</span><span class="sxs-lookup"><span data-stu-id="4c913-109">Go to **Asset management \> Setup \> Workers \> Workers**, and make sure that the worker record that you identified (or created) in the previous step is mapped to a maintenance worker record.</span></span> <span data-ttu-id="4c913-110">Skapa en ny underhållsarbetarepost som obligatorisk, och ange fältet **Arbetare** till arbetarposten från föregående steg.</span><span class="sxs-lookup"><span data-stu-id="4c913-110">Create a new maintenance worker record as required, and set the **Worker** field to the worker record from the previous step.</span></span>
1. <span data-ttu-id="4c913-111">Gå till **Tillgångshantering \> Inställningar \> Arbetare \> underhållsarbetargrupper**, och se till att den underhållsarbetargrupper som du identifierade (eller skapade) i föregående steg är mappad till en underhållspost.</span><span class="sxs-lookup"><span data-stu-id="4c913-111">Go to **Asset management \> Setup \> Workers \> Maintenance worker groups**, and make sure that the maintenance worker record that you identified (or created) in the previous step belongs to a maintenance worker group.</span></span>
1. <span data-ttu-id="4c913-112">Gå till **Systemadministration \> Användare**.</span><span class="sxs-lookup"><span data-stu-id="4c913-112">Go to **System administration \> Users**.</span></span>
1. <span data-ttu-id="4c913-113">Välj relevant användare i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="4c913-113">Select the relevant user in the grid.</span></span>
1. <span data-ttu-id="4c913-114">På snabbfliken **Användardetaljer** anger du fältet **Person** till arbetarkontot som du vill associera med det aktuella användarkontot.</span><span class="sxs-lookup"><span data-stu-id="4c913-114">On the **User Details** FastTab, set the **Person** field to the worker account that you want to associate with the current user account.</span></span> <span data-ttu-id="4c913-115">Det här arbetarkontot ska vara arbetarposten som du identifierade (eller skapade) i steg 1 och mappas till en underhållsarbetarepost i steg 2.</span><span class="sxs-lookup"><span data-stu-id="4c913-115">This worker account should be the worker record that you identified (or created) in step 1 and mapped to a maintenance worker record in step 2.</span></span>

> [!NOTE]
> <span data-ttu-id="4c913-116">Användarbehörigheter och säkerhetsroller gäller funktionerna i den mobila arbetsytan för **hantering av tillgångar** på samma sätt som de gäller funktionerna i användargränssnittet för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4c913-116">User permissions and security roles apply to the features of the **Asset management** mobile workspace just as they apply to the features of the Supply Chain Management user interface.</span></span> <span data-ttu-id="4c913-117">Därför måste varje användare som du ställer in för att få åtkomst till den mobila arbetsytan för **hantering av tillgångar** ha de säkerhetsroller som krävs för att utföra liknande åtgärder direkt i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4c913-117">Therefore, every user that you set up to access the **Asset management** mobile workspace must have the security roles that are required to perform similar operations directly in Supply Chain Management.</span></span>

## <a name="publish-the-asset-management-mobile-workspace"></a><span data-ttu-id="4c913-118">Publicera mobil arbetsyta för tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="4c913-118">Publish the Asset management mobile workspace</span></span>

<span data-ttu-id="4c913-119">Om du vill göra tillgångshanteringsfunktioner tillgängliga i Finance and Operations (Dynamics 365) mobilapp, måste du publicera mobila arbetsytan **tillgångshantering**.</span><span class="sxs-lookup"><span data-stu-id="4c913-119">To make asset management features available in the Finance and Operations (Dynamics 365) mobile app, you must publish the **Asset management** mobile workspace.</span></span>

1. <span data-ttu-id="4c913-120">I Supply Chain Management väljer du knappen **Inställningar** (kugghjulssymbolen i det övre högra hörnet) och väljer sedan **Mobilapp** på menyn.</span><span class="sxs-lookup"><span data-stu-id="4c913-120">In Supply Chain Management, select the **Settings** button (the gear symbol in upper-right corner), and then select **Mobile app** on the menu.</span></span>
1. <span data-ttu-id="4c913-121">I dialogrutan **hantera mobilapp** hitta panelen **Hantera tillgång**.</span><span class="sxs-lookup"><span data-stu-id="4c913-121">In the **Manage mobile app** dialog box, find the **Asset Management** tile.</span></span> <span data-ttu-id="4c913-122">Om den innehåller texten "I metadata - inte publicerats" har arbetsytan ännu inte publicerats.</span><span class="sxs-lookup"><span data-stu-id="4c913-122">If it contains the text "In metadata - not published," the workspace hasn't yet been published.</span></span> <span data-ttu-id="4c913-123">Om den innehåller texten "I metadata - publicerat" har arbetsytan redan publicerats och du kan hoppa över resten av den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="4c913-123">If it contains the text "In metadata - published," the workspace has already been published, and you can skip the rest of this procedure.</span></span>

    <span data-ttu-id="4c913-124">![Dialogrutan Hantera mobilapp](media/mobile-workspaces.png "Dialogrutan Hantera mobilapp")</span><span class="sxs-lookup"><span data-stu-id="4c913-124">![Manage mobile app dialog box](media/mobile-workspaces.png "Manage mobile app dialog box")</span></span>

1. <span data-ttu-id="4c913-125">Välj panelen för **tillgångshantering** och välj sedan **Publicera** i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="4c913-125">Select the **Asset Management** tile, and then select **Publish** on the toolbar.</span></span> <span data-ttu-id="4c913-126">Efter några sekunder bör du få ett meddelande som anger att arbetsytan har publicerats utan resultat.</span><span class="sxs-lookup"><span data-stu-id="4c913-126">After a few seconds, you should receive a notification that states that the workspace has been successfully published.</span></span> <span data-ttu-id="4c913-127">Dessutom ska texten på panelen ändras till "I metadata - publicerat".</span><span class="sxs-lookup"><span data-stu-id="4c913-127">Additionally, the text on the tile should change to "In metadata - published."</span></span>

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a><span data-ttu-id="4c913-128">Installera och konfigurera Finance and Operations (Dynamics 365) mobilappen</span><span class="sxs-lookup"><span data-stu-id="4c913-128">Install and set up the Finance and Operations (Dynamics 365) mobile app</span></span>

1. <span data-ttu-id="4c913-129">Gå till någon av följande appbutiker för att installera **Microsoft Finance and Operations (Dynamics 365)**-appen på din mobila enhet:</span><span class="sxs-lookup"><span data-stu-id="4c913-129">Go to one of the following app stores to install the **Microsoft Finance and Operations (Dynamics 365)** app on your mobile device:</span></span>

    - [<span data-ttu-id="4c913-130">För Google Android enheter</span><span class="sxs-lookup"><span data-stu-id="4c913-130">For Google Android devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
    - [<span data-ttu-id="4c913-131">För Apple iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="4c913-131">For Apple iOS devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

1. <span data-ttu-id="4c913-132">Öppna Finance and Operations (Dynamics 365) appen.</span><span class="sxs-lookup"><span data-stu-id="4c913-132">Open the Finance and Operations (Dynamics 365) app.</span></span> <span data-ttu-id="4c913-133">Inloggningssidan ska visas.</span><span class="sxs-lookup"><span data-stu-id="4c913-133">The sign-in page should appear.</span></span> <span data-ttu-id="4c913-134">I fältet **Logga in** ange Supply Chain Management URL, eller välj senaste URL i listan **senaste miljöer** och tryck **anslut**.</span><span class="sxs-lookup"><span data-stu-id="4c913-134">In the **Sign in** field, enter your Supply Chain Management URL, or select a recent URL in the **Recent environments** list, and then tap **Connect**.</span></span>

    <span data-ttu-id="4c913-135">![Inloggningssida](media/mobile-app-sign-in.png "Inloggningssida")</span><span class="sxs-lookup"><span data-stu-id="4c913-135">![Sign-in page](media/mobile-app-sign-in.png "Sign-in page")</span></span>

1. <span data-ttu-id="4c913-136">Om du uppmanas att bekräfta anslutningen markerar du kryssrutan **Jag förstår** och trycker sedan på **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="4c913-136">If you're prompted to confirm the connection, select the **I understand** check box, and then tap **Connect**.</span></span>
1. <span data-ttu-id="4c913-137">På sidan **Välj ett konto** använder du ditt Microsoft-konto för att logga in på mobilprogrammet.</span><span class="sxs-lookup"><span data-stu-id="4c913-137">On the **Pick an account** page, use your Microsoft account to sign in to the mobile application.</span></span>

    <span data-ttu-id="4c913-138">Sidan **arbetsytor** visas.</span><span class="sxs-lookup"><span data-stu-id="4c913-138">The **Workspaces** page appears.</span></span> <span data-ttu-id="4c913-139">Den listar varje mobil arbetsyta som har publicerats av din Supply Chain Management-instans.</span><span class="sxs-lookup"><span data-stu-id="4c913-139">It lists every mobile workspace that has been published by your Supply Chain Management instance.</span></span>

    <span data-ttu-id="4c913-140">![Lista över arbetsytor](media/mobile-app-workspaces.png "Lista över arbetsytor")</span><span class="sxs-lookup"><span data-stu-id="4c913-140">![List of workspaces](media/mobile-app-workspaces.png "List of workspaces")</span></span>

1. <span data-ttu-id="4c913-141">Om du måste ändra den juridiska personen (företaget) trycker du på menyknappen (kallas ibland hamburgaren eller hamburgerknappen) i det övre vänstra hörnet och sedan på **Ändra företag**.</span><span class="sxs-lookup"><span data-stu-id="4c913-141">If you must change the legal entity (company), tap the Menu button (sometimes referred to as the hamburger or the hamburger button) in the upper-left corner, and then tap **Change company**.</span></span>

    <span data-ttu-id="4c913-142">![Ändra den juridiska personen.](media/mobile-app-change-comp.png "Ändra den juridiska personen.")</span><span class="sxs-lookup"><span data-stu-id="4c913-142">![Changing the legal entity](media/mobile-app-change-comp.png "Changing the legal entity")</span></span>

1. <span data-ttu-id="4c913-143">På sidan **Arbetsytor** väljer du den arbetsyta som du vill arbeta med för att öppna den.</span><span class="sxs-lookup"><span data-stu-id="4c913-143">On the **Workspaces** page, select the workspace that you want to work with to open it.</span></span>

    <span data-ttu-id="4c913-144">![Mobil arbetsyta för tillgångshantering](media/mobile-app-asset-workspace.png "Mobil arbetsyta för tillgångshantering")</span><span class="sxs-lookup"><span data-stu-id="4c913-144">![Asset management mobile workspace](media/mobile-app-asset-workspace.png "Asset management mobile workspace")</span></span>

## <a name="work-with-the-asset-management-mobile-workspace"></a><span data-ttu-id="4c913-145">Arbeta med mobil arbetsyta för tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="4c913-145">Work with the Asset management mobile workspace</span></span>

<span data-ttu-id="4c913-146">Mer information om hur du arbetar med den mobila arbetsytan **tillgångshantering** finns i [Använda den mobila arbetsytan för tillgångshantering](asset-management-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="4c913-146">For more information about how to work with the **Asset management** mobile workspace, see [Use the Asset management mobile workspace](asset-management-mobile-workspace.md).</span></span>

<span data-ttu-id="4c913-147">Mer information om Finance and Operations (Dynamics 365) mobilappen finns på [startsidan för Mobilappen](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="4c913-147">For more information about the Finance and Operations (Dynamics 365) mobile app, see the [Mobile app home page](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span></span>
