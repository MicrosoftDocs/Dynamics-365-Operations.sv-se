---
title: Metod för halvårs avskrivningspraxis
description: Det här ämnet beskriver den metod som anläggningstillgångar använder för att beräkna avskrivning med hjälp av halvårspraxis, som beräknar sex månader från avskrivningen under en tillgångs första och sista tjänstår.
author: moaamer
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: fb15a293bb8cec1b4faba7bcbd29eb4df7916786
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720404"
---
# <a name="half-year-depreciation-convention-methodology"></a>Metod för halvårs avskrivningspraxis

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs metoden som används i anläggningstillgångar för att beräkna avskrivning med hjälp av halvårspraxis. Halvårspraxis beräknar sex månader från avskrivningen under en tillgångs första och sista tjänstår. Mer information finns om avskrivningspraxis finns i [Avskrivningsmetoder och avskrivningspraxis](Fixed-asset-depreciation-conventions.md). 

När du använder avskrivningspraxis för sex månader använder systemet anskaffningsåret eller året som tillgången togs i bruk och därefter beräknas fem avskrivningsår från det året och därefter läggs sex månader till. För att illustrera denna process bör du överväga en tillgång som har anskaffats för priset på 50 000 och som var i drift i april 2020. Anta också att tillgången har ett fem års tjänstelivstid.

Det första året i tjänst kommer att ingå i december 2020, vilket innebär att slutet på till gångens fem års tjänstelivstid kommer att vara den 2024 december. Halvårsvis avskrivningspraxis lägger till sex månader till tillgångens livslängd, vilket innebär att dess tjänstelivstid slutar i juni 2025. 

> Årlig avskrivning 50 000/5 = 10 000 månatlig avskrivning 10000/12 = 833,33 <br>
> Avskrivning första året 10 000/2 = 5 000 och den efterföljande månadsavskrivningen 5000/9 = 555,56

   [![Avskrivningstidsplan för halvårs avskrivningspraxis.](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)

De utökade avskrivningsperioder som läggs till med halvårspraxis ger en mer korrekt fördelning av avskrivningen. Den sex månaders praxis representerar avskrivningskostnaderna mer jämt, vilket är användbart för rapportering av resultaträkningen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
