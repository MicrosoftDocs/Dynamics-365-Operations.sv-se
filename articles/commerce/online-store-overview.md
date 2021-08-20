---
title: Webbplatsöversikt för näthandel
description: Detta ämne innehåller en översikt över stödet för näthandelssajter i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 11/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d8d1b563b08cce1d7b56c0ab5ebc06d1c900f281e1ceb961721978ba8718eba8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741122"
---
# <a name="e-commerce-site-overview"></a>Näthandelsplats – översikt

[!include [banner](includes/banner.md)]

Detta ämne innehåller en översikt över stödet för näthandelssajter i Microsoft Dynamics 365 Commerce. Den innehåller information om hur näthandelsbutiker initieras och hanteras i Dynamics 365 Commerce. Den ger också länkar till mer information om onlinebutiker samt om hur du skapar och konfigurerar en näthandelssajt. Även om detta ämne täcker många av grunderna omfattar det inte allt som krävs för att konfigurera en produktion näthandelssajt. Mer avancerade ämnen finns i Dynamics 365 Commerce-dokumentationen.

## <a name="online-store-channel"></a>Onlinebutikskanal

Innan du kan skapa din plats i Dynamics 365 Commerce måste minst en onlinebutikskanal skapas. Mer information finns i [Konfigurera en onlinekanal](channel-setup-online.md). 

I Dynamics 365 Commerce använder du en onlinebutikskanal för att fastställa produkter, prissättning, språk, betalsätt, leveranssätt, lagercentraler och andra aspekter av online-upplevelsen som ska vara tillgängliga för dina kunder.

Endast en onlinebutikskanal måste ställas in innan du kan komma igång med Dynamics 365 Commerce. En enda näthandelssajt kan emellertid tillhandahålla online-upplevelsen för flera onlinebutiker. Om flera onlinebutiker exempelvis har ställts in för att stödja olika geografiska regioner, kan en enda uppsättning näthandelssidor användas för att tillhandahålla de unika upplevelser som definieras av respektive butik. Mer information om hur du konfigurerar en plats för att stödja flera onlinebutiker finns [i associera en onlinewebbplats med en kanal](associate-site-online-store.md).

När en onlinebutik har ställts in kan den associeras med Dynamics 365 Commerce webbplatsen fungerar som ditt onlineskyltfönster. Mer information om onlinebutiker och hur du konfigurerar dem finns [Konfigurera onlinebutiker](/dynamics365/unified-operations/retail/online-stores).

## <a name="deploy-a-new-e-commerce-tenant"></a>Distribuera en ny klientorganisation för näthandel

Under initieringen av en näthandelssajt uppmanas du att ange ett domännamn. Mer information om domäner i Commerce finns i [Konfigurera ditt domännamn](configure-your-domain-name.md) och [Domäner i Dynamics 365 Commerce](domains-commerce.md). Om du vill distribuera en ny klientorganisation för näthandel genom att använda [Microsoft Dynamics Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide) följer du stegen i [Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md). När din klientorganisation för näthandel har konfigurerats i LCS skapas en länk till Commerce-webbplatsbyggaren. Du kan sedan använda Commerce-webbplatsbyggaren för att initiera och konfigurera dina näthandelssajter.

## <a name="initialize-your-e-commerce-site"></a>Initiera din näthandelssajt

När du startar Commerce-webbplatsbyggaren från LCS visas sidan **Webbplatser**. Den här sidan innehåller två förkonfigurerade webbplatser, **standard** och **fabrikam**, som visas i följande illustration.

![Sidan Webbplatser i Commerce-webbplatsbyggaren.](media/e-commerce-site-01.png)

När du väljer en av dessa webbplatser uppmanas du att välja ett domännamn, en standardkanal för onlinebutik, ett språk som stöds för den valda kanalen och en sökväg. Om bara en kanal används kan du låta sökvägen vara tom. Fler onlinebutikskanaler eller -språk kan konfigureras senare i Commerce-webbplatsbyggaren. Varje ytterligare kanal eller språk kommer att kräva en unik sökväg. Du har till exempel två onlinekanaler som är kopplade till en enda webbplats, och domännamnet för webbplatsen är `www.fabrikam.com`. I det här fallet kan sökvägen för en kanal vara standardvärdet som inte har någon sökväg (`https://www.fabrikam.com`), och den andra kanalen kan ställas in på en ny sökväg, till exempel **webbplats2**, som kommer att ha webbadressen `https://www.fabrikam.com/site2`. I bilden nedan visas ett exempel på en dialogruta för webbplatsinitiering i Commerce-webbplatsbyggaren.

![Dialogrutan för initiering av webbplatser i Commerce-webbplatsbyggaren.](media/e-commerce-site-02.png)

Sidan **Webbplatser** innehåller också knappen **Ny webbplats**. Dialogrutan som visas när du väljer den här knappen liknar dialogrutan för initiering av webbplatsen, men den används för att skapa en ny webbplats. Nya webbplatser är tomma. De innehåller inte samma standardmallar, fragment, sidor och bilder som tillhandahålls med webbplatserna **standard** och **fabrikam**. Efter behov kan du emellertid öppna ett supportärende för att begära att en kopia av standardinnehållet läggs till på en ny, tom webbplats. Mer information finns i [Skapa en näthandels](create-ecommerce-site.md).

När en ny webbplats har initierats visas **Start**-sidan för Commerce-webbplatsbyggaren. Den här sidan innehåller länkar till vanliga åtgärder och vägledningsinnehåll, enligt exemplet i följande illustration.

![Länkar på startsidan i Commerce-webbplatsbyggaren.](media/e-commerce-site-03.png)

## <a name="modify-online-store-channels-or-add-online-store-channels-to-an-e-commerce-site"></a>Ändra kanaler i onlinebutiken eller lägga till onlinebutikskanaler på en näthandelssajt

När en näthandelssajt har skapats kan du ändra kanalen som den är kopplad till genom att följa stegen i [Associera en näthandelssajt med en onlinekanal](associate-site-online-store.md). Exemplet i följande bild visar hur ett numret för en kanaldriftsenhet (OUN) kan ändras på sidan **Kanaler** (**Webbplatsinställningar \> Kanaler**). När du har slutfört en ändring ska du se till att välja **Spara och publicera**. På så sätt ser du till att ändringen publiceras.

![Sidan Kanaler i Commerce-webbplatsbyggaren.](media/e-commerce-site-04.png)

Du kan lägga till nya kanaler genom att välja **Lägg till en kanal**. Om du vill lägga till nya språk i en kanal markerar du kanalen och väljer sedan **Lägg till ett språk** i kanaldialogrutan som visas. Innan språken kan visas i dialogrutan måste de vara förkonfigurerade för onlinebutikskanalen i Commerce-administrationen.

![Kanaldialogrutan i Commerce-webbplatsbyggaren.](media/e-commerce-site-05.png)

## <a name="set-up-an-azure-b2c-tenant"></a>Konfigurera en Azure B2C-klientorganisation

Dynamics 365 Commerce använder Azure Active Directory (Azure AD) B2C-klientorganisationer (business-to-consumer) för att stödja autentiseringsuppgifter för användare och verifikationsflöden. Information om hur du ställer in din Azure B2C-klientorganisation finns i [Konfigurera en B2C-klientorganisation i Commerce](set-up-b2c-tenant.md), [Konfigurera anpassade sidor för inloggningar för användare](custom-pages-user-logins.md) och [Konfigurera flera B2C-klientorganisationer i en Commerce-miljö](configure-multi-b2c-tenants.md).

## <a name="overview-of-the-default-site-pages"></a>Översikt över standardwebbplatssidorna

**Standard**- och **fabrikam**-webbplatserna innehåller förkonfigurerade mallar, fragment och sidor som hjälper dig att komma igång. Mer information finns i följande avsnitt:

- [Översikt över startsidan](quick-tour-home-page.md)
- [Översikt över sida med produktinformation](quick-tour-pdp.md)
- [Översikt över sidor för kundvagn och kassa](quick-tour-cart-checkout.md)
- [Översikt över sidor för kontohantering](quick-tour-account-management.md)

## <a name="manage-site-settings"></a>Hantera webbplatsinställningar

För information om hur du hanterar dina webbplatsinställningar, se följande ämnen:

- [Hantera näthandelsanvändare och roller](manage-ecommerce-users-roles.md)
- [Språkinformation för sökmotoroptimering (SEO) för din webbplats](/search-engine-optimization-considerations.md)
- [Hantera säkerhetspolicy för innehåll (CSP)](manage-csp.md)
- [Välja ett tema för webbplatsen](select-site-theme.md)

## <a name="manage-site-content"></a>Hantera webbplatsinnehåll

För information om hur du hanterar webbplatsinnehåll, se följande ämnen:

- [Ordlista för sidmodell](page-elements-overview.md)
- [Dokumentera tillstånd och livscykel](document-states-overview.md)
- [Mallar och layout](templates-layouts-overview.md)
- [Arbeta med fragment](work-with-fragments.md)
- [Arbeta med moduler](work-with-modules.md)
- [Översikt av digital tillgångshantering](dam-overview.md)
- [Modulbibliotek – översikt](starter-kit-overview.md)

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa en näthandelssajt](create-ecommerce-site.md)

[Distribuera en ny näthandelssajt](deploy-ecommerce-site.md)

[Associera en online-webbplats med en kanal](associate-site-online-store.md)

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]