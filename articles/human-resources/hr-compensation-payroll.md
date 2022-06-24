---
title: Klar att betalas
description: I den här artikeln visas hur du markerar en medarbetare som redo att betalas i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 81c73584e3567d620292227ce4a24c3c0945fa96
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862871"
---
# <a name="ready-to-pay"></a>Klar att betalas


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

> [!NOTE]
> Om du vill markera en medarbetare som redo att betala måste du först aktivera funktionen för **(Förhandsgranska) löneintegrering** i funktionshanteringen. Mer information om hur du aktiverar förhandsfunktioner finns i [Hantera funktioner](hr-admin-manage-features.md).

Med denna funktion kan personalmän förstå vilka medarbetare som är klara för lönebearbetning och vilka åtgärder som måste vidtas innan de förbrukas av en tredje part av löneförmedlare.

## <a name="mark-employee-as-ready-to-pay"></a>Markera medarbetaren som redo att betala

Det kan vara tidskrävande och fel att samla in och validera medarbetarinformation. Genom att tillhandahålla ett sätt för personal på personal att granska och enkelt uppdatera personalinformation, Dynamics 365 Human Resources hjälper till att minska tiden som görs redo att bearbeta löner.

Markera en medarbetare som betalningsredo:

1. Öppna **Kompensationshantering**. Det finns två paneler i arbetsytan: 
    - **Medarbetare som är klara att betalas**
    - **Medarbetare som inte är redo att betala**
    ![Arbetsytan kompensationshantering.](./media/hr-ready-to-pay-1-workspace.png)

2. Välj panelen **Medarbetare som inte är redo att betala**.

3. Välj de medarbetare som ska valideras. På fliken **Lön**, i gruppen **Klar att betala**, välj **Validera**.
    ![Validera medarbetare.](./media/hr-ready-to-pay-2-validate.png)

4. Det finns två paneler på fliken **Lön**, i gruppen **Klar att betala**, välj **Resultat**.

## <a name="validation"></a>Validering

Innan en medarbetare markeras som redo att betalas medarbetarens profil valideras för fullständighet.

![Validera resultaten.](./media/hr-ready-to-pay-3-results.png)

| Validering | Information |
| --- | --- |
| **Ändamålsparameter för adress** | Bekräfta parametern **Använd löneadresser** väljs. |
| **Löneadress** | Bekräftar om arbetarprofilen har minst en adress med syftet **Lönebostad** eller **Lönearbetsplats** och det bara finns en adress per syfte. |
| **Anställning** | Bekräfta om arbetaren har minst en anställning (aktuell, tidigare eller framtida). |
| **ID-nummer** | Bekräfta fältet **Använd identifieringstyper i lönebearbetning** är **Ja** på sidan **personalparametrar** och om identifikationstypen som anges i parametern fylls i arbetarprofilen. |
| **För- och efternamn** | Bekräftar att fälten **Namn** och **Efternamn** har fyllts i.|
| **Plats** | Bekräfta om arbetaren har en tilldelad befattning. |
| **Födelsedatum** | Bekräftar att fältet **Födelsedag** har fyllts i. |
| **Kompensation** | Bekräfta om arbetaren är anmäld till en fast kompensationsplan. |

Om en av dessa valideringar misslyckas kan du inte markera medarbetaren som redo att betala.

Om fältet **Klar att betala** är **Nej**, är detta är en indikation på att du måste utföra en åtgärd för att säkerställa att arbetarprofilen är fullständig. Detta stoppar inte de data som visas i någon dataenhet. 

## <a name="process-automation"></a>Processautomatisering

Du kan automatisera valideringen av alla medarbetare genom att använda [Processautomatisering](/dynamics365/fin-ops-core/dev-itpro/sysadmin/process-automation). I arbetsytan **Kompensationshantering**, gå till **Länkar** \> **Parametrar** \> **Processautomatisering**.

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
