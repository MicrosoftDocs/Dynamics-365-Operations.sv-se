---
title: Registrera artiklar för en avancerad lagerstyrningsaktiverad artikel med hjälp av en artikelinförseljournal
description: I den här proceduren visas hur du registrerar artiklar via artikelinförseljournalen när du använder avancerade processer för lagerlagerstyrning.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec15a5d35c360ed8f8eddffc44d303df193ce3e7
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847284"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a>Registrera artiklar för en avancerad lagerstyrningsaktiverad artikel med hjälp av en artikelinförseljournal

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du registrerar artiklar via artikelinförseljournalen när du använder avancerade processer för lagerlagerstyrning. Detta görs vanligtvis av en inleveransansvarig. 

Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Du måste ha en bekräftad inköpsorder med en öppen inköpsorderrad innan du startar den här guiden. Artikeln på raden måste finnas i lager och får inte innehålla produktvarianter och spårningsdimensioner. Och artikeln måste associeras med en lagerstyrningsprocess för lagringsdimensionsgrupp. Lagerstället som används måste aktiveras för lagerstyrningsprocesser och lagerplatsen som du använder för inleveranser måste vara id-nummerstyrd. Om du använder USMF, kan du använda företagskontot 1001, lagerställe 51 och artikeln M9200 när du skapar inköpsordern. 

Gör en notering om inköpsordernumret du skapar och anteckna också artikelnumret och lagerplatsen för inköpsorderraden.


## <a name="create-an-item-arrival-journal-header"></a>Skapa ett artikelinförseljournalhuvud
1. Gå till Artikelinförsel.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
    * Om du använder USMF kan du skriva WHS. Om du använder andra data måste journalen vars namn du väljer ha följande egenskaper: Kontrollera plockplats måste anges till Nej och Karantänhantering måste anges till Nej.  
4. Ange ett värde i fältet Antal.
5. Ange ett värde i fältet Plats.
    * Markera platsen du använde till inköpsorderraden. Den fungerar som standardplats som blir förvalt värde för alla rader i journalen. Om du använder lagerställe 51 i USMF, välj plats 5.  
6. Ange ett värde i fältet Lagerställe.
    * Välj ett giltigt lagerställe för den plats som du har valt. Den fungerar som standardplats som blir förvalt värde för alla rader i journalen. Om du använder exempelvärdena i USMF, välj 51.  
7. Skriv ett värde i fältet Plats.
    * Välj en giltig lagerplats på lagerstället du har valt. Platsen måste vara kopplade till en platsprofil som styrs av id-numret. Den fungerar som standardplats som blir förvalt värde för alla rader i journalen. Om du använder exempelvärdena i USMF, välj Bulk-008.  
8. Högerklicka på nedrullningspilen i id-nummerfältet och välj sedan Visa detaljer.
9. Klicka på Ny.
10. Ange ett värde i fältet för id-numret.
    * Gör en notering av värdet.  
11. Klicka på Spara.
12. Stäng sidan.
13. Ange ett värde i fältet för id-numret.
    * Ange värdet för den registreringsskylt du just skapade. Den fungerar som standardplats som blir förvalt värde för alla rader i journalen.  
14. Klicka på OK.

## <a name="add-a-line"></a>Lägga till en rad
1. Klicka på Lägg till rad.
2. Skriv ett värde i fältet Artikelnummer.
    * Ange artikelnumret som du använde på inköpsorderraden.  
3. Ange ett tal i fältet Kvantitet.
    * Ange den kvantitet som du vill registrera.  
    * Datumfältet bestämmer datumet då lagerbehållningen för artikeln ska registreras i lagret.  
    * Parti-id:t fylls i av systemet, om det kan identifieras av den tillhandahållna informationen. Annars måste du lägga till det manuellt. Detta är ett obligatoriskt fält, som kopplar den här registreringen till en viss källdokumentrad.  

## <a name="complete-the-registration"></a>Slutför registreringen
1. Klicka på Validera.
    * Detta kontrollerar att journalen är klar att bokföras. Om valideringen misslyckas måste du korrigera felen innan du kan bokföra journalen.  
2. Klicka på OK.
    * Kontrollera meddelandet när du har klickat på OK. Det bör visas ett meddelande om att journalen är OK.  
3. Klicka på Bokför.
4. Klicka på OK.
    * Kontrollera meddelandefältet när du har klickat på OK. Det bör visas ett meddelande om att åtgärden lyckades.  
5. Stäng sidan.

