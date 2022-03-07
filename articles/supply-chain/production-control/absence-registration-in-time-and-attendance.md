---
title: Frånvaroregistrering i Tid och närvaro
description: Det här avsnittet beskriver hur du hanterar frånvaroregistreringar i Tid och närvaro.
author: johanhoffmann
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JMGParameters, JmgAbsenceCalendar
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06adca12c172dffa241fe44a6b64bb30863bcb4a8f3867429ad10bc852efd7c3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730236"
---
# <a name="absence-registration-in-time-and-attendance"></a>Frånvaroregistrering i Tid och närvaro

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver begreppen för frånvaro och hur du hanterar frånvaro i Tid och närvaro.

## <a name="absence-that-is-based-on-regular-work-hours"></a>Frånvaro som baseras på vanliga arbetstider

Arbetare anses vara frånvarande för det antal timmar som de inte arbetar under deras vanliga arbetstider. Vanliga arbetstimmar anges i profilen för en arbetares standardtid.

Exempelvis arbetar en arbetare med en dagprofil som stämplar in klockan 7:00 och stämplar ut kl 15:00. Om arbetaren stämplar in klockan 9:00 anses de frånvarande från 7:00 till 9:00 den dagen.

I det här fallet uppmanas arbetare att ange en orsak till frånvaron. De kan ange en orsak genom att välja en frånvarokod.

## <a name="absence-codes"></a>Frånvarokoder

Frånvarokoder definierar olika typer av frånvaro. Frånvarokoder definieras av företaget.

Olika regler kan tillämpas på frånvarokoder. Exempelvis kan en frånvarokod konfigureras att dra av eller bevilja lön.

Ett företag definierar till exempel frånvarokoden **sen** som arbetare kan använda om de kommer in sent och inte har en bra orsak. Företaget definierar också frånvarokoden **intern kurs** som arbetare använder för tid som de tillbringar med att delta i interna kurser. Dessa koder kan ställas in så att **sen** dras av från en arbetares lön men **intern kurs** inte dras av från en arbetares lön.

Du kan ange automatiska orsakskoder. Dessa frånvarokoder kan användas för att beräkna en arbetare tid när ingen frånvaro har registrerats. Arbetarens tidsprofil avgör om frånvarokoden för standardtid eller flextid används.

### <a name="set-up-standard-time-and-flex-time"></a>Ställa in standardtid och flextid

- Konfigurera parametrar för standardtid och flextid med hjälp av alternativen **Infoga frånvaro automatiskt** och **Infoga flextid automatiskt** på sidan **parametrar för tid och närvaro**.

## <a name="absence-groups"></a>Frånvarogrupper

Frånvarokoder grupperas i frånvarogrupper. Du kan använda frånvarogrupper för att gruppera frånvarokoder som har gemensamma egenskaper. Exempel omfattar frånvarokoder för en giltig frånvaro, eller frånvaro på grund av en avtalad tid hos läkare, jurytjänst eller sjukt barn.

## <a name="planned-absence"></a>Planerad frånvaro

Om du vet att arbetaren kommer att vara frånvarande under en period, till exempel en kommande semester, kan du använda planerad frånvaro. Du kan ställa in planerad frånvarokod genom att konfigurera frånvarokoden så att den anser att den tar hänsyn tilll den planerade frånvaron. När du ställer in en planerad frånvaro blir du inte tillfrågad om en frånvarokod under frånvaroperioden när användarens tidsregistreringar beräknas. Planerad frånvaro kan definieras för en enskild arbetare eller så kan du definiera ett batchjobb för att massuppdatera planerad frånvaro för arbetare.

### <a name="set-up-planned-absence"></a>Ställ in planerad frånvaro

1. Välj **personal**&gt;**arbetare**&gt;**medarbetare** och välj en medarbetare.
2. Välj **tid**&gt;**tidstilldelningar**&gt;**tidsfrånvaroregistrering** och ställ in den planerade frånvaron.

## <a name="interrupted-planned-absence"></a>Avbruten planerad frånvaro

Om du använder alternativet **avbryta** när du ställer in en planerad frånvaro, kommer den planerade frånvaron att avbrytas om arbetaren loggar in under den planerade frånvaroperioden. Den planerade frånvaron markeras som **avbruten** och har någon inverkan på framtida beräkningar.

### <a name="set-up-a-planned-absence-for-interruption"></a>Skapa en planerad frånvaro för avbrott

1. Öppna sidan **tidsfrånvaroregistrering** enligt proceduren för att skapa planerad frånvaro.
2. Välj **avbryta**.

Alternativet **avbryta** används när tiden registreras via terminalen Arbetsstyrning eller enheten Arbetsstyrning. Alternativet kan inte användas om registreringarna anges på sidorna för beräkning och godkännande eller på sidan **elektroniskt tidkort**.

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a>Exempel på användning av frånvaro i en flexprofil

Följande tre exempel visar hur frånvaro beräknas i en profil med flextidperioder.

Exemplen använder följande profiler.

| Instämpling | Standardtid    | Rast             | Standardtid | Flex-        | Utstämpling | Flex+        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| 08:00     | 09:00 till 11:30 | 11:30 till 12:00 | 12:00 till 15:00 | 15:00 till 16:00 | 16:00      | 16:00 till 18:00 |

### <a name="example-1-signing-out-during-a-flex--period"></a>Exempel 1: Loggar ut under en flex- period

Arbetaren stämplar in klockan 8:00 och stämplar ut 15:30. I detta fall, eftersom arbetaren stämplar ut under en flex- period, beräknas ingen frånvaro och en halvtimme dras av från arbetarens flexsaldo.

### <a name="example-2-signing-out-in-during-standard-time-period"></a>Exempel 2: Loggar ut under standardtiden

Arbetaren stämplar in klockan 8:00 och stämplar ut 14:30. I detta fall, eftersom medarbetaren stämplar ut under standardtidsperioden, beräknas frånvaro från 14:30 till 16:00 och en frånvaroperiod på 1,5 timmar registreras. Det krävs en frånvarokod för den perioden.

### <a name="example-3-signing-out-during-a-flex-period"></a>Exempel 3: Loggar ut under en flex+ period

Arbetaren stämplar in klockan 8:00 och stämplar ut 16:30. I detta fall, eftersom arbetaren stämplar ut under en flex+ period, beräknas ingen frånvaro och en halvtimme läggs till arbetarens flexsaldo.

## <a name="absence-in-the-calculation-and-approval-process"></a>Frånvaro i beräknings- och godkännandeprocessen

Tidsregistreringar för arbetare måste beräknas och godkännas innan de kan överföras till ett lönesystem som löneposter.

En godkännare kan ändra tidsregistreringar för en arbetare. Godkännaren kan även ändra eventuell frånvaro som arbetaren har registrerat. Om godkännaren manuellt anger en tidsperiod som har en frånvarokod, åsidosätts frånvarokoden för den perioden inte av standardfrånvarokoden från parametrarna Tid och närvaro.

En arbetare stämplar t.ex. in klockan 10:00 och väljer en frånvarokod som indikerar att de är sena. Arbetaren informerar senare sin arbetsledare att hon hade ett läkarbesök mellan 08:00 till 10:00. Ett läkarbesök bör inte medföra avdrag på arbetarens lön. Därför kan i detta fall chefen justera två timmar av frånvaro mellan 08:00 till 10:00 manuellt genom att ange en frånvarokod som anger sjukdom under de två timmar.

### <a name="calculate-and-approve-absence"></a>Beräkna och godkänn frånvaro

- Välj **Tid och närvaro**&gt;**Granska och godkänn**&gt;**Godkänn eller beräkna**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]