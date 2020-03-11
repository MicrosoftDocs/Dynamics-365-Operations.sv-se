---
title: " Skapa och associera register"
description: I den här proceduren visas hur du skapar ett kassaregister (POS).
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ac75d390b8bbb94c6e039b374b51462d348e355
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057192"
---
# <a name="create-and-associate-registers"></a> Skapa och associera register

[!include[task guide banner](../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar ett kassaregister (POS). I den här proceduren används demonstrationsdataföretaget USRT.

1. Gå till Butik och handel > kanalinställning > POS inställning > register.
2. Klicka på Ny.
3. Skriv ett ID för den nya kassan i fältet Kassanummer.
    * Register-ID:t innehåller vanligtvis koder som gör det enklare att mappa registret till butiken som det tillhör och platsen i butiken.  
4. Ange ett beskrivande namn för den nya kassan i fältet Namn.
5. Ange eller välj ett värde i fältet Butiksnummer.
6. Ange eller välj ett värde i fältet Maskinvaruprofil.
    * Maskinvaruprofiler används för att ange den kringutrustning som kommer att kopplas till registret, som till exempel kassalåda och kvittoskrivare.  
7. Ange eller välj ett värde i fältet Visuell profil.
    * Visuella profiler används för att ange bilderna som används i kassabakgrunden och inloggningssidan samt teman för kassan.  
8. Skriv ett värde i fältet EFT-kassanummer..
    * EFT-kassanumret används för att informera betalningsprocessorn vilken betalningterminal som skickar auktoriseringförfrågningar. Det här värdet kallas ofta ”Terminal-ID ”eller ”Organisationsnummer.” Organisationsnumret hittas på klistermärke på betalningsenheten.  
9. Klicka på Spara.

