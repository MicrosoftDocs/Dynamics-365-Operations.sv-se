---
title: Skapa en mall för fritextfaktura
description: Den här proceduren visar hur du skapar en mall för fritextfaktura.
author: ShivamPandey-msft
ms.date: 05/29/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f84345aa8b157c5ca2a3025d4817af1fb1b1b2d009b3213d15a5b3daca8d763
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763272"
---
# <a name="create-a-free-text-invoice-template"></a>Skapa en mall för fritextfaktura

[!include [banner](../includes/banner.md)]

För den här genomgången använder du demonstrationsföretaget USMF. Proceduren är avsedd för den användare som ansvarar för hantering och bearbetning av kundreskontrafakturor.

## <a name="create-a-template"></a>Skapa en mall

1. Gå till Kundreskontra > Fakturor > Återkommande fakturor > Mallar för fritextfaktura.
    * Använd det här formuläret om du vill skapa fritextfakturamallar som kan innehålla fakturarader, avgifter, en redovisningsfördelning mall och information om redovisningskonto.  
2. Klicka på Ny om du vill skapa en ny fritextfaktura.
3. I fältet Mallnamn, skriv ett värde.
    * "Mallnamn" identifierar unikt en fritextfakturamall. Två mallar kan inte ha samma ”mallnamn".  
4. Ange en beskrivning av mallen i fältet Beskrivning.
5. Expandera fakturaradfliken.
6. Ange en beskrivning av fakturaraden i fältet Beskrivning.
7. Välj ett intäktskonto i huvudkontofältet.
    * Du kan välja mottransaktionskontot för en kundkredit för hela faktureringsbeloppet på sidan Kundbokföringsprofiler.  
8. I fältet Momsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.
    * Momsgruppen för den aktuella fakturaraden, som är standardmomsgruppen för kundkontot.  
9. Klicka på länken på den valda raden i listan.
10. I fältet Artikelmomsgrupp väljer du artikelmomsgruppen för den aktuella fakturaraden.
11. Klicka på länken på den valda raden i listan.
12. Ange eller visa pris per enhet för fakturaraden i fältet Enhetspris.
    * Detta belopp multipliceras med värdet i fältet Kvantitet för att bestämma fakturaradbeloppet.  
13. Lägg till en ny rad i fritextfakturamallen.
14. Ange en beskrivning av fakturaraden i fältet Beskrivning.
15. Välj ett intäktskonto i huvudkontofältet.
    * Du kan välja mottransaktionskontot för en kundkredit för hela faktureringsbeloppet på sidan Kundbokföringsprofiler.  
16. I fältet Momsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.
    * Momsgruppen för den aktuella fakturaraden, som är standardmomsgruppen för kundkontot.  
17. Klicka på länken på den valda raden i listan.
18. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.
    * Artikelmomsgruppen för den aktuella fakturaraden.  
19. Klicka på länken på den valda raden i listan.
20. Ange eller visa antalet enheter för fakturaraden.
    * Detta nummer multipliceras med värdet i fältet Enhetspris för att bestämma fakturaradbeloppet.  
21. Ange eller visa priset per enhet för fakturaraden. 
    * Detta belopp multipliceras med värdet i fältet Kvantitet för att bestämma fakturaradbeloppet.  
22. Visa och ändra redovisningsfördelningarna för en enskild rad, och alla underordnade.
    * Redovisningsfördelningar definierar hur ett belopp ska redovisas, till exempel hur intäkten, momsen eller avgifterna ska redovisas på en fritextfaktura.  
23. Uppdatera redovisningsfördelningarna för fakturaraden.
24. Klicka på Stäng.

## <a name="save-a-free-text-invoice-as-a-template"></a>Spara en fritextfaktura som en mall
Du kan också spara en befintlig fritextfaktura som en mall. När du väljer Spara till mall på fliken Faktura, ange ett namn och en beskrivning för mallen. Om det finns redan en mall med namnet, visas ett meddelande om att en mall med samma namn redan finns. Du kan fortfarande klicka på Ok om du vill ersätta den. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]