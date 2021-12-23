---
title: Användarinställningar för mobil enhet
description: I det här avsnittet beskrivs hur du hanterar inställningar för mobila enheter för lagerarbetare.
author: Mirzaab
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppDeviceBrand,WHSMobileAppUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 13c99854224a6d220e73a43636d85ec1951f8149
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2021
ms.locfileid: "7901906"
---
# <a name="mobile-device-user-settings"></a>Användarinställningar för mobil enhet

[!include [banner](../../includes/banner.md)]

Det nya mobilappen för distributionslagerhantering har en uppsättning appspecifika inställningar som gör det skräddarsyr användarupplevelsen. Eftersom programmet kan användas på enheter av olika skärmstorlek och -konfigurationer (till exempel surfplatta, telefon eller armhållen), kan det vara praktiskt att centralt hantera inställningarna från Microsoft Dynamics 365 Supply Chain Management.

Med hjälp av *användarinställningarna för den mobila enheten* kan du definiera globala användarinställningar som ska användas på alla enheter. Du kan också definiera mer fininställningar för enskilda enhetsmärken, enhetsmodeller och/eller arbetare. När en arbetare loggar in på mobilappen för distributionslagerhantering hämtar programmet och tillämpar den mest specifika inställningsprofilen som lagras i Supply Chain Management för matchande märke, enhet och/eller användar-ID.

Den här funktionen kan hjälpa arbetare att komma igång snabbare när de börjar använda en ny enhet. Nedan följer några exempel:

- Administratörer kan skapa standardinställningar som fungerar bäst för enheter från en viss tillverkare och/eller för specifika enhetsmodeller. Därför kan arbetare komma igång med en ny enhet utan att nödvändigtvis behöva ändra inställningarna.
- Om ditt företag har en pool med identiska enheter som delas bland arbetare, kommer medarbetarna att se de inställningar de föredrar varje gång de loggar in, även om de aldrig har använt den specifika fysiska enhet som de valde en viss dag.
- I Supply Chain Management kan administratörer visa och redigera alla lagrade inställningar, även för enskilda arbetare. Med den här kapaciteten kan de felsöka eller finjustera nya funktioner.

> [!IMPORTANT]
> Funktionen för *användarinställningar för mobila enheter* gäller endast det nya mobilappen för distributionslagerhantering. Det fungerar inte med det gamla lagerställeprogrammet.

## <a name="turn-on-the-mobile-device-user-settings-feature"></a>Aktivera funktionen för användarinställningar för mobila enheter

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Warehouse management*
- **Funktionsnamn:** *användarinställningar, ikoner och stegrubriker för den nya distributionslagerappen*

## <a name="create-and-manage-user-settings"></a>Skapa och hantera användarinställningar

Använd sidan **Användarinställningar för den mobila enheten** till att skapa, visa och hantera inställningar på alla nivån för fininställningar. Första gången en arbetare redigerar användarinställningarna på en ny enhet läggs en ny profil automatiskt till på den här sidan om den inte redan finns. Den profilen uppdateras sedan varje gång arbetaren gör en ändring.

Du kan också definiera en inställningsprofil som gäller alla enhetsmärken, enhetsmodeller och/eller arbetare. Du kan sedan öka fininställningarna genom att använda mer specifika inställningar för enskilda märken, modeller och/eller arbetare.

Följ dessa steg om du vill skapa och hantera användarinställningar för dina mobila enheter.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Användarinställningar för mobil enhet**.
1. Välj en befintlig användarinställningsprofil i listfönstret för att öppna posten. Du kan också välja **Ny** i åtgärdsfönstret om du vill skapa en ny profil.

    Varje profil i listfönstret har en etikett som anger det märke, den modell och/eller det användar-ID som profilen gäller för. Mer allmänna profiler har värdet *Alla* för vissa eller alla av dessa egenskaper.

1. Ställ in följande fält i rubrikavsnittet för posten för den nya eller valda inställningsprofilen:

    - **Enhetsmärkesnamn** – Välj det enhetsmärkesnamn som profilen ska gälla för. Lämna det här fältet tomt om profilen ska gälla för alla märken. Listan med värden omfattar alla märken som har definierats i systemet. Information om hur du definierar listan med märken finns i nästa avsnitt.
    - **Enhetsmodell-ID** – Välj det enhetsmodell som profilen ska gälla för. Om profilen ska gälla för alla modeller av det valda varumärket, lämna det här fältet tomt. Listan med värden omfattar alla modeller som har definierats för det märke som är valt i fältet **Enhetsmärkenamn**. Information om hur du definierar listan med modeller för varje märke finns i nästa avsnitt.
    - **Användar-ID** – Välj användar-ID för lagerarbetaren som inställningsprofilen ska gälla för. Lämna det här fältet tomt om profilen ska gälla för alla arbetare.

1. På snabbfliken **Allmänt** ange följande fält:

    - **Knapposition** – Välj hur knappar ska positioneras på enheten. Elementen i programmet flyttas så att de passar bättre för arbetarens inställning ellerordning. Alternativen är *nederst till höger (standard)*, *längst ned till*, *överst till höger* och *överst till vänster*.
    - **Visa orientering** – Välj den visningsorientering som ska användas som standard i programmet.
    - **Skanna med kamera** – Ställ in det här alternativet till *Ja* för att använda enhetens kamera för att skanna inmatningsfält där önskat inmatningsläge är inställt på *Skanning*. Om enheten har en inbyggd skanner ställer du in det här alternativet på *Nej*, men inte för skannern.
    - **Visa produktbild** – Välj om produktbilder ska visas om de är tillgängliga för den frisläppta produkten. Mer information om hur du lägger till produktbilder finns i [Lägga till en bild i en produkt](../pim/tasks/add-image-product.md).
    - **Visa färgtema** – Välj ett färgtema för enheten.
    - **Säkerhetsnivå** – Välj enhetens säkerhetsnivå. Välj ett värde mellan 0 (noll) och 10. Värdet *0* representerar inget ljud och värdet *10* representerar maximal volym. Standardvärdet är *4*.
    - **Vibrationsnivå** – Välj enhetens vibrationsnivå. Välj ett värde mellan 0 (noll) och 5. Värdet *0* representerar ingen vibration och värdet *5* representerar maximal vibration. Standardvärdet är *1*.
    - **Skalprocent för texten** – Ange textstorleken som en procentandel av standardstorleken. Ange ett värde mellan 70 och 400. Värdet *70* motsvarar den minsta textskalan och värdet *400* motsvarar den största textskalan. Standardvärdet är *100*.
    - **Skalprocent för knappen** – Ange knappstorleken som en procentandel av standardstorleken. Ange ett värde mellan 50 och 200. Värdet *50* motsvarar den minsta knappskalan och värdet *200* motsvarar den största knappskalan. Standardvärdet är *100*.

## <a name="create-and-manage-mobile-device-brands"></a>Skapa och hantera märken på mobila enheter

Använd sidan **Märken för mobila enheter** om du vill visa, skapa och hantera enhetsmärken och modeller som kan användas med dina inställningsprofiler. Mobilappen hämtar och skickar automatiskt det lokala varumärket och modell-ID första gången en arbetare redigerar sina inställningar på en viss enhet. Därför genereras de flesta av dessa poster vanligen automatiskt. Du kan dock också hantera alla poster på den här sidan. Du kan till exempel ge varje märke och modell mer användbara beskrivningar som kan hjälpa till att skilja på liknande eller kryptiska modell-ID:n.

Följ dessa steg för att skapa och hantera dina varumärken och modeller för mobila enheter.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Märken för mobila enheter**.
1. I listfönstret väljer du ett varumärke för mobilenheter för att öppna posten. Du kan också välja **Ny** i åtgärdsfönstret om du vill skapa ett nytt märke.
1. Ställ in följande fält i rubrikavsnittet för posten för den nya eller valda enhetens märke:

    - **Enhetens märkesnamn** – Enhetens märkesnamn, t.ex. *Microsoft Corporation*.
    - **Beskrivning** – Du kan ange en beskrivning för att skilja på varumärken.

1. På snabbflikarna **Modeller för mobila enheter** visas alla modeller för det valda enhetsmärke. Använd knapparna i verktygsfältet för att lägga till rader i rutnätet eller ta bort rader. Ange följande fält för varje rad:

    - **Enhetsmodell-ID** – Enhetsmodell-ID, t.ex. *Surface Book 2*.
    - **Beskrivning** – Du kan ange en beskrivning för att skilja på modell-ID.

## <a name="additional-resources"></a>Ytterligare resurser

- [Installera och ansluta mobilappen för distributionslagerhantering](install-configure-warehouse-management-app.md)
- [Tilldela stegikoner och titlar för mobilappen för Warehouse Management](step-icons-titles.md)