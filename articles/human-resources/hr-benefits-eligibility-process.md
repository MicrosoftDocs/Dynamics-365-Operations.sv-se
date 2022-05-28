---
title: Bearbeta förmånsberättigande
description: Den här proceduren visar hur förmånsberättigandeprocessen fungerar.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 61818ad8d397fe2b61952003aa562818c4bad2f5
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687713"
---
# <a name="benefit-eligibility-process"></a>Bearbeta förmånsberättigande


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Den här proceduren visar hur förmånsberättigandeprocessen fungerar. När processen är klar kan du visa resultaten. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till **Personal \> Förmåner \> Förmåner**.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på önskad rad i valda listan.
4. Välj **Redigera**.
5. I fältet **Berättigande** väljer du **Regelbaserat**.
6. I fältet **Regeltyp** väljer du den policyregel för förmån som du vill tillämpa på förmånen.
7. I åtgärdsfönstret väljer du **Förmån**.
8. Välj **Skapa berättigandehändelse**.
9. I listrutan anger du ett värde i fältet **Händelse**.
10. I fältet **Beskrivning** anger du ett värde.
11. I fältet **Händelsetyp** väljer du **Öppna registering**.
12. I fältet **Startdatum för disponering** anger du datum och tid.
13. I fältet **Startdatum för registreringsperiod** anger du datum och tid.
14. I fältet **Dagar till registrering** anger du ett nummer.
15. Välj **Skapa händelse**.
16. På snabbfliken **Medarbetare** väljer du **Lägg till**.
17. I fältet **Visa efter typ** väljer du **Anställda**.
18. I fältet **Visa efter juridisk person** väljer du **Aktuell juridisk person**.
19. Markera eller avmarkera alla rader i listan.
20. Välj **OK**.
21. Välj **Process**.
22. Välj **OK**.
23. Uppdatera sidan.
24. Välj **Visa resultat**.
25. Öppna kolumnfiltret **Status**.
26. Sortera kolumnen från A till Z.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
