---
title: Batchbalansering
description: "Det här avsnittet beskriver processen för batchbalansering."
author: johanhoffmann
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7d00df6263530ba9fff4c246cb3593cd607f6719
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="batch-balancing"></a>Batchbalansering

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur processen för batchbalansering stöds. 

Titta på en [video om batchbalansering i Microsoft Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=4SNLWsU9KyI&feature=youtu.be).

I processen för batchbalansering beräknas mängden ingredienser som ska användas i ett produktionsparti utifrån koncentrationen av aktiva substanser valda produktionsbatchar.

<a name="products-that-have-an-active-ingredient"></a>Produkter som har ett verksamt ämne
---------------------------------------

En produkt kan definieras av koncentrationen av ett verksamt ämne. Det verksamma ämnet av en produkt är utformat med ett produktspecifikt batchattribut som har ett lägsta värde, högsta värde och en målnivå.

Målnivån för batchattributet representerar beräknad procent av ett verksamt ämne i en produkt. Lägsta och högsta värden representerar godtagbar avvikelse från målnivån. De kan användas till exempel som en godtagen tolerans för batchar till produktinleverans.

En produkt kan endast ha ett verksamt ämne. Om du vill ange den aktiva beståndsdelen hos en produkt måste du först definiera ett batchattribut med olika produkter. Du kan sedan associera attributet som ett basattribut av produkten.

På produktnivå måste du också ange hur nivån på den aktiva beståndsdelen för en batch av produkten ska registreras: som en del av inköpsinleveransprocessen eller som en del av en kvalitetsorderprocess.

Om du vill associera ett basattribut med en produkt krävs följande inställningar:

-   Produkten måste vara batchkontrollerad. Om du vill göra en produkt batchkontrollerad måste du tilldela en spårningsdimensionsgrupp till den produkt som har en aktiv batchdimension.

-   Attributet som anger ingrediensnivåer måste definieras som produktspecifika batchattribut för produkten.

Du kan visa och redigera det faktiska värdet för den aktiva beståndsdelen för en batch på sidan **Batchattribut i lager**. 

-  Välj **Lagerhantering** \> **Förfrågningar och rapporten** \> **Spåra dimensioner** \> **Batcher** \> **Batchattribut i lager**.

<a name="ingredient-types-and-how-they-interact-in-the-batch-balancing-process"></a>Ingredienstyper och hur de samverkar i batchbalanseringsprocessen
---------------------------------------------------------------------

En receptrad som skapas kan ha en av dessa ingredienser:

-   Inga

-   Aktiva

-   Kompenserar

-   Utfyllnad

Resten av det här avsnittet innehåller exempel som visar hur varje beståndsdeltyp fungerar. Exemplen baseras på följande formel som har en total batchstorlek på 100 liter.

| **Komponenttyp** | **Artikelnummer** | **Receptradkvantitet** | **Enhet** |
|---------------------|-----------------|---------------------------|----------|
| Inga                | A               | 20                        | Liter    |
| Aktiva              | B               | 30                        | Liter    |
| Kompenserar        | C               | 10                        | Liter    |
| Utfyllnad              | D               | 40                        | Liter    |

### <a name="active"></a>Aktiva

När en produkt som har ett basattribut läggs till en receptrad kan den anges som en *aktiv beståndsdel* av formeln. Batchorder som innehåller formler som innehåller aktiva substanser kan användas för batchbalanseringsprocessen. För varje beståndsdel i formeln beräknar batchbalanseringsprocessen hur mycket som krävs för att tillverka produkten. Beräkning av belopp baseras på koncentrationen av aktiva beståndsdelar i de valda batcharna.

**Exempel**

beståndsdel B har basattributet X och en målnivå 30 och den ingår i en formel som kräver 30 liter för beståndsdel B för varje 100 liter av produkten. En batchorder skapas som har en batchstorlek på 100 liter. Batchordern startas och under batchbalanseringsprocessen väljer användaren en batch med beståndsdel B som har en potensnivå på 35. Eftersom styrkenivån på 35 är högre än målnivån på 30 minskas den balanserade kvantiteten för beståndsdel B genom att använda förhållandet av potensvärdet till målnivån för den batch som multipliceras med den beräknade kvantiteten. Beräknningen av den balanserade kvantiteten ser ut så här:

(30 ÷ 35) × 30 liter = 25,71 liter

| **Artikelnummer** | **Komponenttyp** | **Uppskattad kvantitet** | **Balanserad kvantitet** | **Aktiv kvantitet** | **Enhet** | **Basvärde** |
|-----------------|---------------------|------------------------|-----------------------|---------------------|----------|----------------|
| A               | Inga                | 20                     | 20                    |                     | Liter    |                |
| B               | Aktiva              | 30                     | 25,71                 | 09:00                | Liter    | 30,00          |
| C               | Kompenserar        | 10                     | 14,72                 |                     | Liter    |                |
| D               | Utfyllnad              | 40                     | 39,57                 |                     | Liter    |                |

### <a name="none"></a>Inga

När du använder batchbalanseringsprocessen när beståndsdeltypen är **ingen** är den beräknade kvantiteten och balanserade kvantiteten för receptraden i batchordern samma.

**Exempel**

beståndsdel A tilldelas till en beståndsdel av typen **Ingen** och läggs till i en formel för en färdig produkt. Formeln kräver 10 liter av en beståndsdel för varje 100 liter av slutprodukt. När en batchorder kräver 200 liter, beräknas både den uppskattade kvantiteten och den balanserade kvantiteten för beståndsdel Akvantitet som 20 liter.

### <a name="compensating"></a>Kompenserar

En ersättningsbeståndsdel kan antingen kompensera eller komplettera effekten av den aktiva beståndsdelen i en produkt. Därför beror mängden ersättningsbeståndsdel som används på styrkan hos produkten:

-   **Motsatt effekt** – om mängden av den aktiva beståndsdelen är större än förväntat måste du lägga till mindre ersättningsbeståndsdel.

-   **Kompletternade effekt** – om mängden av den aktiva beståndsdelen är mindre än förväntat måste du lägga till mer ersättningsbeståndsdel.

Relationen mellan en aktiv beståndsdel och en kompletterande beståndsdel ställs in på sidan **Kompensationsprincipen**.

Följ dessa steg för att ställa in relationer mellan beståndsdelar.

1.  Välj **Produktinformationshantering**\>**Strukturlistor och formler**\>**Formler**, öppna en receptrad och välj sedan **Beståndsdelar** för att öppna sidan **Kompenseringsprincipen**.

2.  Markera raden som representerar en kompenseringsprincip och välj att kompensera den aktiva beståndsdelen.

>   I kompenseringsprincipen anger du även en positiv eller negativ kompenseringsfaktor som anger hur mycket du ska kompensera för och om principen ska vara motsatt eller kompletterande. Anger en positiv faktor anger en komplementerande effekt och en negativ faktor anger en motsatt effekt.

**Exempel**

Beståndsdel B har en aktiv beståndsdel med basattributet X och en målnivå 30. Den inkluderas i en formel som kräver 30 liter av en komponent för varje 100 liter av produkten. Beståndsdel C är en kompenserande beståndsdel och en kvantitet på 10 ingår i samma formel. En kompenserande faktor på 1,10 har ställts in för kompenseringsprincipen. Därför minskas den balanserade kvantiteten av ersättningsbeståndsdelen med skillnaden mellan den aktiva beståndsdelens balanserad kvantitet och den uppskattade kvantiteten multiplicerat med 1,10.

I exemplet för komponenttypen **aktiv** beräknades den balanserade kvantiteten av den aktiva komponenten som 25,71 och den uppskattade krävda kvantiteten beräknas som 30. I det här fallet beräknas ersättningsbeståndsdelen för den balanserade kvantiteten så här:

1.  Skillnaden mellan den beräknade och den balanserade kvantiteten fastställs.

>   25,71 – 30 = –4,29

2.  Resultatet multipliceras sedan med kompensationsfaktorn:

>   4,29 × 1,10 = –4,72

3.  Den uppskattade kompensationskvantiteten minskas med –4,72 för att fastställa den balanserade kompenserande kvantiteten:

>   10 – (–4,72) = 14,72

Eftersom 1,10 är en positiv kompenserande faktor har denna kompenseringsprincip en kompletterande effekt. I det här fallet är den aktiva beståndsdelen starkare än beräknat. Därför krävs mer av ersättningsbeståndsdelen.

### <a name="filler"></a>Utfyllnad

Ett *utfyllnadsmedel* är en neutral beståndsdel som används för att nå önskad utleveranskvantitet för den färdiga produkten. Justeringar av utfyllnadskvantiteter beräknas baserat på variationer av verksamt ämne och ersättningsbeståndsdelen jämfört med en standardkvantiteten.

**Exempel**

Du har utarbetat en produkt som innehåller beståndsdel A, B, C och D för en formelstorlek av 100 liter. Du har beräknat den balanserade kvantiteten av alla beståndsdeltyper förutom beståndsdeltypen **Utfyllnad** som används på en rad.
Den balanserade kvantiteten för utfyllnadsmedel beräknas som skillnaden mellan batchstorleken på 100 liter och summan av beståndsdel A, B och C:

100 – (20 + 25,71 + 14,72) = 39,57

<a name="the-batch-balancing-process"></a>Batchbalanseringsprocessen.
---------------------------

Batchbalanseringsprocessen utförs från sidan **Batchbalansering**.
Välj **kostnadshantering**\>**batchorder** och sedan på fliken **Process** väljer du **Batchbalansering**. Batchbalansering finns för batchorder som har statusen **startad**.

I allmänhet kan batchbalansering användas för batchorder om formeln har minst en receptrad där komponenttypen är **aktiv**. (Undantaget från denna regel, se avsnittet ”Batchorder som inte gäller för batchbalansering” senare i det här avsnittet.)

Batchbalanseringsprocessen kan delas in i två delprocesser:

1.  Balansbatchkomponent

2.  Bekräfta och frisläpp formeln

### <a name="balance-batch-ingredients"></a>Balansbatchkomponent

I delprocessen för balansbatchkomponent beräknas mängden ingredienser som ska användas i ett produktionsparti baserat på de valda batcher som har aktiva substanser. Generellt kan beräkningen endast utföras om det är full täckning av alla komponenter. Du kan inte bara balancerad del av batchen som batchordern har ställts in för att producera.

[!NOTE]
Du kan inte spara en beräkning och sedan utföra batchbalanseringsprocessen senare. Om du stänger sidan **Batchbalansera** måste du upprepa beräkningen för att slutföra processen.

### <a name="confirm-and-release-the-formula"></a>Bekräfta och frisläpp formeln

När beståndsdelkvantiteterna har beräknats kan du bekräfta och frisläppa formeln. Frisläppningsprocessen beror på om produkterna är aktiverade för lagerstyrningsprocesser:

-   Om en produkt är aktiverad för lagerstyrningsprocesser frisläpps receptraden till lagret enligt principerna för lagerstyrningsprocesser. Receptraden frisläpps i kvantiteter som motsvarar balanserade kvantiteter och frisläpps för speciella batcher som väljs för den aktiva komponenten.

> [!NOTE]
>   Receptrader kan frisläppas till lagerstället som en del av batchbalanseringsprocessen. Även om det finns andra alternativ för att frisläppa material för tillverkning på lagerstället, kan inte dessa alternativ användas för receptrader.

-   Om en produkt inte har aktiverats för lagerstyrningsprocesser skapas en produktionsplocklista för produkten när du bekräftar och frisläpper formeln.

Du kan kombinera produkter som är aktiverade för lagerstyrningsprocesser och produkter som inte är aktiverade för lagerstyrningsprocesser i en enstaka formel. När två typer av produkter ingår i en formel kommer produkter som är aktiverade för lagerstyrningsprocesser frisläppas till lagret. För produkter som inte är aktiverade för lagerstyrningsprocesser skapas en plocklista när du bekräftar och frisläpper formeln.

### <a name="batch-orders-that-arent-applicable-for-batch-balancing"></a>Batchorder som inte gäller för batchbalansering

Det finns ett undantag från regeln om att batchorder gäller för batchbalansering  om formeln har minst en receptrad där komponenttypen är **aktiv**.

Om en formel innehåller en aktiv beståndsdel för en produkt som har aktiverats för lagerstyrningsprocesser och batchnumret är under plats i reservationshierarkin gäller inte batchordern för batchbalansering.

En batchorder inte gäller för batchbalansering genomgår den vanliga processcykeln för batchorder.

