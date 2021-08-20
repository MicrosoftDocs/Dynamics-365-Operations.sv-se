---
title: Kassering av avyttrade anläggningstillgångar
description: Ämnet beskriver hur du eliminerar transaktioner för en anläggningstillgång som avsatts som kassation.
author: moaamer
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 90eb791bae2bbe70cf9fe7127a98962305449e1d0b370cfa001afbd3654046ec
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752928"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a>Kassering av avyttrade anläggningstillgångar

[!include [banner](../includes/banner.md)]

Ämnet beskriver hur du eliminerar transaktioner för en anläggningstillgång som avsatts som kassation. Transaktionstyperna som kan elimineras inkluderar en tillgångs anskaffningsvärde och ackumulerade avskrivningstransaktioner och andra transaktioner för anläggningstillgångar. Eliminering av dessa transaktioner påverkar balansräkningskonton, till exempel anskaffningsjustering, avskrivningsjustering, omvärdering, uppskrivningskonton och nedskrivningskonton.

| Transaktion                                         | Debet (Dr.) | Kredit (Cr.) |
|-----------------------------------------------------|-------------|--------------|
| Dr. Ackumulerad avskrivning                        | X           |              |
| Cr. Anläggningstillgångars vinst/förlust                          |             | X            |
| Dr. Anläggningstillgångars vinst/förlust                          | X           |              |
| Cr. Konto för anskaffning av anläggningstillgång                 |             | X            |
| Dr. Anläggningstillgångars vinst/förlust (bokfört nettovärde \[NBV\]) | X           |              |
| Cr. Anläggningstillgångars vinst/förlust (NBV)                    |             | X            |

> [!NOTE]
> Vi rekommenderar att du samarbetar med företagets ekonomichef (CFO) eller controller för att identifiera de korrekta konton som ska användas för varje transaktionstyp och även för att verifiera att kasseringsprocessen och transaktionerna som den genererar uppdaterar dessa konton korrekt.

Innan du avyttrar en anläggningstillgång som kassation måste du skapa redovisningskonton som är kopplade till tillgångens anskaffningsvärde, avskrivning för aktuellt år, avskrivning för föregående år och till gångens NBV. Transaktionstyperna för anläggningstillgången visas på sidan **Bokföringsprofil för anläggningstillgångar**. Gå till **anläggningstillgångar \> inställningar \> bokföringsprofiler för anläggningstillgångar** och på snabbfliken **avyttrande** väljer du **kassation** i fältet ovanför rutnätet. Följande bild visar listan över transaktionstyper för anläggningstillgångar på sidan **bokförings profiler för anläggningstillgångar**.


[![Avyttrande av en tillgång som kassation, figur 1.](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)

För följande exempel förvärvades en anläggningstillgång 1 januari 2018 och den kommer att kasseras den 31 mars 2019.

- **Anskaffningspris** : 24 000,00 USD
- **Tjänstelivstid:** två år
- **Avskrivningsmetod:** Linjär tjänstelivstid
- **Avskrivningsbelopp:** 1 000,00 USD per månad

NBV för en anläggningstillgång beräknas genom att använda följande formel:

Bokfört nettovärde = anskaffningspris – avskrivning

I det här exemplet har anläggningstillgången förvärvats och avskrivits i 15 månader, från 2018 till mars 2019. Därför är tillgångens NBV 9 000,00 USD (24 000,00 USD – 15 000,00 USD).

[![Exempel på avskrivning för anläggningstillgångar.](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)


Om du vill skapa en avskrivningsjournal, gå till **Anläggningstillgångar \> Journalposter \> Journal för anläggningstillgångar** och välj sedan **Rader** i åtgärdsfönstret. Välj **avyttrande – kassation** och välj sedan ett anläggningstillgångs-ID. Ange inte ett värde antingen i fältet **Debet** eller i fältet **Kredit** för att helt avyttra tillgången.

[![Journal för anläggningstillgångar.](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)

Kassationstransaktionen för avyttrande av anläggningstillgångar ändrar fältvärdena i anläggningstillgångens förteckning på följande sätt:

- I avsnittet **saldo** uppdateras fältet **status** till **kasserat**.
- I avsnittet **Utleverans** är fältet **avyttringsdatum** inställt på det datum då tillgången kasserades.

[![Detaljer om journal för anläggningstillgångar.](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)

Följande illustration visar saldot för anläggningstillgångar.

[![Saldo för anläggningstillgångar.](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)

Följande illustration visar den verifikation som bokförs.

[![Bokfört nettovärde.](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]