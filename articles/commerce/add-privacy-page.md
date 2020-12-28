---
title: Lägga till en sida med sekretesspolicy
description: I det här avsnittet beskrivs hur du lägger till en sida med sekretesspolicy till din webbplats i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: ce6491d176f90717877f084b11546010084c5f3b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415777"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="6dbb3-103">Lägga till en sida med sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="6dbb3-103">Add a privacy policy page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6dbb3-104">I det här avsnittet beskrivs hur du lägger till en sida med sekretesspolicy till din webbplats i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6dbb3-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="6dbb3-105">Overview</span></span>

<span data-ttu-id="6dbb3-106">Sekretessefterlevnad omfattar organisatoriska åtgärder som informerar webbplatsanvändarna om hur deras data samlas in och hanteras.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-106">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="6dbb3-107">Användarna kan sedan bestämma hur de vill att deras personuppgifter ska hanteras och kan vidta lämpliga åtgärder.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-107">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="6dbb3-108">Granska Microsofts sekretesspolicy i Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6dbb3-108">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="6dbb3-109">Om du vill granska Microsofts sekretesspolicy när du är inloggad på Dynamics 365 Commerce redigeringsverktygen väljer du knappen **hjälp** (**?**) i det övre högra hörnet och väljer sedan **sekretess och cookies**.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-109">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="6dbb3-110">En ny flik öppnas som har en länk till [Microsofts sekretesspolicy](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="6dbb3-110">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="6dbb3-111">Skapa en sekretesspolicysida för din webbplats</span><span class="sxs-lookup"><span data-stu-id="6dbb3-111">Build a privacy policy page for your site</span></span>

<span data-ttu-id="6dbb3-112">I Dynamics 365 Commerce finns det flera sätt att ge användare av din webbplats tillgång till din sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-112">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="6dbb3-113">Det här avsnittet visar hur du skapar en sekretesspolicysida och sedan referera till sidan med hjälp av ett sidfotavsnitt.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-113">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="6dbb3-114">Vägledningen som följer är ett exempel som visar hur du skapar en generisk sekretesspolicysida för en Commerce-webbplats.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-114">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="6dbb3-115">Du är ansvarig för att utforma och implementera en lösning för sekretesspolicysida som bäst uppfyller ditt företags juridiska krav.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-115">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="6dbb3-116">Starta i redigeringsverktyg, gå till den webbplats som du vill skapa en sekretesspolicysida för.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-116">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="6dbb3-117">Skapa en mall</span><span class="sxs-lookup"><span data-stu-id="6dbb3-117">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="6dbb3-118">Om en mall som kan användas för sekretesspolicysidan redan har skapats, gå vidare till avsnittet [skapa en sekretesspolicysida](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="6dbb3-118">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="6dbb3-119">Gör så här om du vill skapa en arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-119">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="6dbb3-120">Gå till **mallar** och välj sedan **ny** för att skapa en sidmall.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-120">Go to **Templates**, and then select **New** to create a page template.</span></span>
1. <span data-ttu-id="6dbb3-121">I dialogrutan **Ny mal** under **Mallnamn**, ange **annonsbanderollmall** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-121">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="6dbb3-122">I mallen lägger du till nödvändiga moduler till de obligatoriska sidfacken.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-122">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="6dbb3-123">För vägledning håller du muspekaren över de röda utropstecknen.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-123">For guidance, hover over the red exclamation marks.</span></span> <span data-ttu-id="6dbb3-124">(Till exempel facket **HTML-rubrik** kräver en **extern standardskript**-modul.)</span><span class="sxs-lookup"><span data-stu-id="6dbb3-124">(For example, the **HTML Head** slot might require a **Default External Script** module.)</span></span>
1. <span data-ttu-id="6dbb3-125">I facket **Brödtext**, lägg till en **standardsid**-modul.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-125">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="6dbb3-126">I **standardsid**-modulen, i facket **Huvud**, lägg till en **Innehållsrikt block**-modul.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-126">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="6dbb3-127">I **Innehållsrikt block**-modulen lägger du till en **innehållsrika blockobjekt**-modul.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-127">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="6dbb3-128">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-128">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="6dbb3-129">Skapa en sida med sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="6dbb3-129">Build a privacy policy page</span></span>

<span data-ttu-id="6dbb3-130">Gör så här om du vill skapa en sekretesspolicysida.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-130">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="6dbb3-131">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en sida.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-131">Go to **Pages**, and then select **New** to create a page.</span></span>
1. <span data-ttu-id="6dbb3-132">I dialogrutan **Välj en mall**, välj mallen för sidan för sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-132">In the **Choose a template** dialog box, select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="6dbb3-133">Ange ett sidnamn och en sid-URL och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-133">Enter a page name and page URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="6dbb3-134">Lägg till platsen **Huvud** på ny sida, lägg till en **innehållsrik block**-modul.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-134">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="6dbb3-135">I **Innehållsrikt block**-modulen lägger du till en **innehållsrika blockobjekt**-modul.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-135">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="6dbb3-136">I egenskapsfönstret för **innehållsrik block**-modulen, välj **Lägg till data källa** och välj sedan **RTF-innehåll**.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-136">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="6dbb3-137">I RTF-redigeraren anger du innehållet för sidan sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-137">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="6dbb3-138">Expandera RTF-redigeraren till helskärmsläge som du behöver.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-138">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="6dbb3-139">När du är klar med att ange innehåll väljer du **förhandsgranska** för att förhandsgranska sidan i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-139">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="6dbb3-140">Slutför eventuella återstående tillägg till sid- och modulegenskaperna.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-140">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="6dbb3-141">Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-141">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="6dbb3-142">För att publicera URL för sidan sekretesspolicy, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-142">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="6dbb3-143">Gå till **URL:er** och välj webbadressen till sidan sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-143">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="6dbb3-144">Välj **publicera** om du vill publicera den valda URL:en.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-144">Select **Publish** to publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="6dbb3-145">Skapa en länk till sidan sekretesspolicy i en sidfot</span><span class="sxs-lookup"><span data-stu-id="6dbb3-145">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="6dbb3-146">Du kan lägga till en länk till sidan sekretesspolicy till ett fragment.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-146">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="6dbb3-147">På så sätt kan du dela länken och uppdatera den över flera webbplatssidor genom att referera till fragmentet.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-147">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="6dbb3-148">I det här exemplet visas hur du lägger till en länk till sidan sekretesspolicy i ett sidfotavsnitt.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-148">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="6dbb3-149">Om du vill lägga till en länk till ett sidfotavsnitt gör du följande.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-149">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="6dbb3-150">Gå till **Fragment** och välj **ny** för att skapa ett sidfragment.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-150">Go to **Fragments**, and then select **New** to create a page fragment.</span></span>
1. <span data-ttu-id="6dbb3-151">I dialogrutan **Nytt fragment**, välj modulen **Sidfot**.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-151">In the **New fragment** dialog box, select the **Footer** module.</span></span>
1. <span data-ttu-id="6dbb3-152">Under **fragmentets namn**, anger du ett namn på fragmentet och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-152">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="6dbb3-153">I facket **Sidfotskategori**, lägg till en **sidfotsartikel**-modul.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-153">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="6dbb3-154">I egenskapsrutan till höger, välj egenskapen **Länktext**.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-154">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="6dbb3-155">I dialogrutan **länktext** anger du länktexten och länkmålet för sidan sekretesspolicy och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-155">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>
1. <span data-ttu-id="6dbb3-156">Om du vill hämta webbadressen till sidan sekretesspolicy går du till **sidor** går till sidan sekretesspolicy och kopierar webbadressen från fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-156">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>
1. <span data-ttu-id="6dbb3-157">Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-157">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="6dbb3-158">Förhandsgranska fragmentet och testa länken till sidan sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-158">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="6dbb3-159">Fragmentet kan nu refereras i mallen för andra webbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-159">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="6dbb3-160">När det här fragmentet refereras i **sidfoten** i en modul för en mall visas länkreferensen på alla sidor som har skapats med den mallen.</span><span class="sxs-lookup"><span data-stu-id="6dbb3-160">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6dbb3-161">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6dbb3-161">Additional resources</span></span>

[<span data-ttu-id="6dbb3-162">Regelefterlevnad – översikt</span><span class="sxs-lookup"><span data-stu-id="6dbb3-162">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="6dbb3-163">Hjälpmedelsfunktioner och möjligheter</span><span class="sxs-lookup"><span data-stu-id="6dbb3-163">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="6dbb3-164">Cookie-kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="6dbb3-164">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="6dbb3-165">Ersätt användar-ID:n som är associerade med spårade innehållsändringar</span><span class="sxs-lookup"><span data-stu-id="6dbb3-165">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)
