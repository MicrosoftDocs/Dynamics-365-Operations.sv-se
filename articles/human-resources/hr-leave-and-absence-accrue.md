---
title: Periodisera planer för tjänstledighet och frånvaro
description: Du kan periodisera tjänstledighet och frånvaro i Dynamics 365 Human Resources för flera medarbetare eller för en person.
author: twheeloc
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7f765e7cfd97170bd144dfff12c18ced96e3332a
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2022
ms.locfileid: "8533724"
---
# <a name="accrue-leave-and-absence-plans"></a>Periodisera planer för tjänstledighet och frånvaro

>[!Important]
>Funktionen som anges i det här avsnittet är för närvarande tillgänglig för kunder med fristående Dynamics 365 Human Resources. Vissa eller alla funktionerna kommer att vara tillgängliga i en kommande version av Finance-infrastrukturen efter Finance version 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan periodisera tjänstledighet och frånvaro i Dynamics 365 Human Resources för flera medarbetare eller för en person.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Periodisera tjänstledighet och frånvaro för flera medarbetare

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Hantera tjänstledighet**, välj **tjänstledighet och frånvaroplaner**.

3. Dialogrutan **Periodisera planer för tjänstledighet och frånvaro** visas. I **Accrue as of**, either select **Samla ihop från och med** eller välj **Anpassat datum** och ange ett anpassat datum.

4. Om du vill köra periodiseringar för alla företag väljer du **alla företag**. Om du vill bearbeta periodiseringar för en enda tjänstledighetsplan väljer du **Nej** för **Alla planer** och väljer sedan en **Tjänstledighetsplan**. Om du väljer alla företag kan du inte välja en enskild tjänstledighetsplan.

5. Om du vill köra periodiseringsprocessen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:

    1. Ange information för periodiseringsprocessen.
    2. Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.
    3. Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.
    4. Välj **OK**. Periodiseringsprocessen kommer att köras med de parametrar du angett. 

## <a name="accrue-leave-and-absence-for-an-employee"></a>Periodisera tjänstledighet och frånvaro för en medarbetare

1. Välj **tjänstledighet** för medarbetarens post.

2. Välj **Periodisera för tjänstledighet och frånvaro**.

3. Dialogrutan **Periodisera planer för tjänstledighet och frånvaro** visas. I **Accrue as of**, either select **Samla ihop från och med** eller välj **Anpassat datum** och ange ett anpassat datum.

4. Om du vill köra periodiseringar för alla företag väljer du **alla företag**. Om du vill bearbeta periodiseringar för en enda tjänstledighetsplan väljer du **Nej** för **Alla planer** och väljer sedan en **Tjänstledighetsplan**. Om du väljer alla företag kan du inte välja en enskild tjänstledighetsplan.

5. Om du vill köra periodiseringsprocessen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:

   1. Ange information för periodiseringsprocessen.

   2. Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.

   3. Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.

   4. Välj **OK**. Periodiseringsprocessen kommer att köras med de parametrar du angett.

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a>Ta bort periodiseringar av tjänstledighet och frånvaro för flera medarbetare

Ta bort periodiseringsposter för ett specifikt plan- och datumintervall. Periodiseringsdatum måste vara daterade i dag eller i framtiden.

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Hantera tjänstledighet**, välj **Ta bort periodiseringar av plan för tjänstledighet och frånvaro**.

3. I dialogrutan **Ta bort periodiseringar av plan för tjänstledighet och frånvaro** och välj **Tjänstledighetsplan**.

4. Om tillämpligt, välj **Ta bort saldojusteringar**.

5. Ange eller välj ett **periodiseringsdatum för tjänstledighet**. Detta datum måste vara antingen idag eller senare.

6. Välj **OK**. Periodiseringsprocessen kommer att ta bort periodiseringar med de parametrar du angett.

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a>Ta bort periodiseringar av tjänstledighet och frånvaro för en medarbetare

1. Välj **tjänstledighet** för medarbetarens post.

2. Välj **Ta bort periodiseringar av plan för tjänstledighet och frånvaro**.

3. I dialogrutan **Ta bort periodiseringar av plan för tjänstledighet och frånvaro** och välj **Tjänstledighetsplan**.

4. Om tillämpligt, välj **Ta bort saldojusteringar**.

5. Ange eller välj ett **periodiseringsdatum för tjänstledighet**. Detta datum måste vara antingen idag eller senare.

6. Välj **OK**. Periodiseringsprocessen kommer att ta bort periodiseringar med de parametrar du angett.

## <a name="review-leave-accrual-and-deletion-processes"></a>Granska processer för periodisering av tjänstledighet och borttagning

**Granskning av periodisering av tjänstledighet** visas varje gång du kör eller tar bort en periodisering för en eller alla medarbetare. Datumet och personen som utförde åtgärden visas också.

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Hantera tjänstledighet**, välj **Ta bort granskning av periodisering av tjänstledighet**.

## <a name="leave-accrual-transaction-auditing"></a>Granskning av periodiseringstransaktion för tjänstledighet

Den här funktionen hjälper lediga och frånvaroansvariga att förstå transaktioner för periodiseringar för frånvaro och transaktioner relaterade till en anställds lediga saldon för en specifik semester.

För att visa transaktionsdetaljer:

1. Välj **tjänstledighet** för medarbetarens post.

2. Välj **Visa ledighet** och välj fliken **Saldon**.

Om du vill visa periodiseringstransaktionerna för en viss tjänstledighetstyp väljer du numeriskt värde i kolumnen **Aktuell balans**.

Om du vill visa transaktionsdetaljer för ett visst periodiseringsbelopp markerar du en periodiseringsrad, öppnar panelen **Relaterad information** till höger och öppnar sedan avsnittet **Transaktionsinformation**. Avsnittet Transaktionsdetaljer visar:

- Ändringar av medarbetarens saldo för tjänstledighetstyp
- Anställningsdetaljer för den angivna periodiseringsperioden
- Detaljer om periodiseringsperiod och periodiseringssatser
- Ändringar som gjorts för att lämna plankonfigurationer

![Visa granskning av periodiseringstransaktion för tjänstledighet.](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a>Se även

[Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)</br>
[Skapa en plan för tjänstledighet och frånvaro](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
