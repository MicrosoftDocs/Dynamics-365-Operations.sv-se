---
title: Konfigurera jobbkort för enheter
description: I det här avsnittet beskrivs olika alternativ för att konfigurera jobbkorts enheten.
author: johanhoffmann
manager: tfehr
ms.date: 05/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: fc698ac7e0cfc8d6b196abf35658688ad1bc8bc7
ms.sourcegitcommit: 6319a07ee6c36ebb28acaf205bc79d2fd8f7dd5d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/30/2020
ms.locfileid: "3413180"
---
# <a name="configure-job-card-for-devices"></a>Konfigurera jobbkort för enheter

[!include [banner](../includes/banner.md)]

Jobb korts enheten används av medarbetarna i butiken för att registrera sitt dagliga arbete, till exempel när jobb startas, rapportering av återrapportering om jobb, registrering av indirekta aktiviteter och frånvarorapportering. Dessa registreringar är grunden för spårning av framsteg och kostnader på tillverkningsorder och för beräkning av grunden för arbetares lön. I det här avsnittet beskrivs olika alternativ för att konfigurera jobbkorts enheten.

## <a name="enable-new-features-in-feature-management"></a>Aktivera nya funktioner i funktionshantering

Några av de inställningar som beskrivs i det här avsnittet måste vara aktiverade på ditt system innan de blir tillgängliga för dig. Använd [sidan funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) om du vill aktivera någon av eller alla följande funktioner efter behov.

### <a name="generate-license-plate"></a>Generera registreringsskylt

Om du vill göra den här funktionen tillgänglig aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (i ordning):

1. ID-nummer för rapportering som färdig har lagts till på jobbkortenheten
1. Aktivera automatisk generering av ID-nummer när rapportering slutförts i jobbkortenheten

### <a name="print-label"></a>Skriv ut etikett

Om du vill göra den här funktionen tillgänglig aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (i ordning):

1. ID-nummer för rapportering som färdig har lagts till på jobbkortenheten
1. Skriv ut etikett från jobbkortenhet

### <a name="allow-locking-of-touch-screen"></a>Tillåt låsning av pekskärm

Om du vill göra den här funktionen tillgänglig aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- (Förhandsversion) Funktion för att låsa jobbkortsenhet och jobbkortsterminal för att anpassas till språk

## <a name="manage-your-device-configurations"></a>Hantera en enhetskonfigurationer

Gå till om du vill ställa in dina enhetskonfigurationer **Produktionskontroll > Inställningar > Tillverkningskörning > Konfigurera jobbkort för enheter**. Sidan **Konfigurera jobbkort för enheter** öppnas, som visar en lista med befintliga konfigurationer. Härifrån kan du göra följande: 

- Välj en enhetskonfiguration som visas i den vänstra kolumnen om du vill visa och redigera den.
- Välj **ny** i åtgärdsfönstret om du vill lägga till en ny enhetskonfiguration i listan. Ange sedan ett namn i fältet **Konfiguration** för att identifiera den nya konfigurationen. Värdet som du anger här måste vara unikt bland alla enhetskonfigurationer och du kan inte redigera det senare.

I följande avsnitt finns mer information om var och en av inställningarna för konfiguration av jobbkortsenheter.

## <a name="general-settings"></a>Allmänna inställningar

På snabbfliken **Allmänt** kan du konfigurera var och en av de olika alternativen som är tillgängliga för den valda enhetskonfigurationen. Följande inställningar är tillgängliga:

- **Rapportera kvantitet vid utstämpling** – Ange detta till **Ja** för att be arbetare att rapportera återrapportering om pågående jobb när han eller hon stämplar ut. Om det anges till **Nej** kommer medarbetarna inte att uppmanas.
- **Lås medarbetare** – när det här alternativet är inställt på **Nej** loggas varje medarbetare ut omedelbart efter att de har gjort en registrering (t.ex. ett nytt jobb) och sedan kommer enheten att gå tillbaka till inloggningssidan. När det här alternativet är inställt på **Ja** kommer varje medarbetare att vara inloggad på jobbkortsenheten. Arbetaren kan dock fortfarande logga ut manuellt så att en annan arbetare kan logga in medan jobbkortsenheten fortfarande körs under samma systemanvändarkonto. Mer information om dessa typer av konton finns i [Tilldela användare](#assigned-users).
- **Streckkodsskanner** – Ställ in detta på **Ja** för att ange ett alternativ på jobbkortsenheten som tillåter arbetare att registrera starten för ett nytt jobb genom att skanna en streckkod.
- **Använd den faktiska tiden för registrering** – Ställ in detta på **Ja** för att ställa in tiden för varje ny registrering som ska vara lika med den exakta tidpunkten som registreringen lämnades in av en arbetare. Ställ in på **Nej** om du vill använda inloggningstiden i stället. Du vill vanligtvis ange värdet **Ja** om du har aktiverat alternativen **Lås medarbetare** och/eller **enskild arbetare**, där arbetstagarna ofta förblir inloggade under längre perioder.
- **En arbetare** – Ställ in det här alternativet på **Ja** om bara en av dem använder varje jobbkortsenhet där denna konfiguration är aktiv. När det här alternativet är markerat sätts alternativet **Lås medarbetare** automatiskt till **Ja**. Dessutom tar det här alternativet bort kravet (och möjligheten) för arbetaren att logga in med hjälp av ID-bricka (eller liknande). Istället loggar medarbetaren in på Supply Chain Management med ett systemanvändarkonto kopplat till *tidsregistrerad arbetare* (från tabellen *arbetare*) och inloggas på jobbkortsenheten samtidigt som medarbetaren.  Mer information om dessa typer av konton finns i [Tilldela användare](#assigned-users).
- **Tillåt arbetare att ställa in personliga filter** – Ange det här alternativet till **Ja** för att låta medarbetarna filtrera de jobb som visas för dem på enheten. Arbetaren kan ändra värden för något av de tre filterkriterierna: **produktionsenhet**, **resursgrupp** och **resurs**. Endast jobb som har planerats på resurser som matchar det valda filterkriteriet visas på enheten. Du kan också tilldela standardvärden för ett eller alla dessa kriterier, och de gäller även om det här alternativet inte är markerat.
- **Tillåt låsning av pekskärm** – Ange detta alternativ till **Ja** medarbetare ska kunna låsa jobbkortsenheten pekskärm så att de kan sanera den. När det här alternativet är aktiverat läggs en knapp för **Lås skärm för den omorganisering** till på sidan för enhetsinloggning. När en medarbetare väljer den här knappen, låser sig pekskärmen tillfälligt för att förhindra indata och en nedräkningstimer visas. Arbetaren kan nu rensa enheten och skärmen på ett säkert sätt. När nedräkningen är klar låses pekskärmen om automatiskt.
- **Tidslängd för skärmlåsning** – När alternativet **Tillåt låsning pekskärm** är aktiverad, använd detta alternativ för att ange antal sekunder som pekskärmen ska vara låst för omorganisering. Längden måste vara mellan 5 och 120 sekunder.
- **Produktionsenhet** – Välj en produktionsenhet som ska användas som standardfilterkriterium för listan över jobb som visas för varje arbetare. Endast jobb som har planerats på resurser grupperade under den valda produktionsenheten kommer från början att visas av enheten. Om alternativet **Tillåt arbetare att ställa in personliga filter** är aktiverat kan arbetarna redigera det här värdet, annars gäller detta filter alltid när enhetskonfigurationen är aktiv.
- **Resursgrupp** – Välj en resursgrupp som ska användas som standardfilterkriterium för listan över jobb som visas för varje arbetare. Endast jobb som har planerats på resurser grupperade under den valda resursgruppen kommer från början att visas av enheten. Om alternativet **Tillåt arbetare att ställa in personliga filter** är aktiverat kan arbetarna redigera det här värdet, annars gäller detta filter alltid när enhetskonfigurationen är aktiv.
- **Resurs** – Välj en resurs som ska användas som standardfilterkriterium för listan över jobb som visas för varje arbetare. Endast jobb som har planerats på valda resurser kommer från början att visas av enheten. Om alternativet **Tillåt arbetare att ställa in personliga filter** är aktiverat kan arbetarna redigera det här värdet, annars gäller detta filter alltid när enhetskonfigurationen är aktiv.
- **Generera ID-nummer** – Ange det här alternativet **Ja** om du vill generera ett nytt ID-nummer varje gång en medarbetare använder jobbkortsenheten för att rapportera som färdig. ID-numret genereras från en nummerserie som ställs in på sidan **parametrar för lagerstyrning**. Om **Nej** måste arbetare ange ett befintligt ID-nummer när den rapporteras som färdig.
- **Skriv ut etikett** – Ställ in det här alternativet på **Ja** om du vill skriva ut ett ID-nummer när en medarbetare använder en jobbkortsenhet för att rapportera som färdig. Konfigurationen av etiketten ställs in i dokumentflödet som beskrivs i [Layout på dokumentflödet för ID-nummeretiketter](../warehousing/document-routing-layout-for-license-plates.md).

<a name="assigned-users"></a>

## <a name="assigned-users"></a>Tilldelade användare

Använd snabbfliken **tilldelade användare** om du vill koppla en eller flera systemanvändare till den aktuella enhetskonfigurationen. Varje systemanvändare kan bara tilldelas en jobbenhetskonfiguration.

När en enhet konfigureras brukar en IT-anställd normalt logga in på Supply Chain Management med hjälp av ett systemanvändarkonto. Därefter gäller jobbenhetskonfigurationen som är kopplad till den systemanvändaren så länge som system användaren förblir inloggad. Dessa systemanvändarkonton är vanligtvis begränsade för att bara tillåta åtkomst på sidan med jobbkortsenheten och ingen annan del av Supply Chain Management.

När systemanvändaren är inloggad och jobbenhetskonfigurationen har lästs in, kan personalen logga in på jobbkortsenheten med hjälp av ett *konto för registrering av arbetstid* (t.ex. genom att skanna in en streckkod på deras bricka) så att de kan starta nya jobb och göra andra typer av registreringar. Olika arbetare kan logga in och ut under dagen, medan samma enhets konfiguration fortfarande används på den datorn eftersom systemanvändaren fortfarande är inloggad i Supply Chain Management för dagen.

Som tidigare nämnts, när du använder en enhetskonfiguration med alternativet **En arbetare** loggar användarna vanligtvis in själva i Supply Chain Management med en systemanvändare kopplad till deras eget konto för *tidsregistrerad arbetare* så att de läser in enhetskonfiguration och loggar in som arbetare på jobbkortsenheten samtidigt.

## <a name="additional-resources"></a>Ytterligare resurser

[Rapportera som färdigt från jobbkortsenheten](report-finished-job-device.md)
