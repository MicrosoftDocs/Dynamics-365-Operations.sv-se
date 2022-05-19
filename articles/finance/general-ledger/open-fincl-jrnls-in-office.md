---
title: Öppna mallar för redovisningsjournaler i Office
description: Detta ämne beskriver problem som kan uppstå när du skapar anpassade redovisningsjournaler genom att använda en mall i Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 099d3c0074a86913b79b732a4c2a34b6e6488672
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2022
ms.locfileid: "8723090"
---
# <a name="open-financial-journal-templates-in-office"></a>Öppna mallar för redovisningsjournaler i Office

[!include [banner](../includes/banner.md)]

Detta ämne beskriver problem som kan uppstå när du skapar anpassade redovisningsjournaler genom att använda en mall i Microsoft Excel.

## <a name="symptom"></a>Symptom

Du har skapat en anpassad Excel-mall för redovisningsjournaler, men den visas inte på menyn **Öppna rader i Excel**. Eller så visas den på menyn, men en annan mall öppnas när du väljer den.

## <a name="resolution"></a>Lösning

Standardfunktionen Öppna i Excel använder rotdatakällan (tabell) för den aktuella sidan för att bestämma vilka Office-mallar eller datatabeller som visas som alternativ på menyn **Öppna i Excel**. Detta beteende är inte optimalt för redovisningsjournaler, eftersom redovisningsjournaler använder sig av samma tabeller (LedgerJournalTable och LedgerJournalTrans) som rotdatakällan till många andra typer av journaler.

För redovisningsjournaler är funktionen Öppna i Excel avsedd för att visa mallar som har utformats för journalen som du för närvarande arbetar i kontexten av, som till exempel den allmänna journalen eller en betalningsjournal. Exempelvis kommer en mall som är avsedd att användas med en betalningsjournal för leverantörer att utformas för att framtvinga ditt huvudkonto som ett leverantörskonto.

Om du vill framhäva en mall så att den finns tillgänglig på menyerna **Öppna rader i Excel** och **Öppna i Excel**, då kan du enkelt som utvecklare implementera gränssnittet **LedgerIJournalExcelTemplate** och utöka klassen **DocuTemplateRegistrationBase**. Det finns flera exempel på detta tillvägagångssätt implementerat i systemet. Ett exempel som kan användas som referens är gränssnittet **LedgerDailyJournalExcelTemplate** som skapades för den allmänna journalen (eller dagliga journalen).

När gränssnittet **LedgerIJournalExcelTemplate** har implementerats för din mall, kommer menyn **Öppna rader i Excel** att filtrera mallar efter journaltypen på din journal och bara visa mallarna som finns tillgängliga för den journalen. Gränssnittet ger också en valideringsmetod som säkerställer att en mall inte kan öppnas för en journal om den inte uppfyller kraven på kontotyp. Du kan till exempel ange att kontotypen måste vara av typen **Leverantör** eller **Redovisning**.

Mer information om den här funktionen finns i [Lägga till mallar på menyn Öppna rader i Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).
