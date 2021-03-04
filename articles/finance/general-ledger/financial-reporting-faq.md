---
title: Frågor och svar om ekonomisk rapportering
description: Det här avsnittet finns en lista med frågor om ekonomisk rapportering som andra användare har haft.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3f9381f5b656d0cc0b46c8828b2ef9d024e296b0
ms.sourcegitcommit: 14785208d84b2c1efd30f140c52df35a2ccd1577
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "5070227"
---
# <a name="financial-reporting-faq"></a>Frågor och svar om ekonomisk rapportering 

Det här avsnittet finns en lista med frågor om ekonomisk rapportering som andra användare har haft. 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Hur begränsar jag åtkomsten till en rapport med hjälp av trädsäkerhet?

Scenario: Demoföretaget USMF har en balansräkningsrapport som alla användare av Ekonomisk rapportering inte ska kunna visa i D365. Lösning: Du kan använda trädsäkerhet för att begränsa åtkomsten till en enskild rapport så att bara vissa användare kan komma åt rapporten. 

1.  Logga in på Rapportdesignern i ekonomisk rapportering

2.  Skapa en ny träddefinition (Arkiv | Nytt | Träddefinition) a.    Dubbelklicka på **Sammanfattning** i kolumnen **Enhetssäkerhet**.
  i.    Klicka på Användare och grupper.  
          1. Välj de användare eller grupper som ska ha tillgång till rapporten. 
          
[![användarskärm](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)

[![säkerhetsskärm](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)

  b.    Klicka på **Spara**.
  
[![knappen Spara](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)

3.  Lägg till den nya träddefinitionen i rapportdefinitionen

[![formulär för träddefinition](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)

A.  När du är i träddefinitionen klickar du på Inställningar och under "Val av rapportenhet" i "Ta med alla enheter"

[![formuläret Val av rapportenhet](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)

**Före:** [![skärmdump för före](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)

**Efter:** [![skärmdump för efter](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)

Obs! Orsaken till meddelandet ovan är att min användare inte har tillgång till rapporten efter att ha tillämpat enhetssäkerhet.



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a>Hur kan jag ta reda på vilka konton som inte matchar mina saldon i D365?

När du har en rapport som inte matchar vad du förväntade dig i D365, kan du följa några steg som beskrivs här för att identifiera dessa konton och avvikelserna. 

### <a name="in-financial-reporter-report-designer"></a>I Rapportdesignern i ekonomisk rapportering

1.  Skapa en ny raddefinition a.    Klicka på Redigera | Infoga rader från Dimensioner i.  Välj MainAccount [![Välj huvudskärmen_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)
    
    ii. Klicka på OK b.    Spara raddefinitionen

2.  Skapa en ny kolumndefinition     [![Skapa en ny kolumndefinition](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)

3.  Skapa en ny rapportdefinition a.    Klicka på Inställningar och avmarkera [![formuläret Inställningar](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)
   
4.  Skapa rapporten. 

5.  Exportera rapporten till Excel.

### <a name="in-d365"></a>I D365: 
1.  Klicka på Redovisning | Förfrågningar och rapporter | Råbalans a.    Parametrar i.  Från datum: Räkenskapsårets början ii. Till datum: Datumet du genererade rapporten för iii.    Ekonomisk dimensionsuppsättning "Huvudkontouppsättning" [![Huvudkontoformulär](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)
      
  b.    Klicka på Beräkna

2.  Exportera rapporten till Excel

Du bör nu kunna kopiera data från Excel-rapporten i ekonomisk rapportering och till D365-råbalansrapporten och jämföra kolumnerna "Utgående balans".
