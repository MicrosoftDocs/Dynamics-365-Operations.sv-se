---
title: Koncernintern fakturering
description: "Den här artikeln innehåller information om och exempel på koncernintern fakturering för projekt i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 94153
ms.assetid: 33e98da7-01c1-4369-923d-aa1c8326cb80
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 205903bb68804a46414410c85eacce03c6df6fc7
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="intercompany-invoicing"></a>Koncernintern fakturering

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller information om och exempel på koncernintern fakturering för projekt i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

Din organisation kan ha flera dotterbolag, avdelningar och andra juridiska personer som överför produkter och tjänster till varandra för projekt. Den juridiska person som tillhandahåller tjänsten eller produkten kalas för *Långivande juridisk person*, och den juridiska person som erhåller tjänsten eller produkten kallas för *Låntagande juridisk person*. 

Följande bild visar ett typiskt scenario där två juridiska personer, FRSI (den lånande juridiska personen) och USASI (den utlånande juridiska personen) delar resurser för att leverera ett projekt för kund A. I det här scenariot har FRSI i uppdrag att leverera arbetet till kund A. 

[![Exempel på koncernintern fakturering](./media/interco.invoicing-01.jpg)](./media/interco.invoicing-01.jpg) 

Målet är att göra kostnadskontroller, intäktsredovisningar, skatter och överföringspris för koncerninterna projekttransaktioner mer flexibla och effektiva. Dessutom finns följande funktioner:

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
I det här exemplet är US SI en utlånande juridisk person och dess resurser rapporterar tid mot den lånande juridiska personen, FR SI, som innehar kontraktet med slutkunden. Timmar och utgifter som anställda hos USSI rapporterar kan ingå i projektfakturan som FRSI genererar. Det finns dessutom en tredje källa för transaktioner som kan härledas från den utlånande juridiska personen (USSI i det här exemplet) om den innehåller delade leverantörstjänster till dotterbolag (till exempel FRSI) och sedan skickar dessa kostnader till projekt inom dessa dotterbolag. Alla matchande fakturadokument och momsberäkningar slutförs av Finance and Operations. 

I det här exemplet måste FRSI vara en kund till den juridiska personen USSI och USSI måste vara en leverantör till den juridiska personen FRSI. Du kan ställa in en koncernintern relation mellan två juridiska personer. I följande procedur beskrivs hur du ställer in parametrarna så att båda de juridiska personerna kan delta i koncernintern fakturering.

1.  Ställ in FRSI som en kund till den juridiska personen USSI och ställ in USSI som en leverantör till den juridiska personen FRSI. Det finns tre startpunkter för de steg som krävs för uppgiften.
    | Steg | Startpunkt                                                                       | beskrivning   |
    |------|-----------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | A    | I USSI klickar du på **Kundreskontra** &gt; **Kunder** &gt; **Alla kunder**. | Skapa en ny kundpost för FRSI och välj kundgrupp.                                                                                                                                                                                                                           |
    | B    | I FRSI klickar du på **Leverantörsreskontra** &gt; **Leverantörer** &gt; **Alla leverantörer**.        | Skapa en ny leverantörspost för USSI och välj leverantörsgrupp.                                                                                                                                                                                                                               |
    | C    | I FRSI, öppna leverantörsposten du just skapade.                            | I åtgärdsfönstret, på fliken **Allmänt**, i gruppen **Ställ in**, klicka på **Koncernintern**. På sidan **Koncernintern**, fliken **Handelsrelation**, ställ in skjutreglaget **Aktiv** på **Ja**. I fältet **Kundföretag**, markera kundposten som du skapade i steg A. |

2.  Klicka på **Projektledning och redovisning** &gt; **Inställningar** &gt; **Redovisningsparametrar för projekthantering**, och klicka sedan på fliken **Koncernintern**. Hur du ställer in parametrarna beror på om du är den lånande juridiska personen eller den utlånande juridiska personen.
    -   Om du är den lånande juridiska personen, välj anskaffningskategorin som ska användas för att matcha leverantörsfakturor och som genereras automatiskt.
    -   Om du är den utlånande juridiska personen markerar du en standardprojektkategori för varje transaktionstyp för varje lånande juridisk person. Projektkategorier används för konfigurering av skatt när den fakturerade kategorin i koncerninterna transaktioner endast finns för den lånande juridiska personen. Du kan välja om du vill periodisera intäkt för koncerninterna transaktioner. Den här periodiseringen utförs när transaktionerna bokförs och återförs sedan när den koncerninterna fakturan bokförs.

3.  Klicka på **Projekthantering och redovisning** &gt; **Inställningar** &gt; **Priser** &gt; **Överföringspris**.
4.  Välj en valuta, transaktionstyp och överföringsprismodell. Den valuta som används på fakturan är den valuta som är konfigurerad i kundposten för den lånande juridiska personen hos den utlånande juridiska personen. Valutan används för att matcha poster i överföringsprislistan.
5.  Klicka på **Redovisning** &gt; **Bokföringsinställningar** &gt; **Koncernintern redovisning** och skapa en relation för USSI och FRSI.

## <a name="example-2-create-and-post-an-intercompany-timesheet"></a>Exempel 2: Skapa och bokföra en koncernintern tidrapport
USSI, den utlånande juridiska personen måste skapa och bokföra tidrapporten för ett projekt från FRSI, den lånande juridiska personen. Det finns två startpunkter för de steg som krävs för uppgiften.

| Steg | Startpunkt                                                                       | beskrivning                                                                                                                                                                                       |
|------|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Projekthantering och redovisning** &gt; **Tidrapporter** &gt; **Alla tidrapporter** | Skapa en ny tidrapport. På raden tidrapport i fältet **Juridisk person**, markera **FRSI**. I fältet **Projekt-ID**, markera projektet i FRSI. Ange antalet timmar för varje dag i veckan. |
| G    | Sidan **Tidrapport**                                                                | Bokför tidrapporten och anteckna verifikationsnumret när arbetsflödet körs.                                                                                                               |

## <a name="example-3-create-and-post-an-intercompany-vendor-invoice"></a>Exempel 3: Skapa och bokföra en koncernintern leverantörsfaktura
USSI, den utlånande juridiska personen måste skapa och bokföra den koncerninterna leverantörsfakturan för ett projekt från FRSI, den lånande juridiska personen. Den här leverantörsfakturan representerar utkontrakterat arbete och kostnader som utfördes av leverantörer som betalas av USSI. Det finns två startpunkter för de steg som krävs för uppgiften.

| Steg | Startpunkt                                                                                      | beskrivning                                                                                                                                                                                                                                                                          |
|------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Leverantörsreskontra** &gt; **Fakturor** &gt; **Öppna leverantörsfakturor** &gt; **Ny leverantörsfaktura** | Skapa en ny leverantörsfaktura och ange de tjänster som har införskaffats för FRSIS:s projekt.                                                                                                                                                                                  |
| G    | Sidan **Leverantörsfaktura**                                                                      | Ange rader som representerar de utkontrakterade tjänsterna för FRSI. På snabbfliken **Raddetaljer**, på fliken **Projekt** för fakturaraden, i fältet **Projektföretag**, ange **FRSI**. Ange projektet och motsvarande information. Bokför sedan leverantörsfakturan. |

## <a name="example-4-create-and-post-the-intercompany-invoice"></a>Exempel 4: Skapa och bokföra den koncerninterna leverantörsfakturan
USSI, den utlånande juridiska personen måste skapa och bokföra den koncerninterna fakturan. Det finns två startpunkter för de steg som krävs för uppgiften.

| Steg | Startpunkt                                                                                             | beskrivning                                                                                                                                      |
|------|---------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Projekthantering och redovisning** &gt; **Projektfakturor** &gt; **Koncernintern kundfaktura**  | Klicka på **Ny** för att öppna sidan **Skapa koncernintern faktura**.                                                                                  |
| B    | **Projekthantering och redovisning** &gt; **Projektfakturor** &gt; **Koncerninterna kundfakturor** | På sidan **Skapa koncernintern faktura**, ange den juridiska personen, ange vilken transaktion som ska ingå och klicka sedan på **Sök**. |
| C    | **Projekthantering och redovisning** &gt; **Projektfakturor** &gt; **Koncerninterna kundfakturor** | Välj vilka transaktioner som ska faktureras, eller klicka på **Markera alla** för att fakturera alla transaktioner i listan och klicka sedan på **OK**.                  |
| D    | Sidan **Koncernintern faktura**                                                                       | Det koncerninterna kundfakturaförslaget visas.                                                                                             |
| E    | Sidan **Koncernintern faktura**                                                                       | Klicka på **Bokför**.                                                                                                                                  |

## <a name="example-5-post-the-vendor-invoice-and-invoice-the-customer"></a>Exempel 5: Bokföra leverantörsfakturan och fakturera kunden
När den utlånande juridisk personen, USSI, bokför den koncerninterna kundfakturan skapas en matchande väntande leverantörsfaktura för den lånande juridiska personen, FRSI. Efter att denna leverantörsfaktura har bokförs fakturerar även FRSI projektkunden för de timmar som har angetts av USSI. Det finns tre startpunkter för de steg som krävs för uppgiften.

| Steg | Startpunkt                                                                                        | beskrivning                                                                                                             |
|------|----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| A    | **Leverantörsreskontra** &gt; **Fakturor** &gt; **Väntande leverantörsfakturor**                            | Granska fakturan om du vill kontrollera att tidrapportsvärdena ingår och bokför sedan leverantörsfakturan.                  |
| B    | **Projekthantering och redovisning** &gt; **Projektfakturor** &gt; **Projektfakturaförslag** | Skapa en ny projektfaktura för projektet och kontrollera att timtransaktionerna som bokförts visas.            |
| C    | Sidan **Projektfaktura**                                                                       | Välj projektfaktura och klicka sedan på **Visa detaljer** för att granska kostnads- och försäljningsbelopp. Bokför sedan fakturan. |






