---
title: Konfigurera och generera filer för betalningskontroll med hjälp av elektronisk rapportering
description: Detta ämne innehåller information om hur du konfigurerar betalningskontroll med hjälp av elektronisk rapportering.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 491048c7274ba6bb52e0a4b7a6ea5cd0f5ff4741
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878230"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Konfigurera betalningskontrollfiler med hjälp av elektronisk rapportering

Det här ämnet innehåller information om hur du ställer och genererar betalningskontrollfiler genom att använda elektronisk rapportering.

> [!NOTE] 
> Innan du använder funktionen **Generera betalningskontrollfil** måste du först uppdatera enhetslistan.
> Gå till snabbflik **Datahantering > Importera / Exportera > Ramverksparametrar** 
> **Entitetsinställningar** välj **Uppdatera entitetslistan**.


Ställa in betalningskontroll för att generera en elektrisk lista med checkar som ges till banken. När checken sedan visas för banken, jämför banken checken med listan med checkar. Om checken matchar en check i listan behandlar banken checken. Om checken inte matchar en check in listan kvarhåller banken checken för granskning.

## <a name="security-for-positive-pay-files"></a>Säkerhet för betalningskontrollfiler
Betalningskontrollfiler kan innehålla känslig information om betalningsmottagare och checkbelopp. Se därför till att du använder lämpliga säkerhetsåtgärder från det att filerna skapas tills det att de tas emot av banken. Betalningskontrollfiler hämtas till den plats som anges av din webbläsare. Eftersom betalningskontrollfiler kan innehålla känslig information är det viktigt att endast auktoriserade användare har åtkomst för att generera eller visa den här informationen i Microsoft Dynamics 365 Finance. Använd följande tabell som hjälper dig att bestämma behörigheterna som krävs.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Uppgift</th>
<th>Privilegium</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Generera betalningskontrollfiler från listsidan <strong>Bankkonton</strong> eller från sidan <strong>Bankkonton</strong>.</td>
<td><ul>
<li><strong>Hantera information om betalningskontroll</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Generera betalningskontrollfiler för flera juridiska personer och bankkonton från sidan <strong>Skapa en betalningskontrollfil</strong>.</td>
<td><ul>
<li><strong>Hantera information om betalningskontroll</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Visa betalningskontrollfiler på sidan <strong>Sammanfattning om betalningskontrollfil</strong>.</td>
<td><strong>Visa bankbetalningskontrolluppgifter för flera juridiska personer</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Bekräfta en betalningskontrollfil på sidan <strong>Sammanfattning om betalningskontrollfil</strong>.</td>
<td><strong>Bekräfta betalningskontrollfil</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Återkalla en betalningskontrollfil på sidan <strong>Sammanfattning om betalningskontrollfil</strong>.</td>
<td><strong>Återkalla en betalningskontrollfil</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-the-electronic-reporting-configuration"></a>Ställa in konfigurationen för elektronisk rapportering

1. Gå till **Arbetsytor \> Elektronisk rapportering**.
2. På panelen för **Microsoft**-konfigurationsprovidern väljer du **Databaser**.
3. Markera **Global** och välj sedan **Öppna**.
4. Om en anslutning till databasen måste upprättas väljer du den blå länken i dialogrutan.
5. I konfigurationslistan letar du upp och väljer **Modell för betalningskontroll \> Format för betalningskontroll**.
6. På snabbfliken **Versioner** väljer du den senaste versionen och sedan **Importera**.

## <a name="set-up-a-positive-pay-format"></a>Konfigurera ett format för betalningskontrollfil

1. Gå till **Kassa- och bankhantering \> Inställningar \> Format för betalningskontroll**.
2. Välj **Ny**.
3. Konfigurera fälten **Betalningsformat** och **Beskrivning**.
4. Markera kryssrutan **Allmänt elektroniskt exportformat**.
5. Ange fältet **Konfiguration för exportformat** som **Format för betalningskontroll**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Tilldela ett format för betalningskontroll till ett bankkonto
För varje bankkonto som du vill skapa information om lönebetalningskontroll för måste du tilldela lönebetalningskontrollformatet som har angetts i föregående avsnitt. På sidan Bankkonton, välj det format för betalningskontrollfil som motsvarar bankkontot. I fältet **Betalningskontrollens startdatum**, ange det första datumet då betalningskontrollfiler ska genereras. 

>[!Important]
> Ange ett datum i fältet **Startdatum för betalningskontroll**. Om det lämnas tomt kommer den första betalningskontrollfilen som skapas inkludera alla checkar som har skapats för detta bankkonto.

1. Gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton**.
2. Öppna bankkontot.
3. På snabbfliken **Allmänt** anger du fältet **Format för betalningskontroll** till det format som skapades tidigare.
4. Ställ in fältet **Startdatum för betalningskontroll** på aktuellt datum.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Tilldela en nummersekvens för betalningskontrollfiler
Varje betalningskontrollfil måste ha ett unikt nummer. På sidan **Parametrar för kassa- och bankhantering**, skapa en nummersekvens för betalningskontrollfiler på fliken **Nummersekvens**.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Generera en betalningskontrollfil för ett enskilt bankkonto
Du kan generera en betalningskontroll för en enda juridisk person och ett enskilt bankkonto. Information om hur du genererar betalningskontrollfiler för flera juridiska personer och bankkonton samtidigt finns i nästa avsnitt. Om du vill skapa en betalningskontrollfil för ett enskilt bankkonto, öppna dialogrutan **Skapa en betalningskontrollfil** på sidan **Bankkonton**. I fältet **Slutdatum**, ange det datum för senaste kontroll som ska inkluderas i betalningskontrollfilen. Alla checkar som inte har inkluderats i en betalningskontrollfil innan slutet av det här checkdatumet inkluderas i filen.

1. Gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton**.
2. Öppna ett bankkonto som betalningskontroll har ställts in för.
3. Välj **Hantera betalningar \> Betalningskontroll \> Betalningskontrollfil**.
4. Ställ in fältet **Slutdatum**. Checkar som genererats före detta datum kommer att inkluderas.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Generera en betalningskontrollfil för flera bankkonton
Generera en betalningskontrollfil för flera bankkonton med hjälp av den periodiska uppgiften **Betalningskontrollfil**. Välj format för kontrollfilen och ange om du vill generera betalningskontrollfilen för alla juridiska personer eller för en vald juridisk person. Du kan även generera betalningskontrollfilen för alla bankkonton som använder det specificerade formatet för kontrollfilen eller för ett valt bankkonto. I fältet **Slutdatum**, ange det datum för senaste kontroll som ska inkluderas i betalningskontrollfilen. Alla checkar som inte har inkluderats i en betalningskontrollfil innan slutet av det här checkdatumet inkluderas i filen.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Visa resultaten av skapandet av betalningskontrollfilen
När betalningskontrollfilen har skapats kan du visa resultaten på sidan **Sammanfattning om betalningskontrollfil**. Använd detaljsidan **Information om betalningskontrollfil** för att visa information om de enskilda checkarna.

## <a name="confirm-a-positive-pay-file"></a>Bekräfta en betalningskontrollfil
När checkarna som anges i en betalningskontrollfil har betalats får du ett bekräftelsenummer från banken. Sedan kan du bekräfta betalningskontrollfilen. På sidan **Sammanfattning om betalningskontrollfil**, välj en betalningskontrollfil som har statusen **Skapat** och välj sedan åtgärden **Ange bekräftelse**. Vid bekräftelsen av en betalningskontrollfil registreras bekräftelsenumret som du fått från banken.

## <a name="recall-a-positive-pay-file"></a>Återkalla en betalningskontrollfil
Om du måste ändra en betalningskontrollfil kan du sedan återkalla den. På sidan **Sammanfattning om betalningskontrollfil**, välj en betalningskontrollfil som har statusen **Skapat** och välj sedan åtgärden **Återkalla**. För varje check i betalningskontrollfilen återställs fältet som anger om denna check har inkluderats i en betalningskontrollfil. Sedan kan du skapa en ny betalningskontrollfil som innehåller den check som återkallades.


Den resulterande XML-filen hämtas.
