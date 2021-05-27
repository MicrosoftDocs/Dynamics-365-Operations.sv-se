---
title: Felsöka Dynamics 365-betalningskoppling för Adyen-problem
description: Det här ämnet ger felsökningsvägledning som kan hjälpa dig att få support när du har problem med Microsoft Dynamics 365 Payment Connector för Adyen.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 707efeba9553b996e4e33a4754e42a9d22643e33
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019599"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a>Felsöka Dynamics 365-betalningskoppling för Adyen-problem

[!include [banner](../../includes/banner.md)]

Det här ämnet ger felsökningsvägledning som kan hjälpa dig att få support när du har problem med Microsoft Dynamics 365 Payment Connector för Adyen.

## <a name="description"></a>beskrivning

Det finns problem med Dynamics 365 Payment Connector för Adyen inom följande områden, och du behöver stöd från Adyen-teamet:

- Konfiguration av Point of sale (POS), Modern point of sale (MPOS), kundtjänst eller Dynamics 365 Commerce
- Adyen tjänsteleverantör för betalning (PSP) referensnummer (till exempel om du har frågor om avslag, inklusive manuell nyckelinmatning \[MKE\] avslag)
- Allt som inte fungerar i test- eller live handelsmiljöer

## <a name="resolution"></a>Upplösning

Använd följande e-postmall för att starta supportprocessen med Adyen-team. När du vill felsöka bör du se till att e-postmeddelandet innehåller all information som behövs.

| Fält        | Värde |
|--------------|-------|
| Till           | `support@adyen.com` |
| Kopia           | |
| Ämnesrad | Supportförfrågan Microsoft Dynamics |
| Brödtext         | <p>Hej support,</p><p>Ge stöd för följande problem:</p><ul><li>Handlarkonto</li><li>Miljö (Test/Prod)</li><li>Kanal (POS/kundtjänst/e-handel)</li><li>PSP referensnummer om problemet ingår i en specifik transaktion (Du kan hitta PSP-referensnumret på kvittot, i Adyen kundområde eller på transaktionsmenyn i kassaterminalen.)</li><li>Skärmdump eller bild av felmeddelandet, om det är tillämpligt</li><li>Loggfiler för Loggboken (i .txt-format)</li><li>Beskrivning av det problem och de felsökningssteg du har försökt</li></ul> |

## <a name="additional-resources"></a>Ytterligare resurser

[Acceptera betalningar med Adyen-kopplingen för Dynamics 365 Commerce](https://www.adyen.com/partners/dynamics-365-commerce)

[Dynamics 365-betalningskoppling för Adyen](../dev-itpro/adyen-connector.md)

[Ställ in Adyen betalningskoppling för Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
