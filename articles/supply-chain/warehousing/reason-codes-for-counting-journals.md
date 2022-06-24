---
title: Orsakskoder för lagerinventering
description: I denna artikel beskrivs hur du konfigurerar och tillämpar orsakskoder och inventeringsuppgifter.
author: perlynne
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 7d182f1d979543eeec700924d2bd180ee06be8ce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857124"
---
# <a name="reason-codes-for-inventory-counting"></a>Orsakskoder för lagerinventering

[!include [banner](../includes/banner.md)]

Orsakskoder låter dig analysera resultatet från en inventeringsprocess och eventuella avvikelser som inträffar under den här processen. Du kan ange en orsak till att göra inventeringen, t.ex. en trasig lastpall eller en lagerjustering som baseras på lagerexempel. Samtidigt kan du använda justeringsfunktionerna för att bokföra värdet för lagerbehållningsjusteringar på korrekt motkonto baserat på orsaken till varje lagerjustering.

## <a name="recommendation"></a>Rekommendation

Innan du konfigurerar systemet rekommenderar vi att du definierar en strategi för att arbeta med orsakskoder. Exempelvis försök besvara följande frågor:

- Orsakskoder ska finnas på lagerställen?
- Orsakskoder ska vara obligatoriska eller valfria över vissa objekt?
- Hur många orsakskoder behöver du?
- Måste du förvälja en begränsad lista med orsakskoder för justeringar?
- Hur ska användare av streckkodsskannrar använda orsakskoder? Orsakskoderna ska vara förvalda, obligatoriska eller inte redigerbara?
- Behöver lagerarbetare olika orakskodbeteenden på mobila skannrar? Om svaret är Ja kan du skapa fler menyalternativ och tilldela dem till olika personer.
- Ska orsakskoderna driva bokföring av ekonomiskt motkonto?

## <a name="turn-on-reason-code-features-in-your-system"></a>Aktivera funktioner för orsakskoder i systemet

Om du inte ser alla funktioner som beskrivs i denna artikel i systemet måste du troligen aktivera funktionen *Bokför lagerbehållningsjusteringar med konfigurerbara orsakskoder relaterade till motkonton*. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Warehouse management*
- **Funktionsnamn:** *Bokför behållningsjusteringar med konfigurerbara orsakskoder kopplade till motkonton*

## <a name="set-up-reason-codes"></a>Ställ in orsakskoder

### <a name="set-up-reason-code-policies"></a>Ställa in orsakskodprinciper

Du kan skapa flera policyer för orsakskoder för att styra när och hur inventeringsorsakskoder används. Varje orsakskodpolicy kan ha endera av två typer av inventeringsorsakskoder (*Valfri* eller *Obligatorisk*). Orsakskodprinciper för inventering kan användas på lagerställenivå eller artikelnivå.

Följ dessa steg för att skapa en orsakskodpolicy.

1. Gå till **Lagerhantering** \> **Konfiguration** \> **Lager** \> **Orsakskodpolicyer för inventering**.
1. I åtgärdsrutan väljer du **Ny** för att lägga till en policy i rutnätet.
1. Ställ in fältet **Namn** för den nya policyn.
1. På fältet **Typ av orsakskod för inventering** väljer du antingen *obligatorisk* eller *valfri* för att ange om valet av en orsakskod ska vara en valfri eller obligatorisk åtgärd på något av följande lagerjusteringsprocesser:

    - Rullande inventering (mobil enhet)
    - Punktinventering (mobil enhet)
    - Tröskelinventering (mobil enhet)
    - Justering in (mobil enhet)
    - Justering ut (mobil enhet)
    - Inventeringsjournal (rich-klient)
    - Kvantitetsjustering/Onlineinventing (avancerad klient)

Du kan konfigurera orsakskodpolicyer för både enskilda lagerställen och produkter. Inställning av orsakskod för en produkt kan ha företräde före inställningen för produktens lagerställe.

> [!NOTE]
> För lagerställen och artiklar med fältet **Orsakskodpolicy för inventering** inställt som *Obligatorisk* kan inventeringsjournalen inte slutföras och stängas förrän en orsakskod har angetts. Mer information finns i nästa avsnitt.

### <a name="assign-counting-reason-code-policies-to-warehouses"></a>Tilldela lagerställen orsakskodpolicyer för inventering

Följ dessa steg för att tilldela ett lagerställe en orsakskodpolicy för inventering.

1. Gå till **Lagerhantering** \> **Konfiguration** \> **Lagerindelning** \> **Lagerställen**.
1. Välj lagerställe i listrutan.
1. I åtgärdsfönstret, på fliken **Lagerställe**, i gruppen **Konfiguration**, väljer du **Orsakskodpolicy för inventering**. Följ sedan ett av följande steg i dialogrutan **Tilldela orsakskodpolicy för inventering**:

    - Om du vill använda policyinställningarna för alla artiklar för att fastställa om inventeringsjournaler är obligatoriska för dem anger du inget värde (eller raderar det befintliga värdet).
    - För att kräva orsakskod i inventeringsjournaler för lagerstället väljer du en orsakspolicy där fältet **Orsakskodtyp för inventering** är *Obligatorisk*.
    - Om orsakskod är valfri i inventeringsjournaler för lagerstället väljer du en orsakspolicy där fältet **Orsakskodtyp för inventering** är *Valfri*.

### <a name="assign-counting-reason-code-policies-to-products"></a>Tilldela produkter orsakskodpolicyer för inventering

Följ dessa steg för att tilldela en produkt en orsakskodpolicy för inventering.

1. Gå till **Produktinformationshantering** \> **Produkter** \> **Frisläppta produkter**.
1. I rutnätet väljer du en produkt.
1. I åtgärdsfönstret, på fliken **Produkt**, i gruppen **Konfiguration**, väljer du **Orsakskodpolicy för inventering**. Följ sedan ett av följande steg i dialogrutan **Tilldela orsakskodpolicy för inventering**:

    - Om du vill använda policyinställningarna för lagerstället för att fastställa om inventeringsjournaler är obligatoriska för produkten anger du inget värde (eller raderar det befintliga värdet).
    - För att kräva orsakskod i inventeringsjournaler för produkten väljer du en orsakspolicy där fältet **Orsakskodtyp för inventering** är *Obligatorisk*. Den här inställningen åsidosätter inställningen för varje orsakskod på lagernivå.
    - Om orsakskod är valfri i inventeringsjournaler för produkten väljer du en orsakspolicy där fältet **Orsakskodtyp för inventering** är *Valfri*. Den här inställningen åsidosätter inställningen för varje orsakskod på lagernivå.

### <a name="set-up-counting-reason-codes"></a>Konfigurera orsakskoder för inventering

Följ dessa steg för att konfigurera orsakskoder för inventering.

1. Gå till **Lagerhantering** \> **Inställning** \> **Lager** \> **Orsakskoder för inventering**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.
1. Ställ in fälten **Orsakskod för inventering** och **Beskrivning** för den nya raden.
1. Om du vill tilldela ett motkonto anger du eller väljer ett värde i fältet **Motkonto**.

    > [!NOTE]
    > Om ett motkonto tilldelats en orsakskod för inventering och du bokför en inventeringsjournal med den orsakskoden för inventering bokförs värdet mot det tilldelade motkontot i stället för standardkontot för inventeringsjournal i profilen.

### <a name="set-up-counting-reason-code-groups"></a><a name="reason-groups"></a>Ställa in orsakskodgrupper för inventering

*Grupper med orsakskoder för inventering* kan användas som en del av menyalternativen *Justering in* och *Justering ut* i mobilappen Warehouse Management för att begränsa listan med orsakskoder för inventering. (Mer information om orsakskodgrupper för inventering finns i avsittet [Konfigurera menyalternativ för mobila enheter för justering in och justering ut](#setup-adjustment-in-out) senare i denna artikel.)

1. Gå till **Lagerhantering** \> **Konfiguration** \> **Lager** \> **Orsakskodgrupper för inventering**.
1. I åtgärdsfönstret väljer du **Ny** för att lägga till en grupp.
1. Ställ in fälten **Orsaksgrupp för inventering** och **Gruppbeskrivning** för den nya gruppen.
1. Klicka på **Spara** i åtgärdsfönstret.
1. Öppna avsnittet **Information** och välj **Ny** i verktygsfältet för att lägga till en rad i rutnätet. Ställ sedan in fältet **Orsakskod för inventering** för den nya raden. 
1. Upprepa föregående steg för att vid behov tilldela fler koder. Om du måste ta bort en kod från gruppen markerar du den och väljer sedan **Radera** i verktygsfältet.

### <a name="set-up-reason-codes-for-mobile-device-menu-items"></a>Ställa in orsakskoder för menyalternativ för mobila enheter

Du kan konfigurera orsakskoder för följande justeringstyper för behållning:

- Rullande inventering
- Punktinventering
- Tröskelinventering
- Justering in
- Justering ut

I de flesta fall kan du definiera följande information för varje relevant menyalternativ för mobil enhet:

- Om orsakskoden visas till mobiltelefonarbetaren under inventering.
- Standardorsakskoden som visas på ett menyalternativ för mobila enheter.
- Om användaren kan redigera orsakskoden.

#### <a name="set-up-mobile-device-menu-items-for-a-counting-process"></a>Ställa in menyalternativ för mobila enheter för inventeringsprocess

Följ dessa steg för att konfigurera ett menyalternativ för mobila enheter för en inventeringsprocess.

1. Gå till **Lagerställehantering** \> **Inställningar** \> **Mobil enhet** \> **Menyalternativ för mobil enhet**.
1. Välj relevant menyalternativ i listrutan eller skapa ett nytt menyalternativ.
1. Välj **rullande inventering** i åtgärdsfönstret.
1. På fältet **Standard orsakskod för inventering** ställer du in standardorsakskoden som ska registreras när inventeringen görs med menyalternativet för mobil enhet.
1. I fältet **Visa orsakskod för inventering** väljer du ett av följande värden:

    - *Rad* – Visa orsakskoden efter att varje avvikelse har registrerats.
    - *Dölj* – Visa inte orsakskoden.

1. Ställ in **Redigera orsakskod för inventering** som *Ja* så att medarbetaren kan redigera orsakskoden när det visas på den mobila enheten under inventering. Ställ in på *Nej* om du vill förhindra att medarbetaren redigerar koden.

> [!NOTE]
> Knappen **rullande inventering** kan aktiveras på alla menyalternativ för mobil enhet när inventering kan göras. Exemplen inkluderar menyalternativ för punktinventeringar, användarstyrt arbete och systemstyrt arbete.

#### <a name="set-up-mobile-device-menu-items-for-adjustment-in-and-adjustment-out"></a><a name="setup-adjustment-in-out"></a>Ställ in menyalternativ för mobil enhet för justering in och justering ut

Följ dessa steg för att konfigurera ett menyalternativ för mobil enhet för justering in och justering ut.

1. Gå till **Lagerställehantering** \> **Inställningar** \> **Mobil enhet** \> **Menyalternativ för mobil enhet**.
1. I åtgärdsrutan väljer du **Ny** för att skapa ett menyalternativ.
1. Ställ in fälten för **Namn på mobilartikel** och **Rubrik** för det nya menyalternativet.
1. Ställ in fältet **Läge** på *Arbete*.
1. Ange alternativet **Använd befintligt arbete** till *Nej*.
1. I fältet **Process för att skapa arbete** väljer du *Justering in* eller *Justering ut*.
1. På snabbfliken **Allmänt** anger du följande fält. (Alla dessa fält läggs till när du väljer *Justering in* eller *Justering ut* i fältet **Process för att skapa arbete**.)

    - **Använd processguiden** – Om du skapar en process för *Justering ut* ska du se till att ange det här alternativet som *Ja*. Om du skapar en process för *Justering ut* ställs alltid det här alternativet in på *Ja*.
    - **Standard orsakskod för inventering** – Ställ in standardorsakskoden som ska registreras när inventeringen görs med menyalternativet för mobil enhet.
    - **Visa orsakskod för inventering** – Välj ett av följande värden:

        - *Rad* – Visa orsakskoden efter att varje avvikelse har registrerats.
        - *Dölj* – Visa inte orsakskoden.

    - **Redigera orsakskod för inventering** – Ställ in alternativet som *Ja* så att medarbetaren kan redigera orsakskoden när det visas på den mobila enheten under inventering. Ställ in på *Nej* om du vill förhindra att medarbetaren redigerar koden.
    - **Orsakskodgrupp för inventering** – Välj en orsakskodgrupp för att begränsa listan med alternativ som visas för medarbetare. Mer information om hur du konfigurerar orsakskodgrupper finns i avsnittet [Konfigurera orsakskodgrupper för inventering](#reason-groups) tidigare i denna artikel. 

> [!NOTE]
> När du tilldelar en orsakskodgrupp för inventering menyalternativen *Justering in* och *Justering ut* där alternativet **Använd processguide** är inställt på *Ja*, kan du få en begränsad lista över orsakskoderna för inventering som en del av bearbetningen i mobilappen Warehouse Management.
>
> Alternativet **Använd processguide** kan också förhindra att stora justeringskvantiteter sker av misstag. (Exempelvis kanske en medarbetare kråkar skanna en streckkod med ett artikelnummer istället för ett kvantitetsvärde.) För att konfigurera dessa funktioner ställer du in alternativet **Använd processguide** på *Ja* för varje relevant menyalternativ. Gå sedan till **Lagerställehantering \> Inställningar \> medarbetare** och ställ in fältet **Gräns för kvantitetsjustering** för varje relevant lagerställearbetare för att ange den maximala justeringskvantitet som medarbetaren kan registrera.

## <a name="processing-that-uses-counting-reason-codes"></a>Bearbetning som använder orsakskoder för inventering

När medarbetare använder mobilappen Warehouse Management registreras orsakskoderna. Om inte en godkännandeprocess för inventering har definierats används omedelbart de registrerade orsakskoderna som en del av bokföring av inventeringsjournalen som följer.

### <a name="cycle-count-approvals"></a>Godkännande av rullande inventering

Arbetaren kan ändra orsakskoden som är kopplad till inventeringen innan inventeringen kan godkännas. Orsakskoden anges på journalraderna som skapas när inventeringen godkänns.

#### <a name="modify-reason-codes-for-cycle-count-approvals"></a>Ändra orsakskoder för godkännanden av rullande inventering

Följ dessa steg för att ändra ett godkännande av rullande inventering.

1. Hå till **Lagerställehantering** \> **Rullande inventering** \> **Rullande inventeringsarbete som väntar på granskning**.
1. I rutnätet väljer du en rullande inventering.
1. I åtgärdsfönstret på fliken **Arbete** välj **Rullande inventering**. Sedan väljer du en ny orsakskod i fältet **Orsakskod**.

Orsakskoderna läggs till journalraderna i inventeringsjournaler av typen *inventeringsjournal*.

1. Gå till **Lagerhantering** \> **Journalposter** \> **Artikelinventering** \> **Inventering**.
2. I radinformationen i inventeringsjournalen väljer du den orsakskod som matchar den aktuella situationen i fältet **Orsakskod för inventering**.

### <a name="view-the-reason-codes-recorded-in-the-counting-history"></a>Visa registrerade orsakskoder i inventeringshistoriken

Följ de här stegen för att visa orsakskoderna som har registrerats i inventeringshistoriken.

1. Gå till **Lagerhantering** \> **Förfrågningar och rapporter** \> **Inventeringshistorik**.
1. Välj en artikelinventeringspost i listrutan.
1. I fältet **Orsakskod för inventering** visas inventeringshistoriken som har registrerats med orsakskod.

### <a name="use-reason-codes-for-quantity-adjustment-or-online-counting"></a>Använd orsakskoder för kvantitetsjustering eller onlineinventering

Följ de här stegen för att använda en orsakskod för kvantitetsjustering eller onlineinventering.

1. Gå till **Lagerhantering \> Förfrågningar och rapporter \> Behållningslista**.
1. Välj **Kvantitetsjustering** i åtgärdsrutan.
1. Välj **Kvantitetsjustering** och välj sedan orsakskod i fältet **Orsakskod för inventering**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
