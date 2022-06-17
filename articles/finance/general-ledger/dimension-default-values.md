---
title: Ekonomiska standarddimensioner i redovisningsjournaler
description: Den här artikeln beskriver regler som definierar hur värden för ekonomiska dimensioner ställs in i transaktioner som anges genom redovisningsjournaler. Det innehåller även information om scenarier där fasta dimensioner används.
author: kweekley
ms.date: 09/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransDaily, LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8d0fcf836e22207baae562801fb082d735df0f96
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907945"
---
# <a name="default-financial-dimensions-on-financial-journals"></a>Ekonomiska standarddimensioner i redovisningsjournaler

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver regler som definierar hur värden för ekonomiska dimensioner ställs in i transaktioner som anges genom redovisningsjournaler (men inte genom lager- eller projektjournaler). Det innehåller även information om scenarier där fasta dimensioner används.

## <a name="symptom"></a>Symtom

Värden för ekonomiska dimensioner  ställs inte in som förväntat konto eller motkonto i en redovisningsjournal. Följande scenarier är två exempel:

En verifikation registreras i en journal som är en allmän journal. Kontot är ett leverantörskonto och motkontot är ett bankkonto. Leverantörens ekonomiska dimensioner anges som standard på kontot, men bankens ekonomiska dimensioner anges inte som standard på motkontot. I stället anges dimensionsvärdena från kontot som standard på motkontot.

En kund har tilldelats standardvärden för ekonomiska dimensioner och ett intäktshuvudkonto har ett fast dimensionsvärde tilldelat för avdelningens ekonomiska dimension. En verifikation registreras i en allmän journal.  Kontot är kunden och motkontot är ett huvudbokskonto, närmare bestämt intäktskontot med det fasta dimensionsvärdet. Den fasta dimensionen är inte inställd för intäktshuvudkontots motkonto. I stället anges det som avdelningens dimensionsvärde från kontot som kom från kunden.  Efter bokföringen av verifikationen används det fasta dimensionsvärdet på den bokförda redovisningsposten, men verifikationen visar fortfarande kundens avdelningsvärde på intäktskontot. 

Vilka regler följs för ekonomiska dimensionsvärden som anges på verifikationer i en journal?

## <a name="resolution"></a>Lösning

Följande regler följs för att ange ekonomiska dimensionsvärden som standard på raderna i en verifikation i redovisningsjournaler, till exempel den allmänna journalen eller leverantörsfakturajournalen. 

1. **Journalrubrik**

   - Journalrubriksdimensioner anges som standard från journalnamnsdimensioner.

2. **Journalradkonto**

   - Journalradkontodimensioner anges som standard från journalrubriksdimensioner.
   - Om en ekonomisk dimension är tom anges värdet som standard från kund- leverantörs-, bank-, anläggningstillgångs-, projekt- eller redovisningsdimensioner.

     - Om kontotypen är **Redovisning** behandlas en fast dimension i ett huvudbokskonto som en standarddimension under transaktionsinmatning.
     - Om kontotypen är **Kund**, **Leverantör**, **Bank**, **Anläggningstillgångar** eller **Projekt**, kan huvudkontot ännu inte fastställas. Därför anges som standard aldrig en fast dimension för kontot.

3. **Motkonto för journalrad**

 - Motkontodimensioner för journalradkonto anges som standard från journalradkontodimensioner.

 - Om en ekonomisk dimension är tom kommer nästa standardpost från standarddimensionerna från Kund, Leverantör, Bank, Anläggningstillgångar, Projekt eller Redovisning.
   1. Om motkontotypen är **Redovisning** behandlas en fast dimension i ett huvudbokskonto som en standarddimension under transaktionsinmatning. Om ett dimensionsvärde redan har angetts som standard från Konto, åsidosätter inte huvudkontots standard- eller fasta dimensionsvärde det befintliga värdet.
   2. Om motkontotypen är **Kund**, **Leverantör**, **Bank**, **Anläggningstillgångar** eller **Projekt**, är huvudkontot ännu inte känt, varför en fast dimension inte anges för motkontot.

4. **Bokföra**

    1. Under bokföring utvärderas huvudkontot för varje rad i redovisningsposten (för både kontot och motkontot) för att fastställa om det finns ett fast dimensionsvärde. Om en fast dimension är definierad ersätts eventuella befintliga eller tomma värden med det fasta dimensionsvärdet.

        Det fasta dimensionsvärdet visas **inte** på journalraderna efter bokföring. I stället visas den i redovisningsposten när du visar verifikationen efter att den har bokförts.

    2. Inga andra dimensionsvärden anges som standard under bokföringen, inklusive ytterligare redovisningskonton som kanske läggs till under bokföring, till exempel öresavrundningskonton och koncerninterna som förfaller till eller förfaller från konton. Standarddimensionsposterna för ytterligare redovisningskonton tas från konton eller motkonton.

För att ange dimensionsvärden som standard kan journalens standardprocess inte avgöra om ett tomt dimensionsvärde har lämnats tomt med avsikt eller om standardvärdet inte har angetts. Om ett dimensionsvärde lämnas tomt med avsikt kan ett värde fortfarande anges som standard med hjälp av den tidigare beskrivna standardvärdesordningen. Om du vill att en dimension har ett tomt värde måste du kanske skapa en dimension med värdet **0** (noll) eller **Tom** så att den kan användas i stället för en tom dimension.

Följande scenarier innehåller exempel på standardvärdesordningen för ekonomisk dimension.

### <a name="scenario-1"></a>Scenario 1

Öppna **Redovisning \> Journalinställning \> Journalnamn** och välj journalnamnet **GenJrn**. Definiera sedan följande värden för de ekonomiska standarddimensionerna på snabbfliken **Ekonomiska dimensioner**:

- **BUSINESSUNIT:** 001
- **DEPARTMENT:** 024

[![Sidan Journalnamn](./media/financial-dimension-defaulting-jrnl-names-01.png)](./media/financial-dimension-defaulting-jrnl-names-01.png)

Öppna **Redovisning \> Journalposter \> Allmän journal** och skapa en ny allmän journal som använder journalnamnet **GenJrn**. Dimensionerna anges som standard från journalnamnet (tabellen LedgerJournalName) till journalrubriken (tabellen LedgerJournalTable), vilket visas på fliken **Ekonomiska dimensioner**.

[![Fliken Ekonomiska dimensioner på sidan Allmänna journaler](./media/financial-dimension-defaulting-genrl-jrnl-02.png)](./media/financial-dimension-defaulting-genrl-jrnl-02.png)

Gå till **Rader**. Välj **Redovisning** i fältet **Kontotyp** och ange sedan **170150** i fältet **Konto**. Tryck sedan på **Tabb**-tangenten för att flytta ut från fältet. Dimensionerna anges som standard från journalrubriken. Därför visas värdet **Konto** som **170150-001-024**.

[![Journalrader för en allmän journal på sidan Bokföringsorder](./media/financial-dimension-defaulting-jrnl-vchr-03.png)](./media/financial-dimension-defaulting-jrnl-vchr-03.png)

Ändra värdet **Konto** till **170150-001-023**. Ange antingen ett debetbelopp eller kreditbelopp. Välj **Redovisning** i fältet **Motkontotyp** och ange sedan **600150** i fältet **Motkonto**. Dimensionsvärdena anges som standard från kontot. Därför visas värdet **Motkonto** som **600150-001-023**.

### <a name="scenario-2"></a>Scenario 2

Använd samma ekonomiska dimensioner som du definierade för journalnamnet i scenario 1. Gå sedan till **Kundreskontra \> Kunder \> Alla kunder** och definiera standardvärden för ekonomisk dimension för kunden US-001. Välj kunden för vilken kundinformationen öppnas. Behåll standardvärdet för **BUSINESSUNIT**-dimensionen (**001**) på fliken **Ekonomiska dimensioner**. Lägg till dimensionen **COSTCENTER** och ange **007** som värdet.

Skapa en ny allmän journal som använder namnet **GenJrn**. Ändra standardvärdet för **BUSINESSUNIT** från **001** till **002** på fliken **Ekonomiska dimensioner**.

Gå till **Rader**. Välj **Kund** i fältet **Kontotyp** och ange sedan **US-001** i fältet **Konto**. Välj **Ekonomiska dimensioner \> Konto** för att visa ekonomiska dimensioner för kontotyper som inte är redovisningskonton. Följande standardvärden för ekonomiska dimensioner anges:

- **BUSINESSUNIT:** 002 – standardvärdet tas från journalrubriken. Värdet **001** anges inte som standard från kunden US-001 eftersom ett standardvärde redan har angetts.
- **COSTCENTER:** 007 – standardvärdet tas från inställningarna för kund US-001.
- **DEPARTMENT:** 024 – standardvärdet tas från journalrubriken.

Välj **Redovisning** i **Motkontotyp** när du är tillbaka på raden och ange sedan **600150** i fältet **Motkonto**. Följande standardvärden för ekonomiska dimensioner anges på raden:

- **BUSINESSUNIT:** 002 – standardvärdet tas från kontots ekonomiska dimensioner. (Det angavs ursprungligen som standard från journalrubriken.)
- **DEPARTMENT:** 024 – standardvärdet tas från kontots ekonomiska dimensioner. (Det angavs ursprungligen som standard från journalrubriken.)
- **COSTCENTER:** 007 – standardvärdet tas från kontots ekonomiska dimensioner. (Det angavs ursprungligen som standard från kunden.)

### <a name="scenario-3"></a>Scenario 3

Lägg till en ny rad i samma journal som du använde till scenario 2. Välj **Redovisning** i fältet **Kontotyp** och ange sedan **170150** i fältet **Konto**. Rensa standarddimensionsvärdena så att endast huvudkontot 170150 finns kvar. Välj **Kund** i fältet **Motkontotyp** och ange sedan **US-001** i fältet **Motkonto**. Följande standardvärden för ekonomiska dimensioner anges:

- **BUSINESSUNIT:** 002 – standardvärdet tas från journalrubriken, eftersom dimensionsvärdet för Konto är tomt. Värdet **001** anges inte som standard från kunden US-001 eftersom ett standardvärde redan har angetts från journalrubriken. Om värdet **BUSINESSUNIT** har lämnats tomt med avsikt, måste du även ta bort den ekonomiska dimensionen i motkontot.
- **COSTCENTER:** 007 – standardvärdet tas från kunden US-001, eftersom dimensionsvärdet för Konto och journalrubrikens dimensionsvärde är tomma. Om värdet **COSTCENTER** har lämnats tomt med avsikt, måste du även ta bort den ekonomiska dimensionen i motkontot.
- **DEPARTMENT:** 024 – standardvärdet tas från journalrubriken, eftersom dimensionsvärdet för Konto är tomt. Om värdet **DEPARTMENT** har lämnats tomt med avsikt, måste du även ta bort den ekonomiska dimensionen i motkontot.

### <a name="scenario-4"></a>Scenario 4

Använd samma standardvärden för ekonomiska dimension som du definierade för journalnamn och kund i scenariot 1 och 2. Definiera sedan ett fast dimensionsvärde för **BUSINESSUNIT**-dimensionen i huvudkontot 170150. Öppna **Redovisning \> Kontoplan \> Konton \> Huvudkonton**. Markera **170150** i fältet **Huvudkonto** och välj sedan **Lägg till** på fliken **Juridisk person åsidosätter**. Välj **USMF** som juridisk person och välj sedan **Lägg till**. Markera den posten och välj sedan **Standarddimensioner**. Ändra **BUSINESSUNIT-dimensionen** till **Fast värde** och ange **003** som värdet.

Skapa en ny allmän journal som använder namnet **GenJrn**. Ta bort alla standarddimensionsvärden på fliken **Ekonomiska dimensioner**.

Gå till **Rader**. Välj **Redovisning** i fältet **Kontotyp** och ange sedan **170150** i fältet **Konto**. Tryck sedan på **Tabb**-tangenten för att flytta ut från fältet. Dimensionsvärdena anges som standard från huvudkontot för kontot 170150. Därför visas värdet för **Konto** som **170150-003-**.

Ändra värdet för **Konto** till **170150-004-**. **Journalfunktionen förhindrar inte att ett fast dimensionsvärde ändras.** Ange antingen ett debetbelopp eller kreditbelopp. Välj **Redovisning** i fältet **Motkontotyp** och ange sedan **170250** i fältet **Motkonto**. Det ekonomiska dimensionsvärdet 004 anges som standard från kontot. Bokför sedan dokumentet. Välj **Verifikation** i journalen. Observera att **BUSINESSUNIT**-värdet återställdes till det fasta dimensionsvärdet **003** under bokföring.

När du returnerar till verifikationen i journalen återspeglar dimensionen **BUSINESSUNIT**-dimensionen **inte** det fasta dimensionsvärdet. Det har alltid värdet som visades på skärmen före bokföring. Bokföringsprocessen ändrar inte det som anges på verifikationen. Endast redovisningsposten ändras under bokföring.

## <a name="developer-notes"></a>Anmärkningar för utvecklare

Om du är utvecklare och vill titta på standardprocessens kod måste du granska följande metoder:

- **LedgerJournalEngine.accountModified()** – Den här metoden är startpunkten för den primära kontodimensionens standardprocess som är standard för alla journaler (och åsidosätts av vissa journaltyper).
- **LedgerJournalEngine.offsetAccountModified()** – Den här metoden är startpunkten för motkontodimensionens standardprocess.
