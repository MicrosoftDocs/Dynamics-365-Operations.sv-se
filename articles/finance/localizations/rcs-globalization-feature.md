---
title: Regulatory Configuration Services (RCS) – Globaliseringsfunktioner
description: Det här ämnet förklarar hur du använder Microsoft Regulatory Configuration Services (RCS) och den globala databasen för att skapa och använda globaliseringsfunktioner.
author: JaneA07
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: b701e6bfa14ac30e02bfe79666963db4ee657302
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5002807"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a>Regulatory Configuration Services (RCS) – Globaliseringsfunktioner

[!include [banner](../includes/banner.md)]

Du kan använda Microsoft Regulatory Configuration Services (RCS) för att skapa en globaliseringsfunktion som kan användas globaliseringstjänsten, t.ex. en e-faktureringstjänst. Med RCS kan du utföra följande uppgifter:

- Definiera relaterade komponenter för en funktion.
- Hantera funktionens livscykel med hjälp av en funktions status.
- Göra en funktion tillgänglig för definierade miljöer.
- Dela en funktion med andra organisationer.

Följande procedurer förklarar hur en användare i RCS kan lägga till en globaliseringsfunktion och tillhörande komponenter, uppdatera funktionens status och göra funktionen tillgänglig så att den kan användas i globaliseringstjänster.

Innan du slutför procedurerna måste du utföra stegen som hör till följande uppgifter:

- Öppna en RCS-instans.
- Skapa och aktivera en konfigurationsleverantör. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

I Finance and Operations-appinstansen följer du stegen nedan.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. Om ingen RCS-miljö har etablerats för ditt företag väljer du **Regulatory services – konfiguration** och följer sedan instruktionerna för att etablera en.

> [!NOTE]
> Om en RCS-miljö redan har etablerats för ditt företag kan du använda sidans URL för att komma åt miljön genom att välja alternativet för inloggning.

## <a name="turn-on-the-globalization-features"></a>Aktivera globaliseringsfunktionerna

1. I din RCS-instans, välj panelen **funktionshantering**.
2. I arbetsytan **Funktionshantering** välj **Globaliseringfunktioner** i listan och sedan **Aktivera nu**.

    ![Globaliseringsfunktioner i funktionshantering](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a>Globaliseringsfunktioner

Om du vill använda en globaliseringsfunktion måste du först importera den från den globala databasen och skapa en egen version av den. Du kan lägga till globaliseringsfunktioner på två sätt:

- Lägga till en härledd funktion som baseras på en befintlig funktion som har publicerats eller delats.
- Lägg till en ny funktion som du skapat helt från början.

## <a name="access-globalization-features"></a>Få åtkomst till globaliseringsfunktioner

1. Se till att funktionen **globaliseringsfunktioner** är aktiverad i funktionshantering, enligt beskrivningen ovan.
2. Öppna arbetsytan **globaliseringsfunktioner** och under **funktioner**, välj panelen **e-fakturering**.

    ![Arbetsyta för globala funktioner](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    Sidan **e-faktureringsfunktioner** öppnas.

    ![Sidan e-faktureringsfunktioner](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a>Lägga till en härledd globaliseringsfunktion

Du kan lägga till en ny globaliseringsfunktion genom att härleda den från en befintlig funktion som har publicerats eller delats.

1. Välj **importera** om du vill öppna sidan **importfunktionen från den globala databasen**.

    ![Importera funktion från sidan Global databas](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. Välj **synkronisera** om du vill hämta de senaste funktionerna.

    I den synkroniserade listan finns funktioner som du kan välja mellan eftersom de publicerades av Microsoft eller att de har delats med dig av en annan konfigurationsleverantör.

    ![Synkroniserad lista över funktioner](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. Välj de funktioner du vill importera i listan och välj sedan **Importera**. Ett meddelande visas när de valda funktionerna har importerats utan problem.

    ![Meddelandet Import klar](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. Välj **Lägg till** och välj sedan alternativet **baserad på befintlig version i den nedrullningsbara dialogrutan**.
5. Ange ett namn och en beskrivning för funktionen.
6. Välj basversion för funktionen i listan med tillgängliga funktioner och välj sedan **skapa funktion**.

    ![Lägga till en härledd funktion](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    Funktionen som du har lagt till skapas och har statusen **utkast**.

    ![Härledd funktion med utkaststatus](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. Granska funktionskomponenterna och ta reda på om det behövs några uppdateringar:

    - Granska konfigurationerna om du skulle behöva anpassa formaten för elektronisk rapportering (ER) och deras bindningar med formatmappningar för funktionsversionen.
    - Granska inställningarna om du skulle behöva anpassa fliken **åtgärder**, fliken **tillämplighetsregler** eller fliken **variabler** för funktionsversionen.

8. På fliken **Versioner** väljer du ett datum för **Giltighet från** och anger en beskrivning om fältet **Beskrivning** är tomt.
9. Välj **ändra status** om du vill slutföra funktionen. Slutförda funktioner kan göras tillgängliga för en viss miljö så att de kan användas i globaliseringstjänster, och de kan också publiceras i den globala databasen.

> [!NOTE]
> Funktioner med värdet **funktionsversionstatus** för **publicerade** kan delas med externa organisationer.

## <a name="add-a-new-globalization-feature"></a>Lägga till en ny globaliseringsfunktion

Du kan lägga till en ny globaliseringsfunktion genom att skapa den från grunden.

1. På sidan **Importera funktion från global databas**, välj **Lägg till** och sedan i nedrullningsbar dialogruta väljer du alternativet **Ny funktion**.
2. Ange ett namn och en beskrivning för funktionen.
3. Välj **skapa funktion**.

    ![Lägga till en ny funktion](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. På fliken **versioner** välj ett **Giltighet från**-datum och sedan **Ändra status** för att slutföra funktionen. Slutförda funktioner kan göras tillgängliga för en viss miljö så att de kan användas i globaliseringstjänster, och de kan också publiceras i den globala databasen.

> [!NOTE]
> Funktioner med värdet **funktionsversionstatus** för **publicerade** kan delas med externa organisationer.

## <a name="feature-component-overview"></a>Översikt över funktionskomponent

Globaliseringsfunktioner har flera komponenter:

- **Version** – den här komponenten stöder funktionen livscykelhantering och låter användare hantera status för olika versioner av funktionen.
- **Konfigurationer** – med den här komponenten kan användarna hantera, visa och redigera tillhörande ER-format och formatmappningar.
- **Inställningar** – den här komponenten gör det möjligt för användare med globaliseringstjänster, t.ex. en e-faktureringstjänst, att hantera inställningen av den relaterade funktionsversionen. Därför stöder den flexibla uppföranden av kommunikations- och svarsregler.
- **Miljö** – med den här komponenten kan användare med globaliseringstjänster, t.ex. en e-faktureringstjänst, hantera miljön där funktionsversionsinställningarna används och bevilja behörighet till de användare som ska ha åtkomst till den.
- **Organisationer** – med den här komponenten kan användarna dela funktionen med externa organisationer.

## <a name="configuring-feature-components"></a>Konfigurera funktionskomponenter

### <a name="version-and-status"></a>Version och status

Versionen används för att hantera livscykeln för globaliseringsfunktioner.

Statusvärdet kan ändras i fältet **Status** på fliken **Version**. Följande statusvärden finns:

- **Utkast** – funktionen kan endast redigeras om den har denna status.
- **Slutförd** – funktionen och alla relaterade komponenter har slutförts och kan inte redigeras.
- **Publicerad** – funktionen och alla relaterade komponenter har publicerats i den globala databasen.
- **Delad** – funktionen och alla relaterade komponenter har delats med externa organisationer.
- **Aktiverad** – funktionen och alla relaterade komponenter har aktiverats för användning i en globaliseringstjänst, t.ex. en e-faktureringstjänst.

> [!NOTE]
> Funktionerna måste gå sekventiellt genom vissa av dessa statusvärden. Därför kan inte alla statusvärden vara tillgängliga i varje livscykelsteg.

### <a name="configurations"></a>Konfigurationer

Följande åtgärder är tillgängliga för konfigurationer:

- **Visa** – Visa de underliggande funktionskonfigurationerna som inte kräver någon uppdatering.
- **Redigera** – skapa en utkastversion av en vald konfiguration så att du kan redigera formatet eller format mappningen i formatdesignern.
- **Ta bort** – Tar bort en vald konfiguration från funktionen.
- **Basera om** – basera om funktionen. Mer information finns i avsnittet [BAsera om härledda globaliseringsfunktioner](#rebase) senare i det här avsnittet.

### <a name="setups"></a>Inställningar

Följande åtgärder är tillgängliga för framtida inställningar:

- **Lägg till** – skapa en ny funktionsinställning. Dessa funktionsinställning kan härledas från befintliga funktionsinställningar eller skapas från grunden.
- **Ta bort** – ta bort valda funktionsinställningar.
- **Visa** – Visa en underliggande funktionsinställning som inte kräver några ändringar.
- **Redigera** – skapa, ta bort eller ändra attributen för de tre huvudkomponenterna i en funktionsinställning:

    - Åtgärder och deras parametrar
    - Tillämplighetsregler
    - Variabler

![Inställningssida för funktionsversion](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a>Miljöer

Följande åtgärder är tillgängliga för miljöer:

- **Aktivera** – Välj en publicerad miljö under en vald funktionsversion och välj ett **Giltighet från**-datum då den ska vara tillgänglig. Mer information finns i avsnittet [Konfigurera miljöer för aktivering](#configureenvironment) senare i det här avsnittet.
- **Avbryt** – ta bort en miljö för en funktionsinställning.

### <a name="organizations"></a>Organisationer

Följ dessa steg om du vill dela en globaliseringsfunktion med en extern organisation.

1. På sidan **e-faktureringsfunktioner** väljer du funktionen och funktionsversionen som ska delas.
2. På sidan **Organisationer**, välj **Dela med** och ange sedan organisationens domännamn i den nedrullningsbara dialogrutan.
3. Välj **dela**.

    ![Dela en funktion med en organisation](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

Fuktionen delas med den valda organisationen och är tillgänglig för den organisationen i den globala databasen. Därifrån kan funktionen importeras till organisationens instans av RCS eller Dynamics 365 Finance så att den kan användas.

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a>Basera om härledda globaliseringsfunktioner

Du kan basera en härledd globaliseringsfunktion på ny eller uppdaterad basfunktionsversion. På så sätt kan ändringar som har gjorts i basversionen uppdateras automatiskt. Den uppdaterade basfunktionsversionen skapas av den ursprungliga konfigurationsprovidern och publiceras eller delas sedan.

![Uppdaterad basfunktionsversion](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

Om du till exempel vill basera om den härledda versionen av en funktion som du skapade, hämtar du först den senaste versionen av funktionen genom att importera den från den globala databasen.

1. På sidan **e-faktureringsfunktioner**, välj **Importera**.
2. Välj **synkronisera** om du vill hämta de senaste funktionerna.
3. Välj de funktioner du vill importera i listan över funktioner och välj sedan **Importera**.

    ![Importera den senaste versionen av en funktion](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. Välj den funktion som ska återbyggas i listan över funktioner.
5. På fliken **Version**, välj **Ny** för att skapa en utkastversion.

    ![Nytt utkastversion har skapats](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. Välj **Basera om**.
7. I dialogrutan **Basera om** väljer du den senaste versionen av funktionen som ska baseras om till.

    ![Dialogrutan Basera om](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. Välj **OK**.
9. Granska funktionskomponenter och gör nödvändiga ändringar.
10. Välj **ändra status** om du vill slutföra funktionen basera om. När ombaseringen är slutförd kan du utföra ytterligare åtgärder. Du kan till exempel publicera funktionen och göra den tillgänglig för användning i globaliseringstjänster.

    ![Funktionsstatus uppdaterades till slutfört](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a>Konfigurera miljöer för globaliseringsfunktioner

Användare av globaliseringstjänster kan hantera miljön för att ställa in en globaliseringsfunktion och bevilja behörighet till andra användare som kommer att ha åtkomst till den.

1. I arbetsytan **globaliseringsfunktioner** och under **Miljöer**, välj panelen **e-fakturering**.

    ![Arbetsyta för globaliseringsfunktioner](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. Välj **Parametrar för nyckelvalv** och välj sedan **Ny** för att skapa en Azure Key Vault-hemlighet.
3. Ange ett namn och en beskrivning för nyckelvalvet och ange sedan i fältet **URI för nyckelvalv**, ange den URL som identifierar nyckelvalvresursen i Azure.
4. På snabbfliken **Certifikat** väljer du **Lägg till** om du vill lägga till certifikatet och ange ett namn och en beskrivning för varje certifikat.

    ![Certifikat tillagt](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. Skapa en ny miljö genom att välja **Nytt**.
6. Ange ett namn, en beskrivning och hemligheten som krävs för signaturen för signaturen som krävs för lagringen.
7. På snabbfliken **Användare** väljer du **Ny** för att lägga till en användare som har behörighet att komma åt den här miljön.
8. Ange användarens användar-ID och e-postadress.
9. Upprepa steg 7 och 8 om du vill lägga till fler användare.
10. Välj **publicera** om du vill publicera miljön.

    ![Publicerad miljö](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)
