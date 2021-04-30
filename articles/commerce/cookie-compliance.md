---
title: Cookie-kompatibilitet
description: I det här avsnittet beskrivs överväganden för cookie-efterlevnad och standardprinciper som ingår i Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 04/16/2021
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
ms.openlocfilehash: efc84bcea2fb6c28c0b13d4469e858e82cc1c073
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908194"
---
# <a name="cookie-compliance"></a>Cookie-kompatibilitet

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs överväganden för cookie-efterlevnad och standardprinciper som ingår i Microsoft Dynamics 365 Commerce.

Sekretess är en viktig faktor när någon spårningsteknik som påverkar näthandelskunder används. På grund av sekretess standarder för efterlevnad, till exempel den allmänna dataskyddsförordningen (GDPR) i Europeiska unionen (EU), måste riktlinjerna för elektronisk sekretess övervägas för alla webbplatser som är aktiva idag. Eftersom många näthandelssajter är globalt tillgängliga som standard är det viktigt att du granskar efterlevnadsstandarderna för din näthandelssajt.

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
| \_msdyn365___muid_                            | Används om Experimentering har aktiverats för miljön; används som userId i experimenteringssyfte. |
| \_msdyn365___exp_                             | Används om Experimentering har aktiverats för miljön; används för att mäta belastningsutjämning.         |



Om en webbplatsanvändare väljer några sociala medialänkar på en webbplats kommer cookies i följande register även att spåras i webbläsaren.


| Domän                      | Cookie               | beskrivning                                                  | Källa                                          |
| --------------------------- | ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| .linkedin.com                | UserMatchHistory         | ID-synkronisering av LinkedIn-annonser                                      | LinkedIn-flöde och insiktstagg                                |
| .linkedin.com               | li_sugr                  | Webbläsar-ID                                           | Insiktstagg för LinkedIn om IP-adressen inte finns i ett anvisat land |
| .linkedin.com               | BizographicsOptOut       | Bestämmer avanmälningsstatus för tredjepartsspårning.              | LinkedIn-gästkontroller och avanmälningssidor för bransch           |
| .linkedin.com               | \_guid                    | Webbläsar-ID för Google Ads-annonser.                            | LinkedIn-flöde                                                |
| .linkedin.com               | li_oatml                 | Medlem som har ett indirekt ID för konverteringsspårning, ominriktning och analys. | LinkedIn-annonser och insiktstaggar                                |
| Olika första part-domäner | li_fat_id                | Medlem som har ett indirekt ID för konverteringsspårning, ominriktning och analys. | LinkedIn-annonser och insiktstaggar                                |
| .adsymptotic.com            | U                        | Webbläsar-ID                                           | Insiktstagg för LinkedIn om IP-adressen inte finns i ett anvisat land |
| .linkedin.com                | bCookie                  | Cookie för webbläsar-ID                                            | Förfrågningar till LinkedIn                                         |
| .linkedin.com                | bscookie                 | Säker webbläsarcookie                                        | Förfrågningar till LinkedIn                                         |
| .linkedin.com               | lang                     | Anger standardinställningar och -språk.                                 | Förfrågningar till LinkedIn                                         |
| .linkedin.com                | lidc                     | Används för flöde.                                             | Förfrågningar till LinkedIn                                         |
| .linkedin.com               | aam_uuid                 | Cookie för Adobe-målgruppschef                                                     | Inställd för ID-sykronisering                                              |
| .linkedin.com               | \_ga                      | Google Analytics-cookie                                            | Google Analytics                                             |
| .linkedin.com               | \_gat                     | Google Analytics-cookie                                             | Google Analytics                                             |
| .linkedin.com               | liap                     | Google Analytics-cookie                                             | Google Analytics                                             |
| .linkedin.com               | lissc                    |                                                              |                                                              |
| .facebook.com               | c_user                   | Denna cookie innehåller användar-ID:t för den användare som för närvarande är inloggad.  |   Facebook                                                           |
| .facebook.com               | datr                     | Används för att identifiera webbläsaren som används för att ansluta till Facebook oberoende av den inloggade användaren. | Facebook                                                             |
| .facebook.com               | wd                       | Lagrar webbläsarens fönsterdimensioner och används av Facebook för att optimera renderingen av sidan. | Facebook                                                             |
| .facebook.com               | xs                       | Tvåsiffrigt nummer som motsvarar sessionsnumret. Den andra delen av värdet är en sessionshemlighet. |  Facebook                                                            |
| .facebook.com               | fr                       | Innehåller en unik webbläsare och ett unikt användar-ID som används för riktad marknadsföring. |  Facebook                                                            |
| .facebook.com               | sb                       | Används för att förbättra vänförslag i Facebook.                                |  Facebook                                                            |
| .facebook.com               | spin                     |                                                              |  Facebook                                                            |
| .twitter.com                | guest_id                 |                                                              |  Twitter                                                            |
| .twitter.com                | kdt                      |                                                              |  Twitter                                                             |
| .twitter.com                | personalization_id       | Denna cookie innehåller användar-ID:t för den användare som för närvarande är inloggad.  |  Twitter                                                             |
| .twitter.com                | remember_checked_on      |                                                              | Twitter                                                              |
| .twitter.com                | twid                     |                                                              |  Twitter                                                             |
| .pinterest.com              | \_auth                    | Denna cookie innehåller användar-ID:t för den användare som för närvarande är inloggad.  |   Pinterest                                                           |
| .pinterest.com              | \_b                       |                                                              |   Pinterest                                                           |
| .pinterest.com              | \_pinterest_pfob          |                                                              |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_referrer      | Cookien innehåller sidor när användaren väljer knappen Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_sess          | Cookien innehåller sidor när användaren väljer knappen Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_routing_id              |                                                              |  Pinterest                                                            |
| .pinterest.com              | bei                      |                                                              |  Pinterest                                                            |
| .pinterest.com              | cm_sub                   | Innehåller ett användar-ID och tidstämpeln när cookien skapades. |  Pinterest                                                            |
| .pinterest.com              | csrftoken                | Cookien innehåller sidor när användaren väljer knappen Pinterest.      | Pinterest                                                             |
| .pinterest.com              | sessionFunnelEventLogged | Cookien innehåller sidor när användaren väljer knappen Pinterest.      | Pinterest                                                             |
| .pinterest.com              | Lokal lagring            |                                                              |  Pinterest                                                            |
| .pinterest.com              | Servicepersonal          |                                                              |  Pinterest                                                            |


## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>Cookie-tillstånd för webbplatsanvändare på en näthandelssajt 

Om en användare av en näthandelssajt eller en modul använder en icke-väsentlig cookie måste en webbplatsanvändare erhålla ett tillstånd innan cookien spåras. För att webbplatsanvändare ska kunna ge cookie-samtycke på näthandelssajten måste en webbplatsförfattare lägga till och konfigurera en modul för cookie-samtycke i sidans rubrikmodul för att säkerställa att samtycket uppmanas och tas emot. Tillstånd från webbplatsanvändare måste ges innan en funktion eller modul med en icke-väsentlig cookie kan återges på en webbplatssida.

## <a name="additional-resources"></a>Ytterligare resurser

[Hjälpmedelsfunktioner och möjligheter](accessibility.md)

[Regelefterlevnad – översikt](compliance-overview.md)

[Lägga till en sida med sekretesspolicy](add-privacy-page.md)

[Ersätt användar-ID:n som är associerade med spårade innehållsändringar](replace-IDs-tracked-changes.md)

[Modul för cookie-samtycke](cookie-consent-module.md) 
 
[Modul för sidhuvud](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
