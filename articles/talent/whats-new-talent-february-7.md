---
title: Nyheter och ändringar i Dynamics 365 Talent (7 februari 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 002dcd8253a0ab753ac9002e7027441db6d0b858
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462610"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-7-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (7 februari 2019)

Det här ämnet beskriver nya eller ändrade funktioner i Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

### <a name="interview-scheduling-enhancements"></a>Förbättring av tidsplanering av intervjuer
Förbättringar har gjorts i tidsplanering för slutpunkt till slutpunkt-intervju. Du kan nu se kalendertillgängligheten för en intern kandidat och använda interna kandidaters kalender för schemarekommendationer. Mer information finns i [Intervjuplanering och feedback](interview-scheduling-feedback.md).

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a>Jobbpublicering på LinkedIn – företagets matchningsfel har korrigerats
Ett problem har åtgärdats där jobb som publicerades på LinkedIn från Attract visades under fel företagsnamn. Mer information finns i [skapa, godkänna och publicera projekt i Attract](creating-jobs-attract.md).

### <a name="career-site-url-displayed-in-admin-settings"></a>Karriärwebbplatsens URL visas i administrationsinställningar
Karriärwebbplatsens startside-URL visas i **administrationsinställningar** under **Hantera karriärwebbplats**.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

**Skapa 8.1.2134**

### <a name="multiple-compensation-levels-supported-on-jobs"></a>Flera kompensationsnivåer som stöds för jobb
Ändringen tillåter att mer än en kompensationsnivå definieras för ett projekt, vilket tillåter medarbetarens fasta kompensationsintervall som kan variera mellan planer när du använder samma jobb. 

Exempel:    
*Jobb* - Kontohanterare *Associerade kompensationsnivåer:* B1 och B2 - varje nivå har ett definierat värdeintervall. B1 = Min 50 000, Mellan 60 000, Max 75 000 and B2 = Min 65 000, Mellan 74 000, Max 85 000. När du skapar en fast kompensation för medarbetare utifrån definierade berättiganderegler pekar varje fast plan nu på samma jobb och på olika nivåer för jobbet. Detta tillåter att planer definieras i olika regioner/företag och pekar på samma jobb men olika intervall utan att duplicera jobb för att redovisa dessa skillnader.

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a>Fält för kompensationsnivåer har lagts till i entiteten medarbetarens fasta kompensation 
Med den här uppdateringen har entiteten medarbetarens fasta kompensation uppdaterats med fältet **kompensationsnivå**. Detta gör det enklare att uppdatera medarbetarens fasta kompensationsplaner. 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a>Uppdatera jobbfamilj vid uppdatering och skapande av nya befattningar
När du byter jobb på en befattning kommer nu **jobbfamilj** användas som standard baserat på det jobb som valts.

### <a name="performance-improvements-when-rendering-workspaces"></a>Prestandaförbättringar vid återgivning av arbetsytor
Analysflikar på arbetsytor läses nu bara vid åtkomst till sidorna. En indikator visas under den första återgivningen av sidan i det övre vänstra hörnet på sidan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]