---
title: Konfigurera berättigandealternativ för personlig kontakt
description: Konfigurera berättigande alternativ för personliga kontakter i Microsoft Dynamics 365 Human Resources. Personliga kontakter kan vara mottagare eller beroende.
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
ms.openlocfilehash: d85677973f67f0c68de6c5ede62c142524939833
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054414"
---
# <a name="configure-personal-contact-eligibility-options"></a>Konfigurera berättigandealternativ för personlig kontakt

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I den här artikeln beskrivs hur du konfigurerar olika typer av personliga kontakter att använda i förmåner i Microsoft Dynamics 365 Human Resources. Personliga kontakter kan vara mottagare eller beroende. 

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