--- 
title: "Skapa en rekvisition för förbrukning"
description: "I den här proceduren förklaras processen för att skapa en rekvisition."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 8eb4cd47104e2df1c973e5e508c1da02617b9a1d
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-requisition-for-consumption"></a>Skapa en rekvisition för förbrukning

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren förklaras processen för att skapa en rekvisition. Den visar olika metoder för att söka efter produkter i din anskaffningskatalog och hur du lägger till en produkt som inte finns i din katalog. Innan du startar den här proceduren måste du ha en inköpspolicy inställd med Förbrukning som standardinställningstyp för rekvisitionen. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data. Proceduren kan bara utföras av en användarprofil som har ställts in som arbetare.  Uppgiften utförs vanligtvis av en medarbetare. Den säkerhetsroll som medarbetaren använder gör det möjligt för dig att utföra uppgifterna. Om du använder USMF kan du även logga in som Alicia.


## <a name="create-a-new-requisition"></a>Skapa en ny rekvisition
1. Gå till Anskaffning och källa > Inköpsrekvisitioner > Inköpsrekvisitioner som har förberetts av mig.
2. Klicka på Ny.
3. Ange ett namn på rekvisitionen i fältet Namn.
4. Ange ett datum i fältet Begärt datum.
    * Som standard kopieras det begärda datumet och redovisningsdatumet till inköpsrekvisitionsrader. De kan ändras på radnivå. Det begärda datumet är det begärda leveransdatumet.  
5. Ange ett datum i fältet Redovisningsdatum.
    * Redovisningsdatumet används för att registrera redovisningsposten i redovisningen och för att validera att det finns tillgängliga budgetmedel.  
6. Klicka på OK.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Orsak.
    * Affärsmotiveringsorsaken som du väljer visas som standard för raderna på inköpsrekvisitionen, men du kan ändra den på radnivå.    
8. Hitta och markera önskad post i listan.
9. Ange orsaken
10. Ange en mer beskrivande justering för rekvisitionen

## <a name="add-a-line-to-the-requisition"></a>Lägga till en rad i rekvisitionen
1. Klicka på Lägg till rad.
    * Du kan lägga till rader i inköpsrekvisitionen på två sätt. Om du redan känner till produktnumret eller vet att du begär en produkt som inte finns i produktkatalogen kan du lägga till raden direkt med "Lägg till rad". Det andra sättet är att använda "Lägg till produkter" där du kan använda sökning och filtrering för att hitta artiklar i produktkatalogen.    
2. Klicka på den rad som du precis har skapat.
    * Beställaren är den arbetare som har begärt rekvisitionen.   
    * Som standard är det den arbetare som har begärt rekvisitionen som förbereder den. Du måste ges behörighet att förbereda en rekvisitionsrad på uppdrag av en annan arbetare. Om du har sådana behörigheter visas de andra arbetarna i den här sökningen.  
3. Skriv ett värde i fältet Artikelnummer.
    * Det antal artiklar som du kan välja begränsas av kategoriåtkomstpolicyn och anskaffningskatalogen för den köpande juridiska personen.    
4. Ange ett tal i fältet Kvantitet.

## <a name="add-more-products-to-the-requisition"></a>Lägg till fler produkter till rekvisitionen
1. Klicka på Lägg till produkter.
    * Detta är det alternativ där du kan söka efter produkter i produktkatalogen.      
2. I fältet Hitta anskaffningskategorinod skriver du den första delen av namnet på den kategori som du letar efter och klickar sedan på Enter.
    * Skriv till exempel dat.  
3. Använd genvägen InvokeDefaultButton.
4. Använd Filtrera för att filtrera produktlistan i den valda kategorin.
5. Välj det produktkort som du vill lägga till i rekvisitionen.
6. Klicka på Lägg till på rader.
7. Ange ett nummer i fältet Kvantitet.
8. I fältet Hitta anskaffningskategorinod skriver du den första delen av namnet på den kategori som du letar efter och klickar sedan på Enter.
    * Till exempel typen Hög (överstrykningspennor).  
9. Använd genvägen InvokeDefaultButton.
10. Klicka på Lägg till produkt som inte är listad till rader om du vill lägga till en produkt som inte finns med i anskaffningskatalogen.
11. Skriv ett värde i fältet Produktnamn.
12. Skriv ett värde i fältet Enhet.
13. Klicka på OK.
14. Ange en beskrivning av produkten i fältet Artikelbeskrivning.
15. Ange ett tal i fältet Kvantitet.
16. Ange ett tal i fältet Enhetspris.
    * Om du känner till priset för en viss leverantör (som du väljer i fältet Leverantörskonto), så kan du ange det priset.   
17. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.
    * De leverantörer som är tillgängliga i det här fältet är beroende av inköpspolicyerna och den status som leverantören har för den aktuella anskaffningskategorin. Som ett alternativ till att markera en leverantör här kan du klicka på knappen Föreslå leverantör.    
18. Välj den leverantör som du vill använda i listan.
19. Skriv ett värde i fältet Externt artikelnummer.
    * Detta är ett referensnummer för den produkt som leverantören känner till. Detta kan exempelvis vara artikelnumret för produkten i leverantörens egen katalog.  
20. Klicka på OK.

## <a name="distribute-amounts"></a>Fördela belopp
1. Klicka på Ekonomi.
2. Klicka på Fördela belopp.
    * I den här processen visas hur du fördelar kostnaden för den första raden mellan två konton. Detta kan även göras vid ett senare tillfälle, när inköpsrekvisitionen granskas.  
3. Klicka på Dela för att skapa en ny fördelningsrad.
4. I fältet Huvudbokskonto väljer du det första kostnadsställe som ska ingå i kostnaden.
5. Välj den valda fördelningsraden.
6. Ange det andra kostnadsstället i fältet Huvudbokskonto.
7. Klicka på Fördela lika.
8. Stäng sidan.

## <a name="view-line-details"></a>Visa raddetaljer
1. Växla expanderingen av avsnittet Raddetaljer.

## <a name="submit-the-requisition"></a>Skicka rekvisitionen
1. Klicka på Arbetsflöde för att öppna dialogrutan.
2. Klicka på Skicka.
3. Stäng sidan.
4. Skriv en notering för godkännaren av rekvisitionen i fältet Kommentar.
5. Klicka på Skicka.
6. Stäng sidan.
7. Uppdatera sidan.


