---
title: Hantera funktioner
description: Läs mer om hur du aktiverar och inaktiverar nya funktioner i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9176e9519c3bf65ef7a4f1b5ae43dbeb411750f5
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230210"
---
# <a name="manage-features"></a>Hantera funktioner

Som en del av vår kontinuerliga distribution av ny funktioner för Microsoft Dynamics 365 Human Resources, vill vi att kunder får nya funktioner så snart som möjligt. Vi tillhandahåller förhandsfunktioner som snart är allmänt tillgänglig och har genomgått omfattande testning. Vi söker bara en slutlig runda av feedback från kunder och validering innan vi gör dem allmänt tillgångliga.

Mer information om nya funktioner i Personal, se [Nyheter och ändringar i Personal](hr-admin-whats-new.md) och [Viktig information om Dynamics 365 och Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1).

Arbetsytan **Funktionshantering** ger en lista med funktioner som levereras i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem. Mer information om hur du aktiverar Funktionshantering finns i [Översikt över funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Alla nya funktioner förblir i förhandsgranskning i minst 30 dagar, vanligtvis 30-60 dagar. Huvudfunktionerna är vanligtvis tillgängliga i oktober och april varje år efter förhandsgranskningsperioden. Så snart du ser nya funktioner på arbetsytan **Funktionshantering** kan du aktivera dem. Vissa funktioner kan vara aktiverade som standard.

När en funktion är allmänt är tillgänglig kan den aktiveras eller inaktiveras i produktionsmiljöer. Arbetsytan **funktionshantering** anger när en förhandsgranskningsfunktion blir obligatorisk. Detta datum är vanligtvis den 1 oktober eller 1 april för anpassning till halvårs frisläppningsplanerna. De kan inte inaktivera obligatoriska funktioner. Du kan aktivera och inaktivera en funktion i alla miljöer tills den blir obligatorisk.

## <a name="enable-or-disable-preview-features"></a>Aktivera eller inaktivera funktioner för förhandsgranskning

För att du ska kunna använda funktionerna för förhandsgranskning måste du först aktivera dem i miljön. Aktivera eller inaktivera funktioner för förhandsgranskning är miljöspecifika.

> [!IMPORTANT]
> Funktionerna för förhandsgranskning är endast tillgängliga i **begränsade** miljöer När du aktiverar förhandsgranskningsfunktioner kan du aktivera förhandsgranskning för alla användare i organisationen i denna miljö. När du inaktiverar förhandsgranskningsfunktioner, inaktiverar du den och gör dem otillgängliga för användarna. Förhandsgranskningsfunktioner har begränsad funktionalitet i Personal. De använder färre sekretess- och säkerhetsfunktioner och de ingår inte i Personal servicenivåavtal (SLA). Du bör inte använda funktioner för förhandsgranskning för att behandla personuppgifter (d.v.s. all information som kan identifiera dig) eller bearbeta andra data som omfattas av lagar och andra efterföljandekrav.

1. I Personal, välj **Systemadministration**.

2. Välj panelen **funktionshantering**.

3. Aktivera en förhandsgranskningsfunktion genom att markera den i listan och sedan välja **Aktivera**. Inaktivera en förhandsgranskningsfunktion genom att markera den i listan och sedan välja **inaktivera**.

## <a name="enable-or-disable-benefits-management"></a>Aktivera eller inaktivera hantering av förmåner

Om du vill aktivera hantering av förmåner använder du samma procedur i [Aktivera eller inaktivera förhandsgranskningsfunktioner](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> När du har inaktiverat hantering av förmåner i miljön **produktion** efter att du har aktivera den. Du kan dock inaktivera hantering av miljöer i **begränsat läge**.

Mer information om hur du konfigurerar och använder en förmånshantering finn si [Översikt över förmånshantering](hr-benefits-management-overview.md).

Förmånshantering ersätter funktioner i arbetsytan **förmåner**. När du aktiverar funktionen för förhandsgranskning av förmånshantering kan du inte längre komma åt följande formulär på arbetsytan **förmåner**:

- **Förmåner**
- **Förmånselement**
- **Tariffer för lönetilläggsberäkning**
- **Resultat från förmånsanmälan**
- **Förmåner som upphör och resulterande förlängningar**
- **Policyregeltyper för förmånsberättigande**
- **Policyer för förmånsberättigande**
- **Berättigandehändelser**

Du kan visa informationen i dessa formulär i skrivskyddat läge. Om du vill redigera informationen måste du först inaktivera förmånshantering (gäller endast miljöer i **begränsat läge**).

## <a name="enable-or-disable-leave-and-absence"></a>Aktivera eller inaktivera tjänstledighet och frånvaro

Om du vill aktivera tjänstledighet och frånvaro använder du samma procedur i [Aktivera eller inaktivera förhandsgranskningsfunktioner](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> Du kan inte inaktivera funktionen **Flera tjänstledighetstyper** i tjänstledighet och frånvaro när du har aktiverat den. Detta gäller både miljöer i **begränsat läge** och **produktion**.

För mer information om förhandsgranskningsfunktioner för tjänstledighet och frånvaro, se [Förhandsgranskningsfunktioner för tjänstledighet och frånvaro](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

## <a name="send-us-feedback"></a>Skicka feedback

Vi vill gärna höra om din erfarenhet av dessa förhandsfunktioner. Vi rekommenderar att du regelbundet publicerar feedback på följande webbplatser när du använder dessa eller andra funktioner.

- [Gemenskap](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – webbplatsen är ett utmärkt verktyg där användare kan diskutera fall, ställa frågor och få hjälp från andra användare.
- Meddela oss om funktioner som du vill ska visas i produkten och även de ändringar som du tycker att vi ska göra av befintliga funktioner. Föreslå produktidéer om [personalidéer](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources).
    
Inkludera inte personuppgifter (all information som kan identifiera dig) i feedback eller produktomdömen. Insamlad information kan analyseras ytterligare och den används inte för att besvara frågor under tillämplig sekretesslagstiftning. Personuppgifter som samlas in separat under programmen som ingår i den [sekretesspolicyn för Microsoft ](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Se även

- [Nyheter i Personal](hr-admin-whats-new.md)
- [Utgivningsplan för Dynamics 365 och Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1)