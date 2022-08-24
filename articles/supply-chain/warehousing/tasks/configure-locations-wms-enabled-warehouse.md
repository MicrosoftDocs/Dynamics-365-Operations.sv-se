---
title: Konfigurera platser i ett WMS-aktiverat lagerställe
description: Den här guiden visar hur du konfigurerar platsinställningar för ett nytt WMS-aktiverat lagerställe (ett lagerställe som använder avancerade lagerstyrningsprocesser (WMS)).
author: perlynne
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, WHSLocationFormat, WHSLocationType, WHSLocationProfile, WHSParameters, WHSZoneGroup, WHSZone, WHSLocationBuild, WHSLocation, WHSPackSizeCategory, WHSLocationLimit, WHSInventFixedLocation, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4cce7ea0c06938d2ce038853a262f843ec76fe4c
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219671"
---
# <a name="configure-locations-in-a-wms-enabled-warehouse"></a>Konfigurera platser i ett WMS-aktiverat distributionslager

[!include [banner](../../includes/banner.md)]

Den här guiden visar hur du konfigurerar platsinställningar för ett nytt WMS-aktiverat lagerställe (ett lagerställe som använder avancerade lagerstyrningsprocesser (WMS)). Processen normalt utförs av en lagerchef. Du kan köra den här guiden för demonstrationsföretaget USMF eller på dina egna data. En förutsättning är att du har konfigurerat minst en webbplats.


## <a name="create-a-new-warehouse"></a>Skapa ett nytt lagerställe
1. Gå till **Navigeringsfönstret > Moduler > Lagerhantering > Inställningar > Lagerindelning > Lagerställen**.
2. Klicka på **Ny**.
3. Ange ett värde i fältet **Lagerställe**.
4. Skriv ett värde i fältet **Namn**.
5. I fältet **Webbplats** väljer eller anger du ett värde för en befintlig webbplats.
6. Expandera valet **Lagerställe**.
7. Ange alternativet **Använd lagerstyrningsprocesser** till Ja. Den här inställningen gör det möjligt att köra lagerstyrningsprocesser (WMS) med hjälp av lagerarbete och mobila enheter.
8. Stäng sidan.

## <a name="define-a-location-format"></a>Definiera ett platsformat
1. Gå till **Navigeringsfönstret > Moduler > Lagerstyrning > Inställningar > Lagerställe > Platsformat**. Platsformat är ett namnhanteringssystem som används för att skapa unika och konsekventa unika namn för de olika platsbingepositioner som används inom ett lagerställe. Det kan vara praktiskt att använda avgränsare som en del av platsformatet om du vill göra det enklare att identifiera komponenter på platsen, till exempel gångnumret. I det här exemplet ska vi skapa ett namn med fyra komponenter. Till exempel kan du använda gång, ställning, hylla och binge.
2. Klicka på **Ny**.
3. I fältet **Platsformat**, skriv ett värde.
4. Skriv ett värde i fältet **Namn**.
5. I fältet **Segmentbeskrivning**, skriv ett värde. Den beskriver vad den första komponenten i ett platsnamn representerar. Till exempel kan det vara Gång.
6. I fältet **Längd**, ange ett tal. Detta avgör hur många tecken den här delen av platsnamnet måste ha. Observera att summan av alla komponenter i namnet, inklusive avgränsarna, inte får överstiga 10 tecken.    
7. I fältet **Avgränsare**, ange ett värde. Detta avgör vilket tecken eller vilken symbol som används mellan den första och andra komponenten i namnet.  
8. I avsnittet **Detaljer**, klicka på **Ny**.
9. I fältet **Segmentbeskrivning**, skriv ett värde.
10. I fältet **Längd**, ange ett tal.
11. I fältet **Avgränsare**, ange ett värde.
12. I avsnittet **Detaljer**, klicka på **Ny**.
13. I fältet **Segmentbeskrivning**, skriv ett värde.
14. I fältet **Längd**, ange ett tal.
15. I fältet **Avgränsare**, ange ett värde.
16. I avsnittet **Detaljer**, klicka på **Ny**.
17. I fältet **Segmentbeskrivning**, skriv ett värde.
18. I fältet **Längd**, ange ett tal.
19. Klicka på **Spara**.
20. Stäng sidan.

## <a name="define-location-types"></a>Definiera platstyper
1. Gå till **Navigeringsfönstret > Moduler > Lagerstyrning > Inställningar > Lagerställe > Platstyper**. Platstyper kan användas som filtreringsalternativ för att styra de olika lagerstyrningsprocesserna. Som minst måste du skapa platstyper för mellanlagring och slutlig leverans för att definiera den utgående lagerhanteringsprocessen. 
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Platstyp**.
4. I fältet **Beskrivning** anger du ett värde.
5. Stäng sidan.

## <a name="define-location-profile"></a>Definiera platsprofil
1. Gå till **Navigeringsfönstret > Moduler > Lagerstyrning > Inställningar > Lagerställe > Platsprofiler**. Definitionen av platsprofiler är mycket viktig. Grupperad platskapacitet kan kontrolleras här, men även policyer som är relaterade till vilket lager som lagras, och hur det lagras. Platsprofiler kan användas som filtreringsalternativ för att styra de olika lagerstyrningsprocesserna. Som minimum måste du skapa en användarplatsprofil för att kunna aktivera WMS.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Platsprofil-ID.**
4. Skriv ett värde i fältet **Namn**.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Platsformat**.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Platstyp**.
9. Hitta och markera önskad post i listan.
10. Klicka på länken på den valda raden i listan.
11. Markera eller avmarkera kryssrutan **Tillåt blandade lagerstatusar**. Aktivera det här alternativet om du vill tillåta blandade lagerstatusar på de platser som ska grupperas efter den här platsprofilen. 
12. Markera eller avmarkera kryssrutan **Åsidosättningsregler för batchdagar**. Aktivera det här alternativet för att åsidosätta regeln för hur många dagar lagerbatchutgångsdatumen kan skilja sig åt, för att tillåta blandning av lagerbatchar som inte uppfyller den här regeln.  
13. Markera eller avmarkera kryssrutan **Tillåt rullande inventering**. Aktivera det här alternativet om du vill tillåta bearbetning av rullande inventering på alla de platser som ska grupperas efter den här platsprofilen. 
14. Visa eller dölj avsnittet **Dimensioner**. Fliken Dimensioner gör det möjligt att definiera parametrar och metoder för att aktivera exakta beräkningar av kapacitetsbeläggningen på varje plats.  
15. Stäng sidan.

## <a name="enable-warehouse-management-parameters"></a>Aktivera parametrar för lagerstyrning
1. Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Parametrar för lagerstyrning**. För att kunna bearbeta lagerarbete måste du ange parametrar för användarens platsprofil för typen av mellanlagringsplats och den slutliga leveransplatsen. Så snart som den utgående processen avslutas vid typen för den slutliga leveransplatsen som du definierar, de relaterade utgående transaktionerna uppdateras till Plockad.
2. Visa eller dölj avsnittet **Platsprofiler**.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Användarplats**.
4. Klicka på länken på den valda raden i listan.
5. Visa eller dölj avsnittet **Platstyper**.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Typ av mellanlagringsplats**.
7. Klicka på länken på den valda raden i listan.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Typ av slutlig leveransplats**.
9. Klicka på länken på den valda raden i listan.
10. Stäng sidan.

## <a name="define-warehouse-zone-groups"></a>Definiera grupper för lagerställezoner
1. Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Lagerställe > Grupper – lagerställezoner**. Lagerställezoner kan användas som filtreringsalternativ för att styra de olika lagerstyrningsprocesserna. Du måste skapa en zongrupp innan du kan definiera en zon.   
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Zongrupps-ID**.
4. Skriv ett värde i fältet **Zongruppnamn**.
5. Stäng sidan.

## <a name="define-warehouse-zones"></a>Definiera lagerställezoner
1. Gå till **Navigeringsfönstret > Moduler > Lagerstyrning > Inställningar > Lagerställe > Zoner**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Zon-ID**.
4. Skriv ett värde i fältet **Zonnamn**.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Zongrupps-ID**.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Stäng sidan.

## <a name="create-locations-using-the-location-setup-wizard"></a>Skapa platser med hjälp av guiden för platsinställning
1. Gå till **Navigeringsfönstret > Moduler > Lagerstyrning > Inställningar > Lagerställe > Guide för platsinställning**.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagerställe**.
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Zon-ID**.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. I fältet **Platsprofil-ID** öppnar du sökningen genom att klicka på den nedrullningsbara knappen.
9. Hitta och markera önskad post i listan.
10. Klicka på länken på den valda raden i listan.
11. Markera vald rad i listan.
12. Ange ett nummer i fältet **Från nummer**. Fälten Från nummer och Till nummer definierar hur många platser som ska skapas. Om du till exempel ställer in Från nummer till 1 och Till nummer till 3 för alla fyra raderna i platsformatet skapas 81 platser (3 × 3 × 3 × 3).   
13. Ange ett nummer i fältet **Till nummer**.
14. Hitta och markera önskad post i listan.
15. Ange ett nummer i fältet **Från nummer**.
16. Ange ett nummer i fältet **Till nummer**.
17. Hitta och markera önskad post i listan.
18. Ange ett nummer i fältet **Från nummer**.
19. Ange ett nummer i fältet **Till nummer**.
20. Hitta och markera önskad post i listan.
21. Ange ett nummer i fältet **Från nummer**.
22. Ange ett nummer i fältet **Till nummer**.
23. Klicka på Skapa.

## <a name="create-locations-manually"></a>Skapa platser manuellt
1. Gå till **Lagerstyrning > Inställningar > Lagerställe > Platser**. Du kan enkelt skapa platser manuellt inom ett lagerställe. Platsnamnet och platsprofil-ID:t är obligatoriska värden. 
2. Klicka på **Ny**.
3. Ange ett värde i fältet **Lagerställe**.
4. Skriv ett värde i fältet **Plats**. Observera att du skapar en ny plats här, så du behöver skriva en nytt unikt namn snarare än välja ett befintligt.
5. Skriv ett värde i fältet **Platsprofil-ID.**
6. Stäng sidan.

## <a name="define-pack-size-categories"></a>Definiera kategorier för förpackningsstorlekar
1. Gå till **Lagerstyrning > Inställningar > Lagerställe > Kategorier för packningsstorlek**. Kategorier av förpackningsstorlekar kan användas för att gruppera artiklar som har liknande fysiska förpackningsstorlekar. I det här exemplet används kategorin för förpackningsstorlek för att styra kapaciteten på plockningsplatserna inom en viss zon på lagerstället. Observera att packstorlekskategori-ID:t måste tilldelas den frisläppta produktenheten för att kunna användas som en del av bearbetningen av lagringsbegränsningar.  
2. Klicka på **Ny**.
3. I fältet **Kategori-ID för packningsstorlek**, ange ett värde.
4. Skriv ett värde i fältet **Kategorinamn för packningsstorlek**.
5. Stäng sidan.

## <a name="define-location-stocking-limits"></a>Definiera lagerbegränsningar för lagerställen
1. Gå till **Lagerstyrning > Inställningar > Lagerställe > Lagringsbegränsningsplats**. Lagringsbegränsningsplatser hjälper till att kontrollera att arbetet inte skapas för att begära att lagret ska infogas på en plats som inte har den fysiska lagringsmöjligheten.  
2. Klicka på **Ny**.
3. Ange ett värde i fältet **Lagerställe**.
4. Skriv ett värde i fältet **Platsprofil-ID.**
5. I fältet **Kategori-ID för packningsstorlek**, ange ett värde.
6. Ange ett nummer i fältet **Kvantitet**.
7. Klicka på **Spara**.
8. Stäng sidan.

## <a name="define-fixed-picking-locations"></a>Definiera fasta plockplatser
1. Gå till **Lagerstyrning > Inställningar > Lagerställe > Fasta lagerplatser**. Du kan definiera platserna som ska användas per produkt eller per produktvariant. Det är möjligt att skapa flera fasta lagerplatser för samma produkt inom samma lagerställe.     
2. Klicka på **Ny**.
3. I fältet **Artikelnummer**, skriv ett värde.
4. Ange ett värde i fältet **Lagerställe**.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Plats**.
6. Klicka på länken på den valda raden i listan.
7. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
