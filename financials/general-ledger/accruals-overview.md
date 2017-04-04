---
title: "Översikt över periodiseringar"
description: "Det här avsnittet innehåller en beskrivning av periodiseringar och information om hur du ställer in dem och skapar transaktioner."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 328a4a7bef32ee8634e4a9f4854ebe78fcc99f6d
ms.lasthandoff: 03/31/2017


---

# <a name="accruals-overview"></a>Översikt över periodiseringar

Det här avsnittet innehåller en beskrivning av periodiseringar och information om hur du ställer in dem och skapar transaktioner.

Periodiseringar används i periodiserad redovisning för att följa intäkt som redovisas i den period då den har tjänats in, inte när betalningen mottas, och följa utgifter (kostnader) som redovisas när de uppträder, inte när betalning görs.

## <a name="accrual-schemes"></a>Periodiseringsscheman
Periodiseringsscheman används för att ställa in den uppskjutna intäkter och kostnader, och samma periodiseringsschema kan användas för både intäkter och kostnader. Periodiseringen av redovisningen omfördelar de kostnader eller intäkterna för en journalrad så att kostnaderna och intäkterna redovisas i rätt period. På sidan **Periodiseringsschema** anger du debetkonton och kreditkonton som ska användas när schemat används.

-   **Debet** – Huvudkontot som du definierar ska ersätta debethuvudkontot på journalverifikationsraden. Detta konto används också för återföringen av uppskjutandet baserat på redovisningsperiodiseringstransaktionerna.
-   **Kredit** – Huvudkontot som du definierar ska ersätta kredithuvudkontot på journalverifikationsraden. Detta konto används också för återföringen av uppskjutandet baserat på redovisningsperiodiseringstransaktionerna.

När du har definierat vilka konton som ska användas, kan du ange hur verifikationsnummer skapas när periodiseringstransaktioner skapas. Du kan även ange hur ofta transaktionerna ska göras, hur många gånger transaktionerna skapas och när transaktionerna bokförs. När det periodiseringsschemat har skapats, kan du använda det i någon av journalerna genom att använda redovisningsperiodiseringsfunktionen.

## <a name="ledger-accruals"></a>Periodiseringar
När du anger en journal, kan du klicka på **Periodiseringar** på menyn **Funktioner**. Därefter, när du väljer periodiseringsschema, kan du se basbeloppet från journalen som ska fördelas på perioden, vilket bestäms av periodiseringsschemat. Till exempel om du betalar en medarbetares försäkring för hela året, i januari och beloppet är 12 000, måste du tolka utgiften varje månad. Du kan välja ett startdatum. Du kan även ange om beloppet som periodiseras baseras på kontot eller motkontot. När du har gjort dina val klickar du på **transaktioner** att visa alla transaktioner som har skapats utifrån periodiseringsschemat. Till exempel om du sidor 12 000 i försäkring utgifter under året visas 1 000 för varje månad. När du bokför journalen, kan du visa transaktionerna med den **Verifikationstransaktioner** sidan förfrågan. Om ett periodiseringsschema inte kan användas (t.ex, när en försäljningsorderfaktura eller en inköpsorderfaktura inblandade), du krediterar förutbetalt belopp och debiterar utgiftsbeloppet. Du kan sedan välja **Motboka** när du använder periodiseringsschemat.


