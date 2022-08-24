---
title: Butiksbutik visas inte i listan över butiker som ska hämtas från
description: Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när en butik inte visas i listan över butiker där artiklar kan hämtas.
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
ms.openlocfilehash: b6cec3d9d598be221516506388e4797ad579a610
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286763"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a>Butiksbutik visas inte i listan över butiker som ska hämtas från

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när en butik inte visas i listan över butiker där artiklar kan hämtas.

## <a name="description"></a>beskrivning

En butik visas inte i listan över butiker där artiklar kan hämtas.

## <a name="resolution"></a>Upplösning

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a>Konfigurera för butiksadressen i Commerce headquarters

Konfigurera för butiksadressen i Commerce headquarters med dessa steg.

1. Gå till **Retail och Commerce \> Kanaler \> Butiker \> Alla butiker**.
1. Hitta den butik som du vill ska visas bland upphämtningsalternativen på webbplatsen för näthandel. Anteckna dess värde för **Driftenhetsnummer**.
1. Gå till **Organisationsadministration \> Organisationer \> Driftenheter**.
1. Sök efter numret för den driftenhet som du tidigare noterar och välj sedan driftenhet i sökresultaten.
1. På snabbfliken **Adresser**, välj **Fler alternativ** och välj **Avancerat**.
1. PÅ snabbflikarna **Allmänt** ska du kontrollera att fälten **Longitud** och **Latitud** är korrekt inställda. Som en del av det här steget ska du kontrollera att värdena har angetts korrekt som positiva eller negativa tal.

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a>Konfigurera uppfyllelsegrupper i Commerce headquarters

För att konfigurera uppfyllande grupper i Commerce headquarters, följ dessa steg.

1. Gå till **Retail och Commerce \> Kanaler \> Onlinebutiker**.
1. Välj onlinebutiken som ska konfigureras.
1. I åtgärdsfönstret, välj **Inställningar** och välj sedan **Tilldelning av uppfyllelsegrupp**.
1. På sidan **Tilldelning av uppfyllelsegrupp**, välj uppfyllelsegrupp för onlinebutiken.
1. Under **Inställningar** bör du kontrollera att butiksbutiken är korrekt konfigurerad för uppfyllelsegruppen.

## <a name="additional-resources"></a>Ytterligare resurser 

[Skapa en driftenhet](../../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md)

[Ställa in en onlinekanal](../channel-setup-online.md)
