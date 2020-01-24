---
title: Lägga till en sida med sekretesspolicy
description: I det här avsnittet beskrivs hur du lägger till en sida med sekretesspolicy till din webbplats i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fd39ff5f8c5d97f2d524043b65627dc7e87fcf64
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946085"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="33c15-103">Lägga till en sida med sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="33c15-103">Add a privacy policy page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="33c15-104">I det här avsnittet beskrivs hur du lägger till en sida med sekretesspolicy till din webbplats i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="33c15-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="33c15-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="33c15-105">Overview</span></span>

<span data-ttu-id="33c15-106">Sekretessefterlevnad omfattar organisatoriska åtgärder som informerar webbplatsanvändarna om hur deras data samlas in och hanteras.</span><span class="sxs-lookup"><span data-stu-id="33c15-106">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="33c15-107">Användarna kan sedan bestämma hur de vill att deras personuppgifter ska hanteras och kan vidta lämpliga åtgärder.</span><span class="sxs-lookup"><span data-stu-id="33c15-107">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="33c15-108">Granska Microsofts sekretesspolicy i Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="33c15-108">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="33c15-109">Om du vill granska Microsofts sekretesspolicy när du är inloggad på Dynamics 365 Commerce redigeringsverktygen väljer du knappen **hjälp** (**?**) i det övre högra hörnet och väljer sedan **sekretess och cookies**.</span><span class="sxs-lookup"><span data-stu-id="33c15-109">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="33c15-110">En ny flik öppnas som har en länk till [Microsofts sekretesspolicy](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="33c15-110">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="33c15-111">Skapa en sekretesspolicysida för din webbplats</span><span class="sxs-lookup"><span data-stu-id="33c15-111">Build a privacy policy page for your site</span></span>

<span data-ttu-id="33c15-112">I Dynamics 365 Commerce finns det flera sätt att ge användare av din webbplats tillgång till din sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="33c15-112">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="33c15-113">Det här avsnittet visar hur du skapar en sekretesspolicysida och sedan referera till sidan med hjälp av ett sidfotavsnitt.</span><span class="sxs-lookup"><span data-stu-id="33c15-113">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="33c15-114">Vägledningen som följer är ett exempel som visar hur du skapar en generisk sekretesspolicysida för en Commerce-webbplats.</span><span class="sxs-lookup"><span data-stu-id="33c15-114">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="33c15-115">Du är ansvarig för att utforma och implementera en lösning för sekretesspolicysida som bäst uppfyller ditt företags juridiska krav.</span><span class="sxs-lookup"><span data-stu-id="33c15-115">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="33c15-116">Starta i redigeringsverktyg, gå till den webbplats som du vill skapa en sekretesspolicysida för.</span><span class="sxs-lookup"><span data-stu-id="33c15-116">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="33c15-117">Skapa en mall</span><span class="sxs-lookup"><span data-stu-id="33c15-117">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="33c15-118">Om en mall som kan användas för sekretesspolicysidan redan har skapats, gå vidare till avsnittet [skapa en sekretesspolicysida](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="33c15-118">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="33c15-119">Gör så här om du vill skapa en arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="33c15-119">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="33c15-120">Gå till **Mallar \> Ny mall**.</span><span class="sxs-lookup"><span data-stu-id="33c15-120">Go to **Templates \> New Template**.</span></span>
1. <span data-ttu-id="33c15-121">Ange mallnamn och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="33c15-121">Enter the template name, and then select **OK**.</span></span>
1. <span data-ttu-id="33c15-122">I mallen lägger du till nödvändiga moduler till de obligatoriska sidfacken.</span><span class="sxs-lookup"><span data-stu-id="33c15-122">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="33c15-123">För vägledning håller du muspekaren över de röda utropstecknen.</span><span class="sxs-lookup"><span data-stu-id="33c15-123">For guidance, hover over the red exclamation marks.</span></span>

    <span data-ttu-id="33c15-124">Till exempe facket **HTML-rubrik** kräver en **extern standardskript**-modul.</span><span class="sxs-lookup"><span data-stu-id="33c15-124">For example, the **HTML Head** slot might require a **Default External Script** module.</span></span>

1. <span data-ttu-id="33c15-125">I facket **Brödtext**, lägg till en **standardsid**-modul.</span><span class="sxs-lookup"><span data-stu-id="33c15-125">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="33c15-126">I **standardsid**-modulen, i facket **Huvud**, lägg till en **Innehållsrikt block**-modul.</span><span class="sxs-lookup"><span data-stu-id="33c15-126">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="33c15-127">I **Innehållsrikt block**-modulen lägger du till en **innehållsrika blockobjekt**-modul.</span><span class="sxs-lookup"><span data-stu-id="33c15-127">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="33c15-128">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="33c15-128">Check the template in, and publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="33c15-129">Skapa en sida med sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="33c15-129">Build a privacy policy page</span></span>

<span data-ttu-id="33c15-130">Gör så här om du vill skapa en sekretesspolicysida.</span><span class="sxs-lookup"><span data-stu-id="33c15-130">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="33c15-131">Gå till **Sidor \> Ny sida**.</span><span class="sxs-lookup"><span data-stu-id="33c15-131">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="33c15-132">Välj mallen för sidan sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="33c15-132">Select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="33c15-133">Ange ett sidnamn och en URL och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="33c15-133">Enter a page name and URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="33c15-134">Lägg till platsen **Huvud** på ny sida, lägg till en **innehållsrik block**-modul.</span><span class="sxs-lookup"><span data-stu-id="33c15-134">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="33c15-135">I **Innehållsrikt block**-modulen lägger du till en **innehållsrika blockobjekt**-modul.</span><span class="sxs-lookup"><span data-stu-id="33c15-135">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="33c15-136">I egenskapsfönstret för **innehållsrik block**-modulen, välj **Lägg till data källa** och välj sedan **RTF-innehåll**.</span><span class="sxs-lookup"><span data-stu-id="33c15-136">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="33c15-137">I RTF-redigeraren anger du innehållet för sidan sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="33c15-137">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="33c15-138">Expandera RTF-redigeraren till helskärmsläge som du behöver.</span><span class="sxs-lookup"><span data-stu-id="33c15-138">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="33c15-139">När du är klar med att ange innehåll väljer du **förhandsgranska** för att förhandsgranska sidan i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="33c15-139">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="33c15-140">Slutför eventuella återstående tillägg till sid- och modulegenskaperna.</span><span class="sxs-lookup"><span data-stu-id="33c15-140">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="33c15-141">Checka in sidan sekretesspolicy och publicera den.</span><span class="sxs-lookup"><span data-stu-id="33c15-141">Check the privacy policy page in, and publish it.</span></span>

<span data-ttu-id="33c15-142">För att publicera URL för sidan sekretesspolicy, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="33c15-142">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="33c15-143">Gå till **URL:er** och välj webbadressen till sidan sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="33c15-143">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="33c15-144">Publicera markerade URL.</span><span class="sxs-lookup"><span data-stu-id="33c15-144">Publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="33c15-145">Skapa en länk till sidan sekretesspolicy i en sidfot</span><span class="sxs-lookup"><span data-stu-id="33c15-145">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="33c15-146">Du kan lägga till en länk till sidan sekretesspolicy till ett fragment.</span><span class="sxs-lookup"><span data-stu-id="33c15-146">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="33c15-147">På så sätt kan du dela länken och uppdatera den över flera webbplatssidor genom att referera till fragmentet.</span><span class="sxs-lookup"><span data-stu-id="33c15-147">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="33c15-148">I det här exemplet visas hur du lägger till en länk till sidan sekretesspolicy i ett sidfotavsnitt.</span><span class="sxs-lookup"><span data-stu-id="33c15-148">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="33c15-149">Om du vill lägga till en länk till ett sidfotavsnitt gör du följande.</span><span class="sxs-lookup"><span data-stu-id="33c15-149">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="33c15-150">Gå till **Sidfragment \> Nytt sidfragment**.</span><span class="sxs-lookup"><span data-stu-id="33c15-150">Go to **Page Fragments \> New Page Fragment**.</span></span>
1. <span data-ttu-id="33c15-151">Markera **sidfot**-modulen och ange sedan ett namn i fältet **sidfragmentets namn**.</span><span class="sxs-lookup"><span data-stu-id="33c15-151">Select the **Footer** module, and then enter a name in the **Page Fragment Name** field.</span></span>
1. <span data-ttu-id="33c15-152">I facket **Sidfotskategori**, lägg till en **sidfotsartikel**-modul.</span><span class="sxs-lookup"><span data-stu-id="33c15-152">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="33c15-153">I egenskapsrutan till höger, välj egenskapen **Länktext**.</span><span class="sxs-lookup"><span data-stu-id="33c15-153">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="33c15-154">I dialogrutan **länktext** anger du länktexten och länkmålet för sidan sekretesspolicy och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="33c15-154">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>

    <span data-ttu-id="33c15-155">Om du vill hämta webbadressen till sidan sekretesspolicy går du till **sidor** går till sidan sekretesspolicy och kopierar webbadressen från fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="33c15-155">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>

1. <span data-ttu-id="33c15-156">Spara fragmentet, checka in det och publicera det.</span><span class="sxs-lookup"><span data-stu-id="33c15-156">Save the fragment, check it in, and publish it.</span></span>
1. <span data-ttu-id="33c15-157">Förhandsgranska fragmentet och testa länken till sidan sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="33c15-157">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="33c15-158">Fragmentet kan nu refereras i mallen för andra webbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="33c15-158">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="33c15-159">När det här fragmentet refereras i **sidfoten** i en modul för en mall visas länkreferensen på alla sidor som har skapats med den mallen.</span><span class="sxs-lookup"><span data-stu-id="33c15-159">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33c15-160">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="33c15-160">Additional resources</span></span>

[<span data-ttu-id="33c15-161">Regelefterlevnad – översikt</span><span class="sxs-lookup"><span data-stu-id="33c15-161">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="33c15-162">Hjälpmedelsfunktioner</span><span class="sxs-lookup"><span data-stu-id="33c15-162">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="33c15-163">Cookie-kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="33c15-163">Cookie compliance</span></span>](cookie-compliance.md)