---
title: Schemalägg underhållsplaner
description: I det här avsnittet beskrivs schemaläggning av underhållsplaner i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9c215417eacb8a0e1ec0a8324fe35fc053089afb
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016916"
---
# <a name="schedule-maintenance-plans"></a>Schemalägg underhållsplaner

[!include [banner](../../includes/banner.md)]

 

Vid planering av förebyggande underhåll skapas kalenderposter på tillgångar utifrån underhållsplaner som angetts för tillgångarna. Du kan schemalägga kalenderposter baserat på valda underhållsplaner, tillgångstyper och tillgångar.

1. Klicka på **Tillgångshantering** > **Periodiskt** > **Förebyggande underhåll** > **Schemalägg underhållsplaner**.

2. Du kan välja ett tidsintervall i fälten **Period** och **Periodfrekvens**.

>[!NOTE]
>Fälten **Period** och **Periodfrekvens** anger hur långt fram i tiden du vill att underhållsschemarader ska skapas, baserat på de underhållsplaner som du har skapat (tidsbaserad eller räknarbaserad). I bilden nedan skapas rader för underhållsplaner (= arbetsorderförslag) från det aktuella datumet och tre månader framåt.

3. Välj "Ja" på växlingsknappen **Autoskapa om angivet på raden** om arbetsorder automatiskt ska skapas enligt underhållsplanraden.

>[!NOTE]
>Om den här växlingsknappen är inställd på "Ja" *och* kryssrutan **Autoskapa** också har markerats på underhållsplanrader i **Underhållsplaner**, skapas arbetsorder baserade på underhållsplanraderna, och underhållsschemarader med statusen "Arbetsorder skapad" skapas också. Om endast ett alternativ har valts (växlingsknappen **Autoskapa om angivet på raden** i den här dialogrutan eller kryssrutan **Autoskapa** i formuläret **Underhållsplaner**) skapas endast rader för underhållsplaner med status "Skapad". I så fall skapas inga arbetsorder.

4. Det går att generera kalenderposter baserat på underhållsplaner (tid eller räknare), tillgångar, tillgångstyper, funktionsplatser och funktionsplatstyper. Klicka på knappen **Filter** och gör dina val om det behövs.

- När det gäller tidsplanering av underhållsplaner på funktionsplatser: Om du uppdaterar inställningarna för tillgångstyper, tillverkare och modeller på underhållsplaner på snabbfliken **Alla funktionsplatser** > **Underhållsplaner** när du har planerat underhållsplaner, kommer befintliga underhållsschemaposter som är relaterade till funktionsplatsen att raderas automatiskt. Om du vill skapa nya kalenderposter, som motsvarar den uppdaterade underhållsplaninställningen på den funktionsplatsen, måste du köra ett nytt schema för underhållsplanen för den funktionsplatsen. Läs mer om inställningarna av tillgångstyper, tillverkare och modeller på funktionsplatser i [Skapa funktionsplatser](../functional-locations/create-functional-locations.md).

>*Exempel:* Du vill skapa en underhållsplan för en specifik funktionsplats, vilket innebär att alla tillgångar som ställs in på den funktionsplatsen vid en given tidpunkt inkluderas när du planerar underhållsplanen. I så fall skapar du en underhållsplan och väljer en viss funktionsplats, men du lägger INTE till några tillgångar i underhållsplanen. Resultatet blir att när du planerar underhållsplanen skapas underhållsschemarader för alla till gångar som är relaterade till funktionsplatsen vid den tidpunkten.

- Om du gör ändringar i tillgångstyper, tillverkare och modeller i **Tillgångstyper** påverkar dessa ändringar bara nya tillgångar som använder den uppdaterade tillgångstypen. Läs mer om inställning av tillgångstyp i [Tillgångstyper](../setup-for-objects/object-types.md).  

5. Klicka på **OK** för att påbörja genereringen av underhållsschemaposter för tillgångar. De genererade posterna visas på listsidan **Alla underhållsscheman**. Följande illustration visar ett exempel på dialogrutan **Schemalägg underhållsplaner**.

![Figur 1](media/09-preventive-maintenance.png)

- I dialogrutan **Schemalägg underhållsplaner** kan du ställa in batchjobb för snabbfliken **Kör i bakgrunden** för att automatiskt generera kalenderposter med jämna mellanrum.  
- När du planerar förebyggande underhåll skapas inte rader för underhållsplanering med förväntat startdatum och starttid före systemdatumet och systemtiden.  

Bilden nedan visar en grafisk illustration av en beräkning av tidsbaserad underhållsplan.  

![Figur 2](media/10-preventive-maintenance.jpg)

Beträffande räknarbaserade underhållsplaner: I bilderna nedan visas två olika cykler för räknarregistrering. De är baserade på en underhållsplan som ställts in för tillgång "V0001", vilket förväntar tillgången (en bil) att köra cirka 2 000 km varje månad.

I det första exemplet uppnås inte de förväntade 2 000 km varje månad. Enligt den räknarbaserade underhållsplanen är tröskelvärdet 2 000 km, vilket innebär att när du kör en planering av underhållsplan ska en underhållsschemarad skapas varje gång som tröskelvärdet 2 000 km uppnås. I exempel 1 finns 4 registreringsrader, men tröskelvärdet på 2 000 km uppnås bara en gång. Det innebär att när du kör schemaläggning av underhållsplaner för tillgången, till exempel för en period på tre månader, skapas bara underhållsschemarad.

I nästa bild registreras 2 000 km eller mer varje månad. Därför skapas tre underhållsrader om du schemalägger underhållsplaner för den här tillgången under en tremånadersperiod. 

I exemplen som beskrivs här visas att alla räknarregistreringar som görs på en tillgång visar en tendens som beskriver slitage på tillgången. Denna trend används som beräkningsbas vid tidsplanering av underhållsplanen.

![Figur 3](media/11-preventive-maintenance.png)

![Figur 4](media/12-preventive-maintenance.png)

