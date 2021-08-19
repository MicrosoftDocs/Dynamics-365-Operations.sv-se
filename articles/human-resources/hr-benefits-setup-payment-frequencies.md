---
title: Ställa in betalningsfrekvenser
description: Microsoft Dynamics 365 Human Resources använder lönefrekvenser för att beräkna årliga inkomsten av förmånen, avgör vilket förmånsbelopp en medarbetare betalar varje betalningsperiod och definierar hur ofta betalningar görs till providers.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 738df6a31ec8e9f50259461cd7bbf30bd5c2b73c6f8a23ffacba53ab261a80ed
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732763"
---
# <a name="set-up-payment-frequencies"></a>Ställa in betalningsfrekvenser

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources använder lönefrekvenser för att beräkna årliga inkomsten av förmånen, avgör vilket förmånsbelopp en medarbetare betalar varje betalningsperiod och definierar hur ofta betalningar görs till providers.

Lönefrekvenser för förmåner använder konverteringsfaktorer för att konvertera perioder för lönefrekvenser mellan månad, halvår, varannan vecka, vecka och dag. Detta gör det möjligt för företag att definiera beroendet mellan lönefrekvenserna inom en förmånsplan.

Fälten konverteringsfaktorer identifierar konverteringsfaktorn från lönefrekvensen till standardbetalningsperioderna och gör att systemet kan utföra beräkningar mellan lönefrekvenser. Konverteringsfaktorns belopp används också för att bestämma vilket förmånsbidrag som en medarbetare ska betala per lönefrekvens.

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **Lönefrekvenser**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | **Lönefrekvens** | Ett unikt namn för lönefrekvensen. |
   | **Beskrivning** | Beskrivning av lönefrekvensen. |
   | **Period** | Den lämpliga period som bäst matchar förmånsleverantörens och medarbetarens lönefrekvens. Periodlistan består av standardbetalningsperioderna. |
   | **Antal betalningsperioder** | Antalet löneperioder som anger hur ofta förmånsleverantören eller medarbetarna betalas. Detta belopp kommer att användas för att beräkna medarbetarens årliga förmånsbelopp. |
   | **Årskonverteringsfaktor** | Den årliga konverteringsfaktorn för betalningsfrekvensen. Den årliga konverteringsfaktorn för månadsvis lönefrekvens är t.ex.: </br></br>(12 månadsbetalningar/1 år) = 12 |
   | **Halvårskonverteringsfaktor** | Den halvårliga konverteringsfaktorn för betalningsfrekvensen. Den halvårlig konverteringsfaktorn för månadsvis lönefrekvens är t.ex. </br></br>(12 månadsbetalningar/2 gånger per år) = 6 |
   | **Kvartalskonverteringsfaktor** | Den kvartalsvisa konverteringsfaktorn för betalningsfrekvensen. Den halvårlig konverteringsfaktorn för kvartalsvis lönefrekvens är t.ex.: </br></br>(12 månadsbetalningar/4 kvartal) = 3 |
   | **Månadskonverteringsfaktor** | Den månatliga konverteringsfaktorn för betalningsfrekvensen. Den årliga konverteringsfaktorn för månadsvis lönefrekvens är t.ex.: </br></br>(12 månadsbetalningar/12 månader) = 1 |
   | **Halvmånadskonverteringsfaktor** | Den halvmånadsvisa konverteringsfaktorn för betalningsfrekvensen. Den årliga konverteringsfaktorn för halvmånadsvis lönefrekvens är t.ex. </br></br>(12 månadsbetalningar/24 (2x en månad)) = 0,5 | 
   | **Tvåveckorskonverteringsfaktor** | Den årliga konverteringsfaktorn för betalningsfrekvensen. Den årliga konverteringsfaktorn för månadsvis lönefrekvens är t.ex.: </br></br>(12 månadsbetalningar/26 veckor) = 0,461538 |
   | **Veckokonverteringsfaktor** | Den årliga konverteringsfaktorn för betalningsfrekvensen. Den årliga konverteringsfaktorn för månadsvis lönefrekvens är t.ex.: </br></br>(12 månadsbetalningar/52 veckor) = 0,230769 |
   | **Dagskonverteringsfaktor** | Den årliga konverteringsfaktorn för betalningsfrekvensen. Den årliga konverteringsfaktorn för månadsvis lönefrekvens är t.ex.: </br></br>(12 månadsbetalningar/365 dagar) = 0,032877 |
   | **Timkonverteringsfaktor** | Den årliga konverteringsfaktorn för betalningsfrekvensen. Den årliga konverteringsfaktorn för månadsvis lönefrekvens är t.ex.: </br></br>(12 månadsbetalningar/2080 timmar) = 0,005769

4. Välj **Spara**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]