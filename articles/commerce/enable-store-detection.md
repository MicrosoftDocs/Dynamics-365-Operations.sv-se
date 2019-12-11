---
title: Aktivera platsbaserad butiksdetektering
description: I det här avsnittet beskrivs hur du aktiverar platsbaserad identifiering av lager för din Dynamics 365 Commerce-webbplats.
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: a542d6987280451910b4ff3bcfb3a109a0e028c6
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697622"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="6a487-103">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="6a487-103">Enable location-based store detection</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="6a487-104">I det här avsnittet beskrivs hur du aktiverar platsbaserad identifiering av lager för din Dynamics 365 Commerce-webbplats.</span><span class="sxs-lookup"><span data-stu-id="6a487-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="6a487-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="6a487-105">Overview</span></span>

<span data-ttu-id="6a487-106">Med platsbaserad butiksidentifiering i näthandelsbutiken kan du tillhandahålla relevant webbplatsinnehåll för kunderna, baserat på deras plats.</span><span class="sxs-lookup"><span data-stu-id="6a487-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="6a487-107">När platsbaserad identifiering av lager aktiveras, använder näthandelsbutikens återgivningstjänst information om land/region från IP-adressen till kundens webbläsare för att hänvisa kunden till den bästa tillgängliga konfigurationen för geografisk plats.</span><span class="sxs-lookup"><span data-stu-id="6a487-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="6a487-108">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="6a487-108">Privacy notice</span></span>

<span data-ttu-id="6a487-109">Om du aktiverar den platsbaserade funktionen för identifiering av butiken skickas information från kundens webbläsare till en Microsoft-platstjänst.</span><span class="sxs-lookup"><span data-stu-id="6a487-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="6a487-110">Denna information används sedan för att ge kundinnehållet som är relevant för sin plats.</span><span class="sxs-lookup"><span data-stu-id="6a487-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="6a487-111">Både de uppgifter som skickas från kundens webbläsare och den platsbaserade information som returneras till kunden omfattas av policyer för sekretess och cookie-kompatibilitet.</span><span class="sxs-lookup"><span data-stu-id="6a487-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="6a487-112">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="6a487-112">Turn on location-based store detection</span></span>

<span data-ttu-id="6a487-113">Aktivera platsbaserad butiks identifiering i näthandelsbutiken genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="6a487-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="6a487-114">I utvecklingsverktyget går du till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="6a487-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="6a487-115">I navigeringsfönstret till vänster, välj **Platshantering**.</span><span class="sxs-lookup"><span data-stu-id="6a487-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="6a487-116">Välj **Platsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="6a487-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="6a487-117">Ange alternativet **aktivera platsbaserade butiksidentifiering** till **På**.</span><span class="sxs-lookup"><span data-stu-id="6a487-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a487-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6a487-118">Additional resources</span></span>

[<span data-ttu-id="6a487-119">Översikt över onlinebutik</span><span class="sxs-lookup"><span data-stu-id="6a487-119">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="6a487-120">Skapa en näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="6a487-120">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="6a487-121">Distribuera en ny näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="6a487-121">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="6a487-122">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="6a487-122">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="6a487-123">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="6a487-123">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="6a487-124">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="6a487-124">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="6a487-125">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="6a487-125">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)
