---
title: "Skapa en ny layout för lagerställe"
description: "I den här proceduren visas hur du ställer in information om platserna i ett lagerställe."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 15610bc797cf7e7abdec433d0a5cead60da7a555
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-new-warehouse-layout"></a>Skapa en ny layout för lagerställe

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du ställer in information om platserna i ett lagerställe. Detta gäller endast lagerställen som skapats med hjälp av ”grundläggande lagerstyrning” i lagerhanteringmodulen och inte för lagerställen som skapats i lagerstyrningsmodulen. Du kan använda den här proceduren i demonstrationsföretaget USMF eller med dina egna data.


## <a name="set-the-default-location-capacity"></a>Ange standardplatskapaciteten
1. Gå till Lagerhantering > Inställningar > Parametrar för hantering av lager och lagerstyrning.
2. Klicka på fliken Platser.
3. Välj ett nummer i fältet Standardbredd.
4. Välj ett nummer i fältet Standarddjup.
5. Välj ett nummer i fältet Standardhöjd.
6. Klicka på Spara.
7. Stäng sidan.

## <a name="define-the-location-name-format"></a>Definiera platsnamnformatet
1. Gå till Lagerhantering > Inställningar > Lagerindelning > Lagerställen.
2. Klicka på Ny.
3. Ange ett värde i fältet Lagerställe.
4. Skriv ett värde i fältet Namn.
5. Öppna sökningen genom att klicka på listruteknappen i fältet Plats.
6. Hitta och markera önskad post i listan.
7. Växla utökningen av avsnittet Platsnamn.
    * Alternativen i detta avsnitt definierar standardformatet på platsnamn. I vårt exempel ska vi inkludera gångnummer, ställningsnummer och hyllnummer.  
8. Ange alternativet Inkludera gång som Ja.
9. Ange alternativet Inkludera ställning som Ja.
10. I fältet Format skriver du in ett värde för ställningen.
    * Exempel: -##  
11. Ange alternativet Inkludera hylla som Ja.
12. I fältet Format skriver du in ett värde för hyllan.
    * Exempel: -##  

## <a name="define-warehouse-locations"></a>Definiera lagerställesplatser
1. Klicka på Lagerställe i åtgärdsfönstret.
2. Klicka på Platsguide.
3. Klicka på Nästa.
4. Avmarkera alternativet Utlastningsplatser
5. Avmarkera alternativet Bulkplatser
6. Klicka på Nästa.
7. Klicka på Nästa.
8. Klicka på Nästa.
9. Klicka på Nästa.
10. Klicka på Nästa.
11. Klicka på Nästa.
12. Klicka på Nästa.
    * Observera att de fysiska dimensionerna som visas på den här sidan är dem som du angett i början av den här proceduren.  
13. Klicka på Nästa.
14. Klicka på Avsluta.
15. Stäng sidan.
16. Uppdatera sidan.

