---
title: Registrera en medarbetare i en fast kompensationsplan
description: Chefen över kompensationer och förmåner kan tilldela medarbetare till fasta kompensationsplaner för att hantera deras grundlön.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a129bf9a6cb6a3ef92597e2ff9d126e3e5ce973b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468261"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>Registrera en medarbetare i en fast kompensationsplan

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Chefen över kompensationer och förmåner kan tilldela medarbetare till fasta kompensationsplaner för att hantera deras grundlön. I den här proceduren förutsätts att en fast plan har skapats och är aktiv, och att berättiganderegler har angetts för planen. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Gå till Personal > Arbetare > Medarbetare > Kompensation > Fast plan för att starta proceduren

1. Klicka på Ny.
2. Välj en åtgärd för fast kompensation av typen Anställ/återanställ för att beskriva ändringen av en medarbetares kompensation.
3. Klicka på länken på den valda raden i listan.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Befattning.
5. Klicka på länken på den valda raden i listan.
    * Nivån som visas kommer från kompensationsnivån för jobbet på befattningen. Nivån måste anges för jobbet innan kompensation kan tilldelas till medarbetaren.  
6. Välj den fasta kompensationsplanen för medarbetaren i fältet Plan. Planuppslagningen filtreras för att visa endast de planer som medarbetaren är berättigad till baserat på berättiganderegler.
7. Hitta och markera önskad post i listan.
    * Giltighetsdatum och utgångsdatum för kompensationen hämtas som standard från start- och slutdatum för arbetarens befattningstilldelning. Du kan justera dessa datum efter behov.  
    * Om den fasta kompensationsplanen är en stegplan, väljer du det steg som innehåller korrekt lönesats för medarbetaren. Om den fasta kompensationsplanen är en gradplan eller bandplan, anger du lönesatsen för medarbetaren. Lönesatsen ska valideras mot toleransinställningarna för planen, och de lägsta och högsta referenspunkterna för jobbets kompensationsnivå.  
8. Klicka på OK.



[!INCLUDE[footer-include](../includes/footer-banner.md)]