---
title: Ställ in momskoder
description: Det här avsnittet innehåller information om hur du ställer in momskoder i Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3dad006b486f7cd6714c713a3bd83a95fdf0d2b5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447914"
---
# <a name="set-up-sales-tax-codes"></a>Ställ in momskoder

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller information om hur du ställer in momskoder. Momskoder skapas för varje indirekt moms eller skatt som den juridiska personen ska beräkna, samla in och betala till skattemyndigheterna.

I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till **Navigeringsfönster > Moms > Indirekta skatter > Moms > Momskoder**.
2. Välj **Ny**.
3. I fältet **Momskod**, skriv ett värde.
4. Skriv ett värde i fältet **Namn**.
5. Välj en **kvittningsperiod** genom att öppna rullgardinslistan för att ange vilken skattemyndighet och i vilka intervall denna moms ska rapporteras och betalas.
6. Välj en **bokföringgrupp** för att ange huvudkonton för att bokföra moms i redovisningen.
7. Expandera snabbfliken **Beräkning**. Detta inkluderar flera fält som kontrollerar hur momsbelopp ska beräknas. Fyll i dessa fält efter behov.  
8. I **åtgärdsfönstret** överst i gränssnittet, välj **momskod**.
9. Markera **värden**.
10. Ange värdet för den här momskoden i kolumnen **värde**.
    - På snabbfliken **Beräkning** i fältet Ursprung, om belopp per enhet är markerat, kommer värdet multipliceras med kvantiteten på transaktionen för att beräkna momsbeloppet.  Om momskoden inte är en enhetsbaserad moms är värdet en procentsats som används som ursprung för att denna momskod ska kunna beräkna momsbeloppet.     
11. Välj **Spara**.
12. Stäng sidan.
13. Välj **Spara**.

