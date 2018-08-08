--- 
title: Skapa en fritextfaktura
description: "Den här artikeln visar hur du skapar en fritextfaktura."
author: mikefalkner
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f69505f0c6137121cae92d42d052b244326c8436
ms.openlocfilehash: 2a611bdd4dd97109709ed355eb80471e27413744
ms.contentlocale: sv-se
ms.lasthandoff: 06/28/2018

---

# <a name="create-a-free-text-invoice"></a>Skapa en fritextfaktura

[!include [banner](../includes/banner.md)]

Den här artikeln visar hur du skapar en fritextfaktura. För den här proceduren använder du demonstrationsföretaget USMF.

## <a name="create-a-free-text-invoice"></a>Skapa en fritextfaktura

1. Gå till Kundreskontra > Fakturor > Alla fritextfakturor.
2. Klicka på Ny.
3. Välj ett värde i fältet Kundkonto.
    * Fakturakontot blir som standard samma konto som används för kundkontot.   
    * Redovisningsstatusen börjar med Pågår om fakturan inte har bokförts.   
    * Fakturanumret tilldelas när fakturan bokförs.  
    * Om du använder SEPA-fullmakter, fylls autogiromedgivandet i automatiskt med en fullmakt när du väljer kundkontot.  
4. Ange ett värde i fältet Beskrivning.
5. Ange ett kontonummer utan dimensioner i huvudkontofältet.
    * Du kan även ange ett eller flera tecken för huvudkontot och använda sökning för att hitta kontot. Du anger dimensioner senare i den här handboken.  
6. Expandera snabbfliken Radinformation så att du kan lägga till dimensioner i huvudkontot.
7. Klicka på fliken Rad för ekonomisk dimension.
    * Dimensionerna avser endast den valda raden.    
    * Momsgruppen fylls i från kunden. Om kunden inte har en momsgrupp, används momsgruppen från huvudkontot.  
    * Artikelmomsgruppen fylls i från huvudkontot. Om huvudkontot inte har en artikelmomsgrupp, används artikelmomsgruppen i redovisningens momsparametrar.    
8. Ange ett tal i fältet Kvantitet.
    * Kvantiteten är valfri.  
9. Ange ett tal i fältet Enhetspris.
    * Enhetspriset är valfritt.  
    * Beloppet beräknas som kvantitet gånger enhetspriset. Du kan dock åsidosätta den beräkningen och ange ett belopp.  
10. Om du vill visa moms som beräknats för din faktura klickar du på Moms.
    * Visa momsbeloppen på den här sidan, eller så kan du åsidosätta beloppen på fliken Justering.  
11. Klicka på OK.
12. Klicka på Avgifter om du vill lägga till en avgift i din faktura. 
13. I fältet Kod för avgifter, skriv ett värde.
14. I fältet Avgiftsvärde, ange ett värde.
15. Stäng sidan.
16. Klicka på Summor för att visa sammanfattande fakturadetaljer och summor.
17. Klicka på Stäng.
18. Klicka på Bokför när du vill bokföra fakturan. Du kan avbryta innan du bokför.
    * Om du vill ändra timing på din fakturautskrift: Välj Aktuell om du vill skriva ut fakturor när de uppdateras eller välj Efter om du vill skriva ut när alla fakturor har uppdaterats.  
    * Om du vill ändra hur kundens kreditgräns kontrolleras innan bokföring, ändra kreditgränstypen.  
    * Välj Ja om du vill skriva ut fakturan.  
    * Välj Ja om du vill bokföra fakturan. Du kan skriva ut fakturan utan bokföring.  
19. Klicka på OK.

## <a name="copy-lines"></a>Kopiera rader
För att kopiera rader på fritextfakturan, markera en eller flera rader och välj Kopiera markerade rader. Du kan ange hur många kopior som du vill göra och du kan också kopiera anteckningar och bifogade filer. Du kan kopiera fördelningarna eller låta dem återskapas när du bokför. När du kopierar rader kan du redigera informationen efter behov. 

## <a name="create-a-free-text-invoice-from-a-template"></a>Skapa en fritextfaktura från en mall
Du kan skapa en fritextfaktura från en mall. När du väljer Ny från mall på fliken Faktura kan du välja ett mallnamn och kundkontot för den nya fritextfakturan. Du kan också välja standardvärden såsom betalningsvillkor och betalningsmetod från kunden eller använda värden som sparats med mallen. En ny fritextfaktura skapas och du kan redigera värdena i den fakturan. 


