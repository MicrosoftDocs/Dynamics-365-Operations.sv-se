---
title: Skapa ett teamkalender
description: Visa och skapa teamkalendrar i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 07c7f1303238fe61d70be26ec5a198f1ac489090
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790774"
---
# <a name="view-team-and-company-calendars"></a>Visa team- och företagskalendrar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan visa team- och företagskalendrar i Dynamics 365 Human Resources. Endast teamkalendrar visar direktrapporter, enligt definitionen i den här radstrukturen.

## <a name="view-your-team-calendar-as-an-employee"></a>Visa teamkalendern som en medarbetare

1. I arbetsytan **Självbetjäning för medarbetare** väljer du **Frånvarokalender för team** under **Sammanfattning**.

## <a name="view-your-team-calendar-as-a-manager"></a>Visa teamkalendern som en chef

1. I arbetsytan **Självbetjäning för medarbetare** välj **Mitt team**.

2. Välj **Tjänstledighet och frånvaro** och välj sedan **Visa frånvarokalender för chef**.

Chefer kan också komma åt teamkalendern från **Väntande ledighetsansökningar för mitt team**, **Godkänd ledighet** och **Ledighetsansökningar**. 

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

Kalenderkonfiguration i tjänstledighets- och frånvaroparametrar bestämmer tillgängliga visningsalternativ.

Du kan även filtrera kalendern efter chef eller avdelning. Den primära befattningstilldelningen avgör vilka medarbetare som visas när dessa filter ställs in. 

>[!IMPORTANT]
>Att visa tjänstledighet och frånvaro för alla företag är för närvarande i förhandsgranskning. Du måste aktivera den i **sandbox-miljön**. Mer information om att aktivera förhandsfunktioner finns i [Hantera funktioner](hr-admin-manage-features.md).<br><br>
>Sedan måste du aktivera funktionen i **delade personalparametrar** för att visa filtret för juridisk person i kalendrar. Mer information finns i [Konfigurera parametrar för tjänstledighet och frånvaro](hr-leave-and-absence-parameters.md).<br><br>
>Du kan filtrera kalendern per juridisk person. Om du vill visa alla medarbetare oavsett juridisk person avmarkerar du filterrutan och trycker på RETUR. 

Information om kalenderinställningar finns i [konfigurera kalenderparametrar](hr-leave-and-absence-parameters.md?configure-calendar-parameters)



[!INCLUDE[footer-include](../includes/footer-banner.md)]