---
title: Flexgrupper
description: Det här avsnittet beskriver hur flexgrupperna används i tid och närvaro.
author: johanhoffmann
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgFlexGroup, JmgFlexCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: afffdfba965806d18b148c77774a31bbb3c0c46c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831780"
---
# <a name="flex-groups"></a>Flexgrupper

[!include[banner](../includes/banner.md)]

Flexibel arbetstid låter företag minska betalningar för övertid genom att erbjuda arbetare extra ledig tid under perioder när arbetsbelastningen är låg. Den här funktionen gäller exempelvis för segment som är kopplade till säsongsvariationer i arbetsbelastning.

Du kan använda flexgrupper för att ange följande regler och principer för en arbetares flextimmar:

- Regler för flexregler
- Principen för beräkning av arbetarens flexsaldo

## <a name="set-up-flexible-working-hours-in-flex-groups"></a>Ange flexibla arbetstider i flexgrupper

- Välj **tid och närvaro**\>**inställningar**\>**grupper**\>**flexgrupper** för att ställa in flexgrupper för flextimmar.

## <a name="associate-workers-with-flex-groups"></a>Koppla personer till flexgrupper

- Välj **Tid och närvaro** \> **Inställningar** \> **Tidsregistreringsarbetare**.

## <a name="rules-for-flex-regulations"></a>Regler för flexregler

Du kan använda regler för flexregler för att definiera flexgränser eller lägsta och högsta antal timmar som tillåts i arbetarens flexkonto. Flexgränserna ställs in i flexgruppen. När flexgränserna överskrids kan arbetarens flexsaldo och betalning justeras.

Om en arbetares tillåtna flexminimum överskrids (det vill säga om antalet timmar i flexkontot är lägre än det angivna minimum) kan du justera arbetarens flexsaldo genom att göra en flexjustering:

- Arbetarens flexkonto kan justeras till den angivna minsta tillåtna men utan avdrag för arbetarens lön för antalet timmar som flexkontot är lägre än lägsta tillåtna.
- Arbetarens lön kan dras av för antalet timmar som flexkonto är lägre än lägsta tillåtna. Detta avdrag görs genom att generera löneposter för en viss lönetyp som har ett negativt eller positivt löneantal.

Om arbetarens tillåtna flexmaximum överskrids kan du använda dessa metoder för att justera arbetarens flexsaldo genom en flexjustering:

- Arbetarens flexkonto kan justeras tillbaka till den angivna högsta tillåtna men utan att kompensera arbetarens lön för antalet timmar som arbetaren har arbetat över den högsta tillåtna gränsen.
- Antalet timmar som arbetaren har arbetat överskrider maximalt tillåtna kan konverteras till lön. Konverteringen görs genom att generera löneposter för en viss lönetyp.

Du kan också justera flexsaldon på följande tider:

- När en betalningsfil som baseras på lönedata exporteras med hjälp av jobbet **överför lön**. Lönedata genereras när du överför arbetarens registreringen från sidan **Godkänn**.
- När jobbet **Justera flexsaldo** bearbetas.

> [!NOTE]
> Flexjusteringar sker inte under dagligt godkännande och överföring av arbetarregistreringar på sidan **Godkänn**.

## <a name="principle-for-calculating-a-workers-flex-balance"></a>Principen för beräkning av arbetarens flexsaldo

Principen för beräkning av de timmar som arbetarens flexsaldo justeras av anges på flexgruppen. Välj **tid och närvaro**\>**inställningar**\>**grupper**\>**flexgrupper**. 

Följande två principer kan användas:

- **Tid** – arbetarens flextimmar beräknas endast från den arbetarens registrerade tid för dagen. När arbetarens dagliga registreringar beräknas beräknas antalet Flex+ och Flex- -timmar för dagen från de Flex+ och Flex- -zoner som definieras i den berörda personens tidsprofilen.
- **Lönetyper** – arbetarens flextimmar beräknas utifrån intäkter av lönetyper för Flex+ och Flex- som definieras i arbetarens löneavtal. Löneavtalet associeras med tidsregistreringsarbetare. Du kanske vill använda lönetyper för att hantera flexkonton om du vill öka en arbetare flexkonto med en viss faktor i en eller flera flexzoner.

### <a name="scenario-1-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-minimum-is-exceeded"></a>Scenario 1: Justera en arbetares lön och flexkonto eftersom lägsta tillåtna flex överskrids

En arbetare som kan arbeta flextid har ett negativt flexkonto.

- **Flexkonto:** -4

Arbetaren är associerad med en flexgrupp med följande konfiguration:

- **Flexminimum:** -0,5
- **Lönetyp - minimum:** 1302
- **Lönetypfaktor:** -1,00

Som skillnaden mellan arbetarens flexkonto och hans tillåtna flexminimum anger har arbetaren överskridit sitt tillåtna flexminimum med 3,5 timmar.

När löneadministratören överför arbetarens lönedata genom att köra jobbet **överföring till lön** eller **flexjustering** görs följande justeringar:

- Arbetarens flexkonto justeras med 3,5 timmar. Därför justeras flexsaldot på -4,0 timmar till arbetarens tillåtna flexminimum på -0,5 timmar.
- En lönepost för lönetypen 1302 skapas. Den här löneposten har en lönepost på -3,5 timmar som kommer att dras av från arbetarens lön. I det här fallet är löneenheten ett negativt tal, eftersom den positiva justeringen på 3,5 timmar multipliceras med den negativa lönetypfaktorn på -1,0 som definieras i flexgruppen. Den här löneposten förs för den lönefil som genereras av jobbet **överföring till lön**.

### <a name="scenario-2-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-maximum-is-exceeded"></a>Scenario 2: Justera en arbetares lön och flexkonto eftersom lägsta tillåtna flexmaximum överskrids

En arbetare som kan arbeta flextid har ett positiv flexkonto.

- **Flexkonto:** 6

Arbetaren är associerad med en flexgrupp med följande konfiguration:

- **Flexmaximum:** 2,0
- **Lönetyp - minimum:** 1302
- **Lönetypfaktor:** -1,0

Som skillnaden mellan arbetarens flexkonto och hennes tillåtna flexmaximum anger har arbetaren överskridit sitt tillåtna flexmaximum med 4,0 timmar.

När löneadministratören överför arbetarens lönedata genom att köra jobbet **överföring till lön** eller **flexjustering** görs följande justeringar:

- Arbetarens flexkonto justeras med -4,0 timmar. Därför justeras flexsaldot på 6,0 timmar till arbetarens tillåtna flexmaximum på 2,0 timmar.
- En lönepost för lönetypen 1302 skapas. Den här löneposten har en lönepost på 4,0 timmar som kommer att läggas till arbetarens lön. I det här fallet är löneenheten ett positivt tal, eftersom den negativa justeringen på 4,0 timmar multipliceras med den negativa lönetypfaktorn på -1,0 som definieras i flexgruppen. Den här löneposten förs för den lönefil som genereras av jobbet **överföring till lön**.

### <a name="scenario-3-managing-a-workers-flex-balance-based-on-pay-types"></a>Scenario 3: Hantera en arbetares flexsaldot utifrån lönetyper

Som vi förklarade tidigare kan flexkonton antingen hanteras baserat på den tid som har registrerats i Flex+ och Flex- -zoner som definierade arbetarens tidsprofil eller på de lönetyper som definieras i den arbetarens löneavtal. Om lönetyper används justeras en arbetares flexkonto med de löneposter som skapas när du överför arbetarens registrering från sidan **Godkänn**. Du kanske vill använda lönetyper för att hantera flexkonton om du vill öka en arbetare flexkonto med en viss faktor i en eller flera flexzoner.

Detta scenario använder följande flexprofil som representerar en arbetsdag.

| Profiltyp  | Start    | Slut      |
|---------------|----------|----------|
| Flex+         | 12:00 | 08:00 |
| Stämpla in      | 08:00 | 08:00 |
| Flex-         | 08:00 | 09:00 |
| Standardtid | 09:00 | 11:30 |
| Betald rast    | 11:30 | 12:00 |
| Flex-         | 12:00 | 04:00 |
| Stämpla ut     | 04:00 | 04:00 |
| Flex+         | 04:00 | 12:00 |

Du vill då kunna hantera arbetarens flexsaldo baserat på betalningstyper. Därför måste du ange alternativet **baserat på lönetyper** till **Ja** på arbetarens flexgrupp.

För att ta hänsyn till de flexibla timmarna måste du också definiera en ny lönetyp. I det här scenariot heter lönetypen **FlexCnt**.

| Lönetyp | beskrivning  |
|----------|--------------|
| FlexCnt  | Flexräknare |

Följ stegen nedan för att ställa in en lönetyp och lägga till rader på den nya typen till en löneprofil.

1. Välj **tid och närvaro** \> **inställningar** \> **grupper** \> **flexgrupper** och välj sedan **ny**.
2. I både fältet **Flex+** och **Flex-**, anger du den nya lönetypen **FlexCnt**.
3. Välj **tid och närvaro**\>**inställningar**\>**löneavtal**, och välj sedan **avtalsrader**.
4. För **måndag**, för profiltypen **Flex+** lägger du till följande tre rader.

    | Lönetyp | beskrivning  | Från tid | Till tid  | Minimum | Maximum | Faktor |
    |----------|--------------|-----------|----------|---------|---------|--------|
    | FlexCnt  | Flexräknare | 12:00  | 06:00 | 00,00   | 00,00   | 1,00   |
    | FlexCnt  | Flexräknare | 06:00  | 12:00 | 00,00   | 02,00   | 1.50   |
    | FlexCnt  | Flexräknare | 06:00  | 12:00 | 02,00   | 06,00   | 2.00   |

    > [!NOTE]
    > Varje rad används för ett annat tidsintervall och har en annan faktor. Flexibla timmar som arbetaren arbetar i ett tidsintervall multipliceras med faktorn för den här raden. Till exempel multipliceras timmar som arbete utförs från 06:00 till 08:00 med 1,50. Faktorn som anges i fältet **faktor** på fliken **allmänt** på sidan **löneavtalsrader**.

Arbetaren anger följande registreringar för dagen.

| Journalregistreringstyp | Start    | Slut      |
|---------------------------|----------|----------|
| Stämpla in                  | 07:00 | 07:00 |
| Produktionsjobb            | 07:00 | 09:00 |
| Stämpla ut                 | 09:00 | 09:00 |

Det belopp som ska betalas beräknas på sidan **Godkänn** baserat på den berörda personens registrering. Efter att registreringen beräknas kan du visa resultatet på fliken **Tider**. Du är intresserad av följande fält i det här scenariot.

| Flex + | Flex - | Tid  | Betald tid |
|--------|--------|-------|----------|
| 6,00   | 0,00   | 13,50 | 08,00    |

Mängden Flex+-tid är 6 timmar och beräkningen baseras på flexzoner i tidsprofilen. Detta värde består av en timme av Flex+-tid från 07:00 till 08:00 och fem timmars Flex+-tid från 16:00 till 21:00

När du överför registreringarna, ser du att mängden  Flex+-tid ändras från 6,0 timmar till 8,0 timmar.

| Flex + | Flex - | Tid  | Betald tid |
|--------|--------|-------|----------|
| 8,00   | 0,00   | 13,50 | 08,00    |

Den här ändringen sker efter överföringen eftersom flexibla timmar har beräknats utifrån lönetyper istället för tiden. Följande tabell visar hur åtta timmar beräknas.

| Från     | Till       | Tid | Faktor    | Flexkonto |
|----------|----------|------|-----------|--------------|
| 07:00 | 08:00 | 1    | 1         | 1            |
| 04:00 | 06:00 | 2    | 1         | 2            |
| 06:00 | 08:00 | 2    | 1.5       | 3            |
| 08:00 | 09:00 | 1    | 2         | 2            |
|          |          |      | **Summa** | **8**        |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]