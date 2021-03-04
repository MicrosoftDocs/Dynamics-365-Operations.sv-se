---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (27 november 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/27/2018
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
ms.search.validFrom: 2018-11-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1d6b5f5f7b62c400679df5eb014dee05f02e11d0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462569"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-november-27-2018"></a>Nyheter och ändringar i Dynamics 365 Talent - Core HR (27 november 2018)

**Skapa 8.1.2064**

Det här ämnet beskriver nya eller ändrade funktioner i Core HR.


## <a name="changes"></a>Ändringar

### <a name="unable-to-create-a-note-in-case-management"></a>Det gick inte att skapa en anteckning i Ärendehantering

En ändring har gjorts för ett problem vid försök att redigera eller skapa en anteckning i ärendehanteringens ärendelogg.

### <a name="misspelled-word-on-the-analytics-tab-in-the-compensation-workspace"></a>Felstavade ord på fliken analys i kompensationsarbetsytan 

En ändring har gjorts för att korrigera stavningen av "Etniskt ursprung" i diagrammet för kompensationsanalyser i kompensationsarbetsytan.

### <a name="employee-self-service-workspace-not-displaying-when-a-user-isnt-assigned-to-a-worker"></a>Medarbetarens självbetjäningsarbetsyta visas inte när en användare inte tilldelats en arbetare 

En ändring har gjorts när arbetsytan **Självbetjäning för medarbetare** markeras som startsida vid starten för en användare som inte har tilldelats en arbetare. I det här fallet visas standardinstrumentpanel.

### <a name="leave-and-absence-error-object-reference-not-set-to-an-instance-of-an-object"></a>Fel i Tjänstledighet och frånvaro: objektreferensen anges inte till en instans av ett objekt

Ändringar har gjorts i Tjänstledighet och frånvaro för att korrigera felet när du godkänner ledighet och frånvaro av posterna i listan **Arbetsuppgifter som har tilldelats mig**.

### <a name="unable-to-recall-an-image-workflow"></a>Det går inte att återkalla arbetsflödet för en bild

Efter att ha återkallat ett bildflöde kommer arbetsflödet att ställas in till "annullerat" och den befintliga förfrågan kan raderas i arbetsytan för självbetjäning för medarbetare.

### <a name="rehired-employees-or-contractors-show-up-multiple-times-after-termination"></a>Återanställda medarbetare eller leverantörer visas upprepade gånger efter uppsägning 

Med denna uppdatering visas uppsagda medarbetare är återanställda endast en gång i listan avslutade. 

## <a name="known-issue"></a>Kända problem

- **Problem**: när du lägger till en ny bilaga till en arbetare blir knapparna **Ny** och **Redigera** nedtonade. 
- **Lösning:** innan du öppnar bilagesidan, kontrollera att faktaboxar på sidan **Arbetare** är stängda. Om faktarutorna är stängda när sidan **arbetare** hämtas kommer knapparna för bifogade filer att aktiveras. (Det här problemet kommer att åtgärdas i nästa plattformsuppdatering.)


[!INCLUDE[footer-include](../includes/footer-banner.md)]