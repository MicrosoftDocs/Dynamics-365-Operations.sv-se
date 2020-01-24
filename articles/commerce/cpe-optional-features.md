---
title: Konfigurera valfria funktioner för en förhandsversionsmiljö för Commerce
description: Detta ämne förklarar hur du konfigurerar valfria funktioner för förhandsversionsmiljö för Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/10/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2c4872cdebc414eaa865af025237bd9e1d14bfd2
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906126"
---
# <a name="configure-optional-features-for-a-commerce-preview-environment"></a><span data-ttu-id="13660-103">Konfigurera valfria funktioner för en förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="13660-103">Configure optional features for a Commerce preview environment</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="13660-104">Detta ämne förklarar hur du konfigurerar valfria funktioner för förhandsversionsmiljö för Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="13660-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13660-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="13660-105">Prerequisites</span></span>

<span data-ttu-id="13660-106">Följande förutsättningar måste uppfyllas om du vill utvärdera e-postfunktionerna för transaktion:</span><span class="sxs-lookup"><span data-stu-id="13660-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="13660-107">Du kan ha en tillgänglig e-postserver (Simple Mail Transfer Protocol \[SMTP\]- server) som kan användas från Microsoft Azure-prenumeration där du tillhandahåller förhandsversionsmiljön.</span><span class="sxs-lookup"><span data-stu-id="13660-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the preview environment.</span></span>
- <span data-ttu-id="13660-108">Du har serverns fullt kvalificerade domännamn (FQDN)-/IP-nummer, SMTP-portnummer och autentiseringsinformation.</span><span class="sxs-lookup"><span data-stu-id="13660-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

<span data-ttu-id="13660-109">Om du vill utvärdera funktioner för hantering av digitala tillgångar genom att mata in nya flerkanalsbilder, måste du ha namnet på din CMS-klientorganisation (Content Management System) tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="13660-109">If you want to evaluate Digital Asset Management features by ingesting new omni-channel images, you must have the name of your content management system (CMS) tenant available.</span></span> <span data-ttu-id="13660-110">Instruktioner för att hitta det här namnet finns senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="13660-110">Instructions for finding this name are provided later in this topic.</span></span> <span data-ttu-id="13660-111">>>>(F: Var är instruktionerna?)</span><span class="sxs-lookup"><span data-stu-id="13660-111">>>>(Q: where are the instructions?)</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="13660-112">Konfigurera bildserver</span><span class="sxs-lookup"><span data-stu-id="13660-112">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="13660-113">Hitta din mediebas-URL</span><span class="sxs-lookup"><span data-stu-id="13660-113">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="13660-114">Innan du kan slutföra den här proceduren måste du slutföra stegen i [konfigurera din webbplats i Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="13660-114">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="13660-115">Logga in på verktyget Commerce site Management med hjälp av den URL som du antecknade när du initierade e-handel under etableringen (se [initiera e-handel](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="13660-115">Sign in to the Commerce site management tool by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="13660-116">Öppna webbplatsen **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="13660-116">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="13660-117">I menyn till vänster, välj **Tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="13660-117">On the menu on the left, select **Assets**.</span></span>
1. <span data-ttu-id="13660-118">Markera en enskild bildtillgång.</span><span class="sxs-lookup"><span data-stu-id="13660-118">Select any single image asset.</span></span>
1. <span data-ttu-id="13660-119">Hitta egenskapen i egenskapsinspektören till höger **offentlig URL**.</span><span class="sxs-lookup"><span data-stu-id="13660-119">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="13660-120">Värdet är en URL.</span><span class="sxs-lookup"><span data-stu-id="13660-120">The value is a URL.</span></span> <span data-ttu-id="13660-121">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="13660-121">Here is an example:</span></span>

    <span data-ttu-id="13660-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="13660-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="13660-123">Ersätt den sista identifieraren i URL:en (**MA1nQC** i exemplet ovan) med strängen **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="13660-123">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="13660-124">Här är vad exempel-URL ser ut efter denna ändring görs:</span><span class="sxs-lookup"><span data-stu-id="13660-124">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="13660-125">Den här URL:en är din mediebas-URL.</span><span class="sxs-lookup"><span data-stu-id="13660-125">This URL is your media base URL.</span></span> <span data-ttu-id="13660-126">Anteckna det.</span><span class="sxs-lookup"><span data-stu-id="13660-126">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="13660-127">Uppdatera mediebas-URL</span><span class="sxs-lookup"><span data-stu-id="13660-127">Update the media base URL</span></span>

1. <span data-ttu-id="13660-128">Logga in på Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="13660-128">Sign in to Dynamics 365 Retail.</span></span>
1. <span data-ttu-id="13660-129">Med hjälp av menyn till vänster, gå till **Moduler \> Butik \> Kanalinställning \> Kanalprofiler**.</span><span class="sxs-lookup"><span data-stu-id="13660-129">Use the menu on the left to go to **Modules \> Retail \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="13660-130">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="13660-130">Select **Edit**.</span></span>
1. <span data-ttu-id="13660-131">Under **Profilegenskaper**, ersätt värdet för egenskapen **Medieserverbas-URL** med den mediebas-URL du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="13660-131">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="13660-132">I listan till vänster, under kanalen **Standard** väljer du den andra kanalen.</span><span class="sxs-lookup"><span data-stu-id="13660-132">In the list on the left, under the **Default** channel, select the other channel.</span></span>
1. <span data-ttu-id="13660-133">Under **Profilegenskaper**, klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="13660-133">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="13660-134">För egenskapen som har lagts till väljer du **medieserverns bas-URL** som egenskapsnyckel.</span><span class="sxs-lookup"><span data-stu-id="13660-134">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="13660-135">Ange den mediebas-URL som du skapade tidigare som egenskapsvärde.</span><span class="sxs-lookup"><span data-stu-id="13660-135">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="13660-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="13660-136">Select **Save**.</span></span>

## <a name="configure-the-email-server"></a><span data-ttu-id="13660-137">Konfigurera e-postserver</span><span class="sxs-lookup"><span data-stu-id="13660-137">Configure the email server</span></span>

> [!NOTE]
> <span data-ttu-id="13660-138">SMTP-servern eller e-posttjänsten som du anger här måste vara tillgänglig från den Azure-prenumeration du använder för miljön.</span><span class="sxs-lookup"><span data-stu-id="13660-138">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="13660-139">Logga in på Retail.</span><span class="sxs-lookup"><span data-stu-id="13660-139">Sign in to Retail.</span></span>
1. <span data-ttu-id="13660-140">Använd menyn till vänster, gå till **Moduler \> Systemadministration \> Inställning \> E-post \> E-postparametrar**.</span><span class="sxs-lookup"><span data-stu-id="13660-140">Use the menu on the left to go to **Modules \> System administration \> Setup \> Email \> Email parameters**.</span></span>
1. <span data-ttu-id="13660-141">På fliken **SMTP-inställningar** i fältet **utgående e-postserver** anger du FQDN- eller IP-adressen för SMTP-servern eller e-posttjänsten.</span><span class="sxs-lookup"><span data-stu-id="13660-141">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="13660-142">Ange **SMTP-portnummer** anger du portnumret.</span><span class="sxs-lookup"><span data-stu-id="13660-142">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="13660-143">(Om du inte använder Secure Sockets Layer \[SSL\], är standardportnumret **25**.)</span><span class="sxs-lookup"><span data-stu-id="13660-143">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="13660-144">Om autentisering krävs anger du värden i fälten **användarnamn** och **lösenord**.</span><span class="sxs-lookup"><span data-stu-id="13660-144">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="13660-145">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="13660-145">Select **Save**.</span></span>
1. <span data-ttu-id="13660-146">Välj **uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="13660-146">Select **Refresh**.</span></span>
1. <span data-ttu-id="13660-147">På fliken **testa e-post** i fältet **e-postleverantör** väljer du **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="13660-147">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="13660-148">I fältet **Skicka till** ange e-postadressen där du vill att testmeddelandet ska levereras.</span><span class="sxs-lookup"><span data-stu-id="13660-148">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="13660-149">Välj **Skicka testmeddelande**.</span><span class="sxs-lookup"><span data-stu-id="13660-149">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="13660-150">Konfigurera e-postmallar</span><span class="sxs-lookup"><span data-stu-id="13660-150">Configure email templates</span></span>

<span data-ttu-id="13660-151">För varje transaktionshändelse som du vill skicka e-post till måste du uppdatera e-postmallen med en giltig e-postadress till avsändaren.</span><span class="sxs-lookup"><span data-stu-id="13660-151">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="13660-152">Logga in på Retail.</span><span class="sxs-lookup"><span data-stu-id="13660-152">Sign in to Retail.</span></span>
1. <span data-ttu-id="13660-153">Med hjälp av menyn till vänster, gå till **Moduler \> Organisationsadministration \> Inställning \> E-postmall för organisation**.</span><span class="sxs-lookup"><span data-stu-id="13660-153">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="13660-154">Välj **Visa lista**.</span><span class="sxs-lookup"><span data-stu-id="13660-154">Select **Show list**.</span></span>
1. <span data-ttu-id="13660-155">Följ dessa steg i listan för varje mall:</span><span class="sxs-lookup"><span data-stu-id="13660-155">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="13660-156">I fälten **avsändarens e-postadress**, ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="13660-156">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="13660-157">Valfritt: I fältet **Avsändarens namn** ange namnet som ska användas som avsändarnamn.</span><span class="sxs-lookup"><span data-stu-id="13660-157">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="13660-158">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="13660-158">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="13660-159">Anpassa e-postmallar</span><span class="sxs-lookup"><span data-stu-id="13660-159">Customize email templates</span></span>

<span data-ttu-id="13660-160">Du kanske vill anpassa e-postmallarna så att de använder olika bilder.</span><span class="sxs-lookup"><span data-stu-id="13660-160">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="13660-161">Eller så kanske du vill uppdatera länkarna i mallarna så att de går till din förhandsgranskningsmiljö.</span><span class="sxs-lookup"><span data-stu-id="13660-161">Or you might want to update the links in the templates so that they go to your preview environment.</span></span> <span data-ttu-id="13660-162">Den här proceduren förklarar hur du hämtar standardmallarna, anpassar dem och uppdaterar mallarna i systemet.</span><span class="sxs-lookup"><span data-stu-id="13660-162">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="13660-163">Med hjälp av en webbläsare, hämta [Microsoft Dynamics 365 Commerce förhandsversion av standard e-postmallar .zip-fil](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) till den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="13660-163">In a web browser, download the [Microsoft Dynamics 365 Commerce Preview default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="13660-164">Den här filen innehåller följande HTML-dokument:</span><span class="sxs-lookup"><span data-stu-id="13660-164">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="13660-165">Orderbekräftelsemall</span><span class="sxs-lookup"><span data-stu-id="13660-165">Order confirmation template</span></span>
    - <span data-ttu-id="13660-166">Utfärda presentkortsmall</span><span class="sxs-lookup"><span data-stu-id="13660-166">Issue gift card template</span></span>
    - <span data-ttu-id="13660-167">Ny ordermall</span><span class="sxs-lookup"><span data-stu-id="13660-167">New order template</span></span>
    - <span data-ttu-id="13660-168">Förpackningsordermall</span><span class="sxs-lookup"><span data-stu-id="13660-168">Pack order template</span></span>
    - <span data-ttu-id="13660-169">Hämta förpackningsordermall</span><span class="sxs-lookup"><span data-stu-id="13660-169">Pick order template</span></span>

1. <span data-ttu-id="13660-170">Anpassa mallarna med hjälp av en text- eller HTML-redigerare.</span><span class="sxs-lookup"><span data-stu-id="13660-170">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="13660-171">Se listan över [token som stöds](#supported-tokens-in-the-email-template) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="13660-171">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="13660-172">Logga in på Retail.</span><span class="sxs-lookup"><span data-stu-id="13660-172">Sign in to Retail.</span></span>
1. <span data-ttu-id="13660-173">Med hjälp av menyn till vänster, gå till **Moduler \> Organisationsadministration \> Inställning \> E-postmall för organisation**.</span><span class="sxs-lookup"><span data-stu-id="13660-173">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="13660-174">Expandera listan till vänster om du vill se alla mallar.</span><span class="sxs-lookup"><span data-stu-id="13660-174">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="13660-175">Gör så här för varje mall som du vill anpassa:</span><span class="sxs-lookup"><span data-stu-id="13660-175">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="13660-176">Välj mallen i listan.</span><span class="sxs-lookup"><span data-stu-id="13660-176">Select the template in the list.</span></span>
    1. <span data-ttu-id="13660-177">Under **Innehåll i e-postmeddelande**, välj lämplig språkversion från listan.</span><span class="sxs-lookup"><span data-stu-id="13660-177">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="13660-178">(Standardspråk är **en-us**.)</span><span class="sxs-lookup"><span data-stu-id="13660-178">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="13660-179">Under **Innehåll i e-postmeddelande**, välj **redigera**.</span><span class="sxs-lookup"><span data-stu-id="13660-179">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="13660-180">Fönstret **överför e-postmall** visas.</span><span class="sxs-lookup"><span data-stu-id="13660-180">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="13660-181">Välj **bläddra** och leta reda på HTML-filen med det anpassade innehållet.</span><span class="sxs-lookup"><span data-stu-id="13660-181">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="13660-182">Välj **överför**.</span><span class="sxs-lookup"><span data-stu-id="13660-182">Select **Upload**.</span></span> <span data-ttu-id="13660-183">Mallen överförs till systemet och en förhandsversion visas.</span><span class="sxs-lookup"><span data-stu-id="13660-183">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="13660-184">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="13660-184">Select **OK**.</span></span>
    1. <span data-ttu-id="13660-185">Valfritt: Anpassa egenskapen **ämne** för mallen.</span><span class="sxs-lookup"><span data-stu-id="13660-185">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="13660-186">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="13660-186">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="13660-187">Variabler som stöds i e-postmallen</span><span class="sxs-lookup"><span data-stu-id="13660-187">Supported tokens in the email template</span></span>

<span data-ttu-id="13660-188">När e-postmeddelandet återges ersätts dessa tokens med faktiska värden som gäller för kunden och kundens beställning.</span><span class="sxs-lookup"><span data-stu-id="13660-188">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="13660-189">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="13660-189">Sales order</span></span>

<span data-ttu-id="13660-190">Följande token gäller för den övergripande försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="13660-190">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="13660-191">Namn på token</span><span class="sxs-lookup"><span data-stu-id="13660-191">Name of the token</span></span> | <span data-ttu-id="13660-192">Token </span><span class="sxs-lookup"><span data-stu-id="13660-192">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="13660-193">Ordernummer</span><span class="sxs-lookup"><span data-stu-id="13660-193">Order number</span></span>      | <span data-ttu-id="13660-194">%salesid%</span><span class="sxs-lookup"><span data-stu-id="13660-194">%salesid%</span></span> |
| <span data-ttu-id="13660-195">Kundnamn</span><span class="sxs-lookup"><span data-stu-id="13660-195">Customer's name</span></span>   | <span data-ttu-id="13660-196">%customername%</span><span class="sxs-lookup"><span data-stu-id="13660-196">%customername%</span></span> |
| <span data-ttu-id="13660-197">Leveransadress</span><span class="sxs-lookup"><span data-stu-id="13660-197">Delivery address</span></span>  | <span data-ttu-id="13660-198">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="13660-198">%deliveryaddress%</span></span> |
| <span data-ttu-id="13660-199">Faktureringsadress</span><span class="sxs-lookup"><span data-stu-id="13660-199">Billing address</span></span>   | <span data-ttu-id="13660-200">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="13660-200">%customeraddress%</span></span> |
| <span data-ttu-id="13660-201">Orderdatum</span><span class="sxs-lookup"><span data-stu-id="13660-201">Order date</span></span>        | <span data-ttu-id="13660-202">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="13660-202">%shipdate%</span></span> |
| <span data-ttu-id="13660-203">Leveransläge</span><span class="sxs-lookup"><span data-stu-id="13660-203">Delivery mode</span></span>     | <span data-ttu-id="13660-204">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="13660-204">%modeofdelivery%</span></span> |
| <span data-ttu-id="13660-205">Rabatt</span><span class="sxs-lookup"><span data-stu-id="13660-205">Discount</span></span>          | <span data-ttu-id="13660-206">%discount%</span><span class="sxs-lookup"><span data-stu-id="13660-206">%discount%</span></span> |
| <span data-ttu-id="13660-207">Moms</span><span class="sxs-lookup"><span data-stu-id="13660-207">Sales tax</span></span>         | <span data-ttu-id="13660-208">%tax%</span><span class="sxs-lookup"><span data-stu-id="13660-208">%tax%</span></span> |
| <span data-ttu-id="13660-209">Ordersumma</span><span class="sxs-lookup"><span data-stu-id="13660-209">Order total</span></span>       | <span data-ttu-id="13660-210">%total%</span><span class="sxs-lookup"><span data-stu-id="13660-210">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="13660-211">Försäljningsrad</span><span class="sxs-lookup"><span data-stu-id="13660-211">Sales line</span></span>

<span data-ttu-id="13660-212">Följande token ersätts med värden för varje produkt i ordningen.</span><span class="sxs-lookup"><span data-stu-id="13660-212">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="13660-213">Placera token **produktlista - start** i början av HTML-blocket som upprepas för varje produkt och placera token **produktlista - slut** i slutet av blocket.</span><span class="sxs-lookup"><span data-stu-id="13660-213">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="13660-214">Namn på token</span><span class="sxs-lookup"><span data-stu-id="13660-214">Name of the token</span></span>      | <span data-ttu-id="13660-215">Token </span><span class="sxs-lookup"><span data-stu-id="13660-215">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="13660-216">Produktlista - start</span><span class="sxs-lookup"><span data-stu-id="13660-216">Product list - start</span></span>   | <span data-ttu-id="13660-217">\<!--%tablebegin.salesline% --\></span><span class="sxs-lookup"><span data-stu-id="13660-217">\<!--%tablebegin.salesline% --\></span></span> |
| <span data-ttu-id="13660-218">Produktlista - slut</span><span class="sxs-lookup"><span data-stu-id="13660-218">Product list - end</span></span>     | <span data-ttu-id="13660-219">\<!--%tableend.salesline%--\></span><span class="sxs-lookup"><span data-stu-id="13660-219">\<!--%tableend.salesline%--\></span></span> |
| <span data-ttu-id="13660-220">Produktnamn</span><span class="sxs-lookup"><span data-stu-id="13660-220">Product name</span></span>           | <span data-ttu-id="13660-221">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="13660-221">%lineproductname%</span></span> |
| <span data-ttu-id="13660-222">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="13660-222">Description</span></span>            | <span data-ttu-id="13660-223">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="13660-223">%lineproductdescription%</span></span> |
| <span data-ttu-id="13660-224">Antal</span><span class="sxs-lookup"><span data-stu-id="13660-224">Quantity</span></span>               | <span data-ttu-id="13660-225">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="13660-225">%linequantity%</span></span> |
| <span data-ttu-id="13660-226">Pris för radenhet</span><span class="sxs-lookup"><span data-stu-id="13660-226">Line unit price</span></span>        | <span data-ttu-id="13660-227">%lineprice% (verifiera)</span><span class="sxs-lookup"><span data-stu-id="13660-227">%lineprice% (verify)</span></span> |
| <span data-ttu-id="13660-228">totalbelopp för radartikel</span><span class="sxs-lookup"><span data-stu-id="13660-228">line item total</span></span>        | <span data-ttu-id="13660-229">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="13660-229">%linenetamount%</span></span> |
| <span data-ttu-id="13660-230">radrabatt</span><span class="sxs-lookup"><span data-stu-id="13660-230">line discount</span></span>          | <span data-ttu-id="13660-231">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="13660-231">%linediscount%</span></span> |
| <span data-ttu-id="13660-232">Transportdatum</span><span class="sxs-lookup"><span data-stu-id="13660-232">Ship date</span></span>              | <span data-ttu-id="13660-233">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="13660-233">%lineshipdate%</span></span> |
| <span data-ttu-id="13660-234">Anskaffningsmetod</span><span class="sxs-lookup"><span data-stu-id="13660-234">Procurement method</span></span>     | <span data-ttu-id="13660-235">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="13660-235">%linedeliverymode%</span></span> |
| <span data-ttu-id="13660-236">leveransadress</span><span class="sxs-lookup"><span data-stu-id="13660-236">delivery address</span></span>       | <span data-ttu-id="13660-237">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="13660-237">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="13660-238">Försäljningsenhet för raden</span><span class="sxs-lookup"><span data-stu-id="13660-238">Sales unit of the line</span></span> | <span data-ttu-id="13660-239">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="13660-239">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="13660-240">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="13660-240">Additional resources</span></span>

[<span data-ttu-id="13660-241">Förhandsversionsmiljö för Commerce – översikt</span><span class="sxs-lookup"><span data-stu-id="13660-241">Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="13660-242">Etablera en förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="13660-242">Provision a Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="13660-243">Konfigurera en förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="13660-243">Configure a Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="13660-244">Förhandsversionsmiljö för Commerce – vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="13660-244">Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="13660-245">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="13660-245">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="13660-246">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="13660-246">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="13660-247">Microsoft Azure-portal</span><span class="sxs-lookup"><span data-stu-id="13660-247">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="13660-248">Dynamics 365 Commerce webbplatsen</span><span class="sxs-lookup"><span data-stu-id="13660-248">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="13660-249">Hjälpresurser för Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="13660-249">Help resources for Dynamics 365 Retail</span></span>](../retail/index.md)
