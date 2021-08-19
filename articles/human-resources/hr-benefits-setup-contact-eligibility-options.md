---
title: Konfigurera berättigandealternativ för personlig kontakt
description: Konfigurera berättigande alternativ för personliga kontakter i Microsoft Dynamics 365 Human Resources. Personliga kontakter kan vara mottagare eller beroende.
author: andreabichsel
ms.date: 06/25/2021
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
ms.openlocfilehash: 50f290bbf53c70a7b33d061aaa80a9a1b3583d2c0fc2bb15f31f877b611187cd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735385"
---
# <a name="configure-personal-contact-eligibility-options"></a>Konfigurera berättigandealternativ för personlig kontakt

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
   | **Ålder** | Maximal ålder för en berättigad personlig kontakt för förmånsplanen. Det här fältet är bara aktivt om du väljer en relation. Denna ålder jämförs med den beräknade åldern för den personliga kontakten. Beräknad ålder är: (täckningsdatum – personliga kontaktens födelsedatum/365). Det här talet är alltid ett heltal. |

4. Välj **Spara**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
