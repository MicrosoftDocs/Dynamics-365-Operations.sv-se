---
title: Uppdateringsrapport över anläggningstillgångar
description: Det här avsnittet beskriver hur du använder uppdateringsrapporten för anläggningstillgångar.
author: saraschi2
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-12-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: a605f3dac679d98d57f32f9672315c63f1fd7763d111f244f51435d313fd0349
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747117"
---
# <a name="fixed-assets-roll-forward-report"></a>Uppdateringsrapport över anläggningstillgångar

[!include [banner](../includes/banner.md)]

**Uppdateringsrapport över anläggningstillgångar** ger detaljerade data, i ett lättläst Microsoft Excel-format, för periodens stängning, bokslut och skatterapportering. Rapporten innehåller start- och slutsaldon för anläggningstillgångar, samt en värderingen av rörelser för perioden, och ny anskaffning och avyttring som uppstått under perioden. Data rapporteras för enskilda anläggningstillgångar och sammanfattas även för grupper av anläggningstillgångar och juridisk person.

**Uppdateringsrapporten för anläggningstillgångar** använder ramverket för elektronisk rapportering (ER). Innan du kan köra rapporten måste konfigurationen för modellen för anläggningstillgångar och uppdateringsrapporten för anläggningstillgångar importeras från Microsoft Dynamics Lifecycle Services (LCS). Instruktioner finns i [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)

Den här rapporten finns i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, 7.3 eller som en snabbkorrigering för Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017). Tre snabbkorrigeringar måste implementeras för miljöer som har versionen från juli 2017:

- **KB 4041754:** konfigurationen för elektronisk rapportering (ER) kan inte hämtas från LCS eftersom den inte gäller för den aktuella versionen efter implementation av plattformens uppdateringspaket
- **KB 4056107:** elektronisk rapportering (ER) ackumulerad uppdatering 5
- **KB 4056353:** rapporterna anläggningstillgångsutdrag och anteckningar uppfyller inte kraven i GAAP och IFRS

Följande register beskriver de fält som är tillgängliga i rapporten.


|                    Fält                    |                                                                                                                                beskrivning                                                                                                                                |
|---------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              Balans: Ingående              |                                                                                           Det bokförda nettovärdet av fasta tillgångar per det ”från” datum som anges i rapporten.                                                                                           |
|              Balans: Utgående              |                                                                                            Det bokförda nettovärdet av fasta tillgångar per det ”till” datum som anges i rapporten.                                                                                            |
|         Anskaffningar: IB         |                                                 Summan av alla transaktioner av typen <strong>anskaffning</strong> och <strong>anskaffningsjustering</strong> till det ”från” datum som anges i rapporten.                                                  |
|      Anskaffning: Periodens förvärv      |                                                 Summan av alla transaktioner av typen <strong>anskaffning</strong> och <strong>anskaffningsjustering</strong> som registrerats under rapportens datumintervall.                                                  |
|       Anskaffningar: Avyttringar        |                                                                        Summan av alla transaktioner av typen återföring av anskaffning registrerade som avyttringstransaktioner under rapportens datumintervall.                                                                        |
|         Anskaffningar: UB         |                                                  Summan av alla transaktioner av typen <strong>anskaffning</strong> och <strong>anskaffningsjustering</strong> till det ”till” datum som anges i rapporten.                                                   |
|        Avskrivningar: IB         | Summan av alla transaktioner av typen <strong>avskrivning</strong>, <strong>avskrivningsjustering</strong>, <strong>särskild avskrivning</strong>, och <strong>extraordinär avskrivning</strong> fram till det ”från” datum som anges i rapporten. |
|     Avskrivningar: Periodens avskrivningar     |                         Summan av alla transaktioner av typen <strong>avskrivning</strong>, <strong>avskrivningsjustering</strong> och <strong>extraordinär avskrivning</strong> som registrerats under rapportens datumintervall.                          |
| Avskrivningar: Periodens särskilda avskrivningar |                                                              Summan av alla transaktioner av typen <strong>särskild avskrivning</strong> som registrerats under rapportens datumintervall.                                                               |
|       Avskrivningar: Periodens avyttringar       |                                                                       Summan av alla transaktioner av typen återföring av avskrivning registrerade som avyttringstransaktioner under rapportens datumintervall.                                                                        |
|        Avskrivningar: UB         |  Summan av alla transaktioner av typen <strong>avskrivning</strong>, <strong>avskrivningsjustering</strong>, <strong>särskild avskrivning</strong>, och <strong>extraordinär avskrivning</strong> fram till det ”till” datum som anges i rapporten.  |
|    Upp-/nedskrivning: IB     |                              Summan av alla transaktioner av typen <strong>uppskrivning</strong>, <strong>uppskrivningsjustering</strong>och <strong>omvärdering</strong> till det "från" datum som anges i rapporten.                               |
|   Uppskrivningar/Nedskrivningar: Periodiska uppskrivningar   |                                                                    Summan av alla transaktioner av typen <strong>uppskrivningsjustering</strong> som registrerats under rapportens datumintervall.                                                                    |
|  Uppskrivningar/Nedskrivningar: Periodiska nedskrivningar  |                                                                   Summan av alla transaktioner av typen <strong>nedskrivningsjustering</strong> som registrerats under rapportens datumintervall.                                                                   |
| Uppskrivningar/Nedskrivningar: Periodiska omvärderingar  |                                                                        Summan av alla transaktioner av typen <strong>omvärderingar</strong> som registrerats under rapportens datumintervall.                                                                        |
|   Uppskrivningar/Nedskrivningar: Periodiska avyttranden   |                                                           Summan av alla återföringar av typen uppskrivningar, nedskrivningar och omvärderingar som registrerat en avyttringstransaktion under rapportens datumintervall.                                                           |
|    Upp-/nedskrivning: UB     |                               Summan av alla transaktioner av typen <strong>uppskrivning</strong>, <strong>uppskrivningsjustering</strong>och <strong>omvärdering</strong> till det "till" datum som anges i rapporten.                                |
|          Avyttring: Datum för avyttrande           |                                                                                                                Datum för avyttrande av förteckning över anläggningstillgångar.                                                                                                                |
|    Avyttring: Bokfört nettovärde vid avyttring    |                                                                                                    Bokfört nettovärde för förteckning över anläggningstillgångar vid tidpunkten för avyttrande .                                                                                                    |
|            Avyttring: Försäljningsvärde            |                                                                                               Försäljningsvärde för förteckning över anläggningstillgångar med avyttring – försäljningstransaktion.                                                                                                |
|           Avyttring: Kassationsvärde            |                                                                                               Kassationsvärde för förteckning över anläggningstillgångar med avyttring – kassationstransaktion.                                                                                               |
|           Avyttring: Vinst/förlust            |                                                                                 Vinst- eller förlustvärdet som beräknas som en del av avyttringstransaktionen för förteckning över anläggningstillgångar.                                                                                 |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]