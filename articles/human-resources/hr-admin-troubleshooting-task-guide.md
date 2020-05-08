---
title: Spara uppgiftsguider i LCS och spela upp dem igen
description: Det här avsnittet beskriver hur du sparar uppgiftsguider till Microsoft Dynamics Lifecycle Services (LCS) och sedan spelar upp dem igen.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b55937c0867117809471f50f1987f7bf12a4b25d
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010670"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Spara uppgiftsguider i LCS och spela upp dem igen

**Miljöinformation** 

Microsoft Dynamics 365 Human Resources som distribuerades via Microsoft Dynamics Lifecycle Services (LCS)

**Utleverans**

Kunden vill spara nya uppgiftsinspelningar till hans eller hennes LCS-projekt och sedan spela upp de sparade uppgiftsguiderna.

**Upplösning**

Följ dessa steg om du vill spara en uppgiftsinspelning till LCS.

1. Logga in på LCS och välj projektet.
2. Välj panelen **Affärsprocessmodelleraren**.
3. Visa sidan i den "uppdaterade BPM-miljön."
4. Välj ett bibliotek och välj **kopiera**.
5. Ange ett namn för modellen Affärsprocessmodelleraren (BPM).
6. Logga in på Personal från LCS.
7. I fältet **Sök**, ange **Hjälp**. Hjälp för Lifecycle Services är öppen.
8. Välj knappen **Uppdatera** för Hjälpkonfiguration för Lifecycle Services.

    Ditt nya BPM-biblioteket bör visas och det ska vara aktivt.

9. Stäng sidan.
10. Skapa en uppgiftsinspelning.
11. När du är klar, välj **Spara till Lifecycle Services**.

    ![Spara till Lifecycle Services](media/task-guides.png)

12. Välj BPM-bibliotek och nod att spara uppgiftsinspelningen till.

Följ dessa steg för att spela upp en uppgiftsguide från LCS.

1. Starta Uppgiftsinspelare.
2. Välj **Öppna från LCS**.
3. Markera biblioteket och BPM-noden som har den sparade uppgiftsguiden.
4. Öppna uppgiftsguiden.