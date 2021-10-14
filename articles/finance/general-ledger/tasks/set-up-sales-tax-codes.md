---
title: Ställ in momskoder
description: Det här avsnittet innehåller information om hur du ställer in momskoder i Dynamics 365 Finance.
author: twheeloc
ms.date: 09/27/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2539d701dda4ef5e1484d095b2d86d1f68a0dc98
ms.sourcegitcommit: 86f0574363fb869482ef73ff294f345f81d17c5b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7562112"
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

    På snabbfliken **Beräkning** i fältet **Ursprung** om **belopp per enhet** är markerat, kommer värdet multipliceras med kvantiteten på transaktionen för att beräkna momsbeloppet.  Om momskoden inte är en enhetsbaserad moms är värdet en procentsats som används som ursprung för att denna momskod ska kunna beräkna momsbeloppet.     

11. Välj **Spara**.
12. Stäng sidan.
13. Välj **Spara**.

Från och med Microsoft Dynamics 365 Finance version 10.0.22, om du använder [Tax service](../../localizations/global-tax-calcuation-service-overview.md) och funktionen [**Stöd för flera momsregistreringsnummer**](../../localizations/emea-multiple-vat-registration-numbers.md) är aktiverad i arbetsytan **funktionshantering** kan du använda fältet **Typ av moms** för att ange typ av momskod. Följande värden finns:

- Standardmoms
- Reducerad moms
- Moms 0 %
- Punktskatt
- Övriga

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
