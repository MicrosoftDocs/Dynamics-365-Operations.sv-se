---
title: Konsekvenskontroll av butikstransaktion
description: I det här avsnittet beskrivs funktionen för konsekvenskontroll av butikstransaktioner i Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 8b373ce3cfd1183a082e2b1ebaf8c907b16e581e
ms.sourcegitcommit: ca4562fafa33b3512f0a5e246b15545fcf53e834
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2019
ms.locfileid: "380003"
---
# <a name="retail-transaction-consistency-checker"></a>Konsekvenskontroll av butikstransaktion


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

I det här avsnittet beskrivs funktionen för konsekvenskontroll av butikstransaktioner som infördes i Microsoft Dynamics 365 for Finance and Operations version 8.1.3. Konsekvenskontrollen identifierar och isolerar inkonsekventa transaktioner innan de används i bokföringsprocessen för utdrag.

Det går inte att bokföra utdrag i Retail om det finns inkonsekventa data i butikens transaktionsregister. Dataproblemet kan bero på oförutsedda problem i kassaprogrammet, eller om transaktioner har importerats felaktigt från kassasystem från tredje part. Dessa inkonsekvenser kan till exempel uppenbara sig på följande sätt: 

  - Transaktionssumman i huvudtabellen stämmer inte överens med transaktionssumman på raderna.
  - Radantalet i huvudtabellen stämmer inte överens med antalet rader i transaktionstabellen.
  - Momsen i huvudtabellen stämmer inte överens med momsbeloppet på raderna. 
  
När inkonsekventa transaktioner fångas upp i bokföringsprocessen för utdrag, skapas inkonsekventa försäljningsfakturor och betalningsjournaler, och bokföringsprocessen för utdrag går inte att utföra. När utdragen ska återställas från ett sådant tillstånd krävs komplexa datakorrigeringar av flera transaktionsregister. Konsekvenskontrollen av butikstransaktioner förhindrar sådana problem.

I följande diagram visas bokföringsprocessen där konsekvenskontroll av transaktioner tillämpas.

![Bokföringsprocess för utdrag med konsekvenskontroll av butikstransaktioner](./media/validchecker.png "Bokföringsprocess för utdrag med konsekvenskontroll av butikstransaktioner")

Batchprocessen **Validera butikstransaktioner** kontrollerar att butikens transaktionsregister är konsekventa i följande scenarier.

- Kundkonto – Validerar att kundkontot i butikens transaktionsregister finns i huvudkontorets kundmall.
- Radräkning – Validerar att antalet rader, som anges i transaktionsregistret huvudtabell, motsvarar antalet rader i försäljningstransaktionsregistren.

## <a name="set-up-the-consistency-checker"></a>Ställ in konsekvenskontrollen
Konfigurera batchprocessen "Validera butikstransaktioner" i **Butik \> Butikens IT \> Kassabokföring** för periodiska körningar. Batchjobbet kan schemaläggas utifrån butikens organisationshierarki, vilket påminner om hur processerna "Beräkna utdrag i batch" och "Bokför utdrag i batch" konfigureras. Vi rekommenderar att du konfigurerar den här batchprocessen så att den körs flera gånger under en dag och schemalägga den så att den körs i slutet av varje P-jobbskörning.

## <a name="results-of-validation-process"></a>Resultat av valideringsprocessen
Resultaten av batchprocessens valideringskontroll märks i motsvarande butikstransaktion. Fältet **Valideringsstatus** i butikens transaktionspost anges antingen till **Slutförd** eller **Fel**, och datumet för den senaste valideringskörningen visas i fältet **Senaste valideringstid**.

Om du vill visa en mer beskrivande feltext som berör ett valideringsfel markerar du aktuell butikstransaktionspost i Retail och klickar på **Valideringsfel**.

Transaktionerna som inte klarar valideringskontrollen och de transaktioner som ännu inte validerats används inte i utdragen. Under processen "Beräkna utdrag" meddelas användarna om det finns transaktioner som kan ha inkluderats i uttrycket men inte som inte har det.

Om ett valideringsfel inträffar går det bara att korrigera felet genom att kontakta Microsoft Support. I en framtida version kommer en funktion att läggas till som gör att användarna kan korrigera posterna via användargränssnittet. Funktioner för loggning och granskning kommer också att införas, vilka gör det möjligt att spåra ändringshistoriken.

> [!NOTE]
> Ytterligare valideringsregler för andra scenarier kommer i framtida versioner.
