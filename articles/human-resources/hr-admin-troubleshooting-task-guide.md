---
title: Spara uppgiftsguider i LCS och spela upp dem igen
description: Det här avsnittet beskriver hur du sparar uppgiftsguider till Microsoft Dynamics Lifecycle Services (LCS) och sedan spelar upp dem igen.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2efe48a31db533c5f22d4174cc6897f4a590cf49
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875812"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Spara uppgiftsguider i LCS och spela upp dem igen


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Miljöinformation** 

Microsoft Dynamics 365 Human Resources som distribuerades via Microsoft Dynamics Lifecycle Services (LCS)

**Utleverans**

Kunden vill spara nya uppgiftsinspelningar till LCS-projektet och sedan spela upp de sparade uppgiftsguiderna.

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

    ![Spara till Lifecycle Services.](media/task-guides.png)

12. Välj BPM-bibliotek och nod att spara uppgiftsinspelningen till.

Följ dessa steg för att spela upp en uppgiftsguide från LCS.

1. Starta Uppgiftsinspelare.
2. Välj **Öppna från LCS**.
3. Markera biblioteket och BPM-noden som har den sparade uppgiftsguiden.
4. Öppna uppgiftsguiden.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
