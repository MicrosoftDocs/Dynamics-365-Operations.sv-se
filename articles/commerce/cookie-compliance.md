---
title: Cookie-kompatibilitet
description: I det här avsnittet beskrivs överväganden för cookie-efterlevnad och standardprinciper som ingår i Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 4f54b9b8130a167dbecdb13fccd7039f827f6ed0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415732"
---
# <a name="cookie-compliance"></a>Cookie-kompatibilitet

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs överväganden för cookie-efterlevnad och standardprinciper som ingår i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Sekretess är en viktig faktor när någon spårningsteknik som påverkar näthandelskunder används. På grund av sekretess standarder för efterlevnad, till exempel den allmänna dataskyddsförordningen (GDPR) i Europeiska unionen (EU), måste riktlinjerna för elektronisk sekretess övervägas för alla webbplatser som är aktiva idag. Eftersom många näthandelsplatser är globalt tillgängliga som standard är det viktigt att du granskar efterlevnadsstandarderna för din näthandelsplats.

Om du vill veta mer om de grundläggande principer som Microsoft använder för cookie-efterlevnad besöker du [Microsoft Trust Center](https://www.microsoft.com/trust-center). På den webbplatsen kan du också få mer information om efterlevnadsområden och sekretess.

I följande tabell visas den aktuella referenslistan över cookies som placerats på Dynamics 365 Commerce-webbplatser.

| Cookienamn                               | Användning                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| .AspNet.Cookies                             | Lagra Microsoft Azure Active Directory (Azure AD)-verifieringscookies för enkel inloggning (SSO). Lagrar krypterad huvudinformation för användare (namn, efternamn, e-post). |
| &#95;msdyn365___cart&#95;                           | Lagrar kundvagns-ID som används för att hämta listan över produkter som lagts till i kundvagnsinstansen. |
| &#95;msdyn365___ucc&#95;                            | Spårning av samtycket till cookie-kompatibilitet.                          |
| ai_session                                  | Upptäcker hur många sessioner av användaraktivitet som har inkluderat vissa sidor och funktioner i appen. |
| ai_user                                     | Upptäcker hur många personer som har använt appen och dess funktioner. Användare räknas med anonyma ID:n. |
| b2cru                                       | Lagrar omdirigerings-URL dynamiskt.                              |
| JSESSIONID                                  | Används av Adyen-butiksanvändarsession.       |
| OpenIdConnect.nonce.&#42;                       | Äkthetsbevisning                                               |
| x-MS-cpim-cache:.&#42;                          | Används för att underhålla status för begäran.                      |
| x-ms-cpim-csrf                              | Förfalskning av begäran mellan webbplatser (CRSF) som används för att skydda från CRSF.     |
| x-ms-cpim-dc                                | Används för att dirigera förfrågningar till en lämplig serverinstans för produktionsinleverans. |
| x-ms-cpim-rc.&#42;                              | Används för att dirigera förfrågningar till en lämplig serverinstans för produktionsinleverans. |
| x-ms-cpim-slice                             | Används för att dirigera förfrågningar till en lämplig serverinstans för produktionsinleverans. |
| x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0 | Används för att underhålla SSO-sessionen.                        |
| x-ms-cpim-trans                             | Används för att spåra transaktioner (antalet öppna flikar som autentiserar mot en B2C-webbplats), inklusive den aktuella transaktionen. |

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>Cookie-tillstånd för webbplatsanvändare på en näthandelsplats 

Om en användare av en näthandelsplats eller en modul använder en icke-väsentlig cookie måste en webbplatsanvändare erhålla ett tillstånd innan cookien spåras. För att webbplatsanvändare ska kunna ge cookie-samtycke på näthandelsplatsen måste en webbplatsförfattare lägga till och konfigurera en modul för cookie-samtycke i sidans rubrikmodul för att säkerställa att samtycket uppmanas och tas emot. Tillstånd från webbplatsanvändare måste ges innan en funktion eller modul med en icke-väsentlig cookie kan återges på en webbplatssida.

## <a name="additional-resources"></a>Ytterligare resurser

[Hjälpmedelsfunktioner och möjligheter](accessibility.md)

[Regelefterlevnad – översikt](compliance-overview.md)

[Lägga till en sida med sekretesspolicy](add-privacy-page.md)

[Ersätt användar-ID:n som är associerade med spårade innehållsändringar](replace-IDs-tracked-changes.md)

[Modul för cookie-samtycke](cookie-consent-module.md) 
 
[Modul för sidhuvud](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]