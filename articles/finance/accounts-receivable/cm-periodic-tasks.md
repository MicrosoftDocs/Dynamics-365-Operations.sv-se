---
title: Periodiska kredithanteringsuppgifter
description: I det här avsnittet beskrivs de periodiska uppgifter som är en nödvändig del i processen för hantering av kreditgränser för kunder.
author: mikefalkner
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: f6b04c28c0f7b5e4d58d464ad45d42478cde4e0ffb584e5afa43c99ebaed7166
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724025"
---
# <a name="periodic-credit-management-tasks"></a>Periodiska kredithanteringsuppgifter

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs de periodiska uppgifter som är en nödvändig del i processen för hantering av kreditgränser för kunder.

## <a name="update-risk-scores"></a>Uppdatera riskpoäng

Eftersom företag utvecklas och omständigheterna ändras, kan kreditriskerna för en viss kund också ändras. För att upprätthålla lämpliga kreditgränser för kunderna måste du regelbundet granska kriterierna för varje riskpoäng och uppdatera poängen för varje kund. Du kan uppdatera följande resultat med hjälp av sidan **uppdatera riskresultat** (**kredit och inkasso \> periodiska uppgifter \> kredithantering \> uppdatera riskresultat**). Alla användardefinierade beräkningar bearbetas också.

- **Genomsnittligt betalningsdagar** – denna poäng är det genomsnittliga antalet dagar som en kund tar på sig att betala fakturor.
- **Kund sedan** – detta är antalet år som kunden har varit kund i din organisation.
- **I företaget sedan** – detta är antalet år som kunden har varit i rörelse. Den använder värdet på fältet **Affärsstart** på sidan **Kunder**.
- **Antal dagar som kan vara utestående** – det här resultatet baseras på kundens saldo i kundreskontra, försäljningsintäkter och antal dagar för föregående tolv månaders period.
- **Genomsnittligt saldo** – det här resultatet baseras på den föregående tolv månaders periodens saldo i kundreskontra.
- **Kredithanteringsgrupp**, **Kontostatus** och **Land** – dessa resultat använder information från kunden.

## <a name="update-customer-balance-statistics"></a>Uppdatera kundsaldostatistik

Du kan köra processen **Uppdatera statistik för kundsaldo** för att uppdatera beräkningen av saldostatistik som visas på sidan **Fråga om saldostatistik**. Den här informationen används för att beräkna riskresultat och värden som visas i faktarutorna för kreditstatistik på sidan **kund**.

När du kör processen uppdaterar den kundsaldo för en enskild kund. Om du vill ställa in ett batchjobb som kör processen för flera kunder kan du använda sidan **Beräkna saldostatistik** (**Kredithantering \> periodiska uppgifter \> beräkna saldostatistik**).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]