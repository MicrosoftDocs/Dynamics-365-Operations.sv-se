---
title: Referenser till ursprungliga fakturor i kreditfakturor
description: I denna artikel beskrivs hur du ställer in och skriver ut de ursprungliga fakturanumren på relaterade kreditfakturor.
author: ilkond
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ebfeb43aaf137ef336b460f340fbda50f5918d08
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861543"
---
# <a name="references-to-original-invoices-in-credit-notes"></a>Referenser till ursprungliga fakturor i kreditfakturor

[!include [banner](../includes/banner.md)]


I vissa länder och regioner finns det ett juridiskt krav på att utskrivna kreditfakturor innehåller referenser till de ursprungliga fakturorna. I denna artikel beskrivs hur du ställer in och skriver ut de ursprungliga fakturanumren på relaterade kreditfakturor.

## <a name="prerequisites"></a>Förutsättningar

- I arbetsytan **Funktionshantering** aktiverar du funktionen **Kreditfaktureringslayout för försäljnings- och projektfakturerapporter**. Mer information finns i [Översikt för funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- De utskriftsbara formaten för de nödvändiga dokumenten måste konfigureras i Utskriftshantering.

Funktionerna som beskrivs i detta ämne gäller för följande dokument:

**Kundreskontra**

- Fritextkreditfaktura
- Kundkreditfaktura

**Projekthantering och redovisning**

- Projekts kreditfaktura

## <a name="configure-accounts-receivable-parameters"></a>Konfigurera parametrar för kundreskontra

Följ dessa steg om du vill ställa in parametern som styr huruvida referenser till de ursprungliga fakturorna skrivs ut i relaterade kreditfakturor.

1. Gå till **Kundreskontra** \> **Inställningar** \> **Parametrar för kundreskontra**.
2. I fliken **Uppdateringar**, på snabbfliken **Faktura**, anger du alternativet **Tillämpa layouten för kreditfakturor på rapporter för försäljnings- och projektfakturor** som **Ja**.

![Konfigurera parametrar för kundreskontra.](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a>Definiera referenser till ursprungliga fakturor

Använd följande procedurer för att definiera referenser till ursprungliga fakturor, baserat på dokumenttypen.

### <a name="free-text-credit-note"></a>Fritextkreditfaktura

1. Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.
2. Skapa en ny kreditfaktura eller välj en befintlig kreditfaktura.
3. Öppna fakturan.
4. I åtgärdsfönstret på fliken **Faktura** i gruppen **Funktioner** väljer du **Kreditfaktura**.
5. Ange referensen till den ursprungliga fakturan och välj orsaken till korrigeringen.

![Definiera referensen för en fritextfaktura.](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a>Kundkreditfaktura

1. Gå till **Kundreskontra** \> **Order** \> **Alla försäljningsorder**.
2. Välj och öppna den fakturerade försäljningsorder som måste korrigeras.
3. I åtgärdsfönstret, på fliken **Sälj** i gruppen **Kreditfaktura**, väljer du **Kreditfaktura**.
4. Ange orsaken till korrigeringen. Referensen till den ursprungliga fakturan skapas automatiskt.

![Definiera referensen för en försäljningsorder.](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a>Projekts kreditfaktura

1. Gå till **Projekthantering och redovisning** \> **Projektfakturor** \> **Projektfakturor**.
2. Välj och öppna projektfakturan som måste korrigeras.
3. I åtgärdsfönstret, i fliken **Projektfaktura** i gruppen **Funktioner**, väljer du **Välj för kreditfaktura**.
4. Välj **Kreditfaktura**.
5. Ange orsaken till korrigeringen. Referensen till den ursprungliga fakturan skapas automatiskt.

![Definiera referensen för en projektfaktura.](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a>Skriva ut kreditfakturor

När du skriver ut fritext-, kund- och projektkreditfakturor kommer dessa att inkludera referensen till den ursprungliga fakturan och korrigeringsorsaken.

![Utskriven kreditfaktura.](media/credit-note-FTI.jpg)

> [!NOTE]
> Se till att dokumentens utskrivbara format är korrekt konfigurerade, med antagandet att referenser till ursprungliga fakturor skrivs ut.

## <a name="references-to-original-invoices-in-debit-notes"></a>Referenser till ursprungliga fakturor i debetfakturor

Som standard kan referenser till ursprungliga fakturor anges för kreditfakturor. Du kan till exempel ange referenser när du gör negativa (minskande) korrigeringar av ursprungliga fakturor.

Om du vill ange referenser när du gör positiva (ökande) korrigeringar av ursprungliga fakturor, måste du aktivera funktionen **Referenser till ursprungliga fakturor i debetfakturor** i arbetsytan för **funktionshantering**.  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
