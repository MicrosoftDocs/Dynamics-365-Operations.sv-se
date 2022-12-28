---
title: Fel vid utdragsbokföring på grund av obefintligt lager eller uppdateringskonflikter
description: Den här artikeln ger möjliga lösningar på lagerrelaterade problem under utdragsbokföring i Microsoft Dynamics 365 Commerce.
author: Shajain
ms.date: 12/19/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: cebb890b42def6e9b002b01be63266b88bfc35a4
ms.sourcegitcommit: 4ad87483ba0bfea3e04fdb7e578d8abc34e607a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2022
ms.locfileid: "9887636"
---
# <a name="statement-posting-errors-due-to-unavailable-inventory-or-update-conflicts"></a>Fel vid utdragsbokföring på grund av obefintligt lager eller uppdateringskonflikter

[!include [banner](../../includes/banner.md)]

Den här artikeln ger möjliga lösningar på lagerrelaterade problem under utdragsbokföring i Microsoft Dynamics 365 Commerce.

## <a name="description"></a>beskrivning

Under bokföringen av handelstransaktioner kanske felmeddelanden angående lagerproblem eller uppdateringskonflikter visas.

### <a name="inventory-issues-error-message"></a>Felmeddelande om lagerproblem

Om lagerproblem påträffas liknar felmeddelandet som du får detta exempel:

> xx kan inte plockas eftersom bara yy är disponibla i lagret

### <a name="update-conflict-error-messages"></a>Uppdatera felmeddelanden för konflikt

En uppdateringskonflikt uppstår när lagervärderingsmetoden är *standardkostnad* eller *glidande medelvärde*. Eftersom båda dessa metoder är beständig kostnadsredovisning, bestäms slutkostnaden vid bokföring.

Om du använder metoden *glidande medelvärde* kommer felmeddelandet för uppdateringskonflikt likna det här exemplet:

> Lagervärde xx.xx förväntas inte efter den proportionella utgiftsberäkningen

Om du använder metoden *standardkostnad* kommer felmeddelandet för uppdateringskonflikt likna det här exemplet:

> Standardkostnaden matchar inte det ekonomiska lagervärdet efter uppdateringen. Värde = xx.xx, Kvt = yyy.yy, Standardkostnad = zz.zz

## <a name="resolutions"></a>Lösningar

### <a name="workaround-for-the-inventory-error"></a>Lösning för lagerfel

Du kan minska lagerfelet genom att antingen uppdatera lagret för artikeln manuellt eller genom att aktivera fysiskt negativt lager för artikelmodellgruppen som är kopplad till artikeln i Commerce headquarters.

För en konsekvent bokföring rekommenderar Microsoft att du aktiverar fysisk negativ inventering för artikelmodellgruppen. I vissa fall kan utdrag inte bokföras om inte negativt fysiskt lager är aktiverat.

Det finns till exempel inget lager för en artikel, men kassören returnerar artikeln och lägger tillbaka den till samma transaktion till ett reducerat pris för att öppna en prismatchning. I det här fallet dras både returtransaktionen och försäljningstransaktionen till samma utdrag från den enskilda kundordern. Eftersom det inte finns någon garanti för att returraden (som ökar lagret) kommer att bokföras innan försäljningsraden (vilket minskar lagret) bokförs, kan lagerfel inträffa. Om fysiskt negativt lager är aktiverat i det här scenariot påverkas inte transaktionsbokföringen negativt och systemet avspeglar korrekt lagret.

#### <a name="enable-negative-physical-inventory-for-an-item-model-group"></a>Aktivera negativt fysiskt lager för en artikelmodellgrupp

Aktivera negativt fysiskt lager för en artikelmodellgrupp i Commerce headquarters genom att följa dessa steg.

1. Gå till **Lagerhantering \> Inställningar \> Lager**.
1. I vänster navigeringsfönstret, välj artikelmodellgrupp.
1. I avsnittet **Lagerpolicyer**, under **Negativt lager**, markera kryssrutan **Fysiskt negativt lager**.

![Fysiskt negativt lager är aktiverat.](./media/Physical_Negative_Inventory.png)

### <a name="workaround-for-the-update-conflict-error"></a>Lösning på uppdateringskonfliktfelet

Möjliga lösningar på ett uppdateringskonfliktfel finns i [En uppdateringskonflikt där lagervärderingsmetoden är antingen standardkostnad eller glidande medelvärde](/troubleshoot/dynamics-365/supply-chain/costing/update-conflict-standard-cost-moving-average-inventory-valuation).

> [!NOTE]
> För uppdateringskonfliktfelet behöver du inte ta bort kundorder som genererats med hjälp av aggregeringssteget för bokföring. När du har implementerat föreslagna lösningar bör utdraget bokföras om du försöker utföra utdragsbokföringen igen.
