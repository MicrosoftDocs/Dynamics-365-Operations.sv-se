---
title: Konfigurationsnycklar och datatabeller
description: Det här avsnittet beskriver förhållandet mellan konfigurationsnycklar och datatabeller.
author: Sunil-Garg
ms.date: 05/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: 25341
ms.assetid: 8e214c95-616b-4ee1-b5a4-fa5ce5147f2c
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: a9e5204c2bb9c0a58b2e4e223a4a3d2d09d53659
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356273"
---
# <a name="configuration-keys-and-data-entities"></a>Konfigurationsnycklar och datatabeller

[!include [banner](../includes/banner.md)]

Innan du använder datatabeller för att importera och exportera data bör du först fastställa vilken inverkan konfigurationsnycklarna kommer att ha på de datatabeller som du planerar att använda .

Mer information om konfigurationsnycklar finns i [rapporten för licenskoder och konfigurationsnycklar](../sysadmin/license-codes-configuration-keys-report.md).

### <a name="configuration-key-assignments"></a>Tilldelningar för konfigurationsnyckel
Konfigurationsnycklar kan tilldelas till en eller flera av följande artefakter.

- Datatabeller
- Register använda som datakälla
- Registerfält
- Fält i datatabell

I följande tabell sammanfattas hur konfigurationsvärden påverkar olika artefakter som ligger bakom ett objekt och ändrar objektets förväntade beteende.

| Inställning för konfigurationsnyckel i datatabell | Inställning för konfigurationsnyckel i register | Inställning för konfigurationsnyckel i registerfält | Inställning för konfigurationsnyckel i datatabellsfält | Förväntat beteende |
|-----------------------------------------|------------------------------------|------------------------------------------|----------------------------------------|------------------|
| Bortkopplat                                | Inte utvärderad                      | Inte utvärderad                            | Inte utvärderad                          | Om konfigurationsnyckeln för datatabellen inaktiveras fungerar inte datatabellen. Det spelar ingen roll om konfigurationsnycklar i underliggande tabeller och fält är aktiverade eller inaktiverade. |
| Aktiverad                                 | Bortkopplat                           | Inte utvärderad                            | Inte utvärderad                          | Om konfigurationsnyckeln för datatabellen är aktiverad kontrollerar ramverket för datahantering konfigurationsnyckeln för var och en av de underliggande tabellerna. Om konfigurationsnyckeln för ett register är inaktiverad kan registret inte användas i datatabellen. Om konfigurationsnyckeln för ett register inaktiveras utvärderas inte konfigurationsinställningarna för register- och datatabeller. Om det primära registret i enheten har en inaktiverad konfigurationsnyckel hanterar systemet enheten som om konfigurationsnyckeln inaktiverats. |
| Aktiverad                                 | Aktiverad                            | Bortkopplat                                 | Inte utvärderad                          | Om konfigurationsnyckeln för datatabellen är aktiverad och de underliggande tabellernas konfigurationsnycklar aktiveras, kontrollerar ramverket för datahantering konfigurationsnyckeln mot fälten i tabellerna. Om konfigurationsnyckeln för ett fält är inaktiverad blir fältet inte tillgängligt för funktionell användning i datatabellen även om motsvarande fält i datatabellen har konfigurationsnyckeln aktiverad. |
| Aktiverad                                 | Aktiverad                            | Aktiverad                                  | Bortkopplat                               | Om konfigurationsnyckeln är aktiverad på alla andra nivåer, men enhetsfältets konfigurationsnyckel är inaktiverad blir fältet inte tillgängligt för användning i datatabellen. |

> [!NOTE]
> Om en enhet har en annan enhet som datakälla tillämpas semantiken ovan på ett rekursivt sätt.

### <a name="entity-list-refresh"></a>Uppdatering av enhetslista
När entitetslistan uppdateras bygger ramverket för datahantering konfigurationsnyckelns metadata för körning. Dessa metadata byggs med logiken som beskrivs ovan. Vi rekommenderar att du väntar tills enhetslistans uppdatering är färdig innan du använder jobb och enheter i ramverket för datahantering. Om du inte väntar kan konfigurationsnyckelns metadata vara felaktiga och leda till oväntade resultat. När enhetslistan uppdateras visas följande meddelande på enhetslistans sida.

![Uppdatering av entitetslista.](./media/Entity_refresh_list.png)

### <a name="data-entity-list-page"></a>Listsida för datatabell
I arbetsytan för datahantering visar listsidan för datatabellen inställningar för enheternas konfigurationsnycklar. Starta på den här sidan för att förstå effekten av konfigurationsnycklar för datatabellen.

Denna information visas med metadata som skapats under uppdateringen av enheten. Kolumnen för konfigurationsnyckel visar namnet på den konfigurationsnyckel som är associerad med datatabellen. Om den här kolumnen är tom innebär det att det inte finns någon konfigurationsnyckel som associeras med datatabellen. Statuskolumnen visar status för konfigurationsnyckeln. Om den har en markering innebär det att nyckeln är aktiverad. Om den är tom innebär det antingen att nyckeln är inaktiverad eller att ingen nyckel är associerad.

![Listsida för entitet.](./media/Data_entity_list_page.png)

### <a name="target-fields"></a>Målfält
Nästa steg är att gå djupare i datatabellen för att se effekten av konfigurationsnycklar på register och fält. Formuläret för målfält i en datatabell visar konfigurationsnyckeln och dess statusinformation för de relaterade registren och fälten i datatabellerna. Om datatabellen har en inaktiverad konfigurationsnyckel visas ett varningsmeddelande om att register och fält i formuläret för målfält inte är tillgängliga för enheten oavsett status på konfigurationsnyckeln.

![Målfält.](./media/Target_fields_1.png)

### <a name="child-entities"></a>Underordnade enheter 
Vissa enheter har andra enheter som datakällor eller är sammansatta datatabeller: information om konfigurationsnyckel för dessa enheter visas i formuläret underordnade enheter. Använd det här formuläret på liknande sätt som enhetens listsida som beskrivs ovan. Formuläret för målfält för underordnade enheter fungerar enligt beskrivningen ovan.

![Målfält.](./media/Target_fields_2.png)

### <a name="using-data-entities"></a>Att använda datatabeller
När du förstår den fulla inverkan, om någon, av konfigurationsnycklar i de datatabeller som du vill använda kan du nu fortsätta med att använda datatabellerna genom att lägga till dem i dataprojekt. 

### <a name="run-time-validations-for-configuration-keys"></a>Valideringar av körtid för konfigurationsnycklar
Genom att använda de metadata för konfigurationsnycklar som skapas under enhetens uppdatering utförs valideringar av körtid i följande fall.

- När en datatabell läggs till ett jobb
- När användaren klickar på 'Validera' i enhetslistan
- När användaren läser in ett datapaket i ett dataprojekt
- När användaren läser in en mall i ett dataprojekt
- När ett befintligt dataprojekt data läses in
- När en mall läses in i ett dataprojekt
- Innan export/importjobbet körs (batch, icke-batch, återkommande, OData)
- När användaren skapar en mappning
- När användaren mappar fälten i användargränssnittets mappning
- När användaren endast lägger till 'fält som kan importeras'

### <a name="managing-configuration-key-changes"></a>Hantera ändringar av konfigurationsnycklar
När du uppdaterar konfigurationsnycklar i enheten, på register- eller fältnivå, måste enhetslistan i ramverket för datahantering uppdateras. Proceduren säkerställer att ramverket hämtar de senaste inställningarna för konfigurationsnycklar. Tills enhetslistan uppdateras visas följande varningsmeddelande på enhetslistans sida. De uppdaterade ändringarna för konfigurationsnycklar börjar gälla omedelbart efter att enhetslistan uppdateras. Vi rekommenderar att du validerar befintliga dataprojekt och jobb för att säkerställa att de fungerar som förväntat efter att ändringarna av konfigurationsnycklar har börjar gälla.

![Målfält.](./media/Target_fields_3.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]