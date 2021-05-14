---
title: Frågor och svar om ekonomisk rapportering
description: Det här avsnittet finns en lista med frågor om ekonomisk rapportering som andra användare har haft.
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
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923035"
---
# <a name="financial-reporting-faq"></a>Frågor och svar om ekonomisk rapportering 

Det här avsnittet innehåller svar på vanliga frågor om ekonomisk rapportering. 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Hur begränsar jag åtkomsten till en rapport med hjälp av trädsäkerhet?

Följande exempel visar hur du begränsar åtkomsten till en rapport med hjälp av trädsäkerhet.

Demonstrationsföretaget USMF har en balansräkningsrapport som inte alla användare av ekonomisk rapportering ska ha åtkomst till. Du kan använda trädsäkerhet för att begränsa åtkomsten till en enskild rapport så att bara vissa användare kan komma åt rapporten. Gör på följande sätt om du vill begränsa åtkomsten: 

1. Logga in i Financial Reporter Report Designer.
2. Skapa en ny träddefinition. Gå till **Arkiv > Ny > Träddefinition**.
3. Dubbelklicka på **Sammanfattning** i kolumnen **Enhetssäkerhet**.
4. Välj **Användare och grupper**.  
5. Välj de användare eller grupper som behöver ha åtkomst till rapporten. 
6. Välj **Spara**.
7. Lägg till den nya träddefinitionen i rapportdefinitionen.
8. Välj Inställning i **träddefinitionen**. Välj **Ta med alla enheter** under **Val av rapportenhet**.

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a>Hur identifierar jag vilka konton som inte matchar mina saldon?

Om du har en rapport som inte har matchande saldon kan du vidta följande åtgärder för att identifiera dessa konton och avvikelser. 

**Financial Reporter Report Designer**
1. Skapa en ny raddefinition i Financial Reporter Report Designer 
2. Välj **Redigera > Infoga rader från dimensioner**.
3. Välj **Huvudkonto**.  
4. Välj **OK**.
5. Spara raddefinitionen.
6. Skapa en ny kolumndefinition
7. Skapa en ny rapportdefinition.
8. Välj **Inställningar** och avmarkera det här alternativet.  
9. Skapa rapporten. 
10. Exportera rapporten till Microsoft Excel.

**Dynamics 365 Finance** 
1. I Dynamics 365 Finance, gå till **Redovisning > Förfrågningar och rapporter > Råbalans**.
2. Ställ in följande parametrar:
   - **Från datum** – Ange räkenskapsårets början.
   - **Till datum** – Ange det datum som du genererar rapporten för.
   - **Ekonomisk dimension** – Ange detta fält till **huvudkontouppsättning**.
 3. Välj **Beräkna**.
 4. Exportera rapporten till Microsoft Excel.

Du bör nu kunna kopiera data från Excel-rapporten i ekonomisk rapportering till råbalansrapporten så att du kan jämföra kolumnerna **Utgående balans**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]