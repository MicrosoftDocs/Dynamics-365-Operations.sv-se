---
title: Associera anläggningstillgångar med leasingar
description: Ämnet förklarar hur du associerar en befintlig anläggningstillgång med en ny leasing.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0e2261755d98ee38564b4b864daf8e79551d1239
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814090"
---
# <a name="associate-fixed-assets-with-leases"></a>Associera anläggningstillgångar med leasingar

[!include [banner](../includes/banner.md)]

Ämnet förklarar hur du associerar en befintlig anläggningstillgång med en ny leasing. När du associerar en anläggningstillgång med en leasing blir ROU-tillgångsvärdet vid det första redovisningstillfället anskaffningskostnaden för anläggningstillgången.

Innan du kan associera en anläggningstillgång till en leasing måste du skapa en post för anläggningstillgången i Anläggningstillgångar. Därefter, på sidan **Sammanfattning av leasing**, måste du skapa en leasing och en länk till tillgången för den leasingen.

1. Lägg till en leasing genom att följa stegen i [Lägga till och kopiera leasing](add-lease.md). Välj den tillgång som ännu inte har anskaffats i fältet **Nummer för anläggningstillgång**, på sidan **Lägg till leasing**.
2. Välj **Böcker** och bekräfta betalningsplanen.
3. Välj **Första redovisningstillfälle**.
4. Välj **Journal för leasing av tillgång**.

    Den första redovisningsjournalposten för leasingen debiterar anläggningstillgången för det belopp som vanligtvis debiteras till ROU-tillgångskontot.

    Du kan nu visa transaktionstypen och boken för anläggningstillgången.

5. Välj **Journaluppgifter**.
6. Välj **Rader** för att visa de enskilda raderna för journalposten.
7. Välj den journalrad som innehåller tillgången och välj sedan fliken **Anläggningstillgångar**.

    På fliken **Anläggningstillgångar** visas transaktionstypen och boken. Som standard är fältet **Transaktionstyp** inställt på **Anskaffning**, och fältet **Bok** är inställt på den aktuella boken för anläggningstillgången.

När du har bokfört den första redovisningsjournalposten visas transaktionen som en anskaffningstransaktion för anläggningstillgången. Om du vill visa transaktionstabellen går du till **Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**, väljer lämplig tillgång och väljer **Värderingar**. Du bör se att den första redovisningsjournalposten har skapat en anskaffningstransaktion för den angivna anläggningstillgången.

Anläggningstillgången kan nu skrivas av med hjälp av standardavskrivningsfunktionen i Anläggningstillgångar. Mer information finns om avskrivning finns i [Avskrivningsmetoder och avskrivningspraxis](../fixed-assets/depreciation-methods-conventions.md).

> [!NOTE]
> Om du associerar en anläggningstillgång med en leasing inaktiveras knapparna **Avskrivning av tillgång** och **Leasingnedskrivning** i Leasing av tillgångar. Du kan visa tillgångsavskrivningar och transaktioner för leasingnedskrivning från Anläggningstillgångar. Knappen **Transaktioner för tillgångar**, som öppnar ett frågeformulär inaktiveras också. Du kan också öppna föreformuläret **Transaktioner för tillgångar** i Anläggningstillgångar.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]