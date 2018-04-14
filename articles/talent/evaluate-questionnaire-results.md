---
title: "Visa och utvärdera resultaten för en enkät"
description: "Detta hjälpavsnitt förklarar hur visar och utvärderar resultaten för enkäter som svarande slutför."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 7ae83192924a790451d8da511638c7fc1cd92f90
ms.contentlocale: sv-se
ms.lasthandoff: 03/08/2018

---

# <a name="view-and-evaluate-the-results-of-a-questionnaire"></a>Visa och utvärdera resultaten för en enkät

[!INCLUDE [banner](includes/banner.md)]

Detta hjälpavsnitt förklarar hur visar och utvärderar resultaten för enkäter som svarande slutför. 

Efter att svaranden har slutfört en enkät går det att visa och utvärdera enkätresultaten på följande sätt:

-   **Slutförda svarssessioner** – Visa information om de enkäter som svarande har slutfört och generera rapporter om du vill summera svar och eventuella poäng.
-   **Resultatgrupper** – Visa information om resultatgrupper för statistik för enkäter. Resultatgruppsstatistiken kan skapas för antingen en enskild svarssession för en enkät eller för alla svarssessioner.
-   **Enkätstatistik** – Ange villkor för att beräkna statistik för en viss grupp svarande.

Du kan även generera olika rapporter om du vill visa resultat sorterade efter person, svarssession eller resultatgrupp. Följande rapporter som är relaterad till ifyllda enkäter är tillgängliga:

-   Svar
-   Svar per enkät
-   Svar per person
-   Återrapporteringsanalys

## <a name="answer-session-results"></a>Svarssessionsresultat
Efter att svarande slutför en enkät kan du visa resultaten för slutförda svarssessioner. En svarssession är en användarens svar på en enkät. Du kan visa information om slutförda svarssessioner på sidan **Svar**. Svarssessionerna som finns på sidan **Svar** filtreras på olika sätt, beroende på hur du öppnar sidan:

-   Alla enkäter
-   En viss enkät
-   En viss person

På sidan **Svar** kan du visa information om svar, poäng, den svarandes svar i varje resultatgrupp och frågehierarkin som användes på den valda enkäten, om en frågehierarki användes. Du kan även generera och skriva ut följande rapporter:

-   **Resultatrapport** – Den här rapporten visar en grafisk representation av poäng per resultatgrupp för den valda svarssessionen.
-   **Svarsrapport** – Rapporten visar de svaren som svarande valde för varje fråga i enkäten.
-   **Felaktiga svar** – Den här rapporten visar information om felaktiga svar som den svarade markerade.

**Notering:** Rapporten **Resultat** är endast tillgänglig om du använder resultatgrupper i enkäten och om du har valt **Resultatsida** på sidan **Enkäter**. Rapporten **Svar** och rapporten **Felaktiga svar** är tillgängliga om du markerade **Svarsrapport** på sidan **Enkäter**.

## <a name="questionnaire-statistics"></a>Enkätstatistik
Du kan använda enkätstatistik om du vill analysera resultaten i en ifylld enkät baserat på beräkningar som du definierar. Om du vill definiera beräkningar måste du utföra följande uppgifter:

-   Välj kriterier för beräkningen och visa statistiken.
    -   Du kan visa statistik per enkät, frågor, frågerader eller resultatgrupper.
    -   Välj den typ av diagram som ska användas när du visar resultat.
    -   Väljer persontyper i nätverket, såsom medarbetare, kontaktpersoner eller sökande vars svar du vill inkludera. Du kan också ta med svar från enkäter som slutfördes anonymt.
    -   Ställ in intervall som baseras på ålder eller tjänsteålder för att analysera resultaten.
-   Välj eller bekräfta inställningar som begränsar ämnet för statistiken. Genom att t ex välja ett postnummer kan du analysera resultat för alla svarande inom ett visst geografiskt område.
-   Välj eller verifiera kriterier för att analysera resultaten efter svarande- eller enkätegenskaper. Om du väljer till exempel **Postnummer**, kan du analysera korrelationen mellan den svarandes plats och rätta svar.

Inställningar som du definierar sparas så att du kan använda den för att regelbundet räkna om resultat.

<a name="see-also"></a>Se även
--------

[Utforma enkäter](design-questionnaires.md)

[Använda enkäter](questionnaires.md)

[Distribuera och slutföra enkäter](distribute-questionnaires.md)


