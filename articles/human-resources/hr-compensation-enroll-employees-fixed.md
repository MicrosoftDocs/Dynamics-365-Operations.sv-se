---
title: Registrera en medarbetare i en fast kompensationsplan
description: Chefen över kompensationer och förmåner kan tilldela medarbetare till fasta kompensationsplaner för att hantera deras grundlön.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b7c2423faa4a0c50d9d319a9e6f489e2946c36a7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071596"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>Registrera en medarbetare i en fast kompensationsplan


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Chefen över kompensationer och förmåner kan tilldela medarbetare till fasta kompensationsplaner för att hantera deras grundlön. I den här proceduren förutsätts att en fast plan har skapats och är aktiv, och att berättiganderegler har angetts för planen. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Gå till **Personl** > **Arbetare** > **Medarbetare** > **Kompensation** > **Fast plan** för att starta proceduren.

1. Klicka på **Ny**.
2. I fältet **Åtgärd** välj en åtgärd för fast kompensation av typen **Anställ/återanställ** för att beskriva ändringen av en medarbetares kompensation.
3. Klicka på länken på den valda raden i listan.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Befattning**.
5. Klicka på länken på den valda raden i listan.
    * Nivån som visas kommer från fältet **Kompensation** Snabbflik > **Nivå** från **Jobb** som tilldelats **Befattningen**. Nivån måste anges för jobbet innan kompensation kan tilldelas till medarbetaren.  
6. Välj den fasta kompensationsplanen för medarbetaren i fältet **Plan**. **Plan**-uppslagningen filtreras för att visa endast de planer som medarbetaren är berättigad till baserat på **berättiganderegler**.
7. Hitta och markera önskad post i listan.
    * **Giltighetsdatum** och **Utgångsdatum** för kompensationen hämtas som standard från start- och slutdatum för arbetarens befattningstilldelning. Du kan justera dessa datum efter behov.  
    * Om den fasta kompensationsplanen är en stegplan, väljer du det steg som innehåller korrekt lönesats för medarbetaren. Om den fasta kompensationsplanen är en gradplan eller bandplan, anger du lönesatsen för medarbetaren. Lönesatsen ska valideras mot toleransinställningarna för planen, och de lägsta och högsta referenspunkterna för jobbets kompensationsnivå.  
8. Klicka på **OK**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
