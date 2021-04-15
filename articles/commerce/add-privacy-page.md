---
title: Lägga till en sida med sekretesspolicy
description: I det här avsnittet beskrivs hur du lägger till en sida med sekretesspolicy till din webbplats i Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 12cd0358279684ce1d3050348c37209ba3d29140
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797537"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="4d3e7-103">Lägga till en sida med sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="4d3e7-103">Add a privacy policy page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4d3e7-104">I det här avsnittet beskrivs hur du lägger till en sida med sekretesspolicy till din webbplats i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4d3e7-105">Sekretessefterlevnad omfattar organisatoriska åtgärder som informerar webbplatsanvändarna om hur deras data samlas in och hanteras.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-105">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="4d3e7-106">Användarna kan sedan bestämma hur de vill att deras personuppgifter ska hanteras och kan vidta lämpliga åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-106">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="4d3e7-107">Granska Microsofts sekretesspolicy i Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="4d3e7-107">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="4d3e7-108">Om du vill granska Microsofts sekretesspolicy när du är inloggad på Dynamics 365 Commerce redigeringsverktygen väljer du knappen **hjälp** (**?**) i det övre högra hörnet och väljer sedan **sekretess och cookies**.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-108">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="4d3e7-109">En ny flik öppnas som har en länk till [Microsofts sekretesspolicy](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="4d3e7-109">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="4d3e7-110">Skapa en sekretesspolicysida för din webbplats</span><span class="sxs-lookup"><span data-stu-id="4d3e7-110">Build a privacy policy page for your site</span></span>

<span data-ttu-id="4d3e7-111">I Dynamics 365 Commerce finns det flera sätt att ge användare av din webbplats tillgång till din sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-111">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="4d3e7-112">Det här avsnittet visar hur du skapar en sekretesspolicysida och sedan referera till sidan med hjälp av ett sidfotavsnitt.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-112">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="4d3e7-113">Vägledningen som följer är ett exempel som visar hur du skapar en generisk sekretesspolicysida för en Commerce-webbplats.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-113">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="4d3e7-114">Du är ansvarig för att utforma och implementera en lösning för sekretesspolicysida som bäst uppfyller ditt företags juridiska krav.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-114">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="4d3e7-115">Starta i redigeringsverktyg, gå till den webbplats som du vill skapa en sekretesspolicysida för.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-115">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="4d3e7-116">Skapa en mall</span><span class="sxs-lookup"><span data-stu-id="4d3e7-116">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="4d3e7-117">Om en mall som kan användas för sekretesspolicysidan redan har skapats, gå vidare till avsnittet [skapa en sekretesspolicysida](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="4d3e7-117">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="4d3e7-118">Gör så här om du vill skapa en arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-118">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="4d3e7-119">Gå till **mallar** och välj sedan **ny** för att skapa en sidmall.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-119">Go to **Templates**, and then select **New** to create a page template.</span></span>
1. <span data-ttu-id="4d3e7-120">I dialogrutan **Ny mal** under **Mallnamn**, ange **annonsbanderollmall** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-120">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="4d3e7-121">I mallen lägger du till nödvändiga moduler till de obligatoriska sidfacken.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-121">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="4d3e7-122">För vägledning håller du muspekaren över de röda utropstecknen.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-122">For guidance, hover over the red exclamation marks.</span></span> <span data-ttu-id="4d3e7-123">(Till exempel facket **HTML-rubrik** kräver en **extern standardskript**-modul.)</span><span class="sxs-lookup"><span data-stu-id="4d3e7-123">(For example, the **HTML Head** slot might require a **Default External Script** module.)</span></span>
1. <span data-ttu-id="4d3e7-124">I facket **Brödtext**, lägg till en **standardsid**-modul.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-124">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="4d3e7-125">I **standardsid**-modulen, i facket **Huvud**, lägg till en **Innehållsrikt block**-modul.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-125">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="4d3e7-126">I **Innehållsrikt block**-modulen lägger du till en **innehållsrika blockobjekt**-modul.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-126">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="4d3e7-127">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-127">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="4d3e7-128">Skapa en sida med sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="4d3e7-128">Build a privacy policy page</span></span>

<span data-ttu-id="4d3e7-129">Gör så här om du vill skapa en sekretesspolicysida.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-129">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="4d3e7-130">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en sida.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-130">Go to **Pages**, and then select **New** to create a page.</span></span>
1. <span data-ttu-id="4d3e7-131">I dialogrutan **Välj en mall**, välj mallen för sidan för sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-131">In the **Choose a template** dialog box, select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="4d3e7-132">Ange ett sidnamn och en sid-URL och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-132">Enter a page name and page URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="4d3e7-133">Lägg till platsen **Huvud** på ny sida, lägg till en **innehållsrik block**-modul.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-133">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="4d3e7-134">I **Innehållsrikt block**-modulen lägger du till en **innehållsrika blockobjekt**-modul.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-134">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="4d3e7-135">I egenskapsfönstret för **innehållsrik block**-modulen, välj **Lägg till data källa** och välj sedan **RTF-innehåll**.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-135">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="4d3e7-136">I RTF-redigeraren anger du innehållet för sidan sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-136">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="4d3e7-137">Expandera RTF-redigeraren till helskärmsläge som du behöver.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-137">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="4d3e7-138">När du är klar med att ange innehåll väljer du **förhandsgranska** för att förhandsgranska sidan i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-138">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="4d3e7-139">Slutför eventuella återstående tillägg till sid- och modulegenskaperna.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-139">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="4d3e7-140">Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-140">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="4d3e7-141">För att publicera URL för sidan sekretesspolicy, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-141">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="4d3e7-142">Gå till **URL:er** och välj webbadressen till sidan sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-142">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="4d3e7-143">Välj **publicera** om du vill publicera den valda URL:en.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-143">Select **Publish** to publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="4d3e7-144">Skapa en länk till sidan sekretesspolicy i en sidfot</span><span class="sxs-lookup"><span data-stu-id="4d3e7-144">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="4d3e7-145">Du kan lägga till en länk till sidan sekretesspolicy till ett fragment.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-145">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="4d3e7-146">På så sätt kan du dela länken och uppdatera den över flera webbplatssidor genom att referera till fragmentet.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-146">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="4d3e7-147">I det här exemplet visas hur du lägger till en länk till sidan sekretesspolicy i ett sidfotavsnitt.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-147">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="4d3e7-148">Om du vill lägga till en länk till ett sidfotavsnitt gör du följande.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-148">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="4d3e7-149">Gå till **Fragment** och välj **ny** för att skapa ett sidfragment.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-149">Go to **Fragments**, and then select **New** to create a page fragment.</span></span>
1. <span data-ttu-id="4d3e7-150">I dialogrutan **Nytt fragment**, välj modulen **Sidfot**.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-150">In the **New fragment** dialog box, select the **Footer** module.</span></span>
1. <span data-ttu-id="4d3e7-151">Under **fragmentets namn**, anger du ett namn på fragmentet och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-151">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="4d3e7-152">I facket **Sidfotskategori**, lägg till en **sidfotsartikel**-modul.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-152">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="4d3e7-153">I egenskapsrutan till höger, välj egenskapen **Länktext**.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-153">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="4d3e7-154">I dialogrutan **länktext** anger du länktexten och länkmålet för sidan sekretesspolicy och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-154">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>
1. <span data-ttu-id="4d3e7-155">Om du vill hämta webbadressen till sidan sekretesspolicy går du till **sidor** går till sidan sekretesspolicy och kopierar webbadressen från fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-155">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>
1. <span data-ttu-id="4d3e7-156">Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-156">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="4d3e7-157">Förhandsgranska fragmentet och testa länken till sidan sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-157">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="4d3e7-158">Fragmentet kan nu refereras i mallen för andra webbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-158">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="4d3e7-159">När det här fragmentet refereras i **sidfoten** i en modul för en mall visas länkreferensen på alla sidor som har skapats med den mallen.</span><span class="sxs-lookup"><span data-stu-id="4d3e7-159">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4d3e7-160">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4d3e7-160">Additional resources</span></span>

[<span data-ttu-id="4d3e7-161">Regelefterlevnad – översikt</span><span class="sxs-lookup"><span data-stu-id="4d3e7-161">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="4d3e7-162">Hjälpmedelsfunktioner och möjligheter</span><span class="sxs-lookup"><span data-stu-id="4d3e7-162">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="4d3e7-163">Cookie-kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="4d3e7-163">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="4d3e7-164">Ersätt användar-ID:n som är associerade med spårade innehållsändringar</span><span class="sxs-lookup"><span data-stu-id="4d3e7-164">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
