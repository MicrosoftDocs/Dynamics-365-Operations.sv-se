---
title: Konfigurera e-postinställningar i Microsoft Dynamics 365 for Talent - Attract
description: I det här avsnittet beskrivs hur du konfigurerar inställningar för e-post som skickas av Microsoft Dynamcis 365 för Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: a8cf59064dd2f66ee50a0b0566aa712ba1f72dea
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739505"
---
# <a name="configure-email-settings"></a><span data-ttu-id="5ad8a-103">Konfigurera e-postinställningar</span><span class="sxs-lookup"><span data-stu-id="5ad8a-103">Configure email settings</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="5ad8a-104">Ditt varumärke etablerar förtroende och hjälper dig att skapa en relation med kandidater innan de ens kan användas för dina befattningar.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-104">Your brand establishes trust and helps you build a relationship with candidates before they even apply for your positions.</span></span> <span data-ttu-id="5ad8a-105">Positiv varumärkesuppfattning attraherar de bästa talangerna och ökar lojaliteten för befintliga medarbetare.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-105">Positive brand perception attracts top talent and increases the loyalty of existing employees.</span></span> <span data-ttu-id="5ad8a-106">Microsoft Dynamics 365 for Talent: Med Attract kan du konfigurera e-postmeddelanden så att de avspeglar företagets varumärke.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-106">Microsoft Dynamics 365 for Talent: Attract lets you configure emails so that they reflect your company's brand.</span></span> <span data-ttu-id="5ad8a-107">Därför kan du ge en konsekvent upplevelse för jobbsökande när de fortskrider genom ansökningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-107">Therefore, you can provide a consistent experience to job candidates as they progress through the application process.</span></span>

<span data-ttu-id="5ad8a-108">Med Attract kan du utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="5ad8a-108">Attract lets you perform these actions:</span></span>

- <span data-ttu-id="5ad8a-109">Konfigurera e-postinställningar så att ditt företags konto för e-posttjänst i Microsoft Exchange används.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-109">Configure email settings so that your company's Microsoft Exchange email service account is used.</span></span> <span data-ttu-id="5ad8a-110">På så sätt vet kandidater att e-postmeddelandena kommer från ditt företag.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-110">In this way, candidates know that the emails are coming from your company.</span></span> <span data-ttu-id="5ad8a-111">Du kan till exempel konfigurera dina inställningar så att sökande får e-postmeddelanden från `recruiting@contoso.com` i stället för `contoso@microsoft.com`.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-111">For example, you can configure your settings so that candidates receive emails from `recruiting@contoso.com` instead of `contoso@microsoft.com`.</span></span>
- <span data-ttu-id="5ad8a-112">Skapa konsekvent profilering för alla e-postmeddelanden genom att ställa in globalt sidhuvud och sidfot för alla e-postmallar.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-112">Create consistent branding for all your email communications by setting a global header and footer for email templates.</span></span> 

> [!NOTE]
> <span data-ttu-id="5ad8a-113">Om du vill konfigurera Attract så att det använder ditt företags e-postkonto för att skicka e-post, behöver du tillägget för omfattande anställning.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-113">To configure Attract so that it uses your company's email service account to send email, you need the Comprehensive hiring add-on.</span></span>

## <a name="connect-an-email-service-account"></a><span data-ttu-id="5ad8a-114">Anslut ett konto för e-posttjänst</span><span class="sxs-lookup"><span data-stu-id="5ad8a-114">Connect an email service account</span></span>

<span data-ttu-id="5ad8a-115">Genom att ansluta företagets konto för e-posttjänst kan du skapa en varumärkesanpassad e-postupplevelse för dina jobbkandidater.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-115">By connecting your company's email service account, you can create a branded email experience for your job candidates.</span></span> <span data-ttu-id="5ad8a-116">Om du inte ansluter ditt företagskonto använder Attract Microsofts standardinställda varumärkesanpassade e-posttjänstkonto.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-116">If you don't connect your company account, Attract uses the default Microsoft-branded email service account.</span></span>

1. <span data-ttu-id="5ad8a-117">Välj **inställningar** (växelsymbol) i det övre högra hörnet och välj sedan **administratörscenter**.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-117">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="5ad8a-118">På fliken **E-postinställningar** under **Konton för e-posttjänst**, välj **Anslut ett företagskonto**.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-118">On the **Email settings** tab, under **Email service accounts**, select **Connect a company account**.</span></span>

    ![Ansluta företagets konto hos e-posttjänsten i Attract](./media/attract-admin-email-service-accounts.png)

    <span data-ttu-id="5ad8a-120">Mer information om hur du skapar ett delat e-postkonto finns i [delade postlådor i Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="5ad8a-120">For more information about how to create a shared email account, see [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span></span>

3. <span data-ttu-id="5ad8a-121">Logga in i inloggningsfönstret i Microsoft med dina företagsreferenser.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-121">In the Microsoft sign-in window, sign in by using your corporate credentials.</span></span>
4. <span data-ttu-id="5ad8a-122">Om du inte redan har skapat ett konto för e-posttjänsten, eller om du vill lägga till ett nytt väljer du **Lägg till nytt tjänstkonto** och anger sedan din e-postinformation.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-122">If you haven't yet set up an email service account, or if you want to add a new one, select **Add new service account**, and then enter your email information.</span></span> <span data-ttu-id="5ad8a-123">Om du redan har konfigurerat kontot för e-posttjänster som du vill använda väljer du det.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-123">If you've already set up the email service account that you want to use, select it.</span></span>

<span data-ttu-id="5ad8a-124">När kontot för e-posttjänst har konfigurerats visas det under **Konton för e-posttjänst**.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-124">When your email service account is successfully configured, you will see it listed under **Email service accounts**.</span></span>

## <a name="disconnect-an-email-service-account"></a><span data-ttu-id="5ad8a-125">Frånkoppla ett konto för e-posttjänst</span><span class="sxs-lookup"><span data-stu-id="5ad8a-125">Disconnect an email service account</span></span>

<span data-ttu-id="5ad8a-126">Om du vill sluta att använda ditt företags domän i e-postkommunikationer genom Attract kan du koppla från ett konto för e-posttjänsten.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-126">If you want to stop using your company's domain in email communications through Attract, you can disconnect an email service account.</span></span>

1. <span data-ttu-id="5ad8a-127">Välj **inställningar** (växelsymbol) i det övre högra hörnet och välj sedan **administratörscenter**.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-127">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="5ad8a-128">På fliken **E-postinställningar**, under **Konton för e-postinställningar**, välj knappen **Mer** (tre vertikala punkter) under det konto för e-posttjänst som du vill frånkoppla.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-128">On the **Email settings** tab, under **Email service accounts**, select the **More** button (three vertical dots) next to the email service account that you want to disconnect.</span></span>
3. <span data-ttu-id="5ad8a-129">Välj **frånkoppla e-postkonto**.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-129">Select **Disconnect email account**.</span></span>

    ![Frånkoppla företagets konto hos e-posttjänsten](./media/attract-admin-disconnect-email-account.png)

4. <span data-ttu-id="5ad8a-131">Välj **Frånkoppla** när du uppmanas att bekräfta åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-131">When you're prompted to confirm the operation, select **Disconnect**.</span></span>

    ![Bekräfta frånkoppling av företagets konto hos e-posttjänsten](./media/attract-admin-email-confirm-disconnect.png)

<span data-ttu-id="5ad8a-133">Om du inte ansluter ett annat konto för e-posttjänst kommer alla e-postmeddelanden som skickas från Attract att använda det varumärkesanpassade Microsoft e-posttjänstkonto som är standard.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-133">If you don't connect a different email service account, emails that are sent from Attract will use the default Microsoft-branded email service account.</span></span>

## <a name="configure-email-template-settings"></a><span data-ttu-id="5ad8a-134">Konfigurera inställningar för e-postmall</span><span class="sxs-lookup"><span data-stu-id="5ad8a-134">Configure email template settings</span></span>

<span data-ttu-id="5ad8a-135">Du kan överföra en bild av företagets logotyp och annan information som ett anpassat sidhuvud för e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-135">You can upload an image of your company's logo and other information as a branded header for your emails.</span></span> <span data-ttu-id="5ad8a-136">Du kan också ange länkar till din sekretesspolicy och användningsvillkor i e-postsidfötter.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-136">You can also provide links to your privacy policy and terms of use in email footers.</span></span>

> [!NOTE]
> <span data-ttu-id="5ad8a-137">Du måste följa tillämpliga lagar (bland annat gällande skräppost) i ditt land eller region och lagarna i landet eller regionen där e-postmottagaren finns.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-137">You must comply with all applicable laws of your country or region, and also the country or region that governs the email recipient.</span></span> <span data-ttu-id="5ad8a-138">Dessa lagar omfattar regler om skräppost.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-138">These laws include anti-spam regulations.</span></span>

1. <span data-ttu-id="5ad8a-139">Välj **inställningar** (växelsymbol) i det övre högra hörnet och välj sedan **administratörscenter**.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-139">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="5ad8a-140">På fliken **e-postinställningar** under **inställningar för e-postmall** drar du den bild som du vill använda som e-postrubrik till bildrutan, eller bläddrar till filen genom att klicka på bildrutan.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-140">On the **Email settings** tab, under **Email template settings**, drag the image that you want to use as your email header into the image box, or click in the image box to browse for the file.</span></span> <span data-ttu-id="5ad8a-141">Om du vill ersätta en befintlig bild måste du först markera **ta bort** bredvid den.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-141">To replace an existing image, you must first select **Remove** next to it.</span></span> <span data-ttu-id="5ad8a-142">Bilden måste vara en JPEG-, JPG-, PNG- eller SVG-fil.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-142">The image must be a JPEG, JPG, PNG, or SVG file.</span></span> <span data-ttu-id="5ad8a-143">Den rekommenderade storleken för bilder är mellan 25 och 800 bildpunkter bred och mellan 25 och 150 pixlar hög.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-143">The recommended size for images is between 25 and 800 pixels wide, and between 25 and 150 pixels high.</span></span> <span data-ttu-id="5ad8a-144">Den maximala filstorleken för rubriken är 1 MB.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-144">The maximum file size for the header is 1 megabyte (MB).</span></span>

    ![Lägga till en bild för företagets e-posthuvud](./media/attract-admin-email-header.png)

3. <span data-ttu-id="5ad8a-146">Under **Din sekretesspolicy för kommunikation**anger du en länk till företagets sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-146">Under **Your Privacy policy for communications**, provide a link to your company's privacy policy.</span></span> <span data-ttu-id="5ad8a-147">Under **Ditt ditt företags användningsvillkor för kommunikation** ger en länk till ditt företags användningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-147">Under **Your Terms and conditions for communication**, provide a link to your company's terms of use.</span></span>

    ![Lägga till länkar till företagets sekretesspolicy och användningsvillkor för e-postsidfoten](./media/attract-admin-email-footer.png)

4. <span data-ttu-id="5ad8a-149">Välj **Spara** om du vill spara dina inställningar för e-postmall.</span><span class="sxs-lookup"><span data-stu-id="5ad8a-149">Select **Save** to save your email template settings.</span></span>
