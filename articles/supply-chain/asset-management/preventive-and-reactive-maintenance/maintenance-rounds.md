---
title: Underhållsomgångar
description: I det här avsnittet beskrivs underhållsomgångar i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRoundTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 63cb2614b2037fac1129c7d2f82a26dac41a3490
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437702"
---
# <a name="maintenance-rounds"></a>Underhållsomgångar

[!include [banner](../../includes/banner.md)]

 

In **Tillgångshantering** kan du skapa underhållsomgångar för olika tillgångar, där du måste utföra en liknande uppgift med jämna mellanrum. Exempelvis smörjmedelsjobb eller säkerhetsinspektionsjobb som måste utföras på ett antal maskiner inom samma intervall. Första steget är att skapa en underhållsomgång, inklusive tillgångar som kräver samma typ av underhållsjobb. Därefter schemalägger du underhållsomgångarna. När du har avslutat schemat för underhållsomgångar kan du se alla jobbposter som är relaterade till omgången i **Alla underhållsscheman** och **Öppna rader för underhållsschema**.

>[!NOTE]
>Underhållsomgångar kan också ställas in på de funktionsplatser som ska slutföras på de tillgångar som är installerade på funktionsplatsen vid tidpunkten för skapandet av den omgångsbaserade arbetsordern. I [Skapa funktionsplatser](../functional-locations/create-functional-locations.md) finns mer information om inställningen av underhållsomgångar och funktionsplatser.

## <a name="set-up-a-maintenance-round"></a>Ställa in en underhållsomgång

1. Klicka på **Tillgångshantering** > **Inställning** > **Förebyggande underhåll** > **Underhållsomgångar**.

2. Klicka på **Nytt** om du vill skapa en ny underhållsomgång.

3. Infoga ett ID i fältet **Underhållsomgång** och ett namn på det underhållsomgången i fältet **Namn**.

4. Välj ett startdatum för omgången i fältet **Startdatum**.

5. I fälten **Slutför inom dagar** och **Slutför inom timmar** kan du infoga förväntat slutdatum i dagar eller timmar. Det förväntade slutdatumet beräknas i förhållande till startdatumet, som beräknas när underhållsschemarader skapas. Du kan till exempel infoga "7" i fältet **Slutför inom dagar** för att ange att det relaterade jobbet ska slutföras inom en vecka från startdatumet.

6. Välj "Ja" på växlingsknappen **Autoskapa** om arbetsorder automatiskt ska skapas från rader för underhållsschemarader som skapas från den här underhållsomgången.

7. I fältet **Arbetsordertyp** väljer du den arbetsordertyp som ska användas på arbetsorder som skapas från den här underhållsomgången.

8. I fältet **Servicenivå** väljer du den servicenivå för arbetsorder som ska användas på arbetsorder som skapas från den här underhållsomgången.

9. På snabbfliken **Tillgångsrader**, klicka på **Lägg till** för att lägga till en tillgång i underhållsomgången.

10. Ett radnummer anges automatiskt i fältet **Radnummer** för att visa ordningsföljden på tillgångarna i underhållsomgången.

11. Välj tillgången i fältet **Tillgång**.

12. Välj underhållsjobbtypen för tillgången i fältet **Underhållsjobbtyp**.

13. Om det behövs väljer du **Variant av underhållsjobbtyp** och **Yrkesgren** relaterad till underhållsjobbtypen.

14. Välj återkommande (dag, vecka, osv.) i fältet **Periodtyp**.

15. I fältet **Periodfrekvens** anger du antalet upprepningar för underhållsomgången. Exempel: om du har valt "Dag" i fältet **Periodtyp** och infogar siffran "7" i det här fältet, skapas nya underhållsomgångsrader under planering av förebyggande underhåll en gång i veckan.

16. Välj ett startdatum för tillgången som ska tas med i underhållsomgången i fältet **Startdatum**. Datumet kan skilja sig från det startdatum som ställts in för underhållsomgången.

17. Upprepa steg 9 till 16 om du vill lägga till fler tillgångar i underhållsomgången.

18. På snabbfliken **Funktionsplatsrader**, klicka på **Lägg** för att lägga till en funktionsplats i underhållsomgången. Se beskrivningen av de relaterade fälten ovan. Samma fält är tillgängliga för att skapa en tillgångsrad, men du kan också välja **Tillverkare** och **Modell** för en funktionsplats, om det behövs. Om du bara väljer en funktionsplats på en rad men inte gör några val i **Tillgångstyp**, **Tillverkare**, **Modell**, **Underhållsjobbtyp**, **Variant av underhållsjobbtyp** och **Yrkesgren** inkluderas alla tillgångar relaterade till den funktionsplatsen vid tidpunkten för underhållsplaneringen i underhållsomgången.

19. Klicka på **Lägg till** på snabbfliken **Pooler** om du vill välja en arbetsorderpool som ska inkluderas i underhållsomgången. Flera arbetsorderpooler kan kopplas till en underhållsomgång.

20. Spara dina inställningar.

>[!NOTE]
>Fälten **Tillgångar** och **Rader** i gruppen **Information** på snabbfliken **Sidhuvud** visar det totala antalet tillgångar och rader som är relaterade till den valda underhållsomgången.

Bilden nedan visar och exempel på en underhållsrunda som innehåller tre tillgångar.

![Figur 1](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a>Schemalägg underhållsomgångar

När du har ställt in en underhållsomgång kör du ett schemajobb för att tidsplanera alla jobb som relaterar till underhållsomgången.

1. Klicka på **Tillgångshantering** > **Periodiskt** > **Förebyggande underhåll** > **Schemalägg underhållsomgångar** eller **Tillgångshantering** > **Allmänt** > **Underhållsschema** > **Alla underhållsscheman** eller **Öppna rader för underhållsschema** eller **Öppna pooler för underhållsschema** > välj underhållsschemaraden i listan > knappen **Underhållsomgångar**.

2. I fältet **period** väljer du den periodtyp som ska användas för planeringsjobbet.

3. I fältet **Periodfrekvens** anger du antalet perioder som ska inkluderas i planeringsjobbet. Början på planeringen är det aktuella datumet.

4. Välj "Ja" på växlingsknappen **Autoskapa** om en arbetsorder automatiskt ska skapas baserat på en underhållsomgång.

>[!NOTE]
>Om den här växlingsknappen är inställd på "Ja" och växlingsknappen **Autoskapa** även är inställd på "Ja" i formuläret **Underhållsomgångar**, skapas arbetsorder baserade på underhållsomgångsraderna, och underhållsschemarader med statusen "Arbetsorder skapad" skapas också. Om endast en av växlingsknapparna **Autoskapa** är inställd på "Ja", i den här nedrullningsbara eller i **Underhållsomgångar**, skapas bara underhållsschemarader med statusen "Skapad". I så fall skapas inga arbetsorder.

5. Vid behov kan du välja specifika omgångar eller ett annat startdatum för schemajobbet. Klicka på **Filter** och lägg till omgångarna som ska inkluderas.

6. Klicka på **OK**.

7. Du kan nu se underhållsomgångsjobben i **Tillgångshantering** > **Allmänt** > **Underhållsschema** > **Alla underhållsscheman** eller **Öppna rader för underhållsschema**. Om schemalagda omgångar är kopplade till en pool för arbetsorder visas även underhållsschemarader i **Öppna pooler för underhållsschema**. Underhållsschemarader som skapas från en omgång av har referenstypen "Underhållsomgångar".

De två bilderna nedan visar ett schemajobb i dialogrutan **Schemalägg underhållsomgångar** och de rader för underhållsschema som skapats i **Alla underhållsscheman** baserat på det schemajobbet.

![Figur 2](media/14-preventive-maintenance.png)

![Figur 3](media/15-preventive-maintenance.png)

- När arbetsorder skapas manuellt på tillgångar som täcks av en leverantörsgaranti visas en dialogruta som gör användaren medveten om garantin. Skapandet av arbetsordern kan sedan annulleras. Kontrollen av en garantirelation utelämnas för arbetsorder som skapas automatiskt.  
- Du kan ställa in ett batchjobb på snabbfliken **Kör i bakgrunden** för att schemalägga omgångar med regelbundna intervall.  
- Om en omgång ingår i flera arbetsorderpooler (se [Arbetsorderpooler](../work-orders/work-order-pools.md)) visas en post för varje pool i **Öppna pooler för underhållsschema**. Detta görs för att optimera filtreringsalternativen för arbetsorderpooler.

