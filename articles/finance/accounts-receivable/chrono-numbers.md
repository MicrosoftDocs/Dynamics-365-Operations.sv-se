---
title: Numreringsdokument och verifikationer i kronologisk ordning
description: I detta ämne beskrivs hur du ställer in och använder kronologisk ordning för tillämpbara dokument och relaterade verifikationer.
author: ikond
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: fe533052b0e5b04a7d27b954ba644761c631d6d7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838871"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a>Numreringsdokument och verifikationer i kronologisk ordning

[!include [banner](../includes/banner.md)]


I vissa länder finns ett juridiskt krav på att numrera dokument och relaterade verifikationer i kronologisk ordning. Kronologin måste stödjas av perioder. Alla värden som hör till tidigare perioder måste vara mindre än de värden som tillhör senare perioder. För att uppfylla detta krav har funktionen för kronologisk numrering implementerats. I detta ämne beskrivs hur du konfigurerar och använder kronologisk ordning för tillämpbara dokument och relaterade verifikationer.

## <a name="prerequisites"></a>Förutsättningar

I arbetsytan Funktionshantering aktiverar du funktionen **Kronologisk numrering**. Mer information finns i [Översikt för funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-chronological-numbering"></a>Konfigurera kronologisk numrering

Kronologisk numrering påverkar följande dokument.

**Kundreskontra**
- Kundfaktura
- Verifikation av kundfaktura
- Försäljningskreditfaktura
- Verifikation för försäljningskreditfaktura
- Fritextfaktura
- Verifikation för fritextfaktura
- Fritextkreditfaktura
- Verifikation för fritextkreditfaktura
- Följesedel
- Följesedelsverifikation
- Korrigeringsverifikation för följesedel
- Verifikation för räntefaktura
- Verifikation för kravbrev

**Leverantörsreskontra**
- Fakturaverifikation
- Verifikation för kreditfaktura
- Produktinleveransverifikation

**Projekthantering**
- Faktura
- Fakturaverifikation
- Kreditfaktura
- Verifikation för kreditfaktura 

### <a name="define-number-sequences"></a>Definiera nummerserier

Om du vill definiera nummerserier går du till **Organisationsadministration** > **Nummerserier** > **Nummerserier**. Du kan definiera så många nummerserier som krävs för att täcka de perioder som påverkas för erforderliga dokument. 

Ange ett företag för respektive nummerserie. Segmenten i nummerserierna måste definieras så att de ger kronologisk ordning för perioder. Till exempel kan segmentnamnen innehålla ett särskilt prefix som identifierar en viss period.

![Konfigurera nummerserie](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a>Konfigurera nummerseriegrupper

Om du vill konfigurera nummerseriegrupper går du till **Kundreskontra** > **Inställningar** > **Parametrar för kundreskontra**. På fliken **Nummerserier** definierar du så många nummerseriegrupper som krävs för att täcka de perioder som påverkas. 

I avsnittet **Referens** väljer du, för respektive grupp, en av de dokumentreferenser som stöds. I fältet **Nummersekvenskod** refererar du sedan till en nummersekvens som tidigare skapats för relaterad period.

![Konfiguration av nummerseriegrupp](media/chrono-num-sequence-group.jpg)

Konfigurera på samma sätt nummersekvensgrupper i modulerna **Leverantörsreskontra** och **Projekthantering och redovisning**.

### <a name="configure-number-sequence-groups-chronology"></a>Konfigurera kornologisk ordning för nummerseriegrupper

Om du vill konfigurera kornologisk ordning för nummerseriegrupper går du till **Organisationsadministration** > **Nummerserier** > **Kronologiska nummerseriegrupper**. Definiera tillämplighetsvillkor för nummerseriegrupper.

![Inställningar för kronologiska nummer](media/chrono-num-sequence-group-period.jpg)

| Fält            | beskrivning                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Giltighet  | Startdatum för tillämplighet för nummerseriegrupp. |
| Upphörande      | Slutdatum för tillämplighet för nummerseriegrupp. Om inget slutdatum tillämpats väljer du **Aldrig**. |
| Nummerseriegrupp | Nummerseriegrupp som kommer att användas för att generera dokumentnummer under perioden. |
| Ursprunglig nummerseriegrupp | Denna nummerseriegruppkod används för ytterligare filtrering av fall där dokument redan har tilldelats en bestämd *permanent* nummerseriegrupp. Ett tomt värde betraktas som ett specifikt värde. Om du behöver ignorera en preliminär tilldelad grupp använder du alternativet **Standard** för den här inställningen. |
| Standardvärde | Om inställningen aktiveras ignorerar systemet den preliminära tilldelade dokumentnummerseriegruppen, och endast start- och slutdatum används för tillämplighetsanalys. Om den är inaktiverad använder systemet den fullständiga kombinationen **Giltig** + **Förfaller** + **Ursprunglig nummerseriegrupp** för urval. |

## <a name="document-posting"></a>Dokumentbokföring
När du bokför ett dokument tilldelas dokumentet lämplig nummerseriegrupp baserad på dokumentets bokföringsdatum, och används sedan för att skapa ett dokumentnummer baserat på den nummerserie som upptäckts. Systemet visar ett meddelande om tilldelningar av nummerseriegrupper.

![Dokumentnummer](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> För vissa länder finns det en specifik logik som redan har implementerats för dokumentnumrering. I det här fallet åsidosätter landsspecifik logik funktionen **Kronologisk numrering**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
