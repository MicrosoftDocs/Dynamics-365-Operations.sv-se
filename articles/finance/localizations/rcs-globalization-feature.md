---
title: Regulatory Configuration Services (RCS) – Globaliseringsfunktioner
description: Det här ämnet förklarar hur du använder Microsoft Regulatory Configuration Services (RCS) och den globala databasen för att skapa och använda globaliseringsfunktioner.
author: JaneA07
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: d5d42bd076ca77c5d2906593d44ae420d954a0b1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218864"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a><span data-ttu-id="eabaa-103">Regulatory Configuration Services (RCS) – Globaliseringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="eabaa-103">Regulatory Configuration Services (RCS) - Globalization features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eabaa-104">Du kan använda Microsoft Regulatory Configuration Services (RCS) för att skapa en globaliseringsfunktion som kan användas globaliseringstjänsten, t.ex. en e-faktureringstjänst.</span><span class="sxs-lookup"><span data-stu-id="eabaa-104">You can use Microsoft Regulatory Configuration Services (RCS) to create a Globalization feature that can be used in Globalization services, such as an e-invoicing service.</span></span> <span data-ttu-id="eabaa-105">Med RCS kan du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="eabaa-105">RCS lets you perform these tasks:</span></span>

- <span data-ttu-id="eabaa-106">Definiera relaterade komponenter för en funktion.</span><span class="sxs-lookup"><span data-stu-id="eabaa-106">Define related components of a feature.</span></span>
- <span data-ttu-id="eabaa-107">Hantera funktionens livscykel med hjälp av en funktions status.</span><span class="sxs-lookup"><span data-stu-id="eabaa-107">Manage the feature lifecycle through a feature's status.</span></span>
- <span data-ttu-id="eabaa-108">Göra en funktion tillgänglig för definierade miljöer.</span><span class="sxs-lookup"><span data-stu-id="eabaa-108">Make a feature available for defined environments.</span></span>
- <span data-ttu-id="eabaa-109">Dela en funktion med andra organisationer.</span><span class="sxs-lookup"><span data-stu-id="eabaa-109">Share a feature with other organizations.</span></span>

<span data-ttu-id="eabaa-110">Följande procedurer förklarar hur en användare i RCS kan lägga till en globaliseringsfunktion och tillhörande komponenter, uppdatera funktionens status och göra funktionen tillgänglig så att den kan användas i globaliseringstjänster.</span><span class="sxs-lookup"><span data-stu-id="eabaa-110">The following procedures explain how a user in RCS can add a Globalization feature and related components, update the feature's status, and make the feature available so that it can be used in Globalization services.</span></span>

<span data-ttu-id="eabaa-111">Innan du slutför procedurerna måste du utföra stegen som hör till följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="eabaa-111">Before you complete the procedures, you must complete the steps that are related to the following tasks:</span></span>

- <span data-ttu-id="eabaa-112">Öppna en RCS-instans.</span><span class="sxs-lookup"><span data-stu-id="eabaa-112">Accessing an RCS instance.</span></span>
- <span data-ttu-id="eabaa-113">Skapa och aktivera en konfigurationsleverantör.</span><span class="sxs-lookup"><span data-stu-id="eabaa-113">Creating and activating a configuration provider.</span></span> <span data-ttu-id="eabaa-114">Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="eabaa-114">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="eabaa-115">I Finance and Operations-appinstansen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="eabaa-115">In your Finance and Operations apps instance, follow these steps.</span></span>

1. <span data-ttu-id="eabaa-116">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-116">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="eabaa-117">Om ingen RCS-miljö har etablerats för ditt företag väljer du **Regulatory services – konfiguration** och följer sedan instruktionerna för att etablera en.</span><span class="sxs-lookup"><span data-stu-id="eabaa-117">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration**, and follow the instructions to provision one.</span></span>

> [!NOTE]
> <span data-ttu-id="eabaa-118">Om en RCS-miljö redan har etablerats för ditt företag kan du använda sidans URL för att komma åt miljön genom att välja alternativet för inloggning.</span><span class="sxs-lookup"><span data-stu-id="eabaa-118">If an RCS environment has already been provisioned for your company, use the page URL to access the environment by selecting the sign-in option.</span></span>

## <a name="turn-on-the-globalization-features"></a><span data-ttu-id="eabaa-119">Aktivera globaliseringsfunktionerna</span><span class="sxs-lookup"><span data-stu-id="eabaa-119">Turn on the Globalization features</span></span>

1. <span data-ttu-id="eabaa-120">I din RCS-instans, välj panelen **funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-120">In your RCS instance, select the **Feature management** tile.</span></span>
2. <span data-ttu-id="eabaa-121">I arbetsytan **Funktionshantering** välj **Globaliseringfunktioner** i listan och sedan **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-121">In the **Feature management** workspace, select **Globalization features** in the list, and then select **Enable now**.</span></span>

    ![Globaliseringsfunktioner i funktionshantering](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a><span data-ttu-id="eabaa-123">Globaliseringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="eabaa-123">Globalization features</span></span>

<span data-ttu-id="eabaa-124">Om du vill använda en globaliseringsfunktion måste du först importera den från den globala databasen och skapa en egen version av den.</span><span class="sxs-lookup"><span data-stu-id="eabaa-124">To use a Globalization feature, you must first import it from the the Global repository and create your own version of it.</span></span> <span data-ttu-id="eabaa-125">Du kan lägga till globaliseringsfunktioner på två sätt:</span><span class="sxs-lookup"><span data-stu-id="eabaa-125">There are two ways to add Globalization features:</span></span>

- <span data-ttu-id="eabaa-126">Lägga till en härledd funktion som baseras på en befintlig funktion som har publicerats eller delats.</span><span class="sxs-lookup"><span data-stu-id="eabaa-126">Add a derived feature that is based on an existing feature that has been published or shared.</span></span>
- <span data-ttu-id="eabaa-127">Lägg till en ny funktion som du skapat helt från början.</span><span class="sxs-lookup"><span data-stu-id="eabaa-127">Add a new feature that you've created from scratch.</span></span>

## <a name="access-globalization-features"></a><span data-ttu-id="eabaa-128">Få åtkomst till globaliseringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="eabaa-128">Access Globalization features</span></span>

1. <span data-ttu-id="eabaa-129">Se till att funktionen **globaliseringsfunktioner** är aktiverad i funktionshantering, enligt beskrivningen ovan.</span><span class="sxs-lookup"><span data-stu-id="eabaa-129">Make sure that the **Globalization features** feature is turned on in Feature management, as described earlier in this topic.</span></span>
2. <span data-ttu-id="eabaa-130">Öppna arbetsytan **globaliseringsfunktioner** och under **funktioner**, välj panelen **e-fakturering**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-130">Open the new **Globalization Features** workspace, and then, under **Features**, select the **e-Invoicing** tile.</span></span>

    ![Arbetsyta för globala funktioner](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    <span data-ttu-id="eabaa-132">Sidan **e-faktureringsfunktioner** öppnas.</span><span class="sxs-lookup"><span data-stu-id="eabaa-132">The **e-Invoicing Features** page is opened.</span></span>

    ![Sidan e-faktureringsfunktioner](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a><span data-ttu-id="eabaa-134">Lägga till en härledd globaliseringsfunktion</span><span class="sxs-lookup"><span data-stu-id="eabaa-134">Add a derived Globalization feature</span></span>

<span data-ttu-id="eabaa-135">Du kan lägga till en ny globaliseringsfunktion genom att härleda den från en befintlig funktion som har publicerats eller delats.</span><span class="sxs-lookup"><span data-stu-id="eabaa-135">You can add a new Globalization feature by deriving it from an existing feature that has been published or shared.</span></span>

1. <span data-ttu-id="eabaa-136">Välj **importera** om du vill öppna sidan **importfunktionen från den globala databasen**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-136">Select **Import** to open the **Import feature from Global repository** page.</span></span>

    ![Importera funktion från sidan Global databas](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. <span data-ttu-id="eabaa-138">Välj **synkronisera** om du vill hämta de senaste funktionerna.</span><span class="sxs-lookup"><span data-stu-id="eabaa-138">Select **Synchronize** to get the latest features.</span></span>

    <span data-ttu-id="eabaa-139">I den synkroniserade listan finns funktioner som du kan välja mellan eftersom de publicerades av Microsoft eller att de har delats med dig av en annan konfigurationsleverantör.</span><span class="sxs-lookup"><span data-stu-id="eabaa-139">The synced list includes features that are available to you either because they were published by Microsoft or because they were shared with you by another configuration provider.</span></span>

    ![Synkroniserad lista över funktioner](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. <span data-ttu-id="eabaa-141">Välj de funktioner du vill importera i listan och välj sedan **Importera**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-141">In the list, select the features to import, and then select **Import**.</span></span> <span data-ttu-id="eabaa-142">Ett meddelande visas när de valda funktionerna har importerats utan problem.</span><span class="sxs-lookup"><span data-stu-id="eabaa-142">You receive a message when the selected features have been successfully imported.</span></span>

    ![Meddelandet Import klar](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. <span data-ttu-id="eabaa-144">Välj **Lägg till** och välj sedan alternativet **baserad på befintlig version i den nedrullningsbara dialogrutan**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-144">Select **Add**, and then, in the drop-down dialog box, select the **Based on existing version** option.</span></span>
5. <span data-ttu-id="eabaa-145">Ange ett namn och en beskrivning för funktionen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-145">Enter a name and description for the feature.</span></span>
6. <span data-ttu-id="eabaa-146">Välj basversion för funktionen i listan med tillgängliga funktioner och välj sedan **skapa funktion**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-146">In the list of available features, select the base version of the feature, and then select **Create feature**.</span></span>

    ![Lägga till en härledd funktion](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    <span data-ttu-id="eabaa-148">Funktionen som du har lagt till skapas och har statusen **utkast**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-148">The feature that you added is created and has a status of **Draft**.</span></span>

    ![Härledd funktion med utkaststatus](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. <span data-ttu-id="eabaa-150">Granska funktionskomponenterna och ta reda på om det behövs några uppdateringar:</span><span class="sxs-lookup"><span data-stu-id="eabaa-150">Review the feature components to determine whether updates are required:</span></span>

    - <span data-ttu-id="eabaa-151">Granska konfigurationerna om du skulle behöva anpassa formaten för elektronisk rapportering (ER) och deras bindningar med formatmappningar för funktionsversionen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-151">Review the configurations, in case you need to customize the Electronic reporting (ER) formats and their binding with format mappings for the feature version.</span></span>
    - <span data-ttu-id="eabaa-152">Granska inställningarna om du skulle behöva anpassa fliken **åtgärder**, fliken **tillämplighetsregler** eller fliken **variabler** för funktionsversionen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-152">Review the setup, in case you need to customize the **Actions** tab, **Applicability rules** tab, or **Variables** tab for the feature version.</span></span>

8. <span data-ttu-id="eabaa-153">På fliken **Versioner** väljer du ett datum för **Giltighet från** och anger en beskrivning om fältet **Beskrivning** är tomt.</span><span class="sxs-lookup"><span data-stu-id="eabaa-153">On the **Versions** tab, select an **Effective from** date, and enter a description if the **Description** field is blank.</span></span>
9. <span data-ttu-id="eabaa-154">Välj **ändra status** om du vill slutföra funktionen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-154">Select **Change status** to complete the feature.</span></span> <span data-ttu-id="eabaa-155">Slutförda funktioner kan göras tillgängliga för en viss miljö så att de kan användas i globaliseringstjänster, och de kan också publiceras i den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-155">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="eabaa-156">Funktioner med värdet **funktionsversionstatus** för **publicerade** kan delas med externa organisationer.</span><span class="sxs-lookup"><span data-stu-id="eabaa-156">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="add-a-new-globalization-feature"></a><span data-ttu-id="eabaa-157">Lägga till en ny globaliseringsfunktion</span><span class="sxs-lookup"><span data-stu-id="eabaa-157">Add a new Globalization feature</span></span>

<span data-ttu-id="eabaa-158">Du kan lägga till en ny globaliseringsfunktion genom att skapa den från grunden.</span><span class="sxs-lookup"><span data-stu-id="eabaa-158">You can add a new Globalization feature by creating it from scratch.</span></span>

1. <span data-ttu-id="eabaa-159">På sidan **Importera funktion från global databas**, välj **Lägg till** och sedan i nedrullningsbar dialogruta väljer du alternativet **Ny funktion**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-159">On the **Import feature from Global repository** page, select **Add**, and then, in the drop-down dialog box, select the **New feature** option.</span></span>
2. <span data-ttu-id="eabaa-160">Ange ett namn och en beskrivning för funktionen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-160">Enter a name and description for the feature.</span></span>
3. <span data-ttu-id="eabaa-161">Välj **skapa funktion**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-161">Select **Create feature**.</span></span>

    ![Lägga till en ny funktion](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. <span data-ttu-id="eabaa-163">På fliken **versioner** välj ett **Giltighet från**-datum och sedan **Ändra status** för att slutföra funktionen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-163">On the **Versions** tab, select an **Effective from** date, and then select **Change status** to complete the feature.</span></span> <span data-ttu-id="eabaa-164">Slutförda funktioner kan göras tillgängliga för en viss miljö så att de kan användas i globaliseringstjänster, och de kan också publiceras i den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-164">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="eabaa-165">Funktioner med värdet **funktionsversionstatus** för **publicerade** kan delas med externa organisationer.</span><span class="sxs-lookup"><span data-stu-id="eabaa-165">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="feature-component-overview"></a><span data-ttu-id="eabaa-166">Översikt över funktionskomponent</span><span class="sxs-lookup"><span data-stu-id="eabaa-166">Feature component overview</span></span>

<span data-ttu-id="eabaa-167">Globaliseringsfunktioner har flera komponenter:</span><span class="sxs-lookup"><span data-stu-id="eabaa-167">Globalization features have several components:</span></span>

- <span data-ttu-id="eabaa-168">**Version** – den här komponenten stöder funktionen livscykelhantering och låter användare hantera status för olika versioner av funktionen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-168">**Version** – This component supports feature lifecycle management and lets users manage the status for different versions of the feature.</span></span>
- <span data-ttu-id="eabaa-169">**Konfigurationer** – med den här komponenten kan användarna hantera, visa och redigera tillhörande ER-format och formatmappningar.</span><span class="sxs-lookup"><span data-stu-id="eabaa-169">**Configurations** – This component lets users manage, view, and edit related ER formats and format mappings.</span></span>
- <span data-ttu-id="eabaa-170">**Inställningar** – den här komponenten gör det möjligt för användare med globaliseringstjänster, t.ex. en e-faktureringstjänst, att hantera inställningen av den relaterade funktionsversionen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-170">**Setups** – This component lets users of Globalization services, such as an e-invoicing service, manage the setup of the related feature version.</span></span> <span data-ttu-id="eabaa-171">Därför stöder den flexibla uppföranden av kommunikations- och svarsregler.</span><span class="sxs-lookup"><span data-stu-id="eabaa-171">Therefore, it supports the flexible construction of communication and responses rules.</span></span>
- <span data-ttu-id="eabaa-172">**Miljö** – med den här komponenten kan användare med globaliseringstjänster, t.ex. en e-faktureringstjänst, hantera miljön där funktionsversionsinställningarna används och bevilja behörighet till de användare som ska ha åtkomst till den.</span><span class="sxs-lookup"><span data-stu-id="eabaa-172">**Environment** – This component lets users of Globalization services, such as an e-invoicing service, manage the environment where the feature version setup is used and grant authorization to the users who will have access to it.</span></span>
- <span data-ttu-id="eabaa-173">**Organisationer** – med den här komponenten kan användarna dela funktionen med externa organisationer.</span><span class="sxs-lookup"><span data-stu-id="eabaa-173">**Organizations** – This component lets users to share the feature with external organizations.</span></span>

## <a name="configuring-feature-components"></a><span data-ttu-id="eabaa-174">Konfigurera funktionskomponenter</span><span class="sxs-lookup"><span data-stu-id="eabaa-174">Configuring feature components</span></span>

### <a name="version-and-status"></a><span data-ttu-id="eabaa-175">Version och status</span><span class="sxs-lookup"><span data-stu-id="eabaa-175">Version and status</span></span>

<span data-ttu-id="eabaa-176">Versionen används för att hantera livscykeln för globaliseringsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="eabaa-176">The version is used to manage the Globalization feature lifecycle.</span></span>

<span data-ttu-id="eabaa-177">Statusvärdet kan ändras i fältet **Status** på fliken **Version**. Följande statusvärden finns:</span><span class="sxs-lookup"><span data-stu-id="eabaa-177">The status can be changed in the **Status** field on the **Version** tab. The following statuses are available:</span></span>

- <span data-ttu-id="eabaa-178">**Utkast** – funktionen kan endast redigeras om den har denna status.</span><span class="sxs-lookup"><span data-stu-id="eabaa-178">**Draft** – The feature can be edited only when it's in this status.</span></span>
- <span data-ttu-id="eabaa-179">**Slutförd** – funktionen och alla relaterade komponenter har slutförts och kan inte redigeras.</span><span class="sxs-lookup"><span data-stu-id="eabaa-179">**Complete** – The feature and all related components have been finalized (completed) and can't be edited.</span></span>
- <span data-ttu-id="eabaa-180">**Publicerad** – funktionen och alla relaterade komponenter har publicerats i den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-180">**Published** – The feature and all related components have been published to the Global repository.</span></span>
- <span data-ttu-id="eabaa-181">**Delad** – funktionen och alla relaterade komponenter har delats med externa organisationer.</span><span class="sxs-lookup"><span data-stu-id="eabaa-181">**Shared** – The feature and all related components have been shared with external organizations.</span></span>
- <span data-ttu-id="eabaa-182">**Aktiverad** – funktionen och alla relaterade komponenter har aktiverats för användning i en globaliseringstjänst, t.ex. en e-faktureringstjänst.</span><span class="sxs-lookup"><span data-stu-id="eabaa-182">**Enabled** – The feature and all related components have been enabled for use in a Globalization service, such as an e-invoicing service.</span></span>

> [!NOTE]
> <span data-ttu-id="eabaa-183">Funktionerna måste gå sekventiellt genom vissa av dessa statusvärden.</span><span class="sxs-lookup"><span data-stu-id="eabaa-183">Features must move sequentially through some of these statuses.</span></span> <span data-ttu-id="eabaa-184">Därför kan inte alla statusvärden vara tillgängliga i varje livscykelsteg.</span><span class="sxs-lookup"><span data-stu-id="eabaa-184">Therefore, not every status might be available at every lifecycle stage.</span></span>

### <a name="configurations"></a><span data-ttu-id="eabaa-185">Konfigurationer</span><span class="sxs-lookup"><span data-stu-id="eabaa-185">Configurations</span></span>

<span data-ttu-id="eabaa-186">Följande åtgärder är tillgängliga för konfigurationer:</span><span class="sxs-lookup"><span data-stu-id="eabaa-186">The following actions are available for configurations:</span></span>

- <span data-ttu-id="eabaa-187">**Visa** – Visa de underliggande funktionskonfigurationerna som inte kräver någon uppdatering.</span><span class="sxs-lookup"><span data-stu-id="eabaa-187">**View** – View the underlying feature configurations that don't require any update.</span></span>
- <span data-ttu-id="eabaa-188">**Redigera** – skapa en utkastversion av en vald konfiguration så att du kan redigera formatet eller format mappningen i formatdesignern.</span><span class="sxs-lookup"><span data-stu-id="eabaa-188">**Edit** – Create a draft version of a selected configuration so that you can edit the format or format mapping in the Format designer.</span></span>
- <span data-ttu-id="eabaa-189">**Ta bort** – Tar bort en vald konfiguration från funktionen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-189">**Delete** – Delete a selected configuration from the feature.</span></span>
- <span data-ttu-id="eabaa-190">**Basera om** – basera om funktionen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-190">**Rebase** – Rebase the feature.</span></span> <span data-ttu-id="eabaa-191">Mer information finns i avsnittet [BAsera om härledda globaliseringsfunktioner](#rebase) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="eabaa-191">For more information, see the [Rebase derived Globalization features](#rebase) section later in this topic.</span></span>

### <a name="setups"></a><span data-ttu-id="eabaa-192">Inställningar</span><span class="sxs-lookup"><span data-stu-id="eabaa-192">Setups</span></span>

<span data-ttu-id="eabaa-193">Följande åtgärder är tillgängliga för framtida inställningar:</span><span class="sxs-lookup"><span data-stu-id="eabaa-193">The following actions are available for feature setups:</span></span>

- <span data-ttu-id="eabaa-194">**Lägg till** – skapa en ny funktionsinställning.</span><span class="sxs-lookup"><span data-stu-id="eabaa-194">**Add** – Create a new feature setup.</span></span> <span data-ttu-id="eabaa-195">Dessa funktionsinställning kan härledas från befintliga funktionsinställningar eller skapas från grunden.</span><span class="sxs-lookup"><span data-stu-id="eabaa-195">This feature setup can be derived from an existing feature setup or created from scratch.</span></span>
- <span data-ttu-id="eabaa-196">**Ta bort** – ta bort valda funktionsinställningar.</span><span class="sxs-lookup"><span data-stu-id="eabaa-196">**Delete** – Delete a selected feature setup.</span></span>
- <span data-ttu-id="eabaa-197">**Visa** – Visa en underliggande funktionsinställning som inte kräver några ändringar.</span><span class="sxs-lookup"><span data-stu-id="eabaa-197">**View** – View an underlying feature setup that doesn't require any changes.</span></span>
- <span data-ttu-id="eabaa-198">**Redigera** – skapa, ta bort eller ändra attributen för de tre huvudkomponenterna i en funktionsinställning:</span><span class="sxs-lookup"><span data-stu-id="eabaa-198">**Edit** – Create, delete, or modify the attributes of the three main components of a feature setup:</span></span>

    - <span data-ttu-id="eabaa-199">Åtgärder och deras parametrar</span><span class="sxs-lookup"><span data-stu-id="eabaa-199">Actions and their parameters</span></span>
    - <span data-ttu-id="eabaa-200">Tillämplighetsregler</span><span class="sxs-lookup"><span data-stu-id="eabaa-200">Applicability rules</span></span>
    - <span data-ttu-id="eabaa-201">Variabler</span><span class="sxs-lookup"><span data-stu-id="eabaa-201">Variables</span></span>

![Inställningssida för funktionsversion](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a><span data-ttu-id="eabaa-203">Miljöer</span><span class="sxs-lookup"><span data-stu-id="eabaa-203">Environments</span></span>

<span data-ttu-id="eabaa-204">Följande åtgärder är tillgängliga för miljöer:</span><span class="sxs-lookup"><span data-stu-id="eabaa-204">The following actions are available for environments:</span></span>

- <span data-ttu-id="eabaa-205">**Aktivera** – Välj en publicerad miljö under en vald funktionsversion och välj ett **Giltighet från**-datum då den ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="eabaa-205">**Enable** – For a selected feature version, select a published environment, and select an **Effective from** date when it should be available.</span></span> <span data-ttu-id="eabaa-206">Mer information finns i avsnittet [Konfigurera miljöer för aktivering](#configureenvironment) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="eabaa-206">For more information, see the [Configure environments for enablement](#configureenvironment) section later in this topic.</span></span>
- <span data-ttu-id="eabaa-207">**Avbryt** – ta bort en miljö för en funktionsinställning.</span><span class="sxs-lookup"><span data-stu-id="eabaa-207">**Cancel** – Remove an environment for a feature setup.</span></span>

### <a name="organizations"></a><span data-ttu-id="eabaa-208">Organisationer</span><span class="sxs-lookup"><span data-stu-id="eabaa-208">Organizations</span></span>

<span data-ttu-id="eabaa-209">Följ dessa steg om du vill dela en globaliseringsfunktion med en extern organisation.</span><span class="sxs-lookup"><span data-stu-id="eabaa-209">Follow these steps to share a Globalization feature with an external organization.</span></span>

1. <span data-ttu-id="eabaa-210">På sidan **e-faktureringsfunktioner** väljer du funktionen och funktionsversionen som ska delas.</span><span class="sxs-lookup"><span data-stu-id="eabaa-210">On the **e-Invoicing features** page, select the feature and the feature version to share.</span></span>
2. <span data-ttu-id="eabaa-211">På sidan **Organisationer**, välj **Dela med** och ange sedan organisationens domännamn i den nedrullningsbara dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="eabaa-211">On the **Organizations** tab, select **Share with**, and then, in the drop-down dialog box, enter the organization's domain name.</span></span>
3. <span data-ttu-id="eabaa-212">Välj **dela**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-212">Select **Share**.</span></span>

    ![Dela en funktion med en organisation](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

<span data-ttu-id="eabaa-214">Fuktionen delas med den valda organisationen och är tillgänglig för den organisationen i den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-214">The feature is shared with the selected organization and is available for that organization in the Global repository.</span></span> <span data-ttu-id="eabaa-215">Därifrån kan funktionen importeras till organisationens instans av RCS eller Dynamics 365 Finance så att den kan användas.</span><span class="sxs-lookup"><span data-stu-id="eabaa-215">From there, the feature can be imported into the organization's instance of RCS or Dynamics 365 Finance so that it can be used.</span></span>

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a><span data-ttu-id="eabaa-216">Basera om härledda globaliseringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="eabaa-216">Rebase derived Globalization features</span></span>

<span data-ttu-id="eabaa-217">Du kan basera en härledd globaliseringsfunktion på ny eller uppdaterad basfunktionsversion.</span><span class="sxs-lookup"><span data-stu-id="eabaa-217">You can rebase a derived Globalization feature to the new or updated base feature version.</span></span> <span data-ttu-id="eabaa-218">På så sätt kan ändringar som har gjorts i basversionen uppdateras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="eabaa-218">In this way, changes that have occurred in the base version can be automatically updated.</span></span> <span data-ttu-id="eabaa-219">Den uppdaterade basfunktionsversionen skapas av den ursprungliga konfigurationsprovidern och publiceras eller delas sedan.</span><span class="sxs-lookup"><span data-stu-id="eabaa-219">The updated base feature version is created by the originating configuration provider, and it's then published or shared.</span></span>

![Uppdaterad basfunktionsversion](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

<span data-ttu-id="eabaa-221">Om du till exempel vill basera om den härledda versionen av en funktion som du skapade, hämtar du först den senaste versionen av funktionen genom att importera den från den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-221">For example, if you want to rebase the derived version of a feature that you created, you first get the latest version of the feature by importing it from the Global repository.</span></span>

1. <span data-ttu-id="eabaa-222">På sidan **e-faktureringsfunktioner**, välj **Importera**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-222">On the **e-Invoicing features** page, select **Import**.</span></span>
2. <span data-ttu-id="eabaa-223">Välj **synkronisera** om du vill hämta de senaste funktionerna.</span><span class="sxs-lookup"><span data-stu-id="eabaa-223">Select **Synchronize** to get the latest features.</span></span>
3. <span data-ttu-id="eabaa-224">Välj de funktioner du vill importera i listan över funktioner och välj sedan **Importera**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-224">In the list of features, select the features to import, and then select **Import**.</span></span>

    ![Importera den senaste versionen av en funktion](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. <span data-ttu-id="eabaa-226">Välj den funktion som ska återbyggas i listan över funktioner.</span><span class="sxs-lookup"><span data-stu-id="eabaa-226">In the list of features, select the feature to rebase.</span></span>
5. <span data-ttu-id="eabaa-227">På fliken **Version**, välj **Ny** för att skapa en utkastversion.</span><span class="sxs-lookup"><span data-stu-id="eabaa-227">On the **Version** tab, select **New** to create a draft version.</span></span>

    ![Nytt utkastversion har skapats](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. <span data-ttu-id="eabaa-229">Välj **Basera om**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-229">Select **Rebase**.</span></span>
7. <span data-ttu-id="eabaa-230">I dialogrutan **Basera om** väljer du den senaste versionen av funktionen som ska baseras om till.</span><span class="sxs-lookup"><span data-stu-id="eabaa-230">In the **Rebase** dialog box, select the latest version of the feature to rebase to.</span></span>

    ![Dialogrutan Basera om](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. <span data-ttu-id="eabaa-232">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-232">Select **OK**.</span></span>
9. <span data-ttu-id="eabaa-233">Granska funktionskomponenter och gör nödvändiga ändringar.</span><span class="sxs-lookup"><span data-stu-id="eabaa-233">Review the feature components, and make any changes that are required.</span></span>
10. <span data-ttu-id="eabaa-234">Välj **ändra status** om du vill slutföra funktionen basera om.</span><span class="sxs-lookup"><span data-stu-id="eabaa-234">Select **Change status** to complete the rebased feature.</span></span> <span data-ttu-id="eabaa-235">När ombaseringen är slutförd kan du utföra ytterligare åtgärder.</span><span class="sxs-lookup"><span data-stu-id="eabaa-235">When the rebase is completed, you can perform additional actions.</span></span> <span data-ttu-id="eabaa-236">Du kan till exempel publicera funktionen och göra den tillgänglig för användning i globaliseringstjänster.</span><span class="sxs-lookup"><span data-stu-id="eabaa-236">For example, you can publish the feature and make it available for use in Globalization services.</span></span>

    ![Funktionsstatus uppdaterades till slutfört](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a><span data-ttu-id="eabaa-238">Konfigurera miljöer för globaliseringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="eabaa-238">Configure environments for Globalization features</span></span>

<span data-ttu-id="eabaa-239">Användare av globaliseringstjänster kan hantera miljön för att ställa in en globaliseringsfunktion och bevilja behörighet till andra användare som kommer att ha åtkomst till den.</span><span class="sxs-lookup"><span data-stu-id="eabaa-239">Users of Globalization services can manage the environment to set up a Globalization feature and grant authorization to other users who will have access to it.</span></span>

1. <span data-ttu-id="eabaa-240">I arbetsytan **globaliseringsfunktioner** och under **Miljöer**, välj panelen **e-fakturering**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-240">In the **Globalization Features** workspace, under **Environments**, select the **e-Invoicing** tile.</span></span>

    ![Arbetsyta för globaliseringsfunktioner](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. <span data-ttu-id="eabaa-242">Välj **Parametrar för nyckelvalv** och välj sedan **Ny** för att skapa en Azure Key Vault-hemlighet.</span><span class="sxs-lookup"><span data-stu-id="eabaa-242">Select **Key Vault parameters**, and then select **New** to create an Azure Key Vault secret.</span></span>
3. <span data-ttu-id="eabaa-243">Ange ett namn och en beskrivning för nyckelvalvet och ange sedan i fältet **URI för nyckelvalv**, ange den URL som identifierar nyckelvalvresursen i Azure.</span><span class="sxs-lookup"><span data-stu-id="eabaa-243">Enter a name and description for the key vault, and then, in the **Key Vault URI** field, enter the URL that identifies the Key Vault resource in Azure.</span></span>
4. <span data-ttu-id="eabaa-244">På snabbfliken **Certifikat** väljer du **Lägg till** om du vill lägga till certifikatet och ange ett namn och en beskrivning för varje certifikat.</span><span class="sxs-lookup"><span data-stu-id="eabaa-244">On the **Certificates** FastTab, select **Add** to add the certificate, and enter a name and description for each certificate.</span></span>

    ![Certifikat tillagt](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. <span data-ttu-id="eabaa-246">Skapa en ny miljö genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="eabaa-246">Select **New** to create a new environment.</span></span>
6. <span data-ttu-id="eabaa-247">Ange ett namn, en beskrivning och hemligheten som krävs för signaturen för signaturen som krävs för lagringen.</span><span class="sxs-lookup"><span data-stu-id="eabaa-247">Enter a name, a description, and the shared access signature token secret required for the storage.</span></span>
7. <span data-ttu-id="eabaa-248">På snabbfliken **Användare** väljer du **Ny** för att lägga till en användare som har behörighet att komma åt den här miljön.</span><span class="sxs-lookup"><span data-stu-id="eabaa-248">On the **Users** FastTab, select **New** to add a user who will have permission to access this environment.</span></span>
8. <span data-ttu-id="eabaa-249">Ange användarens användar-ID och e-postadress.</span><span class="sxs-lookup"><span data-stu-id="eabaa-249">Enter the user's user ID and email address.</span></span>
9. <span data-ttu-id="eabaa-250">Upprepa steg 7 och 8 om du vill lägga till fler användare.</span><span class="sxs-lookup"><span data-stu-id="eabaa-250">Repeat steps 7 and 8 to add more users.</span></span>
10. <span data-ttu-id="eabaa-251">Välj **publicera** om du vill publicera miljön.</span><span class="sxs-lookup"><span data-stu-id="eabaa-251">Select **Publish** to publish the environment.</span></span>

    ![Publicerad miljö](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]