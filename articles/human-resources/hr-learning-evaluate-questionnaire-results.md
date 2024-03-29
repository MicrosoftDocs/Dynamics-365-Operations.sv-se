---
title: Visa och utvärdera resultaten av enkäter
description: Den här artikeln beskriver hur du visar och utvärderar resultaten för enkäter som svarande slutför.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults, HcmLearningWorkspace
audience: Application User
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 45be2fb7761a3022795a196b140987fcbd732a33
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855153"
---
# <a name="view-and-evaluate-the-results-of-questionnaires"></a>Visa och utvärdera resultaten av enkäter


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Den här artikeln beskriver hur du visar och utvärderar resultaten för enkäter som svarande slutför. 

Efter att svaranden har slutfört en enkät går det att visa och utvärdera enkätresultaten på följande sätt:

-   **Slutförda svarssessioner** – Visa information om de enkäter som de svarande har slutfört, och generera rapporter om du vill summera svar och eventuella poäng.
-   **Resultatgrupper** – Visa information om resultatgrupper för statistik för enkäter. Resultatstatistik för grupp kan skapas för antingen en enskild svarssession för en enkät eller för alla svarssessioner.
-   **Enkätstatistik** – Ange villkor för att beräkna statistik för en viss grupp svarande.

Du kan även skapa olika rapporter om du vill visa resultat sorterade efter person, svarssession eller resultatgrupp. Följande rapporter som är relaterad till ifyllda enkäter är tillgängliga:

-   Svar
-   Svar per enkät
-   Svar per person
-   Återrapporteringsanalys

## <a name="answer-session-results"></a>Svarssessionsresultat

Efter att svarande slutför en enkät kan du visa resultaten för slutförda svarssessioner. En svarssession är en användarens svar på en enkät. Du kan visa information om slutförda svarssessioner på sidan **Svar**. Svarssessionerna som finns på sidan **Svar** filtreras på olika sätt beroende på hur du öppnar sidan:

-   Alla enkäter
-   En viss enkät
-   En viss person

På sidan **Svar** kan du visa information om svar, poäng, den svarandes svar i varje resultatgrupp och frågehierarkin som användes på den valda enkäten, om en frågehierarki användes. Du kan även skapa och skriva ut följande rapporter:

-   **Resultatrapport** – Denna rapport visar en grafisk representation poäng per resultatgrupp för den valda svarssessionen.
-   **Svarsrapport** – Rapporten visar de svaren som svarande valde för varje fråga i enkäten.
-   **Felaktiga svar** – Denna rapport visar information om felaktiga svar som den svarade markerat.

> [!NOTE]
> Rapporten **Resultat** är endast tillgänglig om du använder resultatgrupper i enkäten och om du har valt **Resultatsida** på sidan **Enkäter**. Rapporten **Svar** och rapporten **Felaktiga svar** är tillgängliga om du markerade **Svarsrapport** på sidan **Enkäter**.

## <a name="questionnaire-statistics"></a>Enkätstatistik

Du kan använda enkätstatistik om du vill analysera resultaten i en ifylld enkät baserat på beräkningar som du definierar. Om du vill definiera beräkningar måste du utföra följande uppgifter:

-   Välj kriterier för beräkningen och visa statistiken.
    -   Du kan visa statistik per enkät, frågor, frågerader eller resultatgrupper.
    -   Välj den typ av diagram som ska användas när du visar resultat.
    -   Väljer persontyper i nätverket, såsom medarbetare, kontaktpersoner eller sökande vars svar du vill inkludera. Du kan också ta med svar från enkäter som slutfördes anonymt.
    -   Ställ in intervall som baseras på ålder eller tjänsteålder för att analysera resultaten.
-   Välj eller bekräfta inställningar som begränsar ämnet för statistiken. Genom att t. ex. välja ett postnummer kan du analysera resultat för alla svarande inom ett visst geografiskt område.
-   Välj eller verifiera kriterier för att analysera resultaten efter svarande- eller enkätegenskaper. Om du väljer till exempel **Postnummer**, kan du analysera korrelationen mellan den svarandes plats och rätta svar.

Inställningar som du definierar sparas så att du kan använda den för att regelbundet räkna om resultat.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
