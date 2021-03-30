---
title: Dimensionshierarki
description: Det här ämnet innehåller information om dimensionshierarkier. Du använder en hierarki för att definiera rapporteringsstruktur, kostnadspolicyer och säkerhetsinställningar i kostnadsredovisning.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionHierarchy,
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2a2e48b15bedd25b685686fa18a91f30b600331c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217396"
---
# <a name="dimension-hierarchy"></a>Dimensionshierarki

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om dimensionshierarkier. Du använder en hierarki för att definiera rapporteringsstruktur, kostnadspolicyer och säkerhetsinställningar i kostnadsredovisning.  

## <a name="overview"></a>Översikt

Dimensionshierarkier används på olika ställen i kostnadsredovisning. En dimensionshierarki låter dig ange följande information:

-  Rapportstrukturen som passar organisationens behov
-  Kostnadspolicyer
-  Inställning för säkerhet

Här följer ett exempel på en dimensionshierarki.

![Exempel på en dimensionshierarki](./media/dimension-hierarchy.png)

En dimensionshierarki kan skapas för följande typer av dimensioner:

-  Dimensioner för kostnadselement
-  Kostnadsobjektdimensioner
-  Statistikdimensioner

> [!NOTE]
> - Du kan skapa flera dimensionshierarkier för samma dimension om olika perspektiv krävs.
> - En dimensionshierarki kan endast associeras med en dimension.
> - En dimensionshierarki kan ha obegränsat antal nivåer i strukturen. Alla nivåer ska vara tillgängliga i arbetsytan **kostnadskontroll**. Endast de första 15 nivåerna i dimensionshierarkin exporteras när du använder Microsoft Excel eller Microsoft Power BI för rapporteringsändamål. Denna begränsning beror på att både Excel och Power BI kräver ett fast schema.
> - En dimensionshierarki har inget giltighetsdatum. Därför sparas alla ändringar i en dimensionshierarki omedelbart till posten och kan du inte jämföra före- och efter-datum.

## <a name="dimension-hierarchy-type"></a>Typ av dimensionshierarki

När du skapar en ny dimensionshierarki måste du tilldela en hierarkityp. Gå till **kostnadsredovisning** > **dimensioner** > **Dimensionhierarkier**. Klicka på **Ny**, och välj en typ av dimensionshierarki. Du kan välja antingen **Hierarki för dimensionskategorisering** eller **Hierarki för dimensionsklassificering**.

### <a name="dimension-categorization-hierarchy"></a>Hierarki för dimensionskategorisering

Typen **Hierarki för dimensionskategorisering** används för rapporteringsändamål. Den stöder endast dimensioner för kostnadselement. Följande regler gäller när du väljer den här typen:

-  En dimensionsmedlem kan vara associerad mer än en gång i hierarkistrukturen.
-  Du kan sortera dimensionsmedlemmar för kostnadselement i olika noder genom att tilldela kostnadsbeteende till lövnoden.

### <a name="dimension-classification-hierarchy"></a>Hierarki för dimensionsklassificering

Typen **Hierarki för dimensionsklassificering** används för att definiera regler för rapporteringsändamål. Den stöder alla dimensioner, till exempel kostnadsobjekt, kostnadselement och statistiska dimensioner. När du väljer denna typ kan en dimensionsmedlem endast vara associerad en gång i hierarkistrukturen.

## <a name="create-and-maintain-a-dimension-hierarchy"></a>Skapa och hantera av dimensionshierarki

En dimensionshierarki skapas som en trädstruktur som har nod- och lövnodrelationer.

-  En nod kan ha 1:_n_ undernoder.
-  En nod kan inte ha undernoder och lövnoder tilldelade.
-  En lövnod kan bara tilldelas i den lägsta nivån i hierarkin.

### <a name="example"></a>Exempel

Ett litet företag har följande organisationsstruktur, där ekonomi och personal är avdelningar under Admin och sammansättning och paketering är avdelningar under Produktion.

![Exempel organisationsstruktur](./media/dimension-hierarchy-org.png)

En kostnadsobjektdimension representerar alla kostnadsställen i organisationen.

- Kostnadsobjektdimension
    - Kostnadsställen

Kostnadsobjektdimensionen som representerar alla kostnadsställen kan ställas in enligt vad som visas här.

| Kostnadsställen | beskrivning |
|--------------|-------------|
| CC001        | Personal          |
| CC002        | Finansiellt     |
| CC003        | Skatt         |
| CC007        | AR/LR       |
| CC005        | Sammansättning    |
| CC006        | Paketering   |

En kostnadselementdimension representerar alla kostnadselement i organisationen.

- Dimension för kostnadselement
    - Kostnadselement

Kostnadselementdimensionen som representerar alla kostnadselement kan ställas in enligt vad som visas här.

| Kostnadselement | beskrivning |
|---------------|-------------|
| 10001         | Elektricitet |
| 10010         | Rengöring    |
| 10011         | Uppvärmning     |
| 40001         | KSV        |

En dimensionshierarki som uppfyller rapporteringskraven för organisationen kan ställas in på följande sätt.

**Detaljer om dimensionshierarki**

| Dimensionshierarkins namn | Dimension    | Namn på typ av dimensionshierarki      | Hierarki för åtkomstlista |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organisation             | Kostnadsställen | Hierarki för dimensionsklassificering | Nr                    |

Dimensionshierarkin för rapportering kan ställas in enligt följande.

|                   | Dimensionsmedlemsintervall   |                         |
|-------------------|---------------------------|-------------------------|
| **Noder**         | **Från dimensionsmedlem** | **Till dimensionsmedlem** |
| Organisation      |                           |                         |
| &nbsp;&nbsp;Admin         |                           |                         |
|&nbsp;&nbsp;&nbsp;&nbsp;Finansiellt   | CC002                     | CC003                   |
|                   | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Personal        | CC001                     | CC001                   |
| &nbsp;&nbsp;Produktion    |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Paketering | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Sammansättning  | CC006                     | CC006                   |

En dimensionshierarki som uppfyller policykraven kan ställas in på följande sätt.

**Detaljer om dimensionshierarki**

| Dimensionshierarkins namn | Dimension     | Namn på typ av dimensionshierarki      |
|--------------------------|---------------|------------------------------------|
| Kostnadsbeteende            | Kostnadselement | Hierarki för dimensionsklassificering |

Dimensionshierarkin för policyn kan ställas in enligt följande.

|                   | Dimensionsmedlemsintervall   |                         |
|-------------------|---------------------------|-------------------------|
| **Noder**         | **Från dimensionsmedlem** | **Till dimensionsmedlem** |
| Kostnadsbeteende     |                           |                         |
| &nbsp;&nbsp;Fast kostnad    | 10001                     | 10011                   |
|&nbsp;&nbsp;Variabel kostnad | 40001                     | 40010                   |

> [!NOTE]
> Under **Dimensionsmedlemsintervall**, kan en nod innehålla 1:_n_ dimensionsmedlemsintervall. Du kan infoga dimensionsmedlem-ID som ännu inte finns som dimensionsmedlemmar. Den här metoden gör hierarkin flexibel för framtiden.  

### <a name="copy-a-hierarchy"></a>Kopiera en hierarki

Du kan kopiera en aktuell dimensionshierarki som utgångspunkt för en ny dimensionshierarki. Den här metoden kan vara användbart om du vill jämföra tidigare dimensionshierarki till den nya dimensionshierarkin.

### <a name="rearrange-nodes-in-a-hierarchy"></a>Ordna om noderna i en hierarki

Du kan flytta en nod uppåt respektive nedåt inom den aktuella nivån i strukturen. På så sätt kan du ändra ordning på noder för rapportering i arbetsytan **kostnadskontroll**.

Du kan flytta en nod till en ny plats i hierarkin genom att markera målnoden. Det finns två sätt att flytta en nod:

- **Flytta under** – flytta den markerade noden från dess aktuella position i hierarkin och infoga den **under** den valda målnoden.
- **Flytta after** – flytta den markerade noden från dess aktuella position i hierarkin och infoga den **efter** den valda målnoden i dess nivå i hierarkin.

> [!NOTE] 
> Nodernas ordning bevaras inte när du exporterar data till Excel eller Power BI eftersom dessa verktyg använder bokstavsordning som standard. Du bör ändra ordning manuellt.

## <a name="define-dimension-hierarchies-for-reporting"></a>Definiera dimensionshierarkier för rapportering

Dimensionshierarkier är viktiga för rapportering. De låter dig ange den specifika struktur som passar i den enskilda organisationen. Aggregeringar som görs för på nodnivån i dimensionshierarkin låter intressenter på alla nivåer i organisationen se data på alla nivåer.

Dimensionshierarkier finns i följande rapportverktyg. Den här metoden hjälper till att garantera konsekvens i rapportstrukturen.

- Arbetsytan **kostnadskontroll** (klient):

    - Kontrollerad av konfiguration.

- Arbetsytan **Kostnadskontroll** (mobilapplikation):

    - Kontrollerad av konfiguration.

- Excel

    - Ger möjlighet att välja särskilda dimensionshierarkier per exportdefinition:

        - En dimensionshierarki för kostnadselement (obligatoriskt)
        - En dimensionshierarki för standardkostnadsobjekt (tillval)
        - En hierarki för statistikdimension (tillval)

- Power BI:

    - Alla dimensionshierarkier är tillgängliga.
    
Om du skapar rapporter med hjälp av Excel eller Power BIexporteras endast de första 15 nivåerna av dimensionshierarkier. Denna begränsning beror på att både Excel och Power BI kräver ett fast schema. Om en hierarki har högst 15 nivåer kan ytterligare nivåer inte exporteras. Den normaliserade tabellen innehåller en post för varje dimensionsmedlem i hierarkin. Därför sker automatisk aggregering. Detta beteende hjälper till att garantera att saldon på någon av de 15 tillgängliga nivåerna i hierarkin fortfarande stämmer.

I följande exempel visas hur en dimensionshierarki kan se ut i rapportstrukturen.

| Dimensionshierarki för kostnadsobjekt – nivå 1 | Dimensionshierarki för kostnadsobjekt – nivå 2 | Dimensionshierarki för kostnadsobjekt – nivå 3 | Dimensionshierarki för kostnadsobjekt – nivå 4 | Dimensionshierarki för kostnadsobjekt – nivå 15 |
|-------------------------------------------|-------------------------------------------|-------------------------------------------|-------------------------------------------|--------------------------------------------|
| Organisation                              | Admin                                     | Finansiellt                                   | CC002                                     |                                            |
| Organisation                              | Admin                                     | Finansiellt                                   | CC003                                     |                                            |
| Organisation                              | Admin                                     | Finansiellt                                   | CC007                                     |                                            |
| Organisation                              | Admin                                     | Personal                                        | CC001                                     |                                            |
| Organisation                              | Produktion                                | Paketering                                 | CC005                                     |                                            |
| Organisation                              | Produktion                                | Sammansättning                                  | CC006                                     |                                            |

### <a name="update-the-dimension-hierarchies-that-are-used-for-reporting"></a>Uppdatera de dimensionshierarkier som används för rapportering 

Med tiden kan måste de dimensionshierarkier som används i ovanstående rapportverktyg uppdateras. Du kan uppdatera dimensionshierarkier genom att uppdatera klienten.

- Arbetsytan **kostnadskontroll** (klient)
- Arbetsytan **Kostnadskontroll** (mobilapplikation)

Uppdateringar av dimensionshierarkier fångas upp var 24:e timme efter ett förcachelagrat jobb. Efter att exporterade data har uppdaterats finns de uppdaterade dimensionshierarkierna i följande verktyg:

- Excel
- Power BI

> [!NOTE] 
> Om du vill manuellt utlösa en uppdatering av cachen för dimensionshierarki kan du skapa en ny export till Excel för dimensionshierarki eller hierarkier som måste uppdateras.

## <a name="define-dimension-hierarchies-for-cost-policies"></a>Definiera dimensionshierarkier för kostnadspolicyer

Kostnadsredovisning består av flera policyer där detaljerade regler har definierats. Du måste definiera minst en eller fler dimensionshierarkier för följande policyer:

- Kostnadsbeteende
- Kostnadsfördelning
- Kostnadsallokering
- Samlade kostnader

Dimensionshierarkier gör det enkelt att skapa regler. Om du vill undvika att skapa regler för varje dimensionsmedlem kan du utnyttja sammansättningar med dimensionsmedlemmar som tillhandahålls av dimensionshierarkinivåer. Om du har överlappande regler måste du definiera specifika regler som systemet beaktar när detta gör omkostnadsberäkningen.

### <a name="example-define-a-cost-behavior-policy"></a>Exempel: Definiera en ny kostnadsbeteendepolicy

En ny kostnadsbeteendepolicy skapas och lämpliga dimensionshierarkier tilldelas policyn som visas här.

**Kostnadsbeteendepolicy**

| Policynamn   | Dimensionshierarki för kostnadselement | Dimensionshierarki för kostnadsobjekt | Redovisningsvaluta |
|---------------|----------------------------------|---------------------------------|---------------------|
| Kostnadsbeteende | Kostnadsbeteende                    | Organisation                    | USD                 |

**Regler**

| Dimensionshierarkinod för kostnadselement | Dimensionshierarkinod för kostnadsobjekt | Fast procentsats | Fast belopp | Giltig från | Giltig till |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|----------|
| Fast kostnad                            | Organisation                         | 100,00           | 0,00         | 1/1/2017   | Aldrig    |
| 10001                                 | Organisation                         | 0,00             | 150.00       | 1/1/2017   | Aldrig    |
| 10001 (\*)                             | Finansiellt                              |                  | 50,00        | 1/1/2017   | Aldrig    |
| Kostnadsbeteende eller variabel kostnad (\*\*)   | Organisation                         | 0,00             | 0,00         | 1/1/2017   | Aldrig    |

\* Den variabla kostnadsnoden behövs inte. Om en kostnad inte klassificeras som fasta kostnader, måste det vara en variabel kostnad.

\*\* En detaljerad regel skapas för kombinationen av kostnadselementmedlem 10001 och alla kostnadsobjektmedlemmar som sammanställs i hierarkinivån Finance (CC002, CC003, CC007).

Ovanstående regler har den flexibilitet som dimensionshierarkier ger. Genom att definiera regler på hög nivå kan du minimera underhåll. Du kan sedan definiera detaljerade regler som passar ett visst företags mål.

Om de dimensionshierarkier som används i reglerna uppdateras flyttar systemet automatiskt uppdateringarna framåt.

Om en nivå i reglerna inte längre behövs, kan regeln upphöra att gälla.

Till exempel en särskild kostnadsbeteenderegel för dimensionshierarkinoden för kostnadsobjekt Finance behövs inte längre. I detta fall klickar du på **Dra tillbaka regel** för att regeln ska upphöra att gälla.

| Dimensionshierarkinod för kostnadselement | Dimensionshierarkinod för kostnadsobjekt | Fast procentsats | Fast belopp | Giltig från | Giltig till  |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|-----------|
| Fast kostnad                            | Organisation                         | 100,00           | 0,00         | 1/1/2017   | Aldrig     |
| 10001                                 | Organisation                         | 0,00             | 150,00       | 1/1/2017   | Aldrig     |
| 10001                                 | Finansiellt                              |                  | 50,00        | 1/1/2017   | 20/1/2017 |
| Kostnadsbeteende eller variabel kostnad        | Organisation                         | 0,00             | 0,00         | 1/1/2017   | Aldrig     |

En omkostnadsberäkning som körs efter 20 januari 2017, antar inte längre den här regeln.

> [!NOTE] 
> Fälten **giltig från** och **giltig till** är giltighetsdatum och giltighetstid. Du kan dra tillbaka regeln och köra en ny omkostnadsberäkning samma dag.

## <a name="define-dimension-hierarchies-for-security-setup"></a>Definiera dimensionshierarkier för säkerhetsinställning

Kostnadsredovisningsdata ska göras tillgänglig för alla chefer, som ansvarar för en rapportenhet. I kostnadsredovisningens terminologi representeras rapportenheten av ett kostnadsobjekt eller en uppsättning kostnadsobjekt.

I praktiken kan alla chefer komma åt känslig affärsinformation, som t.ex. intäkter och marginaler. Därför är det viktigt att du ställer in säkerhet, så att chefer bara se de data som är relevanta för dem. För att kontrollera datasäkerhet definierar du dimensionshierarkier.

- Användningen av dimensionshierarkier gäller endast när det dimensionsvärde som har valts i referensdimensionshierarkin är en kostnadsobjektdimension.
- Endast en dimensionshierarki kan aktiveras per kostnadsobjektdimension i hierarkin för åtkomstlistan.

**Detaljer om dimensionshierarki**

| Dimensionshierarkins namn | Dimension    | Namn på typ av dimensionshierarki      | Hierarki för åtkomstlista |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organisation             | Kostnadsställen | Hierarki för dimensionsklassificering | **Ja**               |

En ny snabbflik **användare** finns i hierarkidesigner. Här kan du infoga ett eller flera användar-ID:n på varje nod i hierarkin.

|                 | Användare            | Dimensionsmedlemsintervall   |                         |
|-----------------|------------------|---------------------------|-------------------------|
| **Noder**       | **Användar-ID**      | **Från dimensionsmedlem** | **Till dimensionsmedlem** |
| Organisation    | Benjamin Claire |                           |                         |
| &nbsp;&nbsp;Admin         | april            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finansiellt   | Alicia           | CC002                     | CC003                   |
|                 |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Personal        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Produktion    | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Paketering | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Sammansättning  | Chris            | CC006                     | CC006                   |

> [!NOTE] 
> Kostnadsrevisorerna ska tilldelas till den översta nivån i hierarkin, så att de kan se alla poster i kostnadsredovisningen.

Aktivera hierarkin för åtkomstlista och dess säkerhetsinställningar genom att gå till **kostnadsredovisning** > **inställningar** > **parametrar** > **allmänt**. Välj parametern **Aktivera visningsåtkomst för kostnadsobjektets dimensionsmedlemmar**.

Inställningar för Hierarki för åtkomstlista används för att bestämma vilka data som visas i följande områden:

- Arbetsytan **kostnadskontroll** (klient):

    - Data i formulär som används för att gå igenom scenarier

- Arbetsytan **Kostnadskontroll** (mobilapplikation):

    - Saldon i kort

- Power BI:

    - Data som visas i Power BI-visualiseringar
    - Data Power BI visuella effekter som är inbäddade i Dynamics 365 Finance-klienten

> [!NOTE] 
> - Innan Hierarki för åtkomstlista kan påverka data i Power BI måste hierarkiåtkomst och säkerhet på radnivå i Power BI paras ihop. Mer information finns i [ställa in säkerhet för kostnadsredovisningens innehållspaket](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - Hierarki för åtkomstlista hjälper inte export av data till Excel. Därför ska detta rapportverktyg bara användas av kostnadsrevisorer och chefer som måste ha fullständig behörighet för att visa data.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]