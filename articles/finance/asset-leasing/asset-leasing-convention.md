---
title: Regler för tillgångsleasing
description: Detta ämne beskriver konventioner för leasade tillgångar.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: afc432d448f3b013dd8732120d7e8a50a9169343c705a75465e669156fd5e052
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740036"
---
# <a name="asset-leasing-conventions"></a>Regler för tillgångsleasing

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Detta ämne beskriver konventioner för leasade tillgångar. Leasingkonventioner används för att bestämma uppfyllelsedatum för en leasingbok. Om leasingkonventionen har ställts in på **Ingen** är startdatumet detsamma som startdatumet för leasingavtalet (det vill säga värdet i fältet **Startdatum för leasingavtal**). Om leasingkonventionen anges som **Hel månad** blir startdatumet den första dagen i månaden som leasingavtalets startdatum faller inom.

Startdatumet avgör startdatumet för perioden för skuldamorteringen och tidsplanerna för tillgångsavskrivning. Ränte- och avskrivningsutgifter bokförs på periodens slutdatum i motsvarande tidsplaner. Den första redovisnings- och justeringsjournalposten bokförs på avslutningsdatumet.

> [!NOTE]
> Funktionen för leasingkonventioner måste aktiveras via funktionshanteringen. I arbetsytan **Funktionshantering** väljer du funktionen kallad **Leasingkonvention för tillgångsleasing** och sedan **Aktivera nu**.

Leasingkonventioner tilldelas inställningen för en leasingbok.

Följ de här stegen om du vill visa eller tilldela leasingkonventionen.

1. Gå till **Leasing av tillgångar \> Konfigurera \> Leasingböcker**.
2. I fältet **Leasingkonvention** väljer du ett av följande värden.

    | Leasingkonvention | beskrivning |
    |--------------------|-------------|
    | None               | Skuldamorteringen och avskrivningsschemat för tillgångar börjar på leasingavtalets startdatum, detta eftersom startdatumet är lika med leasingavtalets startdatum. Slutdatumet är en månad senare. Denna leasingkonvention garanterar inte att räntan bokförs den sista dagen i varje månad. |
    | Hel månad         | För leasingavtal med startdatum som infaller när som helst under månaden börjar skuldamorteringen och tidsplanerna för tillgångsavskrivning att periodisera utgifter den första dagen i månaden. Denna leasingkonvention säkerställer att ränta periodiseras på den sista dagen i varje månad för hela månaden. |

3. Välj **Spara**.

När ett leasingavtal skapas, anges startdatum för när respektive bok anges automatiskt baserat på det startdatum som angetts för leasingavtalet och den leasingkonvention som angetts för boken.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
