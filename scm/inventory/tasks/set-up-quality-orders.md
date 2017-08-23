--- 
title: "Ställ in kvalitetsorder"
description: "I den här proceduren visas om hur du aktiverar en kvalitetshantering process där det inkommande lager måste kontrolleras omedelbart efter fakturaregister."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 0bd8bc73a3cbb42cb7e6d42a07d58c0b02673ba1
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-quality-orders"></a>Ställ in kvalitetsorder

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas om hur du aktiverar en kvalitetshantering process där det inkommande lager måste kontrolleras omedelbart efter fakturaregister. Proceduren ska ske ut vanligtvis av en chef kvalitetsnormerna. Processen omfattar att en kvalitetsgrupp, om du vill definiera artiklar, som ska tas prov, och en grupp test om du vill gruppera de tester som ska utföras på artiklarna i kvalitetsgruppen. Du kan köra den här handboken i demoföretaget USMF.


## <a name="enable-quality-management"></a>Aktivera kvalitetshantering
1. Gå till Lagerhantering > Inställningar > Parametrar för hantering av lager och lagerstyrning.
2. Klicka på kvalitetshanteringfliken.
3. Välj alternativet Ja för Använd kvalitetshantering.
4. Klicka på Rapportinställning.
    * I USMF är rapportinställningen för kvalitetshantering redan definierad. Om detta inte görs ska du lägga till nya rader här för de olika rapporttyperna och sedan välj den typ av dokument som ska användas för varje rapport.  
5. Stäng sidan.
6. Stäng sidan.

## <a name="create-a-test"></a>Skapa test
1. Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Tester.
2. Klicka på Ny.
3. Ange ett värde i fältet Test.
4. Ange ett värde i fältet Beskrivning.
5. Välj Alternativ i fältet Typ.
    * I det här exemplet ska du välja ”Alternativ” som ska göra det möjligt att tilldela testresultatet baserat på fördefinierade värden.  
6. Klicka på Spara.
7. Stäng sidan.

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a>Skapa testvariabeln för att definiera hur testresultatet registreras
1. Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Testvariabler.
2. Klicka på Ny.
3. Ange ett värde i fältet Variabel.
4. Ange ett värde i fältet Beskrivning.
5. Klicka på Spara.
6. Klicka på Resultat.
7. Klicka på Ny.
8. Ange ett värde i fältet Resultat.
9. Ange ett värde i fältet Beskrivning.
10. Välj Godkänd i resultatstatusfältet.
11. Klicka på Spara.
12. Klicka på Ny.
13. Ange ett värde i fältet Resultat.
14. Ange ett värde i fältet Beskrivning.
15. Klicka på Spara.
16. Stäng sidan.
17. Stäng sidan.

## <a name="set-up-item-sampling"></a>Ställ in artikelsampling
1. Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Artikelsampling.
2. Klicka på Ny.
3. Skriv ett värde i samplingsfältet.
4. Ange ett värde i fältet Beskrivning.
5. Ange ett nummer i fältet Värde.
    * Det här värdet är relaterade till kvantitetspecifikationen som valts i fältet bredvid.  
6. Dölj eller visa avsnittet Bearbeta.
7. Markera eller avmarkera kryssrutan Full spärr.
    * Om du markerar den här väljare, spärras hel komponent eller orderradkvantiteten, om ett test misslyckas. Om du inte markerar kryssrutan, spärras bara artiklarna i kvalitetsordern.  
8. Klicka på Spara.
9. Stäng sidan.

## <a name="create-a-quality-group"></a>Skapa en kvalitetsgrupp
1. Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Kvalitetsgrupper.
2. Klicka på Ny.
3. Skriv ett värde i fältet Kvalitetsgrupp.
    * Använd ett beskrivande namn som hjälper dig att identifiera vilken typ av artiklar som gruppen ska innehålla (dina samplingvillkor).  
4. Ange ett värde i fältet Beskrivning.
5. Klicka på Spara.
6. Klicka på Lägg till artiklar.
7. Markera raden med artikelnumret
    * I det här exemplet ska vara kört filtrera utifrån artikelnumret.  
8. Ange ett värde i fältet Kriterier.
    * Till exempel typ T* som ska filtreras på artikelnummer som börjar med T.  
9. Klicka på OK.
10. Klicka på OK.
11. Klicka på Kvalitetsgrupper för artiklar.
12. Stäng sidan.
13. Stäng sidan.

## <a name="create-a-test-group"></a>Skapa en testgrupp
1. Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Testgrupper.
2. Klicka på Ny.
3. Skriv ett värde i fältet Testgrupp.
    * Ge testgruppen ett namn som hjälper dig att komma ihåg vilken typ av testerna körs, och vilken kvalitetsgrupp den ska kopplas till. Du kan till exempel använda den med en kvalitetsgrupp för att välja artiklar som börjar med ”T” och du kan kalla den ”T-artikeltest".  
4. Ange ett värde i fältet Beskrivning.
5. Välj artikelsamplingraden som du skapade i artikelsamplingfältet förut.
6. Hitta och markera önskad post i listan.
7. Klicka på Lägg till.
8. Ange ett nummer i fältet Sekvensnummer.
9. I fältet Test väljer du det test som du skapade tidigare.
10. Hitta och markera önskad post i listan.
11. Klicka på fliken Testa.
12. I fältet Variabel väljer du den testvariabel som du skapade tidigare
13. Hitta och markera önskad post i listan.
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Standardkund.
15. Klicka på länken på den valda raden i listan.
16. Klicka på Spara.
17. Stäng sidan.

## <a name="define-when-quality-orders-will-be-created"></a>Definiera när kvalitetsorder ska skapas
1. Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Kvalitetsassociationer.
2. Klicka på Ny.
3. Välj ett alternativ i fältet Referenstyp.
4. Välj Grupp i fältet Artikelkod.
    * I det här exemplet ska du markera Grupp och använder kvalitetsgruppen som du skapade förut. Du kan även ange den här avsnittet som Register för att ange artiklar manuellt eller välja Alla för att lägga till alla artiklar till kvalitetsordern.  
5. I fältet Artikel väljer du den kvalitetsgrupp som du skapade förut.
    * Alternativen som är tillgängliga i fältet Artikel, beror på vad som du har angett i fältet Artikelkod.  
6. Hitta och markera önskad post i listan.
7. Dölj eller visa avsnittet Bearbeta.
8. Välj ett alternativ i fältet Händelsetyp.
    * Det är händelsen som utlöser testet. De tillgängliga väljarna beror på vilken här processen du valde i referenstypfältet.  
9. Markera ett alternativ i fältet Körning.
10. Dölj eller visa avsnittet Kvalitetsorderprocess.
11. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Händelsespärr.
    * Det här fältet visar en lista med processer som det är möjligt att spärra, om kvalitetsordern fortfarande är öppen. Väljarna beror på vad du valde i händelsetypfältet.  
12. Klicka på länken på den valda raden i listan.
    * Det blir beroende på de föregående välja värden. Välj, om följande processer måste spärras, medan ha öppna kvalitetsorder som är kopplade till en källdokument, rad.  
13. dölj eller vis avsnittet Specifikationer.
14. I fältet Testgrupp väljer du den testgrupp som du skapade tidigare.
15. Hitta och markera önskad post i listan.
16. Klicka på Spara.
17. Stäng sidan.


