---
title: Arbetsflöde för utgiftshantering
description: Detta avsnitt förklarar hur du kan använda arbetsflödessystemet i Microsoft Dynamics 365 Finance för att skapa en granskningsprocess för utgiftsrapporter i utgiftshanteraren.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5207be92cb58d8ab2658096b3e0f3fc81d73d91e
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "3153987"
---
# <a name="expense-management-workflow"></a>Arbetsflöde för utgiftshantering

[!include [banner](../includes/banner.md)]

Du kan använda arbetsflödessystemet för att skapa en granskningsprocess för utgiftsrapporter i utgiftshanteraren. Du kan skapa ett arbetsflöde som utnyttjar följande kriterier i syfte att avgöra vem som får godkänna utgiftsrapporter:

- Rapporteringshierarki och fördefinierade godkännandenivåer för medarbetare
- Godkännande på flera nivåer som stöder provisoriska godkännare samt en slutgiltig godkännare
- Finansiella dimensioner och projektansvar
- Tilldelning till specifika användare eller användargrupper

Godkännanden av arbetsflöden kan skapas för utgiftsrapporter, reserekvisitioner, förskott samt återkrävande av moms.

**Exempel**

Följande process är ett exempel på arbetsflödet för utgiftshantering för en utgiftsrapport.

1. En medarbetare skapar och sparar en utgiftsrapport.
2. Medarbetaren skickar in utgiftsrapporten för godkännande. Godkännaren identifieras baserat på de regler som angetts när arbetsflödet skapades.
3. Godkännaren får ett meddelande om att en utgiftsrapport är redo för godkännande. Godkännaren granskar utgiftsrapporten och bekräftar att följande villkor uppfylls:

    - Utgifterna bryter inte mot någon utgiftspolicy, Om en utgift bryter mot någon policy, bekräftar godkännaren att utgiftsrapporten innehåller en giltig affärsmotivering.
    - Elektroniska kvitton bifogas till utgiftsrapporten.

4. Godkännaren godkänner utgiftsrapporten.
5. Utgiftsrapporten tilldelas till godkännaren för leverantörsreskontra för bokföring.
6. Beroende på om automatisk bokföring har ställts in eller inte, uppstår något av följande steg:

    - Om automatisk bokföring har konfigurerats kommer utgiftsrapportern att behandlas för betalning, och utgiftsrapportens status uppdateras.
    - Om automatisk bokföring inte har konfigurerats, bekräftar koordinatorn för leverantörsreskontra att samtliga originalkvitton har lämnats in, samt att kvittona motsvarar utgifterna i utgiftsrapporten. Samtliga momskoder som anges på utgiftsrapporten måste också bekräftas vara korrekta.

När dessa krav har bekräftats bokförs utgiftsrapporten.

När utgiftsrapporten har bokförts godkänns utbetalning för utgiftsrapporten, och medarbetaren får sin ersättning.
