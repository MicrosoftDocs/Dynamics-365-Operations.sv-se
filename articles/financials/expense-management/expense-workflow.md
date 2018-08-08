---
title: "Arbetsflöde för utgifter"
description: "Detta avsnitt förklarar hur du kan använda arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations för att skapa en granskningsprocess för utgiftsrapporter i utgiftshanteraren."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 6ee607f723659a5b6ecd655ba4fdfca35a4c582d
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="expense-workflow"></a>Arbetsflöde för utgifter

[!include [banner](../includes/banner.md)]

Du kan använda arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations för att skapa en granskningsprocess för utgiftsrapporter i utgiftshanteraren. Du kan skapa ett arbetsflöde som utnyttjar följande kriterier i syfte att avgöra vem som får godkänna utgiftsrapporter:

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

