---
title: "Ange initiala lönesaldon"
description: "Avsnittet beskriver stegen för att ange initiala saldon för lönekoder, förmåner, avdrag och moms. Denna information är viktig för partnerföretag som vill migrera eller överföra data för en ny implementering av lönelistor från ett annat system."
author: kherr75
manager: AnnBe
ms.date: 07/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 20931
ms.assetid: b48b1cb2-6e66-467e-9c0e-09b6a4aeb9fe
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 93333757995c874c2cf03514acff28a54ae7f787
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="enter-payroll-beginning-balances"></a>Ange initiala lönesaldon

[!include [banner](../../includes/banner.md)]

Avsnittet beskriver stegen för att ange initiala saldon för lönekoder, förmåner, avdrag och moms. Denna information är viktig för partnerföretag som överför data för en ny implementering av lönelistor från ett annat system. Vi bekräftar följande information när du förbereder inmatningen av initiala lönesaldon:

> * Medarbetarposter anges och finns tillgängliga i systemet
> * Följande uppgifter har konfigurerats och tilldelats medarbetare:
> 
> > * Lönecykler och löneperioder
> > * Inkomstkoder
> > * Moms
> > * Förmåner och avdrag
> 
> * Företaget bör har valt ett datum där initiala lönesaldon kan ställas in.
> 
> * Informationen har samlats in för alla inkomster och förmåner/avdrag, förmånsbidrag, medarbetar- och arbetsgivarmoms deras hittillsvarande belopp under hittillsvarande år från det äldre systemet.

När du planerar att ange initiala balanser, överväg då hur pass detaljerade datan måste vara. De flesta företag anger ett enda, konsoliderat belopp under hittillsvarande år till dags dato. Om mer detaljerad information skulle krävas kan saldon emellertid anges kvartalsvis. Valet av erforderlig detaljnivå avgör hur många manuella löneutdrag som måste skapas för varje arbetstagare. För ett enstaka belopp till dags dato behövs endast ett manuellt utdrag för respektive medarbetare. För att göra detta använder du hittillsvarande belopp under året till dags dato, från det slutliga löneutdraget från det tidigare systemet som det belopp som bokförs i det nya lönesystemet.

I följande exempel visas hur du kan ange medarbetarens initiala lönesaldon, inklusive inkomstkoder, förmåner/avdrag och moms. I ett verkligt exempel skulle det finnas en radartikel för varje inkomstkod, förmånsavdrag, förmånsbidrag, medarbetar- och arbetsgivarskatt där det angivna beloppet är lika med beloppet under hittillsvarande år fram till dags dato. Med hjälp av denna förteckning över koder och belopp följer du instruktionerna för att skapa ett manuellt inkomst- och betalningsutdrag med inaktiverad redovisning om du vill flytta över ingående saldon i betalningsändamål.  Du kan inaktivera redovisningen eftersom du inte vill bokföra detta betalningsutdrag för initial saldo i redovisningen. Detta gjordes i det äldre systemet och kommer att överföras till det nya systemet när du anger initiala saldon i redovisningen.

### <a name="a-how-to-set-up-earnings-codes-to-be-used-on-payroll-beginning-balances"></a>A. Hur du ställer in inkomstkoder som ska användas för ingående lönesaldon på lönelistan
När du anger initiala lönesaldon för lönelistor, se då till att de inkomstkoder som du ska använda konfigureras med alternativet ”Tillåt redigering av tariffer för inkomstutdrag" är aktiverat. Detta gör att du manuellt kan ange beloppet från det äldre systemet. 

### <a name="b-create-earnings-statement-for-an-employee-to-have-a-beginning-balance"></a>B. Skapa inkomstutdrag för en medarbetare för att få ett initialt saldo
Det här steget skapar manuellt ett inkomstutdrag för respektive arbetstagare för det äldre systemet sista löneperiod, vilket skapar inkomstutdragsraderna i det nya lönesystemet. Ange en rad per inkomstkod samt belopp och timmar för hittillsvarande år fram till dags dato. Exempelstegen är som följer:

1. Öppna sidan **Alla intäktsutdrag** och klicka på **Ny**.  

Ange följande: 

| Fält      | Värde                 |
|------------|-----------------------|
| Arbetare     | Michael Redmond       |
| Lönecykel  | sm                    |
| Löneperiod | 2016-06-16 - 2017-06-30 |

2. I fliken **Rad för inkomstutdrag** anger du följande:

Rad 1: Fliken **Rad för inkomsutdrag**

| Fält            | Värde       |
|------------------|-------------|
| Inkomstkod    | Standardlön |
| Kvantitet         | 1,00        |
| Rage             | 30 000      |
| Flik för radinformation |             |
| Manuell           | (markerad)    |

Rad 2: Fliken **Rad för inkomstutrag**

| Fält            | Värde    |
|------------------|----------|
| Inkomstkod    | Bonus    |
| Kvantitet         | 1.0000   |
| Kurs             | 4250.00  |
| Flik för radinformation |          |
| Manuell           | (markerad) |

Rad 3: Fliken **Rad för inkomstutdrag**

| Fält           | Värde      |
|-----------------|------------|
| Inkomstkod   | Provision |
| Kvantitet        | 1.0000     |
| Kurs            | 1 299,00   |
| Kurs            | 1,299.00   |
| Flik för radinformation |            |
| Manuell          | (markerad)   |

> [!NOTE]
> Sätta det **manuella** skjutreglaget till **Ja** på fliken **Radinformation** för respektive rad för inkomstutdrag är nyckeln till att initiala saldon ska anges för respektive arbetstagare.

3. I fönstret **Åtgärd** klickar du på **Frisläpp intäktsutdrag** USA-FED ER-FICA.

4. I fönstret **Åtgärd** klickar du på **Löneutdrag** för att öppna sidan **Skapa löneutdrag** och anger följande:

| Fält              | Värde     |
|--------------------|-----------|
| Betalningsdatum       | 6/30/2017 |
| Typ av lönekörning   | Manuell    |
| Inaktivera redovisning |   Ja     |

> [!NOTE] 
> Detta är endast tillgängligt när betalningens körningstyp är manuell och där användaren vill inaktivera redovisningen för betalningskörningen.

Klicka på **OK** och stäng **Informationsloggen**.

#### <a name="why-the-disable-accounting-slider-needs-to-set-to-yes-when-generating-pay-statements"></a>Varför måste skjutereglaget ställas in på Ja vid generering av lönerapporter?
Att ställa in skjutreglaget på **Ja** förhindrar att rader i löneutdraget distribueras till redovisningen. Redovisningsbeloppen uppdaterar tidigare när kontosaldon från äldre system angavs. Att ange ingående balanser för löner låter dig skapa rapporter som innehåller information från föregående år och för att identifiera gränser av förmåns- och skattemässiga skäl.   

### <a name="c-create-pay-statements-for-employees"></a>C. Skapa löneutdrag för anställda
Du måste kontrollera att betalningsutdrag korrekt återspeglar lönedatan när du genererar löneutdrag med initiala saldon. Du måste även manuellt uppdatera förmåns- och skatteinformationen så att denna matchar värdena i det föregående lönesystemet. När du har bekräftat att beloppen från föregående lönesystem matchar beloppen på aktuella löneutdrag, måste du slutföra löneutdragen.

1. Öppna sidan **Alla löneutdrag**.

2. Markera det senast genererade löneutdraget för Michael Redmond

3. Klicka på **Redigera** för att öppna sidan **Löneutdrag**.

4. Öppna fliken **Förmånsavdrag** och ange följande:

|       Fält       |      Värde       |
|-------------------|------------------|
|      Förmån      | Avdragsbelopp |
|       401K        |   Delta    |
|      Tandvård       |      SubSp       |
| Utgifter för beroendevård |   Delta    |
|      Vision       |      SupSp       |

5. I fliken **Förmånsbidrag** anger du följande:

|  Fält  |        Värde        |
|---------|---------------------|
| Förmån | Förmånsbelopp |
|  401K   |     Delta     |
| Tandvård  |        SubSp        |
| Vision  |        SubSp        |

6. I fliken **Skatteavdrag** anger du följande:

| Fält           | Värde            |
|-----------------|------------------|
| Skattekod        | Avdragsbelopp |
| USA-FED-ER-FICA | 1600.00          |
| USA-FED-ER-MEDI | 825.75           |

7. I fliken **Skattebidrag** anger du följande:

8. Klicka på **Beräkna**.
   > [!IMPORTANT] 
   > Validera summorna i löneutdraget så att de matchar saldot till dags dato det äldre systemet för arbetstagaren. Du kanske vill avstå från att slutföra i nästa steg för att istället validera samtliga löneutdrag sammanlagt. Kör igenom alla löneutdrag och slutför dem när de väl har validerats.

Samma tillvägagångssätt kan vid behov göras kvartalsvis för alla föregående kvartal under varje år. Detta behövs bara om kunden behöver visa data kvartalsvis utan att gå tillbaka till det äldre systemet.

## <a name="if-you-make-a-mistake-entering-beginning-balances-for-an-employee"></a>Om du gör ett misstag när du anger initiala saldon för en medarbetare
Det går att återföra och omregistrera transaktioner. Om du vill återföra transaktionen är allt du behöver göra är att slutföra följande steg på sidan **Alla löneutdrag**.

1. Klicka på **Återför**.

2. Klicka på **Ja** när meddelandet ”När du återför detta löneutdrag kommer ett utdrag om löneåterförande att skapas för att kompensera detta löneutdrag. Ingetdera löneutdrag kan redigeras. Vill du återföra detta löneudrag?" visningar. 

När du återför löneutdraget kan du generera ett nytt löneutdrag för arbetaren från inkomstutdrag som du skapade tidigare. Kom ihåg att korrigera felaktiga rader på inkomstutdraget innan du skapar nya löneutdrag och generera sedan nya löneutdrag med korrekt belopp. 

