---
title: Konfigurera valfria funktioner för en bedömningsmiljö för Dynamics 365 Commerce
description: Detta ämne förklarar hur du konfigurerar valfria funktioner för bedömningsmiljö för Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6bc968c2659380bb8c92292ee19e3a7ec8a20a2b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795917"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="949c4-103">Konfigurera valfria funktioner för en Dynamics 365 Commerce utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="949c4-103">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="949c4-104">Detta ämne förklarar hur du konfigurerar valfria funktioner för bedömningsmiljö för Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="949c4-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="949c4-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="949c4-105">Prerequisites</span></span>

<span data-ttu-id="949c4-106">Följande förutsättningar måste uppfyllas om du vill utvärdera e-postfunktionerna för transaktion:</span><span class="sxs-lookup"><span data-stu-id="949c4-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="949c4-107">Du kan ha en tillgänglig e-postserver (Simple Mail Transfer Protocol \[SMTP\]- server) som kan användas från Microsoft Azure-prenumeration där du tillhandahåller bedömningsmiljö.</span><span class="sxs-lookup"><span data-stu-id="949c4-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the evaluation environment.</span></span>
- <span data-ttu-id="949c4-108">Du har serverns fullt kvalificerade domännamn (FQDN)-/IP-nummer, SMTP-portnummer och autentiseringsinformation.</span><span class="sxs-lookup"><span data-stu-id="949c4-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="949c4-109">Konfigurera bildserver</span><span class="sxs-lookup"><span data-stu-id="949c4-109">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="949c4-110">Hitta din mediebas-URL</span><span class="sxs-lookup"><span data-stu-id="949c4-110">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="949c4-111">Innan du kan slutföra den här proceduren måste du slutföra stegen i [konfigurera din webbplats i Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="949c4-111">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="949c4-112">Logga in på verktyget Commerce webbplatsskaparen med hjälp av den URL som du antecknade när du initierade näthandel under etableringen (se [initiera näthandel](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="949c4-112">Sign in to the Commerce site builder by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="949c4-113">Öppna webbplatsen **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="949c4-113">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="949c4-114">I menyn till vänster, välj **Mediebibliotek**.</span><span class="sxs-lookup"><span data-stu-id="949c4-114">On the menu on the left, select **Media Library**.</span></span>
1. <span data-ttu-id="949c4-115">Markera en enskild bildtillgång.</span><span class="sxs-lookup"><span data-stu-id="949c4-115">Select any single image asset.</span></span>
1. <span data-ttu-id="949c4-116">Hitta egenskapen i egenskapsinspektören till höger **offentlig URL**.</span><span class="sxs-lookup"><span data-stu-id="949c4-116">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="949c4-117">Värdet är en URL.</span><span class="sxs-lookup"><span data-stu-id="949c4-117">The value is a URL.</span></span> <span data-ttu-id="949c4-118">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="949c4-118">Here is an example:</span></span>

    <span data-ttu-id="949c4-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="949c4-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="949c4-120">Ersätt den sista identifieraren i URL:en (**MA1nQC** i exemplet ovan) med strängen **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="949c4-120">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="949c4-121">Här är vad exempel-URL ser ut efter denna ändring görs:</span><span class="sxs-lookup"><span data-stu-id="949c4-121">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="949c4-122">Den här URL:en är din mediebas-URL.</span><span class="sxs-lookup"><span data-stu-id="949c4-122">This URL is your media base URL.</span></span> <span data-ttu-id="949c4-123">Anteckna det.</span><span class="sxs-lookup"><span data-stu-id="949c4-123">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="949c4-124">Uppdatera mediebas-URL</span><span class="sxs-lookup"><span data-stu-id="949c4-124">Update the media base URL</span></span>

1. <span data-ttu-id="949c4-125">Logga in på Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="949c4-125">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="949c4-126">Med hjälp av menyn till vänster, gå till **Moduler \> Retail och Commerce \> Kanalinställning \> Kanalprofiler**.</span><span class="sxs-lookup"><span data-stu-id="949c4-126">Use the menu on the left to go to **Modules \> Retail and commerce \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="949c4-127">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="949c4-127">Select **Edit**.</span></span>
1. <span data-ttu-id="949c4-128">Under **Profilegenskaper**, ersätt värdet för egenskapen **Medieserverbas-URL** med den mediebas-URL du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="949c4-128">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="949c4-129">Välj kanalen med namnet **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="949c4-129">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="949c4-130">Under **Profilegenskaper**, klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="949c4-130">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="949c4-131">För egenskapen som har lagts till väljer du **medieserverns bas-URL** som egenskapsnyckel.</span><span class="sxs-lookup"><span data-stu-id="949c4-131">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="949c4-132">Ange den mediebas-URL som du skapade tidigare som egenskapsvärde.</span><span class="sxs-lookup"><span data-stu-id="949c4-132">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="949c4-133">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="949c4-133">Select **Save**.</span></span>

## <a name="configure-and-test-the-email-server"></a><span data-ttu-id="949c4-134">Konfigurera och testa e-postserver</span><span class="sxs-lookup"><span data-stu-id="949c4-134">Configure and test the email server</span></span>

> [!NOTE]
> <span data-ttu-id="949c4-135">SMTP-servern eller e-posttjänsten som du anger här måste vara tillgänglig från den Azure-prenumeration du använder för miljön.</span><span class="sxs-lookup"><span data-stu-id="949c4-135">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="949c4-136">Logga in på Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="949c4-136">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="949c4-137">Använd menyn till vänster, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> Parametrar \> E-postparametrar**.</span><span class="sxs-lookup"><span data-stu-id="949c4-137">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Email parameters**.</span></span>
1. <span data-ttu-id="949c4-138">På fliken **SMTP-inställningar** i fältet **utgående e-postserver** anger du FQDN- eller IP-adressen för SMTP-servern eller e-posttjänsten.</span><span class="sxs-lookup"><span data-stu-id="949c4-138">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="949c4-139">Ange **SMTP-portnummer** anger du portnumret.</span><span class="sxs-lookup"><span data-stu-id="949c4-139">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="949c4-140">(Om du inte använder Secure Sockets Layer \[SSL\], är standardportnumret **25**.)</span><span class="sxs-lookup"><span data-stu-id="949c4-140">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="949c4-141">Om autentisering krävs anger du värden i fälten **användarnamn** och **lösenord**.</span><span class="sxs-lookup"><span data-stu-id="949c4-141">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="949c4-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="949c4-142">Select **Save**.</span></span>
1. <span data-ttu-id="949c4-143">Välj **uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="949c4-143">Select **Refresh**.</span></span>
1. <span data-ttu-id="949c4-144">På fliken **testa e-post** i fältet **e-postleverantör** väljer du **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="949c4-144">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="949c4-145">I fältet **Skicka till** ange e-postadressen där du vill att testmeddelandet ska levereras.</span><span class="sxs-lookup"><span data-stu-id="949c4-145">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="949c4-146">Välj **Skicka testmeddelande**.</span><span class="sxs-lookup"><span data-stu-id="949c4-146">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="949c4-147">Konfigurera e-postmallar</span><span class="sxs-lookup"><span data-stu-id="949c4-147">Configure email templates</span></span>

<span data-ttu-id="949c4-148">För varje transaktionshändelse som du vill skicka e-post till måste du uppdatera e-postmallen med en giltig e-postadress till avsändaren.</span><span class="sxs-lookup"><span data-stu-id="949c4-148">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="949c4-149">Logga in på Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="949c4-149">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="949c4-150">Använd menyn till vänster, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar**.</span><span class="sxs-lookup"><span data-stu-id="949c4-150">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="949c4-151">Välj **Visa lista**.</span><span class="sxs-lookup"><span data-stu-id="949c4-151">Select **Show list**.</span></span>
1. <span data-ttu-id="949c4-152">Följ dessa steg i listan för varje mall:</span><span class="sxs-lookup"><span data-stu-id="949c4-152">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="949c4-153">I fälten **avsändarens e-postadress**, ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="949c4-153">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="949c4-154">Valfritt: I fältet **Avsändarens namn** ange namnet som ska användas som avsändarnamn.</span><span class="sxs-lookup"><span data-stu-id="949c4-154">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="949c4-155">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="949c4-155">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="949c4-156">Anpassa e-postmallar</span><span class="sxs-lookup"><span data-stu-id="949c4-156">Customize email templates</span></span>

<span data-ttu-id="949c4-157">Du kanske vill anpassa e-postmallarna så att de använder olika bilder.</span><span class="sxs-lookup"><span data-stu-id="949c4-157">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="949c4-158">Eller så kanske du vill uppdatera länkarna i mallarna så att de går till din bedömningsmiljö.</span><span class="sxs-lookup"><span data-stu-id="949c4-158">Or you might want to update the links in the templates so that they go to your evaluation environment.</span></span> <span data-ttu-id="949c4-159">Den här proceduren förklarar hur du hämtar standardmallarna, anpassar dem och uppdaterar mallarna i systemet.</span><span class="sxs-lookup"><span data-stu-id="949c4-159">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="949c4-160">Med hjälp av en webbläsare, hämta [Microsoft Dynamics 365 Commerce utvärdering av standard e-postmallar .zip-fil](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) till den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="949c4-160">In a web browser, download the [Microsoft Dynamics 365 Commerce Evaluation default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="949c4-161">Den här filen innehåller följande HTML-dokument:</span><span class="sxs-lookup"><span data-stu-id="949c4-161">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="949c4-162">Orderbekräftelsemall</span><span class="sxs-lookup"><span data-stu-id="949c4-162">Order confirmation template</span></span>
    - <span data-ttu-id="949c4-163">Utfärda presentkortsmall</span><span class="sxs-lookup"><span data-stu-id="949c4-163">Issue gift card template</span></span>
    - <span data-ttu-id="949c4-164">Ny ordermall</span><span class="sxs-lookup"><span data-stu-id="949c4-164">New order template</span></span>
    - <span data-ttu-id="949c4-165">Förpackningsordermall</span><span class="sxs-lookup"><span data-stu-id="949c4-165">Pack order template</span></span>
    - <span data-ttu-id="949c4-166">Hämta förpackningsordermall</span><span class="sxs-lookup"><span data-stu-id="949c4-166">Pick order template</span></span>

1. <span data-ttu-id="949c4-167">Anpassa mallarna med hjälp av en text- eller HTML-redigerare.</span><span class="sxs-lookup"><span data-stu-id="949c4-167">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="949c4-168">Se listan över [token som stöds](#supported-tokens-in-the-email-template) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="949c4-168">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="949c4-169">Logga in på Commerce.</span><span class="sxs-lookup"><span data-stu-id="949c4-169">Sign in to Commerce.</span></span>
1. <span data-ttu-id="949c4-170">Med hjälp av menyn till vänster, gå till **Moduler \> Organisationsadministration \> Inställning \> E-postmall för organisation**.</span><span class="sxs-lookup"><span data-stu-id="949c4-170">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="949c4-171">Expandera listan till vänster om du vill se alla mallar.</span><span class="sxs-lookup"><span data-stu-id="949c4-171">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="949c4-172">Gör så här för varje mall som du vill anpassa:</span><span class="sxs-lookup"><span data-stu-id="949c4-172">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="949c4-173">Välj mallen i listan.</span><span class="sxs-lookup"><span data-stu-id="949c4-173">Select the template in the list.</span></span>
    1. <span data-ttu-id="949c4-174">Under **Innehåll i e-postmeddelande**, välj lämplig språkversion från listan.</span><span class="sxs-lookup"><span data-stu-id="949c4-174">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="949c4-175">(Standardspråk är **en-us**.)</span><span class="sxs-lookup"><span data-stu-id="949c4-175">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="949c4-176">Under **Innehåll i e-postmeddelande**, välj **redigera**.</span><span class="sxs-lookup"><span data-stu-id="949c4-176">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="949c4-177">Fönstret **överför e-postmall** visas.</span><span class="sxs-lookup"><span data-stu-id="949c4-177">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="949c4-178">Välj **bläddra** och leta reda på HTML-filen med det anpassade innehållet.</span><span class="sxs-lookup"><span data-stu-id="949c4-178">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="949c4-179">Välj **överför**.</span><span class="sxs-lookup"><span data-stu-id="949c4-179">Select **Upload**.</span></span> <span data-ttu-id="949c4-180">Mallen överförs till systemet och en förhandsversion visas.</span><span class="sxs-lookup"><span data-stu-id="949c4-180">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="949c4-181">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="949c4-181">Select **OK**.</span></span>
    1. <span data-ttu-id="949c4-182">Valfritt: Anpassa egenskapen **ämne** för mallen.</span><span class="sxs-lookup"><span data-stu-id="949c4-182">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="949c4-183">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="949c4-183">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="949c4-184">Variabler som stöds i e-postmallen</span><span class="sxs-lookup"><span data-stu-id="949c4-184">Supported tokens in the email template</span></span>

<span data-ttu-id="949c4-185">När e-postmeddelandet återges ersätts dessa tokens med faktiska värden som gäller för kunden och kundens beställning.</span><span class="sxs-lookup"><span data-stu-id="949c4-185">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="949c4-186">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="949c4-186">Sales order</span></span>

<span data-ttu-id="949c4-187">Följande token gäller för den övergripande försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="949c4-187">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="949c4-188">Namn på token</span><span class="sxs-lookup"><span data-stu-id="949c4-188">Name of the token</span></span> | <span data-ttu-id="949c4-189">Token</span><span class="sxs-lookup"><span data-stu-id="949c4-189">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="949c4-190">Ordernummer</span><span class="sxs-lookup"><span data-stu-id="949c4-190">Order number</span></span>      | <span data-ttu-id="949c4-191">%salesid%</span><span class="sxs-lookup"><span data-stu-id="949c4-191">%salesid%</span></span> |
| <span data-ttu-id="949c4-192">Kundnamn</span><span class="sxs-lookup"><span data-stu-id="949c4-192">Customer's name</span></span>   | <span data-ttu-id="949c4-193">%customername%</span><span class="sxs-lookup"><span data-stu-id="949c4-193">%customername%</span></span> |
| <span data-ttu-id="949c4-194">Leveransadress</span><span class="sxs-lookup"><span data-stu-id="949c4-194">Delivery address</span></span>  | <span data-ttu-id="949c4-195">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="949c4-195">%deliveryaddress%</span></span> |
| <span data-ttu-id="949c4-196">Faktureringsadress</span><span class="sxs-lookup"><span data-stu-id="949c4-196">Billing address</span></span>   | <span data-ttu-id="949c4-197">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="949c4-197">%customeraddress%</span></span> |
| <span data-ttu-id="949c4-198">Orderdatum</span><span class="sxs-lookup"><span data-stu-id="949c4-198">Order date</span></span>        | <span data-ttu-id="949c4-199">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="949c4-199">%shipdate%</span></span> |
| <span data-ttu-id="949c4-200">Leveransläge</span><span class="sxs-lookup"><span data-stu-id="949c4-200">Delivery mode</span></span>     | <span data-ttu-id="949c4-201">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="949c4-201">%modeofdelivery%</span></span> |
| <span data-ttu-id="949c4-202">Rabatt</span><span class="sxs-lookup"><span data-stu-id="949c4-202">Discount</span></span>          | <span data-ttu-id="949c4-203">%discount%</span><span class="sxs-lookup"><span data-stu-id="949c4-203">%discount%</span></span> |
| <span data-ttu-id="949c4-204">Moms</span><span class="sxs-lookup"><span data-stu-id="949c4-204">Sales tax</span></span>         | <span data-ttu-id="949c4-205">%tax%</span><span class="sxs-lookup"><span data-stu-id="949c4-205">%tax%</span></span> |
| <span data-ttu-id="949c4-206">Ordersumma</span><span class="sxs-lookup"><span data-stu-id="949c4-206">Order total</span></span>       | <span data-ttu-id="949c4-207">%total%</span><span class="sxs-lookup"><span data-stu-id="949c4-207">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="949c4-208">Försäljningsrad</span><span class="sxs-lookup"><span data-stu-id="949c4-208">Sales line</span></span>

<span data-ttu-id="949c4-209">Följande token ersätts med värden för varje produkt i ordningen.</span><span class="sxs-lookup"><span data-stu-id="949c4-209">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="949c4-210">Placera token **produktlista – start** i början av HTML-blocket som upprepas för varje produkt och placera token **produktlista – slut** i slutet av blocket.</span><span class="sxs-lookup"><span data-stu-id="949c4-210">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="949c4-211">Namn på token</span><span class="sxs-lookup"><span data-stu-id="949c4-211">Name of the token</span></span>      | <span data-ttu-id="949c4-212">Token</span><span class="sxs-lookup"><span data-stu-id="949c4-212">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="949c4-213">Produktlista – start</span><span class="sxs-lookup"><span data-stu-id="949c4-213">Product list - start</span></span>   | \<!--%tablebegin.salesline% --\> |
| <span data-ttu-id="949c4-214">Produktlista – slut</span><span class="sxs-lookup"><span data-stu-id="949c4-214">Product list - end</span></span>     | \<!--%tableend.salesline%--\> |
| <span data-ttu-id="949c4-215">Produktnamn</span><span class="sxs-lookup"><span data-stu-id="949c4-215">Product name</span></span>           | <span data-ttu-id="949c4-216">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="949c4-216">%lineproductname%</span></span> |
| <span data-ttu-id="949c4-217">beskrivning</span><span class="sxs-lookup"><span data-stu-id="949c4-217">Description</span></span>            | <span data-ttu-id="949c4-218">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="949c4-218">%lineproductdescription%</span></span> |
| <span data-ttu-id="949c4-219">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="949c4-219">Quantity</span></span>               | <span data-ttu-id="949c4-220">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="949c4-220">%linequantity%</span></span> |
| <span data-ttu-id="949c4-221">Pris för radenhet</span><span class="sxs-lookup"><span data-stu-id="949c4-221">Line unit price</span></span>        | <span data-ttu-id="949c4-222">%lineprice% (verifiera)</span><span class="sxs-lookup"><span data-stu-id="949c4-222">%lineprice% (verify)</span></span> |
| <span data-ttu-id="949c4-223">totalbelopp för radartikel</span><span class="sxs-lookup"><span data-stu-id="949c4-223">line item total</span></span>        | <span data-ttu-id="949c4-224">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="949c4-224">%linenetamount%</span></span> |
| <span data-ttu-id="949c4-225">radrabatt</span><span class="sxs-lookup"><span data-stu-id="949c4-225">line discount</span></span>          | <span data-ttu-id="949c4-226">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="949c4-226">%linediscount%</span></span> |
| <span data-ttu-id="949c4-227">Transportdatum</span><span class="sxs-lookup"><span data-stu-id="949c4-227">Ship date</span></span>              | <span data-ttu-id="949c4-228">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="949c4-228">%lineshipdate%</span></span> |
| <span data-ttu-id="949c4-229">Anskaffningsmetod</span><span class="sxs-lookup"><span data-stu-id="949c4-229">Procurement method</span></span>     | <span data-ttu-id="949c4-230">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="949c4-230">%linedeliverymode%</span></span> |
| <span data-ttu-id="949c4-231">leveransadress</span><span class="sxs-lookup"><span data-stu-id="949c4-231">delivery address</span></span>       | <span data-ttu-id="949c4-232">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="949c4-232">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="949c4-233">Försäljningsenhet för raden</span><span class="sxs-lookup"><span data-stu-id="949c4-233">Sales unit of the line</span></span> | <span data-ttu-id="949c4-234">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="949c4-234">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="949c4-235">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="949c4-235">Additional resources</span></span>

[<span data-ttu-id="949c4-236">Dynamics 365 Commerce bedömningsmiljö – översikt</span><span class="sxs-lookup"><span data-stu-id="949c4-236">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="949c4-237">Etablera en Dynamics 365 Commerce bedömningsmiljön</span><span class="sxs-lookup"><span data-stu-id="949c4-237">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="949c4-238">Konfigurera en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="949c4-238">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="949c4-239">Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="949c4-239">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="949c4-240">Dynamics 365 Commerce bedömningsmiljö – vanliga frågor</span><span class="sxs-lookup"><span data-stu-id="949c4-240">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="949c4-241">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="949c4-241">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="949c4-242">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="949c4-242">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="949c4-243">Microsoft Azure-portal</span><span class="sxs-lookup"><span data-stu-id="949c4-243">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="949c4-244">Dynamics 365 Commerce webbplatsen</span><span class="sxs-lookup"><span data-stu-id="949c4-244">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]