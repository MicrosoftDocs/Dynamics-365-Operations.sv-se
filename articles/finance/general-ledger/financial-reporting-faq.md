---
title: Vanliga frågor och svar om ekonomisk rapportering
description: Den här artikeln innehåller svar på några vanliga frågor om ekonomisk rapportering.
author: jinniew
ms.date: 07/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5981946a4bba2c58402f4cf566bfa008de67363b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901385"
---
# <a name="financial-reporting-faq"></a>Vanliga frågor och svar om ekonomisk rapportering

Den här artikeln innehåller svar på vanliga frågor om ekonomisk rapportering.

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
- Kontakta supporten om du vill identifiera och arbeta dig igenom problemet. Det kan finnas inkonsekventa data i systemet. Supporttekniker kan hjälpa dig att identifiera problemet på servern och hitta de specifika data som kan behöva uppdatering.

## <a name="how-does-the-selection-of-historical-rate-translation-affect-report-performance"></a>Hur påverkar valet av historisk kursomräkning rapportresultatet?

Den historiska kursen används normalt med balanserade vinstmedel, egendom, anläggningar och utrustning samt konton för eget kapital. Den historiska kursen kan krävas baserat på riktlinjerna från FASB (Financial Accounting Standards Board) eller GAAP-bokföringsprinciper. Mer information finns i [Valutafunktioner i ekonomisk rapportering](financial-reporting-currency-capability.md).

## <a name="how-many-types-of-currency-rate-are-there"></a>Hur många typer av valutakurser finns det?

Det finns tre typer:

- **Aktuell kurs** – Den här typen används normalt för balansräkningskonton. Den kallas vanligen *stickprovskurs* och kan vara kursen sista dagen i månaden eller något annat förutbestämt datum.
- **Genomsnittskurs** – Typen används normalt med resultatkonton (vinst/förlust). Du kan ställa in genomsnittskursen för att göra ett enkelt medelvärde eller ett viktat medelvärde.
- **Historisk kurs** – Den här typen används normalt med balanserade vinstmedel, egendom, anläggningar och utrustning samt konton för eget kapital. Dessa konton kan vara obligatoriska enligt FASB- eller GAAP-riktlinjer.

## <a name="how-does-historical-currency-translation-work"></a>Hur fungerar historisk valutaomräkning?

Kurserna är specifika för transaktionsdatumet. Därför översätts varje transaktion enskilt baserat på närmaste valutakurs.

Vid historisk valutaomräkning kan förberäknade periodsaldon användas i stället för enskilda transaktionsuppgifter. Detta beteende skiljer sig från beteendet för aktuell kursomräkning.

## <a name="how-does-historical-currency-translation-affect-performance"></a>Hur påverkar historisk valutaomräkning resultatet?

När data som visas i rapporterna uppdateras kan det bli en fördröjning eftersom beloppen måste räknas om genom kontroll av transaktionsuppgifter. Den här fördröjningen utlöses varje gång satserna uppdateras eller när ytterligare transaktioner bokförs. Om exempelvis tusentals konton ställs in för historisk omräkning ett par gånger om dagen kan det ta upp till en timme innan uppgifterna i rapporten uppdateras. Om det däremot finns ett mindre antal specifika konton kan bearbetningstiden för uppdateringar av rapportdata minska till minuter eller mindre.

När rapporter genereras med hjälp av valutaomräkning för konton av historisk typ, blir det på samma sätt extra beräkningar per transaktion. Beroende på antal konton kan tiden för att generera rapporten mer än fördubblas.

## <a name="what-are-the-estimated-data-mart-integration-intervals"></a>Vad är de uppskattade integrationsintervallen för data mart?

I Financial Reporter används 16 uppgifter för att kopiera data från Dynamics 365 Finance till Financial Reporter-databasen. I följande tabell visas dessa 16 uppgifter och intervallen som anger hur ofta varje uppgift körs. Det går inte att ändra intervallen.

| Namn                                                       | Intervall | Intervalltid |
|------------------------------------------------------------|----------|-----------------|
| Kontokategorier i AX 2012 till Kontokategori            | 41       | Minuter         |
| Konton i AX 2012 till Konto                                | 7        | Minuter         |
| Företag i AX 2012 till Företag                               | 300      | Sekunder         |
| Företag i AX 2012 till Organisation                          | 23       | Minuter         |
| Dimensionskombinationer i AX 2012 till Dimensionskombination    | 1        | Minuter         |
| Dimensionsvärden i AX 2012 till Dimensionsvärde                | 11       | Minuter         |
| Dimensioner i AX 2012 till Dimension                            | 31       | Minuter         |
| Valutakurser i AX 2012 till Valutakurs                    | 17       | Minuter         |
| Räkenskapsår i AX 2012 till Räkenskapsår                        | 13       | Minuter         |
| Redovisningstransaktioner i AX 2012 till Fakta                | 1        | Minuter         |
| Organisationshierarkier i AX 2012 till Träd                   | 3 600    | Sekunder         |
| Scenarier i AX 2012 till Scenario                              | 29       | Minuter         |
| Kvalificerare för transaktionstyp i AX 2012 till Kvalificerare för faktatyp | 19       | Minuter         |
| Underhållsuppgift                                           | 1        | Minuter         |
| MR-rapportdefinitioner till ekonomiska rapporter i AX7             | 45       | Sekunder         |
| MR-rapportversioner till ekonomiska rapportversioner i AX         | 45       | Sekunder         |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
