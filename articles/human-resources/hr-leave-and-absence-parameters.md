---
title: Konfigurera tjänstledighets- och frånvaroparametrar
description: Definiera personalparametrar för tjänstledighet och frånvaro i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eb992cbfbed33f88e125d3a8b721f8815414599a
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2020
ms.locfileid: "3197991"
---
# <a name="configure-leave-and-absence-parameters"></a>Konfigurera tjänstledighets- och frånvaroparametrar

Innan du ställer in tjänstledighets- och frånvaroplan i Dynamics 365 Human Resources kan det vara en bra idé att kontrollera inställningarna för alla relaterade personalparametrar, t.ex.:

- Nummerserie för tjänstledighetsansökan
- Inställning av Family Medical and Leave Act (FMLA)
- Inställningar för självbetjäning för medarbetare för tjänstledighets- och frånvaroansökningar
- Parametrar för tjänstledighet och frånvaro

## <a name="view-and-change-human-resources-parameters"></a>Visa och ändra personalparametrar

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Inställningar**, välj **Personalparametrar**.

3. På fliken **nummerserier** kontrollerar du **nummerseriekod** för **begäran om tjänstledighet-ID** och ändrar vid behov. Den här inställningen avgör vilken sekvens som används för automatiskt tilldelning av ID:n för att lämna förfrågningar.

4. På fliken **FMLA** kontrollera FMLA-inställningar och ändra efter behov.

5. På fliken **Självbetjäning för medarbetare** anger du om chefer kan ange tjänstledighets- och frånvaroansökningar för medarbetarnas räkning.

6. På fliken **tjänstledighet och frånvaro** kontrollera inställningar och ändra efter behov.

7. Välj **Spara**.

## <a name="view-and-change-leave-and-absence-parameters"></a>Visa och ändra parametrar för ledighet och frånvaro

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Inställningar**, välj **Parametrar för tjänstledighet och frånvaro**.

3. Ange följande parametrar på fliken **Allmänt**:
 
    - Ställ in **Enhet för tjänstledighet och frånvaro** till antingen timmar eller dagar. Om dagar kan du välja **aktivera halvdags definition** om du vill tillåta att medarbetare väljer antingen första eller andra halvan av dagen i sina ledighetsbegäran. 

    - Välj **tjänstmånaders giltighetsdatum** om du vill ange när periodiseringspriser ska gälla för tjänstledighetsplaner med hjälp av tjänstmånader.

    - Välj **saldoberäkning** om du vill visa saldon som visas från och med den period som ska periodiseras. Om du väljer **saldo från idag** visar saldot summan av alla periodiseringar, justeringar och begäranden från och med idag. Om du väljer **saldo för en periodiseringsperiod**, visar saldot summan av alla periodiseringar, justeringar och förfrågningar per den periodiseringsperiod som definieras av frekvensen i planen för tjänstledighet. 

## <a name="configure-calendar-parameters"></a>Konfigurera kalenderparametrar

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Inställningar**, välj **Parametrar för tjänstledighet och frånvaro**.

3. På fliken **Kalender** ändra kalenderinställningar och efter behov.

4. Välj **Spara**.

## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)
