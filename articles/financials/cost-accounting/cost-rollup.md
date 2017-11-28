---
title: "Policy för samlade kostnader och omkostnadsberäkning"
description: "Det här avsnittet innehåller information om hur du avgör korrekt nivå på sekundära kostnadselement och skapar regler för samlade kostnader som passar organisationens rapportering och kostnadsspårbarhet."
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostRollupRule, CAMDimensionHierarchy
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 044a943eeba91f5dbebd4dcd70bc8152c4109037
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="cost-rollup-policy-and-overhead-calculation"></a>Policy för samlade kostnader och omkostnadsberäkning 

[!include[banner](../includes/banner.md)]

Kostnadsredovisning låter dig få en inblick i hur kostnadsflödet relaterar till produkter och tjänster som levereras inom en organisation. För att se kostnadstransparens är det viktigt att uppnå kostnadsfördelning mellan kostnadsobjekt utifrån en lämplig allokeringsbas. Kostnadsfördelning uppnås som standard för det primära kostndselementet vilket önskas i vissa situationer, men har några konsekvenser som du bör överväga.

-   Extra kostnadsobjekt slutar med ett nollsaldo för det primära kostnadselementet efter omkostnadsberäkning.

-   Volymen för kostnadstransaktionerna som skapas av omkostnadsberäkning kan vara mycket hög.

-   Det går inte att spåra kostnadsflödet mellan kostnadsbärare.

För att undvika de här effekterna kan du konfigurera kostnadsallokering med kostnadsredovisningen för att passa din organisation ledarskaprapportering. Det här avsnittet innehåller information om hur du avgör korrekt nivå på sekundära kostnadselement och skapar regler för samlade kostnader som passar organisationens rapportering och kostnadsspårbarhet.

> [!NOTE]
> Du kan ändra konfigurationer om rapporteringskraven ändras.

## <a name="example-of-cost-rollup-policy-setup"></a>Exempel på inställning av policy för samlad kostnad

Anta att företaget har följande struktur med 4 kostnadsställen.

![Exempel organisationsstruktur](./media/dimension-hierarchy-org.png)

**Kostnadsobjektdimension**

| Kostnadsställen | beskrivning          |
|--------------|-----------|
| CC001        | Personal        |
| CC002        | Finansiellt   |
| CC003        | Sammansättning  |
| CC004        | Paketering |

**Dimension för kostnadselement**

| Kostnadselement | beskrivning | Typ    |
|---------------|-------------|---------|
| 1001          | Elektricitet | Primär |
| 1002          | Löner    | Primär |
| 1003          | Reklam | Primär |

En dimensionshierarki som uppfyller rapporteringskraven för organisationen kan ställas in på följande sätt.

**Detaljer om dimensionshierarki**

| Dimensionshierarkins namn | Dimension    | Namn på typ av dimensionshierarki      | Hierarki för åtkomstlista |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organisation             | Kostnadsställen | Hierarki för dimensionsklassificering | Nr                    |

**Dimensionshierarki**

|              | Dimensionsmedlemsintervall |                     |
|--------------|-------------------------|---------------------|
| **Noder**        | **Från dimensionsmedlem**   | **Till dimensionsmedlem** |
| Organisation |                         |                     |
| &nbsp;&nbsp;Admin             |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Finansiellt              | CC001                   | CC001               |
| &nbsp;&nbsp;&nbsp;&nbsp;Personal               | CC002                   | CC002               |
| &nbsp;&nbsp;Produktion               |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Paketering              | CC003                   | CC003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Sammansättning             | CC004                   | CC004               |

En dimensionshierarki som uppfyller policykraven kan ställas in på följande sätt.

**Detaljer om dimensionshierarki**

| Dimensionshierarkins namn | Dimension     | Namn på typ av dimensionshierarki      |
|--------------------------|---------------|------------------------------------|
| Resultaträkning  | Kostnadselement | Hierarki för dimensionsklassificering |

**Dimensionshierarki**

|                         | Dimensionsmedlemsintervall |                     |
|-------------------------|-------------------------|---------------------|
| Noder                   | Från dimensionsmedlem   | Till dimensionsmedlem |
| Resultaträkning |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Primärkostnad                    | 10001                   | 10003               |

När redovisningstransaktionerna bearbetas ser kostnadsbalanspost för kostnadsobjekt ut så här.

|                      | **Kostnadsobjekt** |           |           |           | **Summa**     |
|----------------------|-----------------|-----------|-----------|-----------|---------------|
| **Kostnadselement**     | **CC001**       | **CC002** | **CC003** | **CC004** |               |
| **1001 Elektricitet** | 100,00          | 200 000    | 6.000,00  | 2.000,00  | **8.300,00**  |
| **1002 Löner**    | 10.000,00       | 10.000,00 | 8.000,00  | 6.500,00  | **34.500,00** |
| **1003 Reklam** | 0,00            | 4.000,00  | 0,00      | 0,00      | **4.000,00**  |
|                      | 10.100,00       | 14.200,00 | 14.000,00 | 8.500,00  | **46.800,00** |

**Statistikdimension**

| Statistiska element |    beskrivning   |
|----------------------|------------------|
| SE-1                 | HR-tjänster      |
| SE-2                 | Finanstjänster |

Kostnadsobjekt CC001 HR bidrar till HR-tjänster för flera kostnadsobjekt.

HR-tjänsterna används av följande fördelning av storleken.

| Kostnadsobjekt | beskrivning |   HR-tjänster |
|-------------|-------------|----|
| CC002       | Finansiellt     | 35 |
| CC003       | Sammansättning    | 55 |
| CC004       | Paketering   | 10 |

Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.

Finanstjänsterna används av följande fördelning av storleken.

| Kostnadsobjekt |   beskrivning    |  Finanstjänster   |
|-------------|------------------|----|
| CC003       | Sammansättning         | 65 |
| CC004       | Paketering        | 35 |

Kostnadsfördelningspolicyer kan ställas in på följande sätt.

| Policynamn | beskrivning     | Dimensionshierarki för kostnadsobjekt | Statistikdimension | Dimension för kostnadselement |
|-------------|-----------------|---------------------------------|-----------------------|------------------------|
| 2017        | Kostnadsallokering | Organisation                    | Statistiska element  | Kostnadselement          |

Kostnadsfördelningsregler kan ställas in på följande sätt.

| Dimensionshierarkinod för kostnadsobjekt | Kostnadsbeteende | Allokeringsunderlag        |
|--------------------------------------|---------------|------------------------|
| CC001                                | Totalt         | **HR-tjänster**        |
| CC002                                | Totalt         | **Ekonomitjänster** |

<a name="brhow-cost-flows-between-cost-centers"></a><br>Hur kostnadsflödet går mellan kostnadsställen 
---------------------------------------------------

Om du vill veta hur kostnadsflödet går mellan kostnadsställen i organisationen kan du skapa kostnadselement av typen **sekundär** för varje kostnadsställe. Dessa kostnadselement måste användas för att överföra saldon mellan kostnadsställen under omkostnadsberäkningen.

Dimensionsmedlemmar för kostnadselement kan ställas in på följande sätt.

| Kostnadselement | Typ          |               |
|---------------|---------------|---------------|
| 1001          | Elektricitet   | Primär       |
| 1002          | Löner      | Primär       |
| 1003          | Reklam   | Primär       |
| **SC-CC001**  | **Personal**        | **Sekundära** |
| **SC-CC002**  | **Finansiellt**   | **Sekundära** |
| **SC-CC003**  | **Sammansättning**  | **Sekundära** |
| **SC-CC004**  | **Paketering** | **Sekundära** |

Dimensionshierarkin **Resultaträkning** måste uppdateras med de nya dimensionsmedlemmarna så att dimensionshierarkin innehåller korrekta data som kan användas för att definiera rapportering och policyer.

**Detaljer om dimensionshierarki**

| Dimensionshierarkins namn | Dimension     | Namn på typ av dimensionshierarki      |
|--------------------------|---------------|------------------------------------|
| Resultaträkning  | Kostnadselement | Hierarki för dimensionsklassificering |

**Dimensionshierarki**

|                         | Dimensionsmedlemsintervall |                     |
|-------------------------|-------------------------|---------------------|
| Noder                   | Från dimensionsmedlem   | Till dimensionsmedlem |
| Resultaträkning |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Primärkostnad                        | 10001                   | 10003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Sekundärkostnad                         | **SC-CC001**            | **SC-CC004**        |

Skapa en **Policy för samlade kostnader** där varje kostnadsställe mappas till en motsvarande kostnadselement av typen **sekundära**.

**Policyer för samlade kostnader**

| Policynamn | beskrivning | Dimensionshierarki för kostnadsobjekt | Dimensionshierarki för kostnadselement |
|-------------|-------------|---------------------------------|----------------------------------|
| 2017        | Kostnadsflöde   | Organisation                    | Resultaträkning          |

**Regler för samlade kostnader**

| Dimensionshierarkinod för kostnadsobjekt | Dimensionshierarkinod för kostnadselement | Sekundärt kostnadselement |
|--------------------------------------|---------------------------------------|------------------------|
| CC001                                | Resultaträkning               | **SC-CC001**           |
| CC002                                | Resultaträkning               | **SC-CC002**           |
| CC003                                | Resultaträkning               | **SC-CC003**           |
| CC004                                | Resultaträkning               | **SC-CC004**           |

## <a name="perform-overhead-calculation"></a>Utföra beräkning av indirekta kostnader

**Journal**

| Journal | Journaltyp            | Räkenskapskalenderperiod | År | Period | Version       |
|---------|-------------------------|------------------------|------|--------|---------------|
| 00002   | Kostnadsallokeringsjournal | Skatt                 | 2017    | Period 1 | Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1 |

Systemet kommer nu att använda **Policy för samlade kostnader** när det skapar **Journalposter för kostnadsobjektsaldo**.

**Journalposter för kostnadsobjektsaldo**

| Räkenskapsdatum | Kostnadsobjekt | beskrivning  | Kostnadselement | beskrivning |  Belopp |
|-----------------|-------------|--------------|----------|-----------|-----------|
| 31-01-2017      | CC001       | Personal           | SC-CC001 | Personal        | 10.100,00 |
| 31-01-2017      | CC002       | Finansiellt      | SC-CC002 | Finansiellt   | 17.735,00 |
| 31-01-2017      | CC003       | Sammansättning     | SC-CC003 | Sammansättning  | 31.082,75 |
| 31-01-2017      | CC004       | Paketering    | SC-CC004 | Paketering | 15.717,25 |

> [!NOTE]
> Journaltransaktionerna som skapas baserat på reglerna i **Policy för samlade kostnader** om det redan finns en policy. Saldot som visas är saldot för omkostnadsberäkningen.

Sidan **Information om kostnadsobjektets journalposter för kostnadsbalans** som öppnas från journaltransaktionerna visar hur saldot hämtas.

**Exempel: Journalposten för kostnadsbäraren CC002 ekonomi**

**Information om kostnadsobjektets journalposter för kostnadsbalans**

| Dimensionsmedlem för kostnadselement | beskrivning |  Belopp   |
|-------------------------------|-------------|-----------|
| 1001                          | Elektricitet | 200 000    |
| 1002                          | Löner    | 10.000,00 |
| 1003                          | Reklam | 4.000,00  |
| SC-CC001                      | Personal          | 3.535,00  |

**Kostnadstransaktioner som genereras av omkostnadsberäkningen**

| Kostnadsobjekt | beskrivning  | Kostnadselement   | beskrivning  |        Belopp     |       Räkenskapsdatum     |
|-------------|--------------|----------|-----------------|-------------|------------|
| CC001       | Personal           | SC-CC001 | Personal              | 10.100,00 \- | 31-01-2017 |
| CC002       | Finansiellt      | SC-CC001 | Personal              | 3.535,00    | 31-01-2017 |
| CC003       | Sammansättning     | SC-CC001 | Personal              | 5.555,00    | 31-01-2017 |
| CC004       | Paketering    | SC-CC001 | Personal              | 1.010,00    | 31-01-2017 |
| CC002       | Finansiellt      | SC-CC002 | Finansiellt         | 17.735,00 \- | 31-01-2017 |
| CC003       | Sammansättning     | SC-CC002 | Finansiellt         | 11.527,75   | 31-01-2017 |
| CC004       | Paketering    | SC-CC002 | Finansiellt         | 6.207,25    | 31-01-2017 |

När **omkostnadsberäkning** är klar kan du rapportera resultaten med verktyg som t.ex. Microsoft SharePoint Workspace, Excel eller Power BI.

## <a name="view-reporting-in-excel"></a>Visa rapportering i Excel 

Dimensionshierarkierna låter dig visa data på olika aggregationsnivåer.

Här följer ett exempel på en Power Pivot-rapportering i Excel.

| **Resultaträkning** | **Kostnadsobjekt** |                |               |               |  **Summa**    |
|-----------------------------|-----------------|----------------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002**      | **CC003**     | **CC004**     |               |
| **Primärkostnad**            | **10.100,00**   | **14.200,00**  | **14.000,00** | **8.500,00**  | **46.800,00** |
| 1001 &nbsp;&nbsp;&nbsp;&nbsp;                            | 100,00          | 200 000         | 6.000,00      | 2.000,00      | **8.300,00**  |
| 1002 &nbsp;&nbsp;&nbsp;&nbsp;                            | 10.000,00       | 10.000,00      | 8.000,00      | 6.500,00      | **34.500,00** |
|1003 &nbsp;&nbsp;&nbsp;&nbsp;                             | 0,00            | 4.000,00       | 0,00          | 0,00          | **4.000,00**  |
|**Sekundärkostnad**                            | **-10 100,00**  | **-14 200,00** | **17.082.75** | **7.217,25**  | **0.00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC001                            | 10.100,00 \-     | 3.535,00       | 5.555,00      | 1.010,00      | **0.00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC002                             | 0,00            | 17.735,00 \-    | 11.527,75     | 6.207,25      | **0.00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC003                            | 0,00            | 0,00           | 0,00          | 0,00          | 0,00          |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC004                             | 0,00            | 0,00           | 0,00          | 0,00          | 0,00          |
| **Summa**                   | **0.00**        | **0.00**       | **31.082,75** | **15.717,25** | **46.800,00** |

Med hjälp av **Policy för samlade kostnader** och **kostnadselement av typen sekundär** kan du lämna den primära kostnaden per kostnadsbärare för intern rapportering eftersom den primära kostnaden som återstår efter **omkostnadsberäkningen**.

Om det här exemplet har genomförts utan att skapa **Policy för samlade kostnader** rapporteringsresultat blir enligt nedan. Kostnadsflödet går korrekt men spårbarhet och insyn i hur kostnadsflödet går mellan kostnadsställena försvinner.

| **Resultaträkning** | **Kostnadsobjekt** |           |               |               |          **Summa**  |
|-----------------------------|-----------------|-----------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002** | **CC003**     | **CC004**     |               |
| **Primärkostnad**            | **0.00**        | **0.00**  | **31.082,75** | **15.717,25** | **46.800,00** |
|1001 &nbsp;&nbsp;&nbsp;&nbsp;                              | 0,00            | 0,00      | 6.207,75      | 2.092,25      | **8.300,00**  |
| 1002 &nbsp;&nbsp;&nbsp;&nbsp;                             | 0,00            | 0,00      | 22.275,00     | 12.225,00     | **34.500,00** |
|1003 &nbsp;&nbsp;&nbsp;&nbsp;                              | 0,00            | 0,00      | 2600,00       | 1.400,00      | **4.000,00**  |
|**Sekundärkostnad**                            | **0.00**        | **0.00**  | **0.00**      | **0.00**      | **0.00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC001                             | 0,00            | 0,00      | 0,00          | 0,00          | **0.00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC002                             | 0,00            | 0,00      | 0,00          | 0,00          | **0.00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC003                             | 0,00            | 0,00      | 0,00          | 0,00          | 0,00          |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC004                             | 0,00            | 0,00      | 0,00          | 0,00          | 0,00          |
| **Summa**                   | **0.00**        | **0.00**  | **31.082,75** | **15.717,25** | **46.800,00** |

Det här avsnittet innehåller information om hur du avgör korrekt nivå på sekundära kostnadselement och skapar regler för samlade kostnader som passar organisationens rapportering och kostnadsspårbarhet.

Den tydliga avgränsningen mellan **kostnadsallokering** och **Policyer för samlade kostnader** ger flexibiliteten att kontrollera kontinuerliga uppdateringar utan att påverka varandra.



## <a name="see-also"></a>Se även
-  [Kostnadsobjektdimensioner](cost-objects.md)
-  [Dimensioner för kostnadselement](cost-elements.md)
-  [Dimensionshierarkier](dimension-hierarchy.md)
-  [Beräkning av indirekta kostnader](overhead-calculation.md)

