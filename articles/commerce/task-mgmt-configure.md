---
title: Konfigurera uppgiftshantering
description: I denna artikel beskrivs hur du konfigurerar funktioner för uppgiftshantering i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.search.industry: ''
ms.openlocfilehash: ff97abab330174b41af76d22c202e8338d6d37fd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282772"
---
# <a name="configure-task-management"></a>Konfigurera uppgiftshantering

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar funktioner för uppgiftshantering i Microsoft Dynamics 365 Commerce.

Innan Dynamics 365 Commerce chefer och medarbetare kan använda funktionerna för aktivitets hantering i Commerce måste du konfigurera uppgiftshanteringen. Konfigurationssteg omfattar beviljande av behörigheter till chefer och medarbetare, distribution av behörigheter till kassaklienter, inställning av kassameddelanden och konfigurering av panelen **Uppgifter** på startsidan för en kassaprogram.

## <a name="configure-permissions-for-store-managers"></a>Konfigurera behörigheter för butikshanterare

Alla arbetare i ett visst butik kan visa alla uppgifter som är tilldelade till det arkivet. De kan också uppdatera status för de uppgifter som har tilldelats dem. Profiler som butikschefer måste dock ha behörigheten uppgiftshantering för att hantera uppgifter som är tilldelade till butiken och för att skapa uppgifter för enskilda syften.

Konfigurera behörigheter av uppgiftshantering för butikschefer enligt följande instruktioner.

1. Gå till **Retail och Commerce \> Medarbetare \> Behörighetsgrupper**.
1. Välj en specifik behörighetsgrupp (till exempel **chef**) och välj sedan **redigera**.
1. På snabbfliken **behörigheter** anger du alternativet **tillåt uppgiftshantering** till **ja**.
1. På snabbfliken **meddelanden** lägger du till åtgärden **uppgiftshantering** och anger ett värde i fältet **visningsordning**. Ange till exempel **2** om åtgärden **Orderuppfyllelse** redan har värdet **Visningsordning** av **1**.
    
> [!NOTE]
> Om en icke-chef person måste ha behörighet för uppgiftshantering i POS kan du bevilja behörighet till personen. Du kan också skapa en ny behörighetsgrupp för icke-chefer och ange alternativet **Tillåt uppgiftshantering** till **ja**.

Följande illustration visar hur du konfigurerar behörigheter av uppgiftshantering för butikschefer.

![Konfigurera behörigheter för uppgiftshantering för butikschefer.](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a>Konfigurera behörigheter för medarbetare

Medarbetare måste ha behörighet att skapa uppgiftslistor, hantera tilldelningskriterier och konfigurera återkommande uppgifter för en uppgiftslista. Om du vill konfigurera dessa behörigheter tilldelar du medarbetare till roll **butikshanterarens roll**.

Följ dessa steg för att konfigurera behörigheter för en anställd.

1. Gå till **Retail och Commerce \> Anställda \> Användare**.
1. Välj en medarbetare.
1. På snabbfliken **Användarens roller** klicka på **Tilldela roller**.
1. I dialogrutan **Tilldela roller till användare**, välj rollen **butikshanterarens roll** och klicka sedan på **OK**.

## <a name="distribute-permissions-to-pos-clients"></a>Distribuera behörigheter till kassaklienter

Innan medarbetarna kan använda kassaklienter måste behörigheterna distribueras och synkroniseras till dessa klienter.

Distribuera behörigheter till kassaklienter enligt följande instruktioner.

1. Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.
1. Välj **1060** (**Personal**) distributionsschema och välj sedan **Kör nu**.
1. Välj **1070** (**Kanalkonfiguration**) distributionsschema och välj sedan **Kör nu**.

## <a name="configure-pos-notifications-for-tasks"></a>Konfigurera kassameddelanden för uppgifter

Uppgiftshantering måste konfigureras så att meddelanden är tillgängliga i kassaprogrammet.

Gör på följande vis för att konfigurera kassameddelanden.

1. Navigera till **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassa \> Kassaåtgärder**.
1. Sökåtgärd **1400** (**Uppgiftshantering**) och markera kryssrutan **Aktivera meddelanden**.

Följande bild visar åtgärder **Uppgiftshantering** på sidan **Kassaåtgärder**.

![Åtgärden Uppgiftshantering på sidan Kassaåtgärder.](media/HQ-POS-Tasks-Notifications.png)

Mer information om hur du konfigurerar kassameddelanden finns i [Visa ordermeddelanden i POS](notifications-pos.md).

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a>Konfigurera uppgiftspanelen på en kassaprogram startsida

Innan du konfigurerar panelen **Uppgift** på startsidan för att kassaprogram, se [Skärmlayouter för POS](pos-screen-layouts.md) för information om hur du konfigurerar och lägger till nya knappar i en kassaskärmlayout.

Konfigurera **uppgift** på en kassaprogram startsida, följ dessa steg.

1. Gå till **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassa \> Skärmlayout**.
1. Välj en skärmlayout, välj en storlek på layouten och välj en knappsats.
1. På snabbfliken **Knappsatser**, välj **Designer** om du vill redigera den valda knappsatsen.
1. Lägg till en panel för **Uppgifter** till rätt avsnitt på startsidan.

Följande illustration visar ett exempel på panelen **Uppgifter** på en kassas startsida.

![Uppgiftspanel på en startsida för kassa.](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över uppgiftshantering](task-mgmt-overview.md)

[Skapa uppgiftslistor och lägga till uppgifter](task-mgmt-create-lists.md)

[Tilldela uppgiftslistor till butiker eller medarbetare](task-mgmt-assign-lists.md)

[Uppgiftshantering i POS](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
