---
title: Skapa ett teamkalender
description: Visa och skapa teamkalendrar i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eacf2dc460367ebefb7e9f4d9e301ec719cd2317
ms.sourcegitcommit: a8ac6d9b63eb67d14dd17a086ef4f1eccd7f9fc1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2021
ms.locfileid: "7431496"
---
# <a name="view-team-and-company-calendars"></a>Visa team- och företagskalendrar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan visa team- och företagskalendrar i Dynamics 365 Human Resources. Endast teamkalendrar visar direktrapporter, enligt definitionen i den här radstrukturen.

## <a name="view-your-team-calendar-as-an-employee"></a>Visa teamkalendern som en medarbetare

- I arbetsytan **Självbetjäning för medarbetare** väljer du **Frånvarokalender för team** under **Sammanfattning**.

## <a name="view-your-team-calendar-as-a-manager"></a>Visa teamkalendern som en chef

1. I arbetsytan **Självbetjäning för medarbetare** välj **Mitt team**.

2. Välj **Tjänstledighet och frånvaro** och välj sedan **Visa frånvarokalender för chef**.

Chefer kan också komma åt teamkalendern från **Väntande ledighetsansökningar för mitt team**, **Godkänd ledighet** och **Ledighetsansökningar**. 

## <a name="view-your-absence-manager-calendar-as-the-absence-manager"></a>Visa din kalender för frånvaroansvarig som frånvaroansvarig

> [!NOTE]
> Om du vill visa kalendern för frånvaroansvarig måste du först aktivera funktionen **(förhandsgranska) Frånvarohanteraren för att hantera tjänstledighet** i Funktionshantering. Mer information om hur du aktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

Användare med rollen Frånvaroansvarig kan visa ledighetsansökningar i sin kalender. Följ dessa steg för att komma till ledighetskalendern.

1. I arbetsytan **Självbetjäning för medarbetare**, välj **Tjänstledighetshantering** och sedan **Frånvaroansvarigkalendern**.

2. I fältet **Datum** anger du önskade datum.

3. Uppdatera visningsalternativen efter behov.

I frånvaroansvarigkalendern visas alla poster för medarbetarna som rapporterar till frånvarochefen i tjänstledighetshierarki.

## <a name="view-a-company-calendar"></a>Visa en företagskalender

Personer som är i personalroller kan visa företagskalendrar. Företagskalendrar visar alla medarbetare. Som standard visas dagens datum plus 28 dagar i kalendern, men du kan ändra datumintervallet. Du kan också filtrera kalendern efter **namn**, **personalnummer** och **tjänstledighetstyp**.

1. I arbetsytan **tjänstledighet och frånvaro** välj fliken **länken**.

2. Välj **Tjänstledighet och kalender**.

Personalroller kan också få åtkomst till företagskalendern från **Begäran om tjänstledighet och frånvaro**, **Godkänd ledighet** och **Ledighetsansökningar**. 

Kalendrar innehåller nu ytterligare filter och alternativ. Alla kalendrar inkluderar visningsalternativ för:

- Godkända begäran
- Väntande begäranden
- Medarbetare med tjänstledighetsbegäran
- Medarbetare utan tjänstledighetsbegäran
- Medarbetarnas födelsedagar
- Ansökningar om ledighet 
- Tjänstledighetsansökningar

Kalenderkonfiguration i på sidan **Tjänstledighets- och frånvaroparametrar** bestämmer tillgängliga visningsalternativ.

Du kan även filtrera kalendern efter chef eller avdelning. Den primära befattningstilldelningen avgör vilka medarbetare som visas när dessa filter ställs in. 

> [!IMPORTANT]
> Du kan aktivera funktionen **företagsövergripande tjänstledighet** i funktionshanteringen. Sedan måste du aktivera funktionen på sidan **delade personalparametrar** för att visa filtret för juridisk person i kalendrar. Mer information finns i [Konfigurera parametrar för tjänstledighet och frånvaro](hr-leave-and-absence-parameters.md).
> 
> Du kan filtrera kalendern per juridisk person. Om du vill visa alla medarbetare oavsett juridisk person avmarkerar du filterrutan och trycker på **Retur**. 

Information om kalenderinställningar finns i [konfigurera kalenderparametrar](hr-leave-and-absence-parameters.md?configure-calendar-parameters)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
