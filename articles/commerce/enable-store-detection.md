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
ms.openlocfilehash: 304d8d2f05916295b9c6320561d6a25ff40df955
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003106"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="24a92-103">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="24a92-103">Enable location-based store detection</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="24a92-104">I det här avsnittet beskrivs hur du aktiverar platsbaserad identifiering av lager för din Dynamics 365 Commerce-webbplats.</span><span class="sxs-lookup"><span data-stu-id="24a92-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="24a92-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="24a92-105">Overview</span></span>

<span data-ttu-id="24a92-106">Med platsbaserad butiksidentifiering i näthandelsbutiken kan du tillhandahålla relevant webbplatsinnehåll för kunderna, baserat på deras plats.</span><span class="sxs-lookup"><span data-stu-id="24a92-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="24a92-107">När platsbaserad identifiering av lager aktiveras, använder näthandelsbutikens återgivningstjänst information om land/region från IP-adressen till kundens webbläsare för att hänvisa kunden till den bästa tillgängliga konfigurationen för geografisk plats.</span><span class="sxs-lookup"><span data-stu-id="24a92-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="24a92-108">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="24a92-108">Privacy notice</span></span>

<span data-ttu-id="24a92-109">Om du aktiverar den platsbaserade funktionen för identifiering av butiken skickas information från kundens webbläsare till en Microsoft-platstjänst.</span><span class="sxs-lookup"><span data-stu-id="24a92-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="24a92-110">Denna information används sedan för att ge kundinnehållet som är relevant för sin plats.</span><span class="sxs-lookup"><span data-stu-id="24a92-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="24a92-111">Både de uppgifter som skickas från kundens webbläsare och den platsbaserade information som returneras till kunden omfattas av policyer för sekretess och cookie-kompatibilitet.</span><span class="sxs-lookup"><span data-stu-id="24a92-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="24a92-112">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="24a92-112">Turn on location-based store detection</span></span>

<span data-ttu-id="24a92-113">Aktivera platsbaserad butiks identifiering i näthandelsbutiken genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="24a92-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="24a92-114">I utvecklingsverktyget går du till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="24a92-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="24a92-115">I navigeringsfönstret till vänster, välj **Platshantering**.</span><span class="sxs-lookup"><span data-stu-id="24a92-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="24a92-116">Välj **Platsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="24a92-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="24a92-117">Ange alternativet **aktivera platsbaserade butiksidentifiering** till **På**.</span><span class="sxs-lookup"><span data-stu-id="24a92-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="24a92-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="24a92-118">Additional resources</span></span>

[<span data-ttu-id="24a92-119">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="24a92-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="24a92-120">Distribuera en ny näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="24a92-120">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="24a92-121">Skapa en e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="24a92-121">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="24a92-122">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="24a92-122">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="24a92-123">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="24a92-123">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="24a92-124">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="24a92-124">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="24a92-125">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="24a92-125">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)
