---
title: Aktivera platsbaserad butiksdetektering
description: I det här avsnittet beskrivs hur du aktiverar platsbaserad identifiering av lager för din Dynamics 365 Commerce-webbplats.
author: brianshook
manager: annbe
ms.date: 07/02/2020
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
ms.openlocfilehash: f87d29a8cffb70e4dea211cea7538e5e4c85295c
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517316"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="b7c16-103">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="b7c16-103">Enable location-based store detection</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b7c16-104">I det här avsnittet beskrivs hur du aktiverar platsbaserad identifiering av lager för din Dynamics 365 Commerce-webbplats.</span><span class="sxs-lookup"><span data-stu-id="b7c16-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="b7c16-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="b7c16-105">Overview</span></span>

<span data-ttu-id="b7c16-106">Med platsbaserad butiksidentifiering i näthandelsbutiken kan du tillhandahålla relevant webbplatsinnehåll för kunderna, baserat på deras plats.</span><span class="sxs-lookup"><span data-stu-id="b7c16-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="b7c16-107">När platsbaserad identifiering av lager aktiveras, använder näthandelsbutikens återgivningstjänst information om land/region från IP-adressen till kundens webbläsare för att hänvisa kunden till den bästa tillgängliga konfigurationen för geografisk plats.</span><span class="sxs-lookup"><span data-stu-id="b7c16-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="b7c16-108">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="b7c16-108">Privacy notice</span></span>

<span data-ttu-id="b7c16-109">Om du aktiverar den platsbaserade funktionen för identifiering av butiken skickas information från kundens webbläsare till en Microsoft-platstjänst.</span><span class="sxs-lookup"><span data-stu-id="b7c16-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="b7c16-110">Denna information används sedan för att ge kundinnehållet som är relevant för sin plats.</span><span class="sxs-lookup"><span data-stu-id="b7c16-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="b7c16-111">Både de uppgifter som skickas från kundens webbläsare och den platsbaserade information som returneras till kunden omfattas av policyer för sekretess och cookie-kompatibilitet.</span><span class="sxs-lookup"><span data-stu-id="b7c16-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="b7c16-112">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="b7c16-112">Turn on location-based store detection</span></span>

<span data-ttu-id="b7c16-113">Aktivera platsbaserad butiks identifiering i näthandelsbutiken genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="b7c16-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="b7c16-114">I utvecklingsverktyget går du till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="b7c16-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="b7c16-115">I navigeringsfönstret till vänster, välj **Platshantering**.</span><span class="sxs-lookup"><span data-stu-id="b7c16-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="b7c16-116">Välj **Platsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="b7c16-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="b7c16-117">Ange alternativet **aktivera platsbaserade butiksidentifiering** till **På**.</span><span class="sxs-lookup"><span data-stu-id="b7c16-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b7c16-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b7c16-118">Additional resources</span></span>

[<span data-ttu-id="b7c16-119">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="b7c16-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="b7c16-120">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="b7c16-120">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="b7c16-121">Skapa en näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="b7c16-121">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="b7c16-122">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="b7c16-122">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="b7c16-123">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="b7c16-123">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="b7c16-124">Överför URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="b7c16-124">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="b7c16-125">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="b7c16-125">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="b7c16-126">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="b7c16-126">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="b7c16-127">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="b7c16-127">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="b7c16-128">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="b7c16-128">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)
