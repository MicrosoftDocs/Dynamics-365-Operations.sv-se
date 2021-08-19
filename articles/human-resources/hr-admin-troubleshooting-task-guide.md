---
title: Spara uppgiftsguider i LCS och spela upp dem igen
description: Det här avsnittet beskriver hur du sparar uppgiftsguider till Microsoft Dynamics Lifecycle Services (LCS) och sedan spelar upp dem igen.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8cf6338e17c9d4f0f50e5c36291ce4f81800f76951e873f2e0cf435cc3cc97e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713088"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Spara uppgiftsguider i LCS och spela upp dem igen

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