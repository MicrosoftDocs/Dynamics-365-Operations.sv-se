---
title: "Översikt över periodiseringar"
description: "Det här avsnittet innehåller en beskrivning av periodiseringar och information om hur du ställer in dem och skapar transaktioner."
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5ad5030da963ca961d49e645b1d9ad19453376b8
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="accruals-overview"></a>Översikt över periodiseringar

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller en beskrivning av periodiseringar och information om hur du ställer in dem och skapar transaktioner.

Periodiseringar används i periodiserad redovisning för att följa intäkt som redovisas i den period då den har tjänats in, inte när betalningen mottas, och följa utgifter (kostnader) som redovisas när de uppträder, inte när betalning görs.

## <a name="accrual-schemes"></a>Periodiseringsscheman
Periodiseringsscheman används för att ställa in den uppskjutna intäkter och kostnader, och samma periodiseringsschema kan användas för både intäkter och kostnader. Periodiseringen av redovisningen omfördelar de kostnader eller intäkterna för en journalrad så att kostnaderna och intäkterna redovisas i rätt period. På sidan **Periodiseringsschema** anger du debetkonton och kreditkonton som ska användas när schemat används.

-   **Debet** – Huvudkontot som du definierar ska ersätta debethuvudkontot på journalverifikationsraden. Detta konto används också för återföringen av uppskjutandet baserat på redovisningsperiodiseringstransaktionerna.
-   **Kredit** – Huvudkontot som du definierar ska ersätta kredithuvudkontot på journalverifikationsraden. Detta konto används också för återföringen av uppskjutandet baserat på redovisningsperiodiseringstransaktionerna.

När du har definierat vilka konton som ska användas, kan du ange hur verifikationsnummer skapas när periodiseringstransaktioner skapas. Du kan även ange hur ofta transaktionerna ska göras, hur många gånger transaktionerna skapas och när transaktionerna bokförs. När det periodiseringsschemat har skapats, kan du använda det i någon av journalerna genom att använda redovisningsperiodiseringsfunktionen.

## <a name="ledger-accruals"></a>Periodiseringar
När du anger en journal, kan du klicka på **Periodiseringar** på menyn **Funktioner**. Därefter, när du väljer periodiseringsschema, kan du se basbeloppet från journalen som ska fördelas på perioden, vilket bestäms av periodiseringsschemat. Om du till exempel betalar en medarbetares försäkring för hela året i januari och beloppet är 12 000, måste du redovisa utgiften varje månad. Du kan välja startdatum. Du kan även ange om beloppet som periodiseras baseras på kontot eller motkontot. När du har gjort dina val klickar du på **Transaktioner** att visa alla transaktioner som har skapats baserat på periodiseringsschemat. Om du till exempel sprider ut de 12 000 i försäkringsutgifter över året, visas 1 000 för varje månad. När du bokför journalen kan du visa transaktionerna via förfrågningssidan **Verifikationstransaktioner**. Om ett periodiseringsschema inte kan användas (t.ex. när en försäljningsorderfaktura eller en inköpsorderfaktura är inblandad), kan du kreditera det förskottsbetalda beloppet och debitera utgiftsbeloppet. Du kan sedan välja **Motboka** när du använder periodiseringsschemat.




