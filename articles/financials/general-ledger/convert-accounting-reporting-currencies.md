---
title: Konvertera redovisning eller rapporteringsvalutor
description: 
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 78223
ms.assetid: 31c56f9a-9c64-40a2-90e3-1969a760614b
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 363543f8befacbf2e1b3ab28e6b9f14a5caf3c10
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="convert-accounting-or-reporting-currencies"></a>Konvertera redovisning eller rapporteringsvalutor

[!include[banner](../includes/banner.md)]


Ett företag som måste ändra sin redovisningsvaluta eller rapportvaluta har två alternativ. Det första alternativet är för att skapa ett nytt företag och starta på nytt. Det andra alternativet är att köra konverteringsprocessen för redovisnings- och rapporteringsvaluta. Detta är mycket en avancerad process som ändrar varje transaktion i systemet. En del inställningar krävs också innan du kan köra processen.

## <a name="preparing-the-legal-entity-for-currency-conversion"></a>Förbered en juridisk enhet för en valutakonvertering
Innan du kan konvertera den juridiska personens valuta måste du återställa alla belopp för omräkning i utländsk valuta för kund- och leverantörskonton och stänga föregående räkenskapsår. Du måste också förbereda databasen för konverteringen, och sedan göra nödvändiga ändringar av den juridiska personens konto som genomgår valutakonverteringen. När du har slutfört en valutakonvertering, måste du utföra vissa extra procedurer. Du måste stämma av avrundningsdifferenser i konverterade belopp, räkna om affärsstatistik, journalföra redovisningstransaktioner, begränsa åtkomst till konverteringsverktyget och omvärdera utländska valutabelopp för kund- och leverantörskonton.

## <a name="setting-up-accounts-for-automatic-transactions"></a>Ange konton för automatiska transaktioner
Under valutakonverteringprocessen bokförs vinst eller förlust eller öresskillnader, på kontona som definieras på sidan **Konton för automatiska transaktioner**. Huvudkonton måste tilldelas följande transaktionstyper innan konverteringsprocessen körs:

-   Konverteringsvinst för redovisningsvaluta
-   Konverteringsförlust för redovisningsvaluta
-   Öresdifferens i redovisningsvaluta
-   Öresdifferens i rapporteringsvaluta
-   Årsslutsresultat

## <a name="posting-rounding-differences-and-sum-recalculations"></a>Bokföring av avrundningsdifferenser och omberäkning av summor
Följande information beskriver var skillnader i avrundning kan inträffa:

-   Om priser på produkter har konverterats till 0 (noll), skapas en rapport som visar produktnummer, modultyp, pris före konverteringen och enhet.
-   Avrundningsdifferenser mellan moms och redovisningen bokförs till den allmänna journalen.
-   Belopp för omräkning i utländsk valuta omberäknas, och kund- och leverantörstransaktionbelopp räknas om.
-   Kvittningsposter för kunder och leverantörer skapas för avrundningsdifferenserna per kund- och leverantörstransaktion.
-   Avrundningsdifferenser för kunder och leverantörer bokförs till den allmänna journalen.
-   Kvittade kostnadsbelopp och kostnadsjusteringsbelopp i stängda lagertransaktioner beräknas på nytt.
-   Avrundningsdifferenser i lagerhanteringen bokförs till den allmänna journalen.
-   Lagerbehållning räknas om.
-   Totalsummor i redovisningsjournaler räknas om.
-   Bokslutsarken i redovisningen har räknats om.
-   Redovisningssaldon har räknats om.
-   Avrundningsdifferenser i redovisningen bokförs till den allmänna journalen.
-   Ingående redovisningstransaktioner räknas om.
-   Det sista beloppet i redovisningssaldon beräknas.

Om du konverterar till en ny huvudboksredovisningsvaluta, och ett fel har uppstår under omberäkningen av summor eller bokföringen av avrundningsdifferenser, måste du stänga sidan **Konvertering av redovisningsvaluta**. De totala beloppen räknas om och avrundningsdifferenserna kommer att bokföras.

## <a name="processing-the-currency-conversion"></a>Bearbeta valutakonverteringen
När du startar valutakonverteringprocessen, måste alla användare signeras ut ur systemet. Du måste definiera den nya redovisningen eller rapporteringsvalutan och valutakurser. När du klickar på **OK** körs processen och uppdaterar varje transaktion i systemet. Valutakonvertering är en mycket lång process. När du har slutat kommer du att se att redovisningen eller rapporteringsvalutan uppdateras på sidan **Redovisning**.

## <a name="completing-the-currency-conversion"></a>Slutför valutakonverteringen
Alla avstämningsrapporter måste köras igen efter konverteringen för att kontrollera att alla konverterade belopp stämmer.

-   Om omvandlingen av redovisningredovisningsvalutan orsakar avrundningsdifferenser, bokförs inte dessa genom att använda verifikationen där avrundningsdifferensen uppstod. I stället bokförs avvikelserna genom att använda verifikationen som har angetts för konverteringsbokföringen. Efter konverteringen inkluderar alla rapporterna som kontrollerar efter verifikation och datum dessa avrundningsdifferenser. Detta beteende stämmer och kan ignoreras.
-   Om kundens och leverantörens avstämningsrapporter visar ett differensbelopp på raden med summan och inget differensbelopp förekom före konverteringen måste differensbeloppet bokföras. Kontot är samlingskontot för kunder och leverantörer. Motkontot är redovisningskontot för konverteringsförlust eller konverteringsvinst.

När alla journaler för redovisningstransaktioner har raderats kan du journalföra redovisningstransaktionerna. Klicka på **Redovisning** &gt; **Journalföring av** &gt; **Periodiska** &gt; **Journaler**. Du kan omvärdera belopp i utländsk valuta efter valutakonverteringen om omvärdering krävs. Du omvärderar belopp i utländsk valuta, genom att välja **Standard** i fältet **Metod** för omvärdering.

Mer information finns i [Journalföra bokförda poster i redovisningsjournal](tasks/journalize-posted-journal-entries.md).


