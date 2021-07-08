---
title: Frågor och svar om ekonomisk rapportering
description: Det här avsnittet innehåller svar på några vanliga frågor om ekonomisk rapportering.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266643"
---
# <a name="financial-reporting-faq"></a>Frågor och svar om ekonomisk rapportering

Det här avsnittet innehåller svar på vanliga frågor om ekonomisk rapportering.

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a>Hur begränsar jag åtkomsten till en rapport med hjälp av trädsäkerhet?

Följande exempel visar hur du begränsar åtkomsten till en rapport med hjälp av trädsäkerhet.

Demonstrationsföretaget USMF har en **balansräkningsrapport** som inte alla användare av ekonomisk rapportering ska ha åtkomst till. Du kan använda trädsäkerhet för att begränsa åtkomsten till en enskild rapport så att bara specifika användare kan komma åt den.

1. Logga in i Financial Reporter Report Designer.
2. Välj **Arkiv \> Ny \> Träddefinition** för att skapa en ny träddefinition.
3. Dubbelklicka på **Sammanfattning** i kolumnen **Enhetssäkerhet**.
4. Välj **Användare och grupper**.
5. Välj de användare eller grupper som behöver ha åtkomst till rapporten.
6. Välj **Spara**.
7. Lägg till den nya träddefinitionen i rapportdefinitionen.
8. Välj Inställning i **träddefinitionen**. Välj sedan **Ta med alla enheter** under **Val av rapportenhet**.

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a>Hur identifierar jag vilka konton som inte matchar mina saldon?

Om du har en rapport som inte har matchande saldon kan du använda dig av följande procedurer för att identifiera dessa konton och avvikelser.

### <a name="in-financial-reporter-report-designer"></a>I Financial Reporter Report Designer

1. Skapa en ny raddefinition.
2. Välj **Redigera \> Infoga rader från dimensioner**.
3. Välj **MainAccount**.
4. Välj **OK**.
5. Spara raddefinitionen.
6. Skapa en ny kolumndefinition.
7. Skapa en ny rapportdefinition.
8. Välj **Inställningar** och avmarkera det här alternativet.
9. Skapa rapporten. 
10. Exportera rapporten till Microsoft Excel.

### <a name="in-dynamics-365-finance"></a>I Dynamics 365 Finance

1. Gå till **Redovisning \> > Förfrågningar och rapporter \> Råbalans**.
2. Ange följande fält.

    - **Från datum** – Ange räkenskapsårets startdatum och räkenskapsår.
    - **Till datum** – Ange det datum som du genererar rapporten för.
    - **Ekonomisk dimension** – Ange detta fält till **huvudkontouppsättning**.

3. Välj **Beräkna**.
4. Exportera rapporten till Excel.

Du bör nu kunna kopiera data från Excel-rapporten Financial Reporter till rapporten **Råbalans** så att du kan jämföra kolumnerna **Utgående balans**.

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a>När jag designar en rapport i Report Designer eller genererar en ekonomisk rapport får jag ett meddelande om att åtgärden inte kunde slutföras på grund av ett problem i dataleverantörens ramverk. Vad ska jag göra?

Meddelandet anger att ett problem inträffade när systemet skulle hämta ekonomiska metadata från den ekonomiska rapporteringen medan du använde Financial Reporting. Det finns två sätt att hantera det här problemet:

- Granska integrationsstatusen för data genom att gå till **Verktyg \> Integrationsstatus** i Report Designer. Om integrationen inte är klar väntar du tills den är klar. Försök sedan igen med det du gjorde när du fick meddelandet.
- Kontakta supporten om du vill identifiera och arbeta dig igenom problemet. Det kan finnas inkonsekventa data i systemet. Supporttekniker kan hjälpa dig att identifiera problemet på servern och hitta de specifika data som kan kräva en uppdatering.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
