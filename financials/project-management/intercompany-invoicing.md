---
title: Koncernintern fakturering
description: "Denna artikel innehåller information och exempel om koncerninterna fakturering för projekt i Microsoft Dynamics 365 för operationer."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 94153
ms.assetid: 33e98da7-01c1-4369-923d-aa1c8326cb80
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 8a606f81e6e66390bf0add3deeeb032ab4cbd90b
ms.lasthandoff: 03/31/2017


---

# <a name="intercompany-invoicing"></a>Koncernintern fakturering

Denna artikel innehåller information och exempel om koncerninterna fakturering för projekt i Microsoft Dynamics 365 för operationer.

Din organisation kan ha flera dotterbolag, avdelningar och andra juridiska personer som överför produkter och tjänster till varandra för projekt. Den juridiska personen som tillhandahåller tjänsten eller produkten kallas den *utlåning juridisk person*, och den juridiska personen som tar emot tjänsten eller produkten kallas den *Lånande juridisk person*. 

Följande bild visar ett typiskt scenario där två juridiska personer, FRSI (den lånande juridiska personen) och USASI (den utlånande juridiska personen) delar resurser för att leverera ett projekt för kund A. I det här scenariot har FRSI i uppdrag att leverera arbetet till kund A. 

[![Exempel på koncerninterna fakturering](./media/interco.invoicing-01.jpg)](./media/interco.invoicing-01.jpg) 

Målet är att underlätta kostnadskontroll, intäktsredovisning, skatter och internpris för koncerninterna projekttransaktioner mer flexibelt och kraftfullt. Dessutom finns följande funktioner:

-   Skapa kundfakturor mot ett projekt för en lånande juridisk person med hjälp av koncerninterna tidrapporter, utgifter och leverantörsfakturor för en utlånande juridisk person.
-   Stöd för momsberäkningar och indirekta kostnader.
-   Skjuta upp intäktsredovisning för en utlånande juridisk person och när en lånande juridisk person ska godkänna kostnaden.
-   Periodisera intäkter för resurser i arbete (PIA) för den utlånande juridiska personen.
-   Ställa in överföringspriser som kan baseras på olika prismodeller. Nedan följer några exempel:
    -   **Kvantitet** – Det belopp du anger i fältet **Prissättning** är den faktiska kostnaden per kvantitet eller enhet.
    -   **Belopp för avgifter** – Priset/kostnaden per transaktion plus beloppet för avgifter som du anger i fältet **Prissättning**.
    -   **Procentuell avgift** – Överföringspriset är priset/kostnaden per transaktion multiplicerat med den procentuella avgiften som du anger i fältet **Prissättning**.
    -   **Procent av försäljningspriset** – Procentandelen av försäljningspriset som överförs till den utlånande juridiska personen.
    -   **Belopp under försäljningspriset** – Det belopp som den lånande juridiska personen håller tillbaka från försäljningspriserna före överföringen till den utlånande juridiska personen.
    -   **Täckningsgrad** – Den siffra du anger i fältet **Prissättning** täckningsgraden som uttrycks som en procentandel av försäljningspriset.

## <a name="example-1-set-up-parameters-for-intercompany-invoicing"></a>Exempel 1: Ställ in parametrar för koncernintern fakturering
I det här exemplet är US SI en utlånande juridisk person och dess resurser rapporterar tid mot den lånande juridiska personen, FR SI, som innehar kontraktet med slutkunden. Timmar och utgifter som anställda hos USSI rapporterar kan ingå i projektfakturan som FRSI genererar. Det finns dessutom en tredje källa för transaktioner som kan härledas från den utlånande juridiska personen (USSI i det här exemplet) om den innehåller delade leverantörstjänster till dotterbolag (till exempel FRSI) och sedan skickar dessa kostnader till projekt inom dessa dotterbolag. Alla matchande fakturadokument och momsberäkningarna utförs av Dynamics 365 för operationer. 

I det här exemplet måste FRSI vara en kund till den juridiska personen USSI och USSI måste vara en leverantör till den juridiska personen FRSI. Du kan ställa in en koncernintern relation mellan två juridiska personer. I följande procedur beskrivs hur du ställer in parametrarna så att båda de juridiska personerna kan delta i koncernintern fakturering.

1.  Ställ in FRSI som en kund till den juridiska personen USSI och ställ in USSI som en leverantör till den juridiska personen FRSI. Det finns tre startpunkter för de steg som krävs för uppgiften.
    | Steg | Startpunkt                                                                       | beskrivning   |
    |------|-----------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | A    | Klicka på USSI, **kundreskontra**&gt;**kunder**&gt;**alla kunder**. | Skapa en ny kundpost för FRSI och välj kundgrupp.                                                                                                                                                                                                                           |
    | B    | Klicka på FRSI, **Leverantörsreskontra**&gt;**leverantörer**&gt;**alla leverantörer**.        | Skapa en ny leverantörspost för USSI och välj leverantörsgrupp.                                                                                                                                                                                                                               |
    | C    | I FRSI, öppna leverantörsposten du just skapade.                            | I åtgärdsfönstret, på fliken **Allmänt**, i gruppen **Ställ in**, klicka på **Koncernintern**. På sidan **Koncernintern**, fliken **Handelsrelation**, ställ in skjutreglaget **Aktiv** på **Ja**. I fältet **Kundföretag**, markera kundposten som du skapade i steg A. |

2.  Klicka på **projekthantering och redovisning**&gt;**inställningar**&gt;**management redovisning Projektparametrar**, och klicka sedan på de **koncerninterna** fliken. Hur du ställer in parametrarna beror på om du är den lånande juridiska personen eller den utlånande juridiska personen.
    -   Om du är den lånande juridiska personen, välj anskaffningskategorin som ska användas för att matcha leverantörsfakturor och som genereras automatiskt.
    -   Om du är den utlånande juridiska personen markerar du en standardprojektkategori för varje transaktionstyp för varje lånande juridisk person. Projektkategorier används för konfigurering av skatt när den fakturerade kategorin i koncerninterna transaktioner endast finns för den lånande juridiska personen. Du kan välja om du vill periodisera intäkt för koncerninterna transaktioner. Den här periodiseringen utförs när transaktionerna bokförs och återförs sedan när den koncerninterna fakturan bokförs.

3.  Klicka på **projekthantering och redovisning**&gt;**inställningar**&gt;**priser**&gt;**överföringspriset**.
4.  Välj en valuta, transaktionstyp och överföringsprismodell. Den valuta som används på fakturan är den valuta som är konfigurerad i kundposten för den lånande juridiska personen hos den utlånande juridiska personen. Valutan används för att matcha poster i överföringsprislistan.
5.  Klicka på **redovisning**&gt;**bokföringsinställningar**&gt;**koncernintern redovisning**, och ange en relation för USSI och FRSI.

## <a name="example-2-create-and-post-an-intercompany-timesheet"></a>Exempel 2: Skapa och bokföra en koncernintern tidrapport
USSI, den utlånande juridiska personen måste skapa och bokföra tidrapporten för ett projekt från FRSI, den lånande juridiska personen. Det finns två startpunkter för de steg som krävs för uppgiften.

| Steg | Startpunkt                                                                       | beskrivning                                                                                                                                                                                       |
|------|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Projekthantering och redovisning**&gt;**tidrapporter**&gt;**alla tidrapporter** | Skapa en ny tidrapport. På raden tidrapport i fältet **Juridisk person**, markera **FRSI**. I fältet **Projekt-ID**, markera projektet i FRSI. Ange antalet timmar för varje dag i veckan. |
| G    | Sidan **Tidrapport**                                                                | Bokför tidrapporten och anteckna verifikationsnumret när arbetsflödet körs.                                                                                                               |

## <a name="example-3-create-and-post-an-intercompany-vendor-invoice"></a>Exempel 3: Skapa och bokföra en koncernintern leverantörsfaktura
USSI, den utlånande juridiska personen måste skapa och bokföra den koncerninterna leverantörsfakturan för ett projekt från FRSI, den lånande juridiska personen. Den här leverantörsfakturan representerar utkontrakterat arbete och kostnader som utfördes av leverantörer som betalas av USSI. Det finns två startpunkter för de steg som krävs för uppgiften.

| Steg | Startpunkt                                                                                      | beskrivning                                                                                                                                                                                                                                                                          |
|------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Leverantörsreskontra**&gt;**fakturor**&gt;**öppna leverantörsfakturor**&gt;**ny leverantörsfaktura** | Skapa en ny leverantörsfaktura och ange de tjänster som har införskaffats för FRSIS:s projekt.                                                                                                                                                                                  |
| G    | Sidan **Leverantörsfaktura**                                                                      | Ange rader som representerar de utkontrakterade tjänsterna för FRSI. På snabbfliken **Raddetaljer**, på fliken **Projekt**för fakturaraden, i fältet **Projektföretag**, ange **FRSI**. Ange projektet och motsvarande information. Bokför sedan leverantörsfakturan. |

## <a name="example-4-create-and-post-the-intercompany-invoice"></a>Exempel 4: Skapa och bokföra den koncerninterna leverantörsfakturan
USSI, den utlånande juridiska personen måste skapa och bokföra den koncerninterna fakturan. Det finns två startpunkter för de steg som krävs för uppgiften.

| Steg | Startpunkt                                                                                             | beskrivning                                                                                                                                      |
|------|---------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Projekthantering och redovisning**&gt;**projektfakturor**&gt;**koncernintern kundfaktura**  | Klicka på **Ny** för att öppna sidan **Skapa koncernintern faktura**.                                                                                  |
| B    | **Projekthantering och redovisning**&gt;**projektfakturor**&gt;**koncernintern kundfakturor** | På sidan **Skapa koncernintern faktura**, ange den juridiska personen, ange vilken transaktion som ska ingå och klicka sedan på **Sök**. |
| C    | **Projekthantering och redovisning**&gt;**projektfakturor**&gt;**koncernintern kundfakturor** | Välj vilka transaktioner som ska faktureras, eller klicka på **Markera alla** för att fakturera alla transaktioner i listan och klicka sedan på **OK**.                  |
| D    | Sidan **Koncernintern faktura**                                                                       | Det koncerninterna kundfakturaförslaget visas.                                                                                             |
| E    | Sidan **Koncernintern faktura**                                                                       | Klicka på **Bokför**.                                                                                                                                  |

## <a name="example-5-post-the-vendor-invoice-and-invoice-the-customer"></a>Exempel 5: Bokföra leverantörsfakturan och fakturera kunden
När den utlånande juridisk personen, USSI, bokför den koncerninterna kundfakturan skapas en matchande väntande leverantörsfaktura för den lånande juridiska personen, FRSI. Efter att denna leverantörsfaktura har bokförs fakturerar även FRSI projektkunden för de timmar som har angetts av USSI. Det finns tre startpunkter för de steg som krävs för uppgiften.

| Steg | Startpunkt                                                                                        | beskrivning                                                                                                             |
|------|----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| A    | **Leverantörsreskontra**&gt;**fakturor**&gt;**pågående leverantörsfakturor**                            | Granska fakturan om du vill kontrollera att tidrapportsvärdena ingår och bokför sedan leverantörsfakturan.                  |
| B    | **Projekthantering och redovisning**&gt;**projektfakturor**&gt;**projektfakturaförslag** | Skapa en ny projektfaktura för projektet och kontrollera att timtransaktionerna som bokförts visas.            |
| C    | Sidan **Projektfaktura**                                                                       | Välj projektfaktura och klicka sedan på **Visa detaljer** för att granska kostnads- och försäljningsbelopp. Bokför sedan fakturan. |



