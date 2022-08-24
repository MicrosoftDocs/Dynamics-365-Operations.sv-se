---
title: Felsöka Dynamics 365-betalningskoppling för Adyen-problem
description: Denna artikel ger felsökningsvägledning som kan hjälpa dig att få support när du har problem med Microsoft Dynamics 365 Payment Connector för Adyen.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 687f2fdff5e29cc25fae911b015164f0d90aee88
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268876"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a>Felsöka Dynamics 365-betalningskoppling för Adyen-problem

[!include [banner](../../includes/banner.md)]

Denna artikel ger felsökningsvägledning som kan hjälpa dig att få support när du har problem med Microsoft Dynamics 365 Payment Connector för Adyen.

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
| Brödtext         | <p>Hej support,</p><p>Ge stöd för följande problem:</p><ul><li>Handlarkonto</li><li>Miljö (Test/Prod)</li><li>Kanal (POS/kundtjänst/näthandel)</li><li>PSP referensnummer om problemet ingår i en specifik transaktion (Du kan hitta PSP-referensnumret på kvittot, i Adyen kundområde eller på transaktionsmenyn i kassaterminalen.)</li><li>Skärmdump eller bild av felmeddelandet, om det är tillämpligt</li><li>Loggfiler för Loggboken (i .txt-format)</li><li>Beskrivning av det problem och de felsökningssteg du har försökt</li></ul> |

## <a name="additional-resources"></a>Ytterligare resurser

[Acceptera betalningar med Adyen-kopplingen för Dynamics 365 Commerce](https://www.adyen.com/partners/dynamics-365-commerce)

[Dynamics 365-betalningskoppling för Adyen](../dev-itpro/adyen-connector.md)

[Ställ in Adyen betalningskoppling för Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
