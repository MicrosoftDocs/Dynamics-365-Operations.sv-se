---
title: Återställa Dataverse-synkronisering
description: I det här avsnittet beskrivs hur du felsöker poster som inte synkroniseras korrekt mellan Microsoft Dynamics 365 Human Resources och HCM Common-lösningen (administration av humankapital) i Microsoft Dataverse.
author: jaredha
ms.date: 09/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-27
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: d6b20b6b2ae4fdbbfb27a765dfb7a1dc82fe7981
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071170"
---
# <a name="reset-dataverse-synchronization"></a>Återställa Dataverse-synkronisering


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Problem

Poster synkroniseras inte mellan Microsoft Dynamics 365 Human Resources och enheterna i HCM Common-lösningen (administration av humankapital) i Microsoft Dataverse. Mer information om synkronisering finns i [Konfigurera Dataverse integration](hr-admin-integration-common-data-service.md). Underlåtenhet att synkronisera korrekt kan uppstå när **Dataverse försök igen med integration** eller **Dataverse integration missad förfrågan synkronisering** batchjobb fastnar i ett **Kör**-tillstånd.

## <a name="resolution"></a>Lösning

När **Dataverse försök igen med integration** eller **Dataverse integration, synkronisering av missad begäran** batchjobb fastnar i tillståndet **Kör** eller **Avbryt** kan du återställa status. Du gör detta genom att annullera batchjobbet genom att följa riktlinjerna i [Återställ låsta batchjobb](hr-admin-troubleshooting-batch-execution.md). När du har annullerat batchjobbet kan du återställa batchjobbet genom att ange det till **Väntande** tillstånd. Batchjobbet kommer sedan att köras under nästa planerade körtid.

1. Om du inte redan har gjort det ska du aktivera funktionen **Förbättrad avbrytning av batch** i **Funktionshantering**.
   1. Gå till sidan **Funktionshantering** (**Systemadministration** > **Sammanfattning** > **Funktionshantering**).
   2. Välj fliken **Alla**.
   3. Välj kolumnen **Funktionsnamn** och filtrera efter **Förbättrad avbrytning av batch**.
   4. Välj åtgärden **aktivera** om den inte redan är aktiverad.

2. Inaktivera Dataverse-integreringen.
   1. Gå till sidan **Microsoft Dataverse integration** (**Systemadministration** gå till **Länkar** > **Integrationer** > **Dataverse konfiguration**).
   2. Ange **Aktivera Dataverse-integration** till **Nej**.

3. Avbryt batchjobbet **Dataverse försök igen med integration**.
   1. Gå till sidan **Batchjobb** (**Systemadministration** gå till **Länkar** > **Batchjobb** > **Batchjobb**).
   2. Filtrera kolumnen **Jobbbeskrivning** efter **Integration**.
   3. Välj batchjobbet **Dataverse försök igen med integration**.
   4. På åtgärdsmenyfliken, välj **Batchjobb**, **Tvinga annullering** och välj **Ja** för att bekräfta.

   > [!NOTE]
   > Beroende på när integrationen först aktiverades, kan det hända att batchjobbet har beskrivningen **Common Data Service försök igen med integration**. Välj det här batchjobbet om det visas, i stället för batchjobbet **Dataverse försök igen med integration**.

4. Ta bort alla Dataverse integrationsbatchjobb.
   1. På sidan **Batchjobb** väljer du batchjobben **Dataverse integration, synkronisering av missad begäran**, **Dataverse försök igen med integration** och **Dataverse integration, inledande synkronisering**.
   2. På åtgärdsmenyfliken väljer du åtgärden **Ändra status**. 
   3. Välj **Undanhåll** och **OK**.
   4. På åtgärdsmenyfliken, välj åtgärden **Radera** och sedan **Ja** för att bekräfta åtgärden.

5. Aktivera Dataverse integrationsbatchjobben.
   1. Gå till sidan **Microsoft Dataverse integration** (**Systemadministration** > **Länkar** > **Integration** > **Dataverse konfiguration**).
   2. Ange **Aktivera Dataverse-integration** till **Ja**.

6. Gå till sidan **Batchjobb** och bekräfta att batchjobben **Dataverse försök igen med integration** och **Dataverse integration, synkronisering av missad begäran** har skapats.

När batchjobben har återskapats kan du nu övervaka batchjobbet **Dataverse försök igen med integration** för att se hur lång tid det tar att utföra jobbet. Du kan sedan kontrollera att posterna synkroniseras korrekt till HCM Common-lösningen i Microsoft Dataverse.

## <a name="see-also"></a>Se även

[Konfigurera Dataverse-integrering](hr-admin-integration-common-data-service.md)<br>
[Återställ batchjobb som fastnat](hr-admin-troubleshooting-batch-execution.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
