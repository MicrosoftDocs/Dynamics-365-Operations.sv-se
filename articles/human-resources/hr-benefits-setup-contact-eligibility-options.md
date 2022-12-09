---
title: Konfigurera berättigandealternativ för personlig kontakt
description: Detta ämne förklarar hur du konfigurerar berättigande alternativ för personliga kontakter i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e3e393002901f31c035a54bd8036ed20ecdf9e00
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803895"
---
# <a name="configure-personal-contact-eligibility-options"></a>Konfigurera berättigandealternativ för personlig kontakt


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Det här ämnet förklarar hur du konfigurerar de typer av personliga kontakter som kan användas i förmåner i Microsoft Dynamics 365 Human Resources. Personliga kontakter är de personer som omfattas av dina planer (beroende) eller som kan dra fördel av dina planer (förmåner). Beroende är vanligtvis make/maka eller barn. Det kan vara make/maka, barn, förtroenden eller underhålls.

1. I arbetsytan **olämplig** under **inställningar**, välj **Berättigandealternativ för personlig kontakt**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | **Berättigandealternativ** | Ett unikt namn eller en kod som identifierar alternativet för berättigande. |
   | **Beskrivning** | En kort beskrivning av berättigandealternativet. |
   | **Berättigandekod för kontakt** | Den systemkod som bäst beskriver det personliga berättigandealternativet. Du kan välja mellan: <ul><li>Relation</li><li>Student</li><li>Överårig beroende</li><li>Överårig funktionshindrad beroende</li></ul> |
   | **Status** | Status för berättigandealternativet. Om status för ett alternativ är inaktiverad kan du inte välja det personliga kontaktalternativet för personliga kontakter. |
   | **Relation** | Anger relationen mellan den personliga kontakten och medarbetaren. Det här fältet är endast aktivt om kontakt villkorskoden är inställd på relation. |
   | **Ålder** |Anger maximal ålder för en berättigad personlig kontakt för förmånsplanen. Det här fältet är bara aktivt om du väljer en relation. Denna ålder jämförs med den beräknade åldern för den personliga kontakten. Beräknad ålder är: (täckningsdatum – personliga kontaktens födelsedatum/365). Det här talet är alltid ett heltal.
För kontaktalternativet **Överårig beroende personlig** är åldersgränsen i det här fältet minimiåldern. Om t.ex. ålder har satts till 18 för alternativet **Överårig beroende** kommer de beroende som är markerade som överåriga beroende och är 18 år eller äldre omfattas av berättigandealternativet.  |

4. Välj **Spara**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
