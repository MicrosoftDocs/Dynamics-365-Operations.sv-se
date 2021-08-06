---
title: Klar att betalas
description: I det här avsnittet visas hur du markerar en medarbetare som redo att betalas i Dynamics 365 Human Resources.
author: marcelbf
ms.date: 07/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f9aa9e60b51b1801c07981ad120cb77f65fee286
ms.sourcegitcommit: baad2723291774f610324a8054fc14abf3287fe1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2021
ms.locfileid: "6560129"
---
# <a name="ready-to-pay"></a>Klar att betalas

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

> [!NOTE]
> Om du vill markera en medarbetare som redo att betala måste du först aktivera funktionen för **(Förhandsgranska) löneintegrering** i funktionshanteringen. Mer information om hur du aktiverar förhandsfunktioner finns i [Hantera funktioner](hr-admin-manage-features.md).

Med denna funktion kan personalmän förstå vilka medarbetare som är klara för lönebearbetning och vilka åtgärder som måste vidtas innan de förbrukas av en tredje part av löneförmedlare.

## <a name="mark-employee-as-ready-to-pay"></a>Markera medarbetaren som redo att betala

Det kan vara tidskrävande och fel att samla in och validera medarbetarinformation. Genom att tillhandahålla ett sätt för personal på personal att granska och enkelt uppdatera personalinformation, Dynamics 365 Human Resources hjälper till att minska tiden som görs redo att bearbeta löner.

Markera en medarbetare som betalningsredo:

1. Öppna **Kompensationshantering**. Det finns två paneler i arbetsytan 
    - **Medarbetare som är klara att betalas**
    - **Medarbetare som inte är redo att betala**
    ![Arbetsytan kompensationshantering.](./media/hr-ready-to-pay-1-workspace.png)

2. Välj panelen **Medarbetare som inte är redo att betala**.

3. Välj de medarbetare som ska valideras. På fliken **Lön**, i gruppen **Klar att betala**, välj **Validera**.
    ![Validera medarbetare.](./media/hr-ready-to-pay-2-validate.png)

4. Det finns två paneler på fliken **Lön**, i gruppen **Klar att betala**, välj **Resultat**.

## <a name="validation"></a>Validering

Innan en medarbetare markeras som redo att betalas gör systemet en grundläggande validering av profilfärdigheten.

![Validera resultaten.](./media/hr-ready-to-pay-3-results.png)

Följande tabell ger information om var och en av de valideringar som utförs. 

| Validering | Information |
| --- | --- |
| Ändamålsparameter för adress | Validerar om parametern **Använd löneadresser** är på. |
| Löneadress | Validerar om arbetarprofilen har minst en adress med syftet "Lönebostad" eller "Lönearbetsplats", och det bara finns en adress per syfte. |
| Anställning | Verifiera om arbetaren har minst en anställning (aktuell, tidigare eller framtida). |
| ID-nummer | Validerar om parametern "Använd identifieringstyper i lönebearbetning" är Ja, och om identifieringstypen som anges i parametern har fyllts i i arbetsprofilen. |
| För- och efternamn | Validerar om arbetsprofilen är giltig och kontrollerar om fälten **Namn** och **Efternamn** har fyllts i.|
| Plats | Verifiera om arbetaren har en tilldelad befattning. |
| Födelsedatum | Validerar om arbetsprofilen är giltig och kontrollerar om fältet **Födelsedag** har fyllts i. |
| Kompensation | Kontrollera om arbetaren är anmäld till en fast kompensationsplan. |

Om en av dessa valideringar misslyckas kan du inte markera medarbetaren som redo att betala.

Om fältet **Klar att betala** är **Nej**, är detta är en indikation på att du måste utföra en åtgärd för att säkerställa att arbetarprofilen är fullständig. Detta stoppar inte de data som visas i någon dataenhet. 

## <a name="known-issues"></a>Kända problem

- Du måste inaktivera funktionen **Strömlinjeformad medarbetarpost** i funktionshanteringen. Det som gör att arbetsytan för kompensationshantering inte fungerar som den ska om du använder den här funktionen.
- I arbetsformuläret är gruppen **fliken Lön**, **Klar att betala** tillgänglig för alla användarroller. 

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
