---
title: Konfigurera befordrade fält för steg i mobilappen Warehouse Management
description: Denna artikel beskriver hur du främjar och lyfter fram specifik information för varje steg i uppgiftsflödena för mobilappen för Warehouse Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepSelectPromotedFields, WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour, WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: e2d65f20febaf9bd1d143414054b121f8decb7c0
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689841"
---
# <a name="configure-promoted-fields-for-steps-in-the-warehouse-management-mobile-app"></a>Konfigurera befordrade fält för steg i mobilappen Warehouse Management

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Funktionerna som beskrivs i denna artikel gäller bara den nya mobilappen Warehouse Management. De påverkar inte den gamla lagerställeappen, som nu har blivit inaktuell.

Denna artikel beskriver hur du främjar och lyfter fram specifik information för varje steg i uppgiftsflödena för mobilappen för Warehouse Management. Den här kapaciteten kan hjälpa medarbetare att fokusera på de viktigaste fälten när de arbetar genom ett flöde. För varje steg i varje process kan admins välja vilka fält som ska höjas upp och vilka fält som ska markeras.

## <a name="enable-promoted-fields-in-your-system"></a>Aktivera som stöds av fält i systemet

Om du kör Supply Chain Management version 10.0.28 eller tidigare, innan du kan konfigurera befordrade fält måste du slutföra följande procedur för att aktivera de nödvändiga funktionerna och generera de obligatoriska fältnamnen i mobilappen Warehouse Management. Om du kör version 10.0.29 av Supply Chain Management eller senare är funktionerna obligatoriska och kan inte inaktiveras, så du kan hoppa över den här proceduren.

1. Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**. (Se [Översikt över funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för mer information om denna sida.)
1. Se till att funktionen *Steginstruktioner för lagerställeapp* är aktiverad för systemet. Den här funktionen är en förutsättning för funktionen *Lagerställeapp som stöds fält*. Från och med version 10.0.29 av Supply Chain Management är obligatorisk och kan inte inaktiveras. Mer information om funktionen *Steginstruktioner för lagerställeapp* finns i [Anpassa stegtitlar och instruktioner för Warehouse Management-mobilappen](mobile-app-titles-instructions.md).
1. Se till att funktionen *Erbjudna fält i lagerställeapp* är aktiverad för systemet. Det här är funktionen som beskrivs i den här artikeln. Från och med version 10.0.29 av Supply Chain Management är obligatorisk och kan inte inaktiveras.
1. Uppdatera fältnamnen i Warehouse Management-mobilappen genom att gå till **Warehouse Management \> Inställningar \> Mobil enhet \> Fältnamn i lagerställeapp** och väljer **Skapa standardinställningar**. Upprepa detta steg för varje juridisk person (företag) där du använder mobilappen Warehouse Management. - Mer information finns i [Konfigurera fält för mobilappen för distributionslagerhantering](configure-app-field-names-priorities-warehouse.md).

## <a name="configure-promoted-fields-from-a-menu-specific-override"></a>Konfigurera baserade fält från en menyspecifik åsidosättning

Använd följande procedur för att konfigurera befordrade fält.

1. Skapa en menyspecifik åsidosättning för relevant meny och steg enligt beskrivningen i [Anpassa stegrubriker och instruktioner för Warehouse Management mobilapp](mobile-app-titles-instructions.md).
1. Hitta kombinationen av värden för **Steg-ID** och **Namn på menyalternativ** som du vill redigera, och välj sedan värdet i kolumnen **Steg-ID**.
1. På sidan som visas på snabbfliken **Välj erbjudna fält**, markera **Välj fältet** i verktygsfältet.
1. I dialogrutan **Erbjudna fält** välj de fält som du vill marknadsföra. Du kan också markera upp till två av de valda fälten. Markerade fält visas i fetstil i mobilappen Warehouse Management. När du väljer fält bör du tänka på att vissa skärmar kan vara stora nog att bara visa de översta fälten eller två som stöds. Ett exempel på hur du använder de här inställningarna finns i scenariot senare i denna artikel.

    > [!NOTE]
    > Listan **Tillgängliga fält** är begränsad till de fält som kan visas för menyalternativet. Andra faktorer (till exempel artikelsammansättning) avgör om ett fält faktiskt visas i mobilappen Warehouse Management. Om du har konfigurerat fält som stöds visas bara de valda fälten på huvudsidan i mobilappen Warehouse Management. Däremot kan arbetare fortfarande visa de återstående fälten genom att titta på detaljsidan.

1. Välj **OK** om du vill applicera dina inställningar. Dina valda fält visas nu på snabbflikarna **Välj erbjudna fält**.

## <a name="example-scenario"></a>Exempelscenario

### <a name="enable-sample-data"></a>Aktivera exempeldata

För att använda de angivna exempelposterna och värdena för att arbeta igenom det här scenariot måste du använda ett system där standard [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) är installerade. Du måste också välja den **USMF** juridiska personen innan du börjar.

### <a name="configure-sales-picking-with-promoted-steps-on-the-license-plate-step"></a>Konfigurera försäljningsplockning med stegvisa steg i licenssteget

I den här proceduren ställer du in uppflyttade och markerade fält för menyalternativet **Försäljningsplockning** i licenssteget.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Steg för mobil enhet**.
1. Sök efter steg-ID som kallas *LicensePlateId* och välj det.
1. Klicka på **Lägg till stegkonfiguration** i åtgärdsfönstret.
1. Använd fältet **Menyalternativ** i listrutan om du vill söka efter och välja *Försäljningsplockning*.
1. Välj **OK**.
1. Detaljsidan för åsidosättningen som du just skapat visas. På snabbfliken **Välj erbjudna fält**, markera **Välj fältet** i verktygsfältet.
1. I dialogrutan **Erbjudna fält** kan du välja de fält som du vill främja och lyfta fram. I listan **Tillgängliga fält**, hitta och välj följande fält och använd knapparna för att flytta dem till listan **Valda fält**:

    - Plats
    - Artikel
    - Produktnamn
    - Lagerstatus

1. Använd pil- och nedpilsknapparna när du vill anpassa ordningen på fälten i listan **Valda fält**. I mobilappen Warehouse Management visas fälten i den ordning som du anger här.
1. Markera fältet **Plats** och välj sedan **Markera**.
1. Välj **OK** för att spara konfiguration.

### <a name="view-the-promoted-fields-in-the-warehouse-management-mobile-app"></a>Visa befordrade fält i mobilappen Warehouse Management

I den här proceduren öppnar du mobilappen Warehouse Management och går igenom stegen för att visa de fält som du har visat och markerat i den föregående proceduren.

1. I Microsoft Dynamics 365 Supply Chain Management, skapa en försäljningsorder som kräver ett plocksteg för att plocka från en plats som spåras med ID-nummer. Släpp sedan försäljningsordern till lagret. Anteckna de arbets-ID som har genererats.
1. Öppna mobilappen för Warehouse Management och logga in på lagerställe 24. (I standarddemodata, logga in med *24* som användar-ID och *1* som lösenord.)
1. Välj menyn **Utgående** och välj sedan menyalternativet **Försäljningsplockning**.
1. Följ instruktionerna i dataposten på skärmen och ange det arbets-ID som genererades i steg 1.
1. På steget som innehåller texten **Skanna en ID-skylt** bör du se de ändringar som du har gjort på detaljsidan. Fälten visas i den ordning som du anger för de som stöds, och fältet **Plats** visas i fetstil.
