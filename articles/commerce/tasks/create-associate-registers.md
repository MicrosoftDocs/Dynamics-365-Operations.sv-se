---
title: " Skapa och associera register"
description: I den här proceduren visas hur du skapar ett kassaregister (POS).
author: rubencdelgado
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff6fb42cd0b080ff576aa3a784cfce985d69fe0347af44dfa9935b4e8e5ffe00
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743369"
---
# <a name="create-and-associate-registers"></a> Skapa och associera register

[!include [banner](../includes/banner.md)]

I den här proceduren visas hur du skapar ett kassaregister (POS). I den här proceduren används demonstrationsdataföretaget USRT.

1. Gå till Butik och handel > kanalinställning > POS inställning > register.
2. Klicka på Ny.
3. Skriv ett ID för den nya POS i fältet Kassanummer.
    * Register-ID:t innehåller vanligtvis koder som gör det enklare att mappa registret till butiken som det tillhör och platsen i butiken.  
4. Ange ett beskrivande namn för den nya POS i fältet Namn.
5. Ange eller välj ett värde i fältet Butiksnummer.
6. Ange eller välj ett värde i fältet Maskinvaruprofil.
    * Maskinvaruprofiler används för att ange den kringutrustning som kommer att kopplas till registret, som till exempel kassalåda och kvittoskrivare.  
7. Ange eller välj ett värde i fältet Visuell profil.
    * Visuella profiler används för att ange bilderna som används i kassabakgrunden och inloggningssidan samt teman för POS.  
8. Skriv ett värde i fältet EFT-kassanummer..
    * EFT-kassanumret används för att informera betalningsprocessorn vilken betalningterminal som skickar auktoriseringförfrågningar. Det här värdet kallas ofta ”Terminal-ID ”eller ”Organisationsnummer”. Organisationsnumret hittas på klistermärke på betalningsenheten.  
9. Klicka på Spara.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]