---
title: " Definiera förmånsscheman"
description: Den här proceduren går igenom hur du definierar ett bonusprogram.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2bec8653c05d7684202c0e63d049ddb517e12834
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415873"
---
# <a name="define-loyalty-schemes"></a> Definiera förmånsscheman

[!include [banner](../includes/banner.md)]

Den här proceduren går igenom hur du definierar ett bonusprogram. Bonusplaner är regler för intjänande och inlösen av belöningar i ett bonusprogram. I proceduren används demonstrationsföretaget USRT.

1. Gå till Butik och handel > kunder > lojalitet > lojalitetssystem.
2. Klicka på Ny.
3. Skriv ett värde i fältet Program-ID.
4. Ange ett värde i fältet Beskrivning.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
    * Du kan ha flera lojalitetssystem för ett lojalitetsprogram. Bonusplaner kan gälla för alla kanaler eller endast en underuppsättning kanaler.  
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Klicka på Spara.
9. Klicka på Lägg till rad.
10. Välj ett alternativ i fältet Aktivitetstyp.
    * Välj Köp produkter efter belopp om du vill ge kunderna belöningar som baseras på hur mycket de spenderar. Välj köpa produkter av kvantitet om du vill kunderna att få belöningar baseras på hur många produkter de köper.  Välj Antal försäljningstransaktioner om kunden ska få belöningar för varje försäljningstransaktion, oavsett vad som köps eller hur mycket.  
    * Markera en kategori. Kategorin avgränsar vilka produkter den här förtjänstregeln gäller för.  
    * Lämna fältet tomt om du vill att intäktsregeln ska gälla för alla produkter.  
11. I fältet Aktivitetens belopp/kvantitet, ange ett nummer.
    *  För aktivitetstyp försäljningstransaktion räknar, bör du alltid använda ett värde på '1.0'. För aktivitet typer av inköp av beloppet eller köp av kvantitet, varje transaktion som är mindre än det angivna värdet utlöser inte tjäna regeln. Om till exempel aktivitetstypen är Köp efter belopp och du anger 10,00 ger en försäljningstransaktion på 9,00 ingen intjänad belöning för den här förtjänstregeln.  
12. Ange ett värde i fältet Aktivitetsvaluta.
13. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Belöningspoäng-ID.
14. Klicka på länken på den valda raden i listan.
15. Välj ett nummer i fältet Belöningspoäng.
    * Belöningspoängen för beloppstypen lagrar intjänade belopp med decimaler. Om till exempel intjäningsregeln anger att medlemmen får en belöningspoäng för varje kanadensisk dollar som spenderas och medlemmen spenderar 1,25 kanadensiska dollar får hon eller han 1,25 belöningspoäng. Kvantitetstyp extrapoäng kommer posten intjänat belopp i heltal. Om till exempel intjäningsregeln anger att medlemmen får en belöningspoäng för varje kanadensisk dollar som spenderas och medlemmen spenderar 1,25 kanadensiska dollar får hon eller han 1,0 belöningspoäng.  
16. Klicka på Spara.
17. Klicka på Lägg till rad.
    * Regler för inlösen används när lojalitetbetalningsmetoden används.  
18. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Belöningspoäng-ID.
    * Endast inlösbara belöningspoäng visas.  
19. Klicka på länken på den valda raden i listan.
20. Välj ett nummer i fältet Belöningspoäng.
21. Välj ett alternativ i fältet Inlösningstyp.
    * Om du väljer Betalning efter belopp gör detta att fältet Belopp eller Kvantitet behandlas som ett valutavärde. I detta fall skall beloppet av extrapoäng per valuta betalningsmedel är ett fast förhållande. För att välja betalning av kvantiteten orsakar beloppet eller kvantitet som ska behandlas som en kvantitet. I detta fall skall beloppet av extrapoäng per kvantitet är ett fast förhållande, men beloppet i valutan kan variera om priset på poster betalas med lojalitet extrapoäng varierar för samma kvantitet. Inlösentypen för lojalitetspoängrabatt är endast giltig när konfigurationsnyckeln för Ryssland – lands-/regionsspecifika funktioner – är aktiverad och kassafunktionsprofilerna har ISO-koden RU.  
    * Markera en kategori. Kategorin avgränsar vilka produkter den här inlösenregeln gäller för.  
    * Lämna fältet tomt om du vill att inlösenregeln ska gälla för alla produkter.  
22. I fältet Belopp eller kvantitet, ange ett nummer.
23. Ange ett värde i fältet Valuta.
24. Klicka på Spara.
25. Klicka på Lägg till rad.
    * Markera en eller flera noder i listan Tillgängliga organisationsnoder och flytta dem till listan Valda organisationsnoder genom att klicka på pilen mellan de två listorna.  
26. Klicka på OK.
27. Klicka på Spara.
    * Så snart du ändrar kanalerna för ett bonusprogram måste du köra Bearbeta förmånsscheman. Det kanaler uppdateras lojalitetssystem.  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]