---
title: Ordna scenarier för fakturabetalning
description: Detta ämne beskriver hur man konfigurerar Dynamics 365 Commerce så att det stöder olika scenarier som gäller fakturabetalningar.
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9fe8fde32549568812a724311781d3515ef7036c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004422"
---
# <a name="set-up-pay-invoice-scenarios"></a>Ordna scenarier för fakturabetalning

[!include [banner](includes/banner.md)]

Funktionen Betala fakturan i Dynamics 365 Commerce har utökats och stöder nu detta:

- Betalning av flera försäljningsorderfakturor i samma kassatransaktion.
- De typer av kundfakturor som går att betala är fritextfakturor, projektbaserade fakturor och kreditfakturor.

Om du vill aktivera dessa scenarier måste funktionsprofilen för butiker konfigureras enligt beskrivningen nedan.

1. Öppna **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler** och välj en profil som är kopplad till butikerna du vill göra ändringar för.
2. Konfigurera de följande parametrarna på fliken **Funktioner** efter behov.

    - **Försäljningsorderfaktura** – Välj **Ja** så att användarna kan betala en eller flera försäljningsorderbaserade fakturor i samma kassatransaktion.
    - **Fritextfaktura** – Välj **Ja** så att användarna kan betala en eller flera fritextbaserade fakturor i samma kassatransaktion.
    - **Projektfaktura** – Välj **Ja** så att användarna kan betala en eller flera projektbaserade fakturor i samma kassatransaktion.
    - **Försäljningsorder - Kreditfaktura** – Välj **Ja** så att användarna kan kvitta flera försäljningsorderbaserade kreditfakturor mot öppna fakturor eller bearbeta en återbetalning till kunden för en öppen kreditfaktura.

> [!NOTE]
> Betalning eller kvittning av partiella belopp stöds inte ännu.