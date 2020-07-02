---
title: Cookie-kompatibilitet
description: I det här avsnittet beskrivs överväganden för cookie-efterlevnad och standardprinciper som ingår i Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 06/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e1fa016dc9f46b048220f0f83e4b0783087de91e
ms.sourcegitcommit: c66c4c67a21e7d7d3a94a3fd766c3184b6e65c4e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/12/2020
ms.locfileid: "3446923"
---
# <a name="cookie-compliance"></a><span data-ttu-id="a6df6-103">Cookie-kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="a6df6-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a6df6-104">I det här avsnittet beskrivs överväganden för cookie-efterlevnad och standardprinciper som ingår i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a6df6-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a6df6-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="a6df6-105">Overview</span></span>

<span data-ttu-id="a6df6-106">Sekretess är en viktig faktor när någon spårningsteknik som påverkar e-handelskunder används.</span><span class="sxs-lookup"><span data-stu-id="a6df6-106">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="a6df6-107">På grund av sekretess standarder för efterlevnad, till exempel den allmänna dataskyddsförordningen (GDPR) i Europeiska unionen (EU), måste riktlinjerna för elektronisk sekretess övervägas för alla webbplatser som är aktiva idag.</span><span class="sxs-lookup"><span data-stu-id="a6df6-107">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="a6df6-108">Eftersom många e-handelsplatser är globalt tillgängliga som standard är det viktigt att du granskar efterlevnadsstandarderna för din e-handelsplats.</span><span class="sxs-lookup"><span data-stu-id="a6df6-108">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="a6df6-109">Om du vill veta mer om de grundläggande principer som Microsoft använder för cookie-efterlevnad besöker du [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="a6df6-109">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="a6df6-110">På den webbplatsen kan du också få mer information om efterlevnadsområden och sekretess.</span><span class="sxs-lookup"><span data-stu-id="a6df6-110">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="a6df6-111">I följande tabell visas den aktuella referenslistan över cookies som placerats på Dynamics 365 Commerce-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="a6df6-111">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="a6df6-112">Cookienamn</span><span class="sxs-lookup"><span data-stu-id="a6df6-112">Cookie name</span></span>                               | <span data-ttu-id="a6df6-113">Användning</span><span class="sxs-lookup"><span data-stu-id="a6df6-113">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="a6df6-114">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="a6df6-114">.AspNet.Cookies</span></span>                             | <span data-ttu-id="a6df6-115">Lagra Microsoft Azure Active Directory (Azure AD)-verifieringscookies för enkel inloggning (SSO).</span><span class="sxs-lookup"><span data-stu-id="a6df6-115">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="a6df6-116">Lagrar krypterad huvudinformation för användare (namn, efternamn, e-post).</span><span class="sxs-lookup"><span data-stu-id="a6df6-116">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="a6df6-117">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="a6df6-117">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="a6df6-118">Lagrar kundvagns-ID som används för att hämta listan över produkter som lagts till i kundvagnsinstansen.</span><span class="sxs-lookup"><span data-stu-id="a6df6-118">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="a6df6-119">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="a6df6-119">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="a6df6-120">Spårning av samtycket till cookie-kompatibilitet.</span><span class="sxs-lookup"><span data-stu-id="a6df6-120">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="a6df6-121">ai_session</span><span class="sxs-lookup"><span data-stu-id="a6df6-121">ai_session</span></span>                                  | <span data-ttu-id="a6df6-122">Upptäcker hur många sessioner av användaraktivitet som har inkluderat vissa sidor och funktioner i appen.</span><span class="sxs-lookup"><span data-stu-id="a6df6-122">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="a6df6-123">ai_user</span><span class="sxs-lookup"><span data-stu-id="a6df6-123">ai_user</span></span>                                     | <span data-ttu-id="a6df6-124">Upptäcker hur många personer som har använt appen och dess funktioner.</span><span class="sxs-lookup"><span data-stu-id="a6df6-124">Detects how many people used the app and its features.</span></span> <span data-ttu-id="a6df6-125">Användare räknas med anonyma ID:n.</span><span class="sxs-lookup"><span data-stu-id="a6df6-125">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="a6df6-126">b2cru</span><span class="sxs-lookup"><span data-stu-id="a6df6-126">b2cru</span></span>                                       | <span data-ttu-id="a6df6-127">Lagrar omdirigerings-URL dynamiskt.</span><span class="sxs-lookup"><span data-stu-id="a6df6-127">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="a6df6-128">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="a6df6-128">JSESSIONID</span></span>                                  | <span data-ttu-id="a6df6-129">Används av Adyen-butiksanvändarsession.</span><span class="sxs-lookup"><span data-stu-id="a6df6-129">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="a6df6-130">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="a6df6-130">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="a6df6-131">Äkthetsbevisning</span><span class="sxs-lookup"><span data-stu-id="a6df6-131">Authentication</span></span>                                               |
| <span data-ttu-id="a6df6-132">x-MS-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="a6df6-132">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="a6df6-133">Används för att underhålla status för begäran.</span><span class="sxs-lookup"><span data-stu-id="a6df6-133">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="a6df6-134">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="a6df6-134">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="a6df6-135">Förfalskning av begäran mellan webbplatser (CRSF) som används för att skydda från CRSF.</span><span class="sxs-lookup"><span data-stu-id="a6df6-135">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="a6df6-136">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="a6df6-136">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="a6df6-137">Används för att dirigera förfrågningar till en lämplig serverinstans för produktionsinleverans.</span><span class="sxs-lookup"><span data-stu-id="a6df6-137">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="a6df6-138">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="a6df6-138">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="a6df6-139">Används för att dirigera förfrågningar till en lämplig serverinstans för produktionsinleverans.</span><span class="sxs-lookup"><span data-stu-id="a6df6-139">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="a6df6-140">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="a6df6-140">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="a6df6-141">Används för att dirigera förfrågningar till en lämplig serverinstans för produktionsinleverans.</span><span class="sxs-lookup"><span data-stu-id="a6df6-141">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="a6df6-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="a6df6-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="a6df6-143">Används för att underhålla SSO-sessionen.</span><span class="sxs-lookup"><span data-stu-id="a6df6-143">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="a6df6-144">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="a6df6-144">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="a6df6-145">Används för att spåra transaktioner (antalet öppna flikar som autentiserar mot en B2C-webbplats), inklusive den aktuella transaktionen.</span><span class="sxs-lookup"><span data-stu-id="a6df6-145">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="a6df6-146">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a6df6-146">Additional resources</span></span>

[<span data-ttu-id="a6df6-147">Hjälpmedelsfunktioner och möjligheter</span><span class="sxs-lookup"><span data-stu-id="a6df6-147">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="a6df6-148">Regelefterlevnad – översikt</span><span class="sxs-lookup"><span data-stu-id="a6df6-148">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="a6df6-149">Lägga till en sida med sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="a6df6-149">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="a6df6-150">Ersätt användar-ID:n som är associerade med spårade innehållsändringar</span><span class="sxs-lookup"><span data-stu-id="a6df6-150">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)
