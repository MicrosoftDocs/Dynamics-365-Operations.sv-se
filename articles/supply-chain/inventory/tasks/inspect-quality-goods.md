---
title: Kontrollera kvaliteten på varor
description: I detta ämne beskrivs hur du bearbetar kvalitetsorder.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ceb5547b6c1d4c44e53faba0d6e2c1f0368fb95768a2520ecc39066ff73a03d2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755380"
---
# <a name="inspect-the-quality-of-goods"></a>Kontrollera kvaliteten på varor

[!include [banner](../../includes/banner.md)]

I detta ämne beskrivs hur du bearbetar kvalitetsorder. Kvalitetsinspektioner utförs vanligtvis av en kvalitetsansvarig.

Om standarddemonstrationsdatan har installerats kan du använda den för att genomföra procedurerna i detta ämne. Om du vill använda demonstrationsdatan väljer du den juridiska personen *USMF* innan du börjar. Du måste sedan bekräfta inköpsordern *000016* och bokföra en produktinleverans. En kvalitetsorder genereras automatiskt.

## <a name="step-1-select-a-quality-order"></a>Steg 1: Välj en kvalitetsorder

Gör så här om du vill välja en kvalitetsorder:

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Kvalitetsorder**.
1. Välj den kvalitetsorder som genererades innan du startade den här proceduren.

## <a name="step-2-record-test-results"></a>Steg 2: Registrera testresultaten

Gör så här om du vill registrera testresultat:

1. Välj **resultat**.
1. Välj **Redigera**.
1. Ange ett nummer i fältet **Resultatkvantitet**.
1. Välj önskad post i fältet **Resultat**. I det här exemplet baseras resultatet på ett fördefinierat resultat. Vanligtvis skulle du registrera ett mer specifikt testresultat, till exempel en storlek eller en annan dimension.
1. Välj **Spara**.
1. Stäng sidan.

## <a name="step-3-validate-the-quality-order"></a>Steg 3: Validera kvalitetsordern

Gör så här om du vill validera en kvalitetsorder:

1. Välj **validera**.
1. I fältet **Validerades av** väljer du den användare utför inspektionen.
1. Välj **Välj**.
1. Välj **OK**.
1. Stäng sidan.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
