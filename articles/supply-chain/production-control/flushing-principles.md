---
title: Avräkningsprinciper
description: Det här avsnittet beskrivs de fyra avräkningsprinciperna som används för förbrukning av råmaterial.
author: johanhoffmann
manager: tfehr
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorReleaseOrders
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9f7546b70ddef30d88a79b00fe31d4e82d9bfb9b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437603"
---
# <a name="flushing-principles"></a>Avräkningsprinciper

[!include [banner](../includes/banner.md)]

Avräkningsprinciper återspeglar olika förbrukningsstrategier för råmaterial som används i produktionsprocessen. Förbrukningen är den process som drar av material från lagerbehållningen och anger värdet för det förbrukade materialet till **Pågående arbete** (PIA) för produktionsorder och batchorder. Vanligen förbrukas råmaterial från en plats som har konfigurerats för processen som förbrukar materialet. Den här platsen kallas produktionsinleveransplatsen.

Materialet flyttas till inleveransplatsen före materialförbrukning. På bilden nedan visas processen.

[![scenario4a](./media/scenario4a.png)](./media/scenario4a.png)

1. Lagerställe för material
2. Råmaterialhämtning
3. Plats för produktionsinleverans
4. Råmaterialförbrukning
5. Produktionsprocess

Mmaterialförbrukning kontrolleras av följande avräkningsprinciper:

- Manuell
- Starta
- Slutför
- Tillgänglig på plats

Avräkningsprinciperna konfigureras i en hierarki med standardvärden. Hierarkin börjar på frisläppt produkt, där avräkningsprincipen har värdet **starta**. I strukturlistan (BOM) eller receptrad kan avräkningsprincipen från produkten åsidosättas. Standardavräkningsprincipen på produktionsstrukturraderna eller receptrader för batchorder hämtas från produkten eller det åsidosatta värdet på strukturlistan eller receptet.

## <a name="description-of-the-flushing-principles"></a>Beskrivning av avräkningsprincipen

### <a name="manual"></a>Manuell
Den manuella avräkningsprincipen anger att registrering av materialförbrukning är en manuell åtgärd. Denna princip gäller om du t.ex. vill kunna spåra tid och antalet förbrukade batchnummer eller serienummer måste redovisas för i spårningssyften. Manuell förbrukning registreras i en produktionsplocklistejournal. För artiklar som aktiveras för avancerade lagerprocesser kan ett handhållet flöde appliceras.

### <a name="start"></a>Starta
Startavräkningsprincipen anger att materialet förbrukas automatiskt när tillverkningsordern startas. Mängden material som används är proportionell mot den kvantitet som startas. När startavräkningsprincipen används tillsammans med tillverkningskörningssystemet kan den även användas till att avräkna material när en åtgärd eller ett processjobb startas. Denna princip är relevant om exempelvis avvikelsen i förbrukningen är låg, materialet är lågvärdesmaterial, det inte finns några spårningskrav eller det är kort bearbetningstid i operationer. 

### <a name="finish"></a>Slutför
Avslutavräkningsprincipen anger att materialet ska förbrukas automatiskt, när produktionsordern rapporteras som färdig eller när en åtgärd som har ställts upp för att använda materialet registreras som slutförd. Mängden material som används är proportionell mot den kvantitet som rapporteras som klar. När avslutaavräkningsprincipen används tillsammans med tillverkningskörningssystemet kan den även användas till att avräkna material när en åtgärd eller ett processjobb slutförts. Denna princip gäller i samma situationer som startprincipen. Emellertid är avslutaprincipen för åtgärder som har en längre körtid där material inte anges till PIA innan åtgärden är slutförd. 

### <a name="available-at-location"></a>Tillgänglig på plats
Tillgänglig på platsen-avräkningsprincipen anger att materialet ska förbrukas automatiskt, när det registreras som plockat för produktion. Materialet har registrerats som plockat från plats när arbetet med råmaterialplockningen har slutförts eller när material finns på platsen för produktionsinleverans och materialraden släppts till lagret. Plocklistan som skapas under processen bokförs i ett batchjobb. Denna princip är användbar om du till exempel har många plockaktiviteter mot en tillverkningsorder. I det här fallet behöver du inte manuellt uppdatera plocklistan och du får en aktuell vy över PIA-saldo.
