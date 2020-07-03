---
title: Periodisera planer för tjänstledighet och frånvaro
description: Du kan periodisera tjänstledighet och frånvaro i Dynamics 365 Human Resources för flera medarbetare eller för en person.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f045cb7ab9f5e7aa4259f29e1b026f110425c236
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429069"
---
# <a name="accrue-leave-and-absence-plans"></a>Periodisera planer för tjänstledighet och frånvaro

Du kan periodisera tjänstledighet och frånvaro i Dynamics 365 Human Resources för flera medarbetare eller för en person.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Periodisera tjänstledighet och frånvaro för flera medarbetare

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Hantera tjänstledighet**, välj **tjänstledighet och frånvaroplaner**.

3. Dialogrutan **Periodisera planer för tjänstledighet och frånvaro** visas. I **Accrue as of**, either select **Samla ihop från och med** eller välj **Anpassat datum** och ange ett anpassat datum.

4. Om du vill köra periodiseringsprocessen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:

   1. Ange information för periodiseringsprocessen.

   2. Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.

   3. Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.

   4. Välj **OK**. Periodiseringsprocessen kommer att köras med de parametrar du angett.

## <a name="accrue-leave-and-absence-for-an-employee"></a>Periodisera tjänstledighet och frånvaro för en medarbetare

1. Välj **tjänstledighet**för medarbetarens post.

2. Välj **Periodisera för tjänstledighet och frånvaro**.

3. Dialogrutan **Periodisera planer för tjänstledighet och frånvaro** visas. I **Accrue as of**, either select **Samla ihop från och med** eller välj **Anpassat datum** och ange ett anpassat datum.

4. Om du vill köra periodiseringsprocessen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:

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

1. Välj **tjänstledighet**för medarbetarens post.

2. Välj **Ta bort periodiseringar av plan för tjänstledighet och frånvaro**.

3. I dialogrutan **Ta bort periodiseringar av plan för tjänstledighet och frånvaro** och välj **Tjänstledighetsplan**. 

4. Om tillämpligt, välj **Ta bort saldojusteringar**.

5. Ange eller välj ett **periodiseringsdatum för tjänstledighet**. Detta datum måste vara antingen idag eller senare. 

6. Välj **OK**. Periodiseringsprocessen kommer att ta bort periodiseringar med de parametrar du angett. 

## <a name="review-leave-accrual-and-deletion-processes"></a>Granska processer för periodisering av tjänstledighet och borttagning

**Granskning av periodisering av tjänstledighet** visas varje gång du kör eller tar bort en periodisering för en eller alla medarbetare. Datumet och personen som utförde åtgärden visas också.

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Hantera tjänstledighet**, välj **Ta bort granskning av periodisering av tjänstledighet**.

## <a name="configure-preview-features"></a>Konfigurera förhandsfunktioner

[!include [banner](includes/preview-feature-leave-absence.md)]

Om du har aktiverat förhandsfunktioner för tjänstledighet och frånvaro, måste du också konfigurera inställningarna för dem.

### <a name="accrue-leave-per-company-or-per-leave-plan"></a>Periodisera tjänstledighet per företag eller per tjänstledighetsplan

När du ska periodisera planer för tjänstledighet och frånvaro kan du välja att periodisera för alla företag. Om du väljer alla företag kan du inte välja enskilda tjänstledighetsplaner. Om du väljer att inte periodisera för alla företag kan du periodisera för en viss tjänstledighetsplan. 

Dessa alternativ är tillgängliga när du periodiserar för alla medarbetare eller enskilda medarbetare. 

## <a name="see-also"></a>Se även

[Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)</br>
[Skapa en plan för tjänstledighet och frånvaro](hr-leave-and-absence-plans.md)
