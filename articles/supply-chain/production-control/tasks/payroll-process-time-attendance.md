---
title: Aktivera löneprocessen för tid och närvaro
description: I den här proceduren visas hur du aktiverar lönelistprocessen för tid och närvaro.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39f3495f23ece2ea6989c3a6d74e8694789ea8dd1ae663fad85143c327cde407
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726739"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a>Aktivera löneprocessen för tid och närvaro

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du aktiverar lönelistprocessen för tid och närvaro. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-a-pay-type-with-a-related-pay-rate"></a>Skapa en lönetyp med en relaterad lönesats
1. Tid och närvaro > Inställningar > Lön > Lönetyper
2. Klicka på Ny.
3. Skriv ett värde i fältet Lönetyp.
4. Ange ett värde i fältet Beskrivning.
5. Klicka på Spara.
6. Klick på Tariffer.
    * Satser för lönetyper ställs in för särskilda tidsintervall och individuella satser kan skapas för enskilda arbetare. Du behöver inte alltid skapa satser för lönetyper i tid och närvaro. Den här informationen kanske redan finns i lönesystemet som används för att generera löner.  
7. Klicka på Ny.
8. Markera vald rad i listan.
9. Välj ett tal i fältet Tariff.
10. Klicka på Spara.

## <a name="create-a-pay-agreement"></a>Skapa ett löneavtal
1. Stäng sidan.
2. Stäng sidan.
3. Gå till Löneavtal.
    * Tid och närvaro > Inställningar > Löneavtal  
4. Klicka på Ny.
5. Skriv ett värde i fältet Löneavtal.
6. Ange ett värde i fältet Beskrivning.
7. Klicka på Spara.
8. Klicka på Avtalsrader.
9. Klicka på Ny.
10. Markera vald rad i listan.
11. Ange eller välj ett värde i fältet Profiltyp.
12. Ange eller välj ett värde i fältet Lönetyp.

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a>Ställ in löneavtal för tids- och registreringsarbetare
1. Stäng sidan.
2. Stäng sidan.
3. Gå till Tidsregistreringsarbetare.
    * Tid och närvaro > Inställningar > Tidsregistreringsarbetare  
4. Klicka på länken på den valda raden i listan.
5. Klicka på fliken Anställning.
6. Expandera tidsregistreringsavsnittet.
7. Klicka på Redigera.
8. Ange eller välj ett värde i fältet Löneavtal.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]