---
title: Arbeta med CSS-åsidosättningsfiler
description: Det här avsnittet beskriver varför, när och hur du använder Cascading Style Sheets (CSS) åsidosätta filer i Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b5a50fc0c9060117cdddc0875446afc2edc12a11
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915449"
---
# <a name="work-with-css-override-files"></a><span data-ttu-id="4c9a0-103">Arbeta med CSS-åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="4c9a0-103">Work with CSS override files</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="4c9a0-104">Det här avsnittet beskriver varför, när och hur du använder Cascading Style Sheets (CSS) åsidosätta filer i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-104">This topic describes why, when, and how to use Cascading Style Sheets (CSS) override files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4c9a0-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="4c9a0-105">Overview</span></span>

<span data-ttu-id="4c9a0-106">Permanenta webbplatsstilar bör vanligtvis hanteras via webbplatsens tema.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-106">Permanent site styles should usually be handled through a site's theme.</span></span> <span data-ttu-id="4c9a0-107">Teman ger grundläggande CSS och stilinställningar för modulerna på alla sidor på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-107">Themes provide the foundational CSS and style settings for the modules on any page of your site.</span></span> <span data-ttu-id="4c9a0-108">Teman skapas med hjälp av Dynamics 365 Commerce online Software Development Kit (SDK) och de distribueras till dina webbplatser via Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4c9a0-108">Themes are created by using the Dynamics 365 Commerce online software development kit (SDK), and they are deployed to your websites through Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="4c9a0-109">Tema felsökningsfunktioner och konfigurationer av modulgränssnitt i SDK hjälp webbplatsutvecklare skapar anpassningsbara och sammanhängande designpaket för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-109">Theme debugging capabilities and module interface configurations in the SDK help site developers create customizable and cohesive site design packages.</span></span> <span data-ttu-id="4c9a0-110">När dessa designpaket distribueras till en webbplats kan webbplatsförfattarna fokusera på att skapa, redigera och publicera innehåll i stället för webbplatsutveckling.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-110">When these design packages are deployed to a site, site authors can focus on creating, editing, and publishing content instead of site development.</span></span>

<span data-ttu-id="4c9a0-111">Med tanke på den vanliga livscykeln för ett tema kan beroendet för utvecklare att göra formatändringar via SDK och LCS distributionspipeline vara oöverkomliga i vissa fall.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-111">Given the usual lifecycle of a theme, the dependency on developers to make style changes through the SDK and LCS deployment pipeline can be prohibitive in some scenarios.</span></span> <span data-ttu-id="4c9a0-112">Webbplatsprototyper eller snabbkorrigeringar kan verka omständligt om SDK inte har konfigurerats eller om du inte har tid att vänta på en LCS-distribution.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-112">Site prototypes or hotfixes can seem cumbersome if the SDK isn't configured, or if you don't have time to wait for an LCS deployment.</span></span>

<span data-ttu-id="4c9a0-113">I dessa fall kan CSS åsidosätta filer hjälpa.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-113">In these scenarios, CSS override files can help.</span></span> <span data-ttu-id="4c9a0-114">I Commerce redigeringsverktyg kan autentiserade användare ladda upp en CSS-fil, förhandsgranska den och sedan aktivera den för att åsidosätta webbplatsens tema.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-114">In the Commerce authoring tools, authenticated users can upload a CSS file, preview it, and then activate it to override a site's theme.</span></span> <span data-ttu-id="4c9a0-115">Omkostnader för SDK- eller LCS-distribution krävs inte.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-115">The overhead of SDK or LCS deployment isn't required.</span></span> <span data-ttu-id="4c9a0-116">Åsidosättningar som anges i en CSS åsidosättningfil kan vara så liten som en ändring i en enda textstil eller så vittomfattande som en fullständig varumärkesöversyn.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-116">The overrides that are specified in a CSS override file can be as small as a change to a single text style or as wide-ranging as a complete brand overhaul.</span></span>

<span data-ttu-id="4c9a0-117">Innan du använder CSS åsidosättningsfiler bör du vara medveten om följande begränsningar:</span><span class="sxs-lookup"><span data-stu-id="4c9a0-117">Before you use CSS override files, be aware of the following limitations:</span></span>

- <span data-ttu-id="4c9a0-118">Endast en CSS åsidosättningfil kan vara aktiv på en plats i taget.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-118">Only one CSS override file can be active on a site at a time.</span></span> <span data-ttu-id="4c9a0-119">Därför måste alla aktiva åsidosättningar finnas i en enda åsidosättningfil.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-119">Therefore, all active overrides must be present in a single override file.</span></span>
- <span data-ttu-id="4c9a0-120">Även om du kan förhandsgranska åsidosättningarna i Commerce redigeringsverktygen finns det inga särskilda felsökningsfunktioner som hjälper dig att identifiera eventuella buggar som åsidosättningarna introducerar.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-120">Although you can preview the overrides in the Commerce authoring tools, there are no dedicated debugging features to help identify any bugs that the overrides introduce.</span></span> <span data-ttu-id="4c9a0-121">Med andra ord, när du använder CSS åsidosättningsfiler, har du inte samma verktygsuppsättning som SDK ger för modul och redigeringsvalidering.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-121">In other words, when you use CSS override files, you don't have the same toolset that the SDK provides for module and authoring validation.</span></span>

<span data-ttu-id="4c9a0-122">CSS åsidosätta filer ger dock ett snabbt sätt att göra en prototyp av en design eller implementera en snabbkorrigering innan en fullständig temauppdatering har utvecklats och distribuerats.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-122">Nevertheless, CSS override files provide a quick way to prototype a design or implement a hotfix before a full theme update is developed and deployed.</span></span>

## <a name="create-a-css-override-file"></a><span data-ttu-id="4c9a0-123">Skapa en CSS åsidosättningfil</span><span class="sxs-lookup"><span data-stu-id="4c9a0-123">Create a CSS override file</span></span>

<span data-ttu-id="4c9a0-124">Om du vill skapa en CSS åsidosättningfil kan du använda valfri integrerad utvecklingsmiljö (IDE), textredigerare eller källkodsredigerare.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-124">To create a CSS override file, you can use any integrated development environment (IDE), text editor, or source code editor.</span></span> <span data-ttu-id="4c9a0-125">Ett typiskt tillvägagångssätt är att använda vanliga webbfelsökare i din webbläsare för att identifiera stilväljare, egenskaper och värden på din befintliga webbplats.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-125">A typical approach is to use standard web debuggers in your browser to identify style selectors, properties, and values on your existing site.</span></span> <span data-ttu-id="4c9a0-126">I de flesta webbläsare kan du ändra värden och förhandsgranska dem i felsökaren.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-126">Most browsers let you change values and preview them in the debugger.</span></span> <span data-ttu-id="4c9a0-127">När du har identifierat de ändringar du vill göra kan du spara dem i din egen CSS-fil.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-127">After you've identified the changes that you want to make, you can save them to your own CSS file.</span></span>

## <a name="upload-a-css-override-file"></a><span data-ttu-id="4c9a0-128">Överför en CSS åsidosättningfil</span><span class="sxs-lookup"><span data-stu-id="4c9a0-128">Upload a CSS override file</span></span>

<span data-ttu-id="4c9a0-129">Så här överför du en CSS-fil till din webbplats i Commerce.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-129">To upload a CSS file to your site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="4c9a0-130">I redigeringsverktygen går du till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-130">In the authoring tools, go to your site.</span></span>
1. <span data-ttu-id="4c9a0-131">I navigeringsfönstret till vänster, välj **Design**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-131">In the navigation pane on the left, select **Design**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c9a0-132">Beroende på vilken version av Commerce redigeringsverktyg du använder kan du behöva expandera **inställningarna** i navigeringsfönstret innan du kan välja **design**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-132">Depending on the version of the Commerce authoring tools that you're using, you might have to expand **Settings** in the navigation pane before you can select **Design**.</span></span>

1. <span data-ttu-id="4c9a0-133">Överst i huvuddesignfönstret väljer du fliken **CSS åsidosätt** om den inte redan är markerad.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-133">At the top of the main design pane, select the **CSS override** tab, if it isn't already selected.</span></span>
1. <span data-ttu-id="4c9a0-134">Under **tillgängliga CSS åsidosättningar** väljer du **överför CSS-fil**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-134">Under **Available CSS overrides**, select **Upload CSS file**.</span></span> <span data-ttu-id="4c9a0-135">Ett filwebbläsarfönster visas.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-135">A File Explorer window appears.</span></span>
1. <span data-ttu-id="4c9a0-136">I Utforskaren bläddrar du till och väljer en CSS-fil och väljer sedan **öppna**</span><span class="sxs-lookup"><span data-stu-id="4c9a0-136">In File Explorer, browse to and select a CSS file, and then select **Open**.</span></span> <span data-ttu-id="4c9a0-137">Den överförda CSS-filen visas nu under **tillgängliga CSS åsidosättningar**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-137">The uploaded CSS file now appears under **Available CSS overrides**.</span></span>

## <a name="preview-a-css-override-file"></a><span data-ttu-id="4c9a0-138">Förhandsgranska en CSS åsidosättningfil</span><span class="sxs-lookup"><span data-stu-id="4c9a0-138">Preview a CSS override file</span></span>

<span data-ttu-id="4c9a0-139">För att förhandsgranska en CSS åsidosättningfil innan du gör den aktiv på din aktiva webbplats.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-139">To preview a CSS override file before you make it active on your live site, follow these steps.</span></span>

1. <span data-ttu-id="4c9a0-140">I navigeringsfönstret till vänster väljer du **design** och sedan på fliken **CSS åsidosätt** under **tillgängliga CSS åsidosättningar**, leta upp CSS-filen som du vill förhandsgranska.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-140">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to preview.</span></span>
1. <span data-ttu-id="4c9a0-141">Bredvid CSS filnamnet, välj **förhandsgranska webbplats**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-141">Next to the CSS file name, select **Preview site**.</span></span>
1. <span data-ttu-id="4c9a0-142">I dialogrutan **Välj en URL** väljer du URL-adressen till den webbplats som du vill visa åsidosättningen för och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-142">In the **Select a URL** dialog box, select the URL of the site that you want to see the override applied to, and then select **OK**.</span></span>
1. <span data-ttu-id="4c9a0-143">Om det finns flera varianter för den valda webbadressen väljer du önskad variant i dialogrutan **Förhandsgranska variationer** som visas.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-143">If there are multiple variants for the selected URL, select the desired variant in the **Preview variations** dialog box that appears.</span></span>

<span data-ttu-id="4c9a0-144">En ny webbläsarflik eller ett nytt fönster öppnas, där du kan validera dina stilåsidosättningar mot din webbplats.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-144">A new browser tab or window is opened, where you can validate your style overrides against your site.</span></span> <span data-ttu-id="4c9a0-145">Du kan sedan dela URL:en med andra autentiserade Commerce-användare för granskning och feedback.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-145">You can then share the URL with other authenticated Commerce users for review and feedback.</span></span>

## <a name="activate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="4c9a0-146">Aktivera en CSS åsidosättningfil på din aktiva webbplats</span><span class="sxs-lookup"><span data-stu-id="4c9a0-146">Activate a CSS override file on your live site</span></span>

<span data-ttu-id="4c9a0-147">När du har förhandsgranskat och godkänt CSS åsidosättningfilen kan du aktivera den på din aktiva webbplats.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-147">After you've previewed and approved the CSS override file, you can activate it on your live site.</span></span>

> [!NOTE]
> <span data-ttu-id="4c9a0-148">Endast en CSS åsidosättningfil kan vara aktiv på en plats i taget.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-148">Only one CSS override file can be active on your site at a time.</span></span> <span data-ttu-id="4c9a0-149">Om du aktiverar en ny åsidosättningfil inaktiveras den tidigare åsidosättningsfilen.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-149">If you activate a new override file, the previous override file is inactivated.</span></span> <span data-ttu-id="4c9a0-150">Kontrollera därför att alla obligatoriska åsidosättningar finns i en enda CSS åsidosättningfil.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-150">Therefore, make sure that all required overrides are present in a single CSS override file.</span></span>

<span data-ttu-id="4c9a0-151">Gör så här om du vill aktivera en CSS åsidosättningfil.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-151">To activate a CSS override file, follow these steps.</span></span>

1. <span data-ttu-id="4c9a0-152">I navigeringsfönstret till vänster väljer du **design** och sedan på fliken **CSS åsidosätt** under **tillgängliga CSS åsidosättningar**, leta upp CSS-filen som du vill aktivera.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-152">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to activate.</span></span>
1. <span data-ttu-id="4c9a0-153">Under CSS filnamnet väljer du **aktivera**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-153">Under the CSS file name, select **Activate**.</span></span> <span data-ttu-id="4c9a0-154">Åsidosättningfilen blir omedelbart aktiv på din aktiva webbplats.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-154">The override file immediately becomes active on your live site.</span></span>

## <a name="deactivate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="4c9a0-155">Inaktivera en CSS åsidosättningfil på din aktiva webbplats</span><span class="sxs-lookup"><span data-stu-id="4c9a0-155">Deactivate a CSS override file on your live site</span></span>

<span data-ttu-id="4c9a0-156">Så här inaktiverar du en CSS åsidosättningfil på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-156">To deactivate a CSS override file on your site, follow these steps.</span></span>

1. <span data-ttu-id="4c9a0-157">I navigeringsfönstret till vänster väljer du **design** och sedan på fliken **CSS åsidosätt** under **tillgängliga CSS åsidosättningar**, leta upp CSS-filen som du vill inaktivera.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-157">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to deactivate.</span></span>
1. <span data-ttu-id="4c9a0-158">Under CSS filnamnet väljer du **inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-158">Under the CSS file name, select **Deactivate**.</span></span> <span data-ttu-id="4c9a0-159">Åsidosättningfilen blir omedelbart inaktiv på din aktiva webbplats.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-159">The override file immediately becomes inactive on your live site.</span></span>

> [!TIP]
> <span data-ttu-id="4c9a0-160">Om du vill komma åt ytterligare alternativ för CSS åsidosättningsfiler väljer du ellipsen (**...**) bredvid CSS-filnamnet.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-160">To access additional options for CSS override files, select the ellipsis (**...**) next to the CSS file name.</span></span> <span data-ttu-id="4c9a0-161">Alternativen **Hämta**, **Byt namn** och **Ersätt** är användbara för snabba ändringar i en befintlig CSS åsidosättningfil.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-161">The **Download**, **Rename**, and **Replace** options are useful for quick changes to an existing CSS override file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4c9a0-162">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4c9a0-162">Additional resources</span></span>

[<span data-ttu-id="4c9a0-163">Lägg till en logotyp</span><span class="sxs-lookup"><span data-stu-id="4c9a0-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="4c9a0-164">Välj ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="4c9a0-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="4c9a0-165">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="4c9a0-165">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="4c9a0-166">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="4c9a0-166">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="4c9a0-167">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="4c9a0-167">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="4c9a0-168">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="4c9a0-168">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="4c9a0-169">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="4c9a0-169">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)
