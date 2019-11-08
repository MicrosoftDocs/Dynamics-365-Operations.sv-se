---
title: Ekonomiska insikter
description: Ekonomiska insikter använder Microsoft Power BI för att sammanföra bokslut, diagram och ekonomiska nyckeltal (KPI).
author: kweekley
manager: AnnBe
ms.date: 05/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 596a067611ac4477f4469dbbc370c971e0f7a35d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181782"
---
# <a name="financial-insights"></a>Ekonomiska insikter

[!include [banner](../includes/banner.md)]

**Ekonomiska insikter**använder Microsoft Power BI för att sammanföra bokslut, diagram och ekonomiska nyckeltal (KPI). Power BI är inbäddad i appen. Tyngdpunkten i **Ekonomiska insikter** är analytisk rapportering. All personal i organisationen kan läsa, undersöka, förstå och agera. 

**Ekonomiska insikter** kombinerar data från redovisningen och reskontran för att ge en mer fullständig bild av den ekonomiska situationen i en organisation.

> [!NOTE]
> Det här dokumentet använder följande termer från Power BI:
> 
> - **Rapport** – en enda .pbix fil som sparar alla flikars samtliga visuella element.
> - **Sida** – en flik i en enda .pbix-fil. Varje sida kan innehålla en eller flera visuella element.
> - **Visuellt element** – en enda datakälla, till exempel kort, KPI, diagram, matris eller bokslut. En sida som har ett bokslut som ett visuellt element kan inte ha andra visuella element, på grund av storleken på de data som rapporteras.

För närvarande används **Ekonomiska insikter** för att visa data för den aktiva juridiska personen eller alla juridiska personer. I framtida versioner kommer arbetsytan att utvecklas till den plats där du kan använda Power BI för att redigera och skapa visuella element.

Arbetsytan **Översikt över ekonomichef** visar samma visuella element som **Ekonomiska insikter**, men fokuserar på att du kan visa och filtrera data i befintliga rapporter. I framtida versioner kommer du att kunna lägga till nya bilder till arbetsytan **Ekonomiska insikter**. De nya visuella elementen kan också bli tillgängliga på arbetsytor som är särskilt avsedda för andra roller, till exempel projektledare eller ekonomichefer. Arbetsytan **Översikt över ekonomichef** visar fortsättningsvis data för alla juridiska personer, oavsett vilken roll de juridiska personerna har tillgång till.

## <a name="dynamics-365-finance-setup"></a>Dynamics 365 Finance-konfiguration
**Redovisning**

Huvudkontotypen och huvudkontonas kategorier används för att fylla i lämpliga standardkonton i **balansräkning**, bokslut och de olika **resultaträkningarna** och boksluten i **Ekonomiska insikter**.

På sidan för **huvudkonton** måste du definiera ditt huvudkonto så att en av följande typer tilldelas kontot:

- Intäkter
- Expense
- Tillgångar
- Skulder
- Eget kapital

Tilldela inte kontot någon annan huvudkontotyp, t ex **balansräkning** eller **resultat**. Rapporteringen kan inte avgöra typ av huvudkonto när andra typer av huvudkontotyper tilldelas kontot, eftersom de inte är tillräckligt detaljerade. Typ av huvudkonto måste bestämmas för att skulder och intäkter ska visas som positiva belopp i ekonomiska rapporter.

För att visas i bokslut och inkluderas i andra visuella element, t ex KPI:er, måste varje huvudkonto tilldelas en huvudkontokategori. Kategorier för huvudkonton har förbättrats så att de omfattar en visningsordning. Ordningen används särskilt för bokslut i **Ekonomiska insikter**. När du redigerar eller lägger till en ny huvudkontokategori kan du ändra värdet på den **visningsordning** som definierar vilken ordning kategorier för huvudkonton ska visas i ett bokslut. Om du behöver ändra visningsordningen för många huvudkontokategorier använder du funktionen för att öppna i Excel för att snabbt redigera och publicera ändringarna i appen.

## <a name="entity-store"></a>Enhetslagring
Data för **Ekonomiska insikter** hämtas från enhetsbutiken (**systemadministration** \> **inställningar** \> **enhetsbutik**). Om du öppnar arbetsytorna för **Översikt över ekonomichef** eller **Ekonomiska insikter** och följande varningsmeddelande visas måste du uppdatera enheterna.

![Varning](./media/Cantdisplay.png)

Du måste uppdatera följande enheter om du vill se data i arbetsytorna **Ekonomiska insikter** och **Översikt över ekonomichef**:

- Ekonomi rapport transaktionsdata version 2 (**Obs!** Detta är nytt med version 10.0.1 och ersätter den tidigare enheten.)
- Transaktionsdata för ekonomiska rapporter
- CustCollectionsBIMeasurements
- LedgerCovLiquidityMeasurement
- Inköpskub
- Försäljningskub

I tidigare utgåva användes enheterna LedgerActivityMeasure och VendPaymentBIMeasure för data i arbetsytan **Översikt över ekonomichef**. Men dessa används inte i den nuvarande versionen.

Du kan definiera ett återkommande batchjobb för att regelbundet uppdatera data i enheterna. Eftersom varje enhet återskapas fullständigt under en uppdatering ska du noggrant välja tid och frekvens för uppdateringar. Den primära enhet som används för bokslut är enheten FinancialReportingTransactionData. Därför kanske du vill uppdatera just den enheten oftare.

## <a name="security"></a>Säkerhet
För närvarande kan inte data i inbäddade Power BI-rapporter begränsas till de juridiska personer som användaren har åtkomst till. Därför kontrolleras inbäddade Power BI-rapporter via uppgifter i säkerhetsinställningarna. Behörigheterna som definierar åtkomst till data gäller antingen för alla juridiska personer eller endast för det aktiva företaget. Följande register visar de behörigheter som finns och vilka roller som de har tilldelats. Behörigheter kan tas bort eller tilldelas till olika roller, utifrån organisationens behov.

| Avgift                                    | Roller | Beskrivning |
|-----------------------------------------|-------|------------|
| Visa arbetsyta för ekonomichefsöversikt             | Ekonomichef | Behörigheten ger åtkomst till arbetsytan Översikt över ekonomichef. Normalt används det aktiva företaget som ett filter. Du kan emellertid lägga till alla juridiska personer, oavsett om användaren har åtkomst till de övriga juridiska personerna. |
| Visa aktuellt företag för ekonomiska insikter | <ul><li>Redovisare</li><li>Redovisningschef</li><li>Redovisningsansvarig</li><li>Revisor</li><li>Budgetchef</li><li>Verkställande direktör</li><li>Ekonomichef</li><li>Ekonomicontroller</li></ul> | Behörigheten ger tillgång till Ekonomiska insikter. Normalt används det aktiva företaget som ett filter. Du kan inte lägga till andra juridiska personer. |
| Visa korsföretag för ekonomiska insikter   | In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, uppgiften inte är tilldelade till en roll. I nästa utgåva kommer behörigheten att tilldelas rollen ekonomichef. | Behörigheten ger åtkomst till menyn för arbetsytan Översikt över ekonomichef. Normalt används det aktiva företaget som ett filter. Du kan emellertid lägga till alla juridiska personer, oavsett om användaren har åtkomst till de övriga juridiska personerna. |


## <a name="financial-reporting-vs-finanical-insights"></a>Ekonomisk rapportering jämfört med finansiell information
Även om **ekonomiska insikter** innehåller bokslut ersätter det inte ekonomisk rapportering i appen. Standardbokslut i **ekonomiska insikter** är begränsade och innehåller inte alla typer av bokslut. Ekonomiska rapporter är fortfarande huvudverktyget för att utforma, skapa och generera lagstadgade bokslut.

Jämförelsediagrammet nedan hjälper dig att skilja de två alternativen:


|                                                          | Ekonomisk rapportering                                               | Ekonomiska insikter |
|----------------------------------------------------------|-------------------------------------------------------------------|--------------------|
| **Redigera standardrapporter**                                 | Ja                                                               | Nr |
| **Skapa nya rapporter**                                   | Ja                                                               | Nr |
| **Skriv ut rapporter**                                        | Ja                                                               | Nr |
| **Exportera till Excel**                                      | Ja                                                               | Begränsade exporter av rådata till Excel, inte en formaterad rapport |
| **Stöd för rapportering av hierarki/organisationshierarki**   | Ja                                                               | Nr |
| **Rapport för redovisningsjournal**                             | Ja Begränsat till en enda leverantör, kund                              | Ja Leverantör, kund, leverantör/kundgrupper, adresser för leverantör/kundgrupp osv. |
| **Rapporteringsvaluta**                                   | Ja Redovisningsvaluta och översätt till rapporteringsvaluta       | Nej Endast redovisningsvaluta |
| **Säkerhet**                                             | Ja Ansluter sig till Finance och rapportträdsäkerhet | Begränsad Visa rapporter för alla företag (oavsett Finance and Operations-säkerhet) eller endast aktiva företag |
| **Stöd för olika kontoplaner och räkenskapsår** | Ja                                                               | Nr |
| **rapport för externa data**                              | Nr                                                                | Nr |
| **Ge stöd till konsolideringar**                               | Ja                                                               | Begränsad Kan rapportera om flera företag men endast använda redovisningsvalutan |

Utöver användargränssnittet i den ursprungliga arbetsytan **Översikt för ekonomichef** är diagram, nya KPI: er och bokslut nu också tillgängliga. Följande bokslut är tillgängliga:

- Råbalans
- Balansräkning
- Resultaträkning per region
- Resultaträkning - utfall jämfört med budget
- Resultaträkning med avvikelser
- Resultaträkning med tolv månaders trend
- Utgifter - treårig trend
- Utgifter per leverantör
- Försäljning per kund

## <a name="edit-visuals"></a>Redigera visuella element
I den ursprungliga versionen av **Ekonomiska insikter**kunde inga visuella element redigeras. I framtida versioner kommer användare som har lämplig behörighet kunna skapa nya visuella element, kopiera befintliga och redigera elementen. Även om .pbix-filer som innehåller rapporter är tillgängliga som resurser, rekommenderas inte att du ändrar i standardrapporterna. Ytterligare ändringar kommer att göras i de visuella element för egna bokslut, standardrapport och datamodell som används för bokslut. För att dra nytta av nya funktioner och ändringar i nästa versions datamodell måste du göra om alla ändringar som du gjort i standardrapporterna via Microsoft Power BI Desktop.

## <a name="filtering"></a>Filtrering
Användare kan filtrera rapporten med hjälp av fönstret **Filter** till vänster. Det här fönstret är detsamma som det som finns på skrivbordet för Power BI Desktop. Det finns olika nivåer av filtrering, varav en del kanske inte är tillgängliga, beroende på vad du har markerat på en sida (flik) eller om du använder funktionerna för detaljgranskning:

- **Rapportnivåfilter** – dessa filter tillämpas på alla visuella element på alla sidor (flikar).
- **Sidnivåfilter** – dessa filter tillämpas på alla visuella element på den aktiva fliken. Filtren läggs ovanpå rapportnivåfiltren.
- **Visuellt filter** – dessa filter tillämpas endast på det utvalda visuella elementet. Dessa filter läggs ovanpå sidnivåfiltren.
- **Detaljgranskningsfilter** – detta filter filtrerar från ett "visuellt källelement" som tillämpas på aktuellt element när du detaljgranskar från källan till aktuellt visuellt element.

![Filter](./media/filter.png)

Välj symbolen för att radera om du vill ta bort ett specifikt filtervärde. Ta inte bort ett filter genom att markera X. Om du väljer X raderas det fält som du filtrerar och försvinner som filteralternativ. Om du av misstag tar bort ett fält från filtret kan du stänga arbetsytan och öppna den igen. Standardinställningarna för filtret kommer att återställas.

Första gången du öppnar arbetsytor används den aktiva juridiska personen som rapportnivåfilter. Beroende på deras behörighet kanske användarna kan lägga till andra juridiska personer eller ändra den standardinställning för juridisk person som har valts i filtret.

Filtret för **räkenskapskalender** krävs för att rätt kalender ska användas för det visuella elementet. Som standard sätts rapportnivåfiltret till den aktiva juridiska personens räkenskapskalender. Om du ändrar filtret till en räkenskapskalender med annat start- eller slutdatum kommer inte ingående balanser att inkluderas. Därför kommer bokslutet **balansräkning** inte att visa korrekta saldon. Om du väljer ytterligare en räkenskapskalender i filtret, får du ytterligare en uppsättning kolumner. Varje ytterligare uppsättning kolumner visar beloppen för en annan räkenskapskalender.

Filtret **bokföringsskikt** krävs också. Som standard ställs filtret in på aktuellt. Du kan välja ytterligare bokföringsskikt i filtret för att visa de sammanlagda beloppen.

Filter finns också för fälten **datum** och **räkenskapsår**. Vanligtvis tillämpas filtren på sidnivå. Som standard använder filtret för **datum** ett relativt datum som du kan ändra. Du kan ta bort det relativa datumfiltret och använda filter för **räkenskapsår** istället.

## <a name="currency"></a>Valuta

Alla visuella element som rapporterar redovisningsdata visar belopp i redovisningsvalutan. När du filtrerar på den juridiska personen ska du därför vara noga med att inkludera endast juridiska personer som har samma redovisningsvaluta. I annat fall kan du samla data i olika valutor.

Alla effekter som rapporteras i redovisningsjournalen, såsom **kassaflödesprognos** och **top 10** visuella element, visar belopp i systemvalutan. Systemvaluta och systemets valutakurstyp definieras på sidan **systemparametrar**.

**Saldo per bankkonto** använder belopp i bankkontots valuta.

## <a name="dimensions"></a>Dimensioner

Som standard inkluderar bokslut inte ekonomiska dimensioner, utan fokuserar endast på huvudkontot. Stöd för ekonomiska dimensioner kan användas i kommande versioner, när rapporterna kan redigeras. Organisationer kommer sedan att kunna filtrera efter värden för ekonomiska dimensioner.

Vissa bokslut innehåller dimensioner som baseras på transaktioner i redovisningsjournalen. Syftet med de nya boksluten är att kunna filtrera på dimensioner som inte är inställda som ekonomiska dimensioner. Till exempel så låter standardrapporten för utgifter per leverantör att du kan expandera bortom huvudkontot, så att du kan visa saldona per leverantör. Leverantören finns inte som en ekonomisk dimension. I stället återgår systemet till den ursprungliga transaktionen i redovisningsjournalen för att hitta leverantören.

Följande dimensioner används i standardrapporter. Inga av dessa dimensioner är ekonomiska dimensioner.

- Leverantör
- Leverantörsgrupp
- Kund
- Kundgrupp
- Land/region
- Delstat/region
- Ort

> [!IMPORTANT] 
> Om du har summerat transaktioner för flera leverantörer eller kunder i en enda verifikation med hjälp av de ekonomiska journalerna blir dessa data felaktiga. Rapporteringen kan inte avgöra vilken leverantör eller kund som hör till ett visst redovisningskonto i en journalpost eftersom informationen inte underhålls någonstans. Därför rekommenderar vi inte att du anger flera leverantörer, kunder, anläggningstillgångar och projekt i en enda verifikation.

## <a name="drill-on-data"></a>Granska data

Olika nivåer av granskning är tillgängliga via Power BI. Varje nivå har olika namn och olika funktioner. Du kan också granska rader och kolumner. Det här avsnittet beskriver de olika alternativen med hjälp av bokslutet **råbalans** som ett exempel och visar hur du kan granska raderna. Samma funktion finns för kolumner. Du behöver bara ändra inställningen för **Detaljgranska**.

På följande bild är utdraget **råbalans** komprimerat till den högsta nivån i radhierarkin, dvs huvudkontotypen.

![Råbalans](./media/trial-balance.png)

Om du vill visa nästa nivå i hierarkin huvudkontokategorier, kan du ställa in fältet **Detaljgranska** till **rader** och välj sedan knappen **visa** (den tredje efter granskningsfältet). Nu visas alla huvudkontokategorier i expanderat format. För närvarande kan Power BI inte expandera bara en rad eller kolumn och samtidigt visa alla de andra raderna eller kolumnerna.

![Råbalans](./media/trial-balance2.png)

För att expandera till huvudkonton för alla rader kan du åter använda knappen **visa**. Men om du vill granska huvudkonton för en enstaka rad väljer du först knappen **detaljgranska** (den enda nedåtriktade pilen till höger i fönstret) och markerar sedan den rad du vill detaljgranska. I följande bild visas resultatet när raden **Sales** har markerats efter att knappen **detaljgranska** har valts.

![Råbalans](./media/trial-balance3.png)

När du detaljgranskar en enda rad krävs flera val för att återgå till full råbalans. Knappen för **upp** (den första knappen efter **detaljgranska**) går uppåt endast vad gäller kategorin **Sales**, vilket visas i följande illustration.

![Råbalans](./media/trial-balance4.png)

Du kan fortsätta att använda knappen **upp** för att gå tillbaka till den högsta nivån av sammanfattning för raderna.

Power BI har även en knapp som gör att du kan gå till nästa nivå i hierarkin (den andra knappen efter fältet **detaljgranska**). Effekten av den här knappen skiljer sig från effekterna av knappen **expandera** (tredje knappen efter fältet **detaljgranska**), som används för att expandera hierarkin. När du expanderar hierarkin underhålls hierarkin i rapporten. Till exempel, som visades tidigare, om du expanderar på huvudkontotypen syns fortfarande huvudkontotypen i rapporten. Men när du går till nästa nivå i hierarkin visar rapporten inte längre den överordnade hierarkin, enligt följande illustration.

![Råbalans](./media/trial-balance5.png)

För att se transaktionsdetaljer bakom summerade saldon kan du välja att granska vissa summor tillbaka till Financial and Operations.

Granskningen av boksluten tar dig till Accounting source explorer (ASE), inte till verifikationstransaktioner. ASE visar inte bara redovisningsposter i redovisningen. I stället visas detaljer om transaktionen i redovisningsjournalen. På så sätt får du mer detaljerad information om den ursprungliga transaktionen och kan använda den för analys. Till exempel kan du se leverantör eller kund, vad kunden köpte eller leverantören sålde och även vilka projekt som fanns på transaktionen.

Följande filter från boksluten skickas till ASE, så att ASE visar de transaktioner som sammanställs:

Obligatoriska fält för att filtrera:

- Juridisk person
- Räkenskapskalender
- År
- Huvudkonto-ID

Valfria fält för att filtrera:

- Kvartal
- Månad
- Period

Om du inte expanderar en rad tillräckligt fungerar inte detaljgranskningen. Om du till exempel bara expanderar till huvudkontokategorin kan du inte detaljgranska saldo i ASE, eftersom huvudkontot är ett obligatoriskt fält för att filtrera i ASE.

Om du expanderar en rad för mycket skickas inte ytterligare filter på boksluten till ASE. Därför kan talen skilja sig. Till exempel, om du expanderar ned till land eller region på bokslutets rader för inkomstutdrag kommer land eller region inte att inkluderas som ett filter i ASE.

> [!NOTE]
> Du kan detaljgranska bokslutets rader eller kolumner mer än det som ASE för tillfället ger stöd för. I vissa situationer kanske beloppen därför inte matchar den summa i ASE som du granskar. Den här funktionen utvecklas vidare i framtiden.

## <a name="hierarchies"></a>Hierarkier

Standardbokslut använder två hierarkier för att granska och expandera data. En hierarki är för raderna och den andra för kolumnerna. Båda hierarkierna är fördefinierade i designen av bokslutet. För de flesta bokslut är radhierarkin är **huvudkontotyp** \> **huvudkontokategorier** \> **huvudkonto**. Vissa rapporter kan dock ha ytterligare fält, t ex land och region. Övriga noder i hierarkin är baserade på varje transaktions data i redovisningsjournalen.

För kolumner fokuserar hierarkin på de juridiska personerna och räkenskapsperioder. För de flesta bokslut är kolumnhierarkin **Juridisk person** \> **Räkenskapskalender** \> **Räkenskapsår** \> **Kvartal** \> **Period**.

För närvarande stöder boksluten inte organisationshierarkier som gör att du kan samla in data.

## <a name="data-limitations"></a>Databegränsningar
De visuella elementen för bokslut har en gräns för hur många rader som kan visas. För närvarande är gränsen satt till 30 000. Om du överskrider den här gränsen ser du en varningssymbol som informerar dig om detta.

![Databegränsningar](./media/data-limit.png)

Om maximalt antal överskrids blir summorna som visas i bokslutet felaktiga, eftersom inte alla rader har lästs in i det visuella elementet.

### <a name="empty-rows"></a>Tomma rader
Power BI har inte något alternativ för att visa och dölja tomma rader. Om en rad inte innehåller några data visas den inte.


## <a name="additional-resources-for-power-bi"></a>Ytterligare resurser för Power BI

Informationen i följande resurser krävs inte för att aktivera inbäddade rapporter i arbetsytan för **Översikt över ekonomichef** eller **Ekonomiska insikter** i en produktionsmiljö. Däremot är de användbara för dev och om du vill bädda in Power BI rapporterna.

- <https://blogs.msdn.microsoft.com/dynamicsaxbi/2017/07/29/accessing-analytical-workspaces-on-1box-environment/>

- <https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/add-analytics-tab-workspaces>