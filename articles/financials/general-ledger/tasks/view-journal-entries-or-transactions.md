---
title: Visa poster eller transaktioner i redovisningsjournal
description: Detta förfarande anger hur du använder verifikationstransaktionförfrågan för att söka efter poster i redovisningsjournaler eller transaktioner.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm, LedgerTransVoucher, LedgerTransBase, Originaldocuments
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c93b581e22665b27c1b99503cc91c20ead14ac81
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834694"
---
# <a name="view-journal-entries-or-transactions"></a>Visa poster eller transaktioner i redovisningsjournal

[!include [task guide banner](../../includes/task-guide-banner.md)]

Detta förfarande anger hur du använder verifikationstransaktionförfrågan för att söka efter poster i redovisningsjournaler eller transaktioner.

1. Gå till huvudboken > undersökningar och rapporter > verifikattransaktioner.
2. Ange fältet som du vill ange ett filterkriterium för.
3. Ange dina filterkriterier för det valda fältet.
    * Du kan filtrera efter ett enskilt värde eller ett intervall. Kontrollera att korrekt syntax används när du definierar ett intervall. Värdena ska separeras med dubbla punkter (.).  
4. Klicka på fliken Joins om du vill lägga till ytterligare register att filtrera ifrån.
5. Välj "Tables\General journal entry" i trädet.
6. Klicka på Add table join.
7. Klicka på Cancel om du väljer att inte lägga till ett ytterligare register.
8. Klicka på fliken Intervall.
9. Klicka på OK om du vill köra frågan.
10. Klicka på Transaktionsursprung.
    * Olika knappar för rutnätet kan användas för att utforska ytterligare information om den valda verifikationsposten. Vissa knappar kanske inte är tillgängliga, beroende på typen av transaktion och transaktionsegenskaperna.  
11. Stäng sidan.
12. Klicka på ursprungligt dokument.
13. Stäng sidan.

