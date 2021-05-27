---
title: Butiksbutik visas inte i listan över butiker som ska hämtas från
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en butik inte visas i listan över butiker där artiklar kan plockas.
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
ms.openlocfilehash: ad7ddf8a17640471a2344c45eef76f682d29ef2b
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020837"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a>Butiksbutik visas inte i listan över butiker som ska hämtas från

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en butik inte visas i listan över butiker där artiklar kan plockas.

## <a name="description"></a>beskrivning

En butik visas inte i listan över butiker där artiklar kan hämtas.

## <a name="resolution"></a>Upplösning

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a>Konfigurera för butiksadressen i Commerce-administration

Konfigurera för butiksadressen i Commerce-administration med dessa steg.

1. Gå till **Retail och Commerce \> Kanaler \> Butiker \> Alla butiker**.
1. Hitta den butik som du vill ska visas bland upphämtningsalternativen på webbplatsen för e-handel. Anteckna dess värde för **Driftenhetsnummer**.
1. Gå till **Organisationsadministration \> Organisationer \> Driftenheter**.
1. Sök efter numret för den driftenhet som du tidigare noterar och välj sedan driftenhet i sökresultaten.
1. På snabbfliken **Adresser**, välj **Fler alternativ** och välj **Avancerat**.
1. PÅ snabbflikarna **Allmänt** ska du kontrollera att fälten **Longitud** och **Latitud** är korrekt inställda. Som en del av det här steget ska du kontrollera att värdena har angetts korrekt som positiva eller negativa tal.

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a>Konfigurera uppfyllelsegrupper i Commerce-administration

För att konfigurera uppfyllande grupper i Commerce-administration, följ dessa steg.

1. Gå till **Retail och Commerce \> Kanaler \> Onlinebutiker**.
1. Välj onlinebutiken som ska konfigureras.
1. I åtgärdsfönstret, välj **Inställningar** och välj sedan **Tilldelning av uppfyllelsegrupp**.
1. På sidan **Tilldelning av uppfyllelsegrupp**, välj uppfyllelsegrupp för onlinebutiken.
1. Under **Inställningar** bör du kontrollera att butiksbutiken är korrekt konfigurerad för uppfyllelsegruppen.

## <a name="additional-resources"></a>Ytterligare resurser 

[Skapa en driftenhet](../../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md)

[Ställa in en onlinekanal](../channel-setup-online.md)