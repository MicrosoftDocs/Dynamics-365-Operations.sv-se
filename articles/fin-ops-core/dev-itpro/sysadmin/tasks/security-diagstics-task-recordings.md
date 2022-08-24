---
title: Säkerhetsdiagnos för uppgiftsinspelningar
description: I den här artikeln finns information om hur du analyserar och hanterar krav på säkerhetsbehörighet baserat på en uppgiftsinspelning.
author: Peakerbl
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.search.form: ''
ms.openlocfilehash: e564a0499cb1a5dc00fc027c20a027f9b454600c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272533"
---
# <a name="security-diagnostics-for-task-recordings"></a>Säkerhetsdiagnos för uppgiftsinspelningar

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a>Innan du börjar

I den här artikeln finns information om hur du analyserar och hanterar krav på säkerhetsbehörighet baserat på en uppgiftsinspelning. Innan du slutför stegen i den här artikeln måste du ha en uppgiftsinspelning av affärsprocessen som du vill analysera. Information om hur du spelar in affärsprocesser finns i [resurser för uppgiftsinspelare](../../user-interface/task-recorder.md). 

## <a name="manage-security-for-a-task-recording"></a>Hantera säkerhet för en uppgiftsinspelning

1. Gå till **Systemadministration** > **Säkerhet** > **Diagnostik för säkerhet för uppgiftsinspelning**.
2. Öppna uppgiftsinspelningen från dess plats. Välj **Öppna från den här datorn** eller **Öppna från Lifecycle Services** och välj sedan **Stäng**.
3. Då öppnas sidan **Uppgifter om säkerhetsmeny** med en lista över de säkerhetsobjekt som krävs för processen.

 > [!NOTE]
 > Menyalternativen **Åtgärd** och **Utdata** finns inte med i listan.

4. Välj användare i fältet **Användar-ID**. Om användaren inte har behörighet för vissa menyalternativ uppdateras fältet **Saknade behörigheter** till **Ja**.
  
  ![Sidan Artikeldetaljer för säkerhetsmeny.](../media/Security-Menu-Item-Details.png)

5. Välj **Lägg till referens** för att visa en lista över de säkerhetsobjekt, inklusive roller, uppgifter och behörigheter som ger den saknade behörigheten.
6. Välj ett säkerhetsobjekt i listan:

    - Om **Roll** har valts väljer du **Lägg till roll till användare**. Då öppnas sidan **Tilldela användare till roller**. Mer information finns på sidan [Tilldela användare till säkerhetsroller](assign-users-security-roles.md).
    - Om **Uppdrag** är valt väljer du **Lägg till uppgift i roll**, väljer de roller som uppgiften ska läggas till i och väljer sedan **OK**.
    - Om **Privilegium** är valt väljer du **Lägg till privilegium i uppgifter**, väljer de roller som privilegium ska läggas till i och väljer sedan **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
