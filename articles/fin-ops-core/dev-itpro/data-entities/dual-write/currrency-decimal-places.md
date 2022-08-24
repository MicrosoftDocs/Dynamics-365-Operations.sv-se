---
title: Migrering av valutatyp för dubbelriktad skrivning
description: I den här artikeln beskrivs hur du ändrar antalet decimaler som stöds av dubbelriktad skrivning för valuta.
author: RamaKrishnamoorthy
ms.date: 12/08/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-04-06
ms.openlocfilehash: 327d6ced7fca4bdae1fd80928086dafed6b0f931
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289727"
---
# <a name="currency-data-type-migration-for-dual-write"></a>Migrering av valutatyp för dubbelriktad skrivning

[!include [banner](../../includes/banner.md)]



Du kan öka antalet decimaler som stöds för valutavärden till maximalt 10. Standardgränsen är fyra decimaler. Genom att öka antalet decimaler bidrar du till att undvika dataförlust när du använder dubbelriktad skrivning för att synkronisera data. Ökningen av antalet decimaler är att välja en ändring. Om du vill implementera den måste du begära hjälp från Microsoft.

Det finns två steg i processen att ändra antalet decimaler:

1. Begär migrering från Microsoft.
2. Ange antalet decimalplatser i Dataverse.

Appen för ekonomi och drift och Dataverse måste stödja samma antal decimaler i valutavärden. I annat fall kan det hända att data går förlorade när den här informationen synkroniseras mellan appar. Vid migreringsprocessen omkonfigureras det sätt på vilket valuta- och växelkursvärden lagras, men inga data ändras. När migreringen är slutförd kan antalet decimaler för valutakoder och priser ökas och de data som användarna anger och visar kan ha mer decimal precision.

Migrering är valfritt. Om du kan ha nytta av stödet för fler decimaler rekommenderar vi att du tar över migreringen. Organisationer som inte kräver värden med fler än fyra decimalplatser behöver inte migreras.

## <a name="requesting-migration-from-microsoft"></a>Begär migrering från Microsoft

Lagring för befintliga valuta kolumner i Dataverse kan inte hantera fler än fyra decimaler. Under migreringsprocessen kopieras därför valutavärden till nya interna kolumner i databasen. Den här processen sker kontinuerligt tills alla data har migrerats. Vid slutet av migreringen ersätter de nya lagringstyperna de gamla lagringstyperna, men datavärdena ändras inte. Valutakolumner kan sedan stödja upp till 10 decimaler. Under migreringsprocessen kan Dataverse fortfarande användas utan avbrott.

På samma gång ändras valutakurserna så att de stöder upp till 12 decimaler i stället för den aktuella gränsen på 10. Den här ändringen krävs för att antalet decimaler ska vara detsamma i både appen för ekonomi och drift och i Dataverse.

Migreringen ändrar inte några data. När du har konverterat kolumnerna valuta och valutakurs kan administratörer konfigurera systemet att använda upp till 10 decimaler för valutakolumner genom att ange antalet decimaler för varje transaktionsvaluta och för prissättning.

### <a name="request-a-migration"></a>Begär en migrering

Gör den här funktionen tillgänglig genom att använda e-post **CDSExpandDecimal@microsoft.com** och inkludera följande information:

+ **Ämne:** begäran om att aktivera expanderat decimalstöd för \<organizationID\>
+ **Brödtext:** Jag vill aktivera expanderat decimalstöd för min organisation \<organizationID\>.

En Microsoft-representant kommer att kontakta dig inom två till tre arbetsdagar under de kommande stegen.

När du begär en migrering bör du vara medveten om följande uppgifter och planera för dem i enlighet med detta:

+ Den tid som krävs för att migrera data beror på mängden data i systemet. Migrering av stora databaser kan ta flera dagar.
+ Databasens storlek ökar tillfälligt när migreringen körs, eftersom det krävs ytterligare utrymme för index. Större delen av det extra utrymmet frigörs när migreringen är slutförd.
+ Om fel uppstår under migreringsprocessen när migreringen inte kan slutföras, höjer systemet notifieringar till Microsoft-supporten så att supportpersonalen kan ingripa. Även om fel uppstår under migreringen förblir Dataverse helt tillgänglig för regelbunden användning.
+ Migreringsprocessen går inte att ångra.

## <a name="changing-the-number-of-decimal-places"></a>Ändra antalet decimaler

När migreringen har slutförts kan Dataverse lagra nummer med fler decimaler. Administratörer kan välja hur många decimaler som ska användas för särskilda valutakoder och för prissättning. Användare av Microsoft Power Apps, Power BI och Power Automate kan sedan visa och använda tal med fler decimaler.

Om du vill göra den här ändringen måste du uppdatera följande inställningar i Power Apps:

+ **Systeminställningar: valutaprecision för prissättning** – Kolumnen **ange valutaprecisionen som används för prissättning i hela system** anger hur valutan ska uppföras för organisationen när **Prissättningsprecision** är vald.
+ **Företagshantering: valutor** – Kolumnen **Valutaprecision** låter dig ange ett anpassat antal decimaler för en viss valuta. Det finns en återgång till inställningen för hela organisationen.

Det finns några begränsningar:

+ Du kan inte konfigurera valutakolumnen i en tabell.
+ Du kan bara ange fler än fyra decimaler på nivåerna för **Prissättning** och **Transaktionsvaluta**.

### <a name="system-settings-currency-precision-for-pricing"></a>Systeminställningar: valutaprecision för prissättning

När migreringen har slutförts kan administratörer ställa in valutaprecision. Gå till **Inställningar \> Administration** och välj **Systeminställningar**. På fliken **Allmänt** ändrar du värdet för kolumnen **Ange valuta precisionen som används för prissättning i hela system** som du ser i bilden nedan.

![Systeminställningar för valuta.](media/currency-system-settings.png)

### <a name="business-management-currencies"></a>Affärshantering: valutor

Om du kräver att valutaprecisionen för en viss valuta avviker från den valutaprecision som används för prissättningen kan du ändra den. Gå till **Inställningar \> Företagshantering**, välj **Valutor** och välj sedan vilken valuta du vill ändra. Ställ sedan in kolumnen **Valutaprecision** till önskat antal decimaler, som du ser i bilden nedan.

![Valutainställningar för en specifik plats.](media/specific-currency.png)

### <a name="tables-currency-column"></a>Tabeller: valutakolumn

Antalet decimaler som kan konfigureras för särskilda valutakolumner är begränsat till fyra.

### <a name="default-currency-decimal-precision"></a>Standardvalutan decimalprecision
Information om förväntat beteende för decimalprecision i standardvalutan under migrering och icke-migreringsscenarier finns i tabellen nedan. 

| Skapades den  | tabeller: decimalfält    | Befintlig organisation (valutafältet har inte migrerats) | Befintlig organisation (valutafältet har migrerats) | Ny org skapad post build 9.2.21062.00134 |
|---------------------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|------------------------------------------------|
| Valutafält som skapades innan 9.2.21111.00146  |     |  |       |
|    | Maximal precision som visas i användargränssnitt   | 4 siffror    | 10 siffror    | Inte tillämpligt    |
| | Maximal precision synlig i databas- och DB-frågeresultat-UI         | 4 siffror   | 10 siffror   | Inte tillämpligt    |
| Valutafält som skapades efter 9.2.21111.00146 |    |  |     |   |
|   | Maximal decimal precision som visas i användargränssnitt     | 4 siffror   | 10 siffror   | 10 siffror     |
|          | Maximal decimalprecision synlig i databas- och DB-frågeresultat-UI | 10 siffror. Endast 4 är signifikanta med alla nollor utöver de 4 decimalsiffrorna. På så sätt blir det enklare och snabbare att migrera en org, om det behövs. | 10 siffror      | 10 siffror     |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

