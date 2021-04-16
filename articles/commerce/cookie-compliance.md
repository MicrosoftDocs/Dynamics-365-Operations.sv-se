---
title: Cookie-kompatibilitet
description: I det här avsnittet beskrivs överväganden för cookie-efterlevnad och standardprinciper som ingår i Microsoft Dynamics 365 Commerce.
author: BrianShook
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
ms.openlocfilehash: 2cc2089bc3052c0c59cb0414f8301123a9a30df2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796037"
---
# <a name="cookie-compliance"></a><span data-ttu-id="420e8-103">Cookie-kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="420e8-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="420e8-104">I det här avsnittet beskrivs överväganden för cookie-efterlevnad och standardprinciper som ingår i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="420e8-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="420e8-105">Sekretess är en viktig faktor när någon spårningsteknik som påverkar näthandelskunder används.</span><span class="sxs-lookup"><span data-stu-id="420e8-105">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="420e8-106">På grund av sekretess standarder för efterlevnad, till exempel den allmänna dataskyddsförordningen (GDPR) i Europeiska unionen (EU), måste riktlinjerna för elektronisk sekretess övervägas för alla webbplatser som är aktiva idag.</span><span class="sxs-lookup"><span data-stu-id="420e8-106">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="420e8-107">Eftersom många näthandelssajter är globalt tillgängliga som standard är det viktigt att du granskar efterlevnadsstandarderna för din näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="420e8-107">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="420e8-108">Om du vill veta mer om de grundläggande principer som Microsoft använder för cookie-efterlevnad besöker du [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="420e8-108">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="420e8-109">På den webbplatsen kan du också få mer information om efterlevnadsområden och sekretess.</span><span class="sxs-lookup"><span data-stu-id="420e8-109">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="420e8-110">I följande tabell visas den aktuella referenslistan över cookies som placerats på Dynamics 365 Commerce-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="420e8-110">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="420e8-111">Cookienamn</span><span class="sxs-lookup"><span data-stu-id="420e8-111">Cookie name</span></span>                               | <span data-ttu-id="420e8-112">Användning</span><span class="sxs-lookup"><span data-stu-id="420e8-112">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="420e8-113">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="420e8-113">.AspNet.Cookies</span></span>                             | <span data-ttu-id="420e8-114">Lagra Microsoft Azure Active Directory (Azure AD)-verifieringscookies för enkel inloggning (SSO).</span><span class="sxs-lookup"><span data-stu-id="420e8-114">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="420e8-115">Lagrar krypterad huvudinformation för användare (namn, efternamn, e-post).</span><span class="sxs-lookup"><span data-stu-id="420e8-115">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="420e8-116">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="420e8-116">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="420e8-117">Lagrar kundvagns-ID som används för att hämta listan över produkter som lagts till i kundvagnsinstansen.</span><span class="sxs-lookup"><span data-stu-id="420e8-117">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="420e8-118">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="420e8-118">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="420e8-119">Spårning av samtycket till cookie-kompatibilitet.</span><span class="sxs-lookup"><span data-stu-id="420e8-119">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="420e8-120">ai_session</span><span class="sxs-lookup"><span data-stu-id="420e8-120">ai_session</span></span>                                  | <span data-ttu-id="420e8-121">Upptäcker hur många sessioner av användaraktivitet som har inkluderat vissa sidor och funktioner i appen.</span><span class="sxs-lookup"><span data-stu-id="420e8-121">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="420e8-122">ai_user</span><span class="sxs-lookup"><span data-stu-id="420e8-122">ai_user</span></span>                                     | <span data-ttu-id="420e8-123">Upptäcker hur många personer som har använt appen och dess funktioner.</span><span class="sxs-lookup"><span data-stu-id="420e8-123">Detects how many people used the app and its features.</span></span> <span data-ttu-id="420e8-124">Användare räknas med anonyma ID:n.</span><span class="sxs-lookup"><span data-stu-id="420e8-124">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="420e8-125">b2cru</span><span class="sxs-lookup"><span data-stu-id="420e8-125">b2cru</span></span>                                       | <span data-ttu-id="420e8-126">Lagrar omdirigerings-URL dynamiskt.</span><span class="sxs-lookup"><span data-stu-id="420e8-126">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="420e8-127">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="420e8-127">JSESSIONID</span></span>                                  | <span data-ttu-id="420e8-128">Används av Adyen-butiksanvändarsession.</span><span class="sxs-lookup"><span data-stu-id="420e8-128">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="420e8-129">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="420e8-129">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="420e8-130">Äkthetsbevisning</span><span class="sxs-lookup"><span data-stu-id="420e8-130">Authentication</span></span>                                               |
| <span data-ttu-id="420e8-131">x-MS-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="420e8-131">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="420e8-132">Används för att underhålla status för begäran.</span><span class="sxs-lookup"><span data-stu-id="420e8-132">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="420e8-133">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="420e8-133">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="420e8-134">Förfalskning av begäran mellan webbplatser (CRSF) som används för att skydda från CRSF.</span><span class="sxs-lookup"><span data-stu-id="420e8-134">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="420e8-135">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="420e8-135">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="420e8-136">Används för att dirigera förfrågningar till en lämplig serverinstans för produktionsinleverans.</span><span class="sxs-lookup"><span data-stu-id="420e8-136">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="420e8-137">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="420e8-137">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="420e8-138">Används för att dirigera förfrågningar till en lämplig serverinstans för produktionsinleverans.</span><span class="sxs-lookup"><span data-stu-id="420e8-138">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="420e8-139">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="420e8-139">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="420e8-140">Används för att dirigera förfrågningar till en lämplig serverinstans för produktionsinleverans.</span><span class="sxs-lookup"><span data-stu-id="420e8-140">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="420e8-141">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="420e8-141">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="420e8-142">Används för att underhålla SSO-sessionen.</span><span class="sxs-lookup"><span data-stu-id="420e8-142">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="420e8-143">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="420e8-143">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="420e8-144">Används för att spåra transaktioner (antalet öppna flikar som autentiserar mot en B2C-webbplats), inklusive den aktuella transaktionen.</span><span class="sxs-lookup"><span data-stu-id="420e8-144">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a><span data-ttu-id="420e8-145">Cookie-tillstånd för webbplatsanvändare på en näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="420e8-145">Site user cookie consent on an e-Commerce site</span></span> 

<span data-ttu-id="420e8-146">Om en användare av en näthandelssajt eller en modul använder en icke-väsentlig cookie måste en webbplatsanvändare erhålla ett tillstånd innan cookien spåras.</span><span class="sxs-lookup"><span data-stu-id="420e8-146">If an e-Commerce site feature or module uses a non-essential cookie, a site user's consent must be obtained before the cookie is tracked.</span></span> <span data-ttu-id="420e8-147">För att webbplatsanvändare ska kunna ge cookie-samtycke på näthandelssajten måste en webbplatsförfattare lägga till och konfigurera en modul för cookie-samtycke i sidans rubrikmodul för att säkerställa att samtycket uppmanas och tas emot.</span><span class="sxs-lookup"><span data-stu-id="420e8-147">To allow site users to provide cookie consent on the e-Commerce site, a site author must add and configure a cookie consent module in the page's header module to ensure that the consent is prompted for and received.</span></span> <span data-ttu-id="420e8-148">Tillstånd från webbplatsanvändare måste ges innan en funktion eller modul med en icke-väsentlig cookie kan återges på en webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="420e8-148">Site user consent must be given before a feature or module using a non-essential cookie can be rendered on a site page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="420e8-149">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="420e8-149">Additional resources</span></span>

[<span data-ttu-id="420e8-150">Hjälpmedelsfunktioner och möjligheter</span><span class="sxs-lookup"><span data-stu-id="420e8-150">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="420e8-151">Regelefterlevnad – översikt</span><span class="sxs-lookup"><span data-stu-id="420e8-151">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="420e8-152">Lägga till en sida med sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="420e8-152">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="420e8-153">Ersätt användar-ID:n som är associerade med spårade innehållsändringar</span><span class="sxs-lookup"><span data-stu-id="420e8-153">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)

[<span data-ttu-id="420e8-154">Modul för cookie-samtycke</span><span class="sxs-lookup"><span data-stu-id="420e8-154">Cookie consent module</span></span>](cookie-consent-module.md) 
 
[<span data-ttu-id="420e8-155">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="420e8-155">Header module</span></span>](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
