---
title: Skapa en fritextfaktura
description: Det här avsnittet innehåller information om hur du skapar fritextfakturor.
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 1ac06e7d702ffe3a8cdb6bd2823f2ffdc055c722
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447875"
---
# <a name="create-a-free-text-invoice"></a>Skapa en fritextfaktura

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om hur du skapar fritextfakturor. För den här proceduren använder du demonstrationsföretaget **USMF**.

## <a name="create-a-free-text-invoice"></a>Skapa en fritextfaktura

1. Gå till **Kundreskontra \> Fakturor \> Alla fritextfakturor**.
2. Markera **Nytt**.
3. Välj ett värde i fältet **Kundkonto**.

    * Som standard används kontot som valts som kundkonto som fakturakonto.
    * Om fakturan inte bokförts börjar redovisningsstatusen med **Pågår**.
    * Fakturanumret tilldelas när fakturan bokförs.
    * Om du använder SEPA-debitering (Single Euro Payments Area) fylls autogiromedgivandet i automatiskt när du väljer kundkontot.

4. I fältet **Beskrivning** anger du ett värde.
5. I fältet **Huvudkonto** anger du ett kontonummer utan dimensioner. Du anger dimensioner längre fram i det här avsnittet.

    Du kan även ange ett eller flera tecken för huvudkontot och använda sökning för att hitta kontot.

6. Välj snabbfliken **Radinformation** så att du kan lägga till dimensioner i huvudkontot.
7. Välj fliken **Rad för ekonomisk dimension**.

    * Dimensionerna avser endast den valda raden.
    * Momsgruppen fylls i av kunden. Om kunden inte har någon momsgrupp, används momsgruppen från huvudkontot.
    * Artikelmomsgruppen fylls i från huvudkontot. Om huvudkontot inte har en artikelmomsgrupp, används artikelmomsgruppen som anges i redovisningens momsparametrar.

8. Valfritt: I fältet **Kvantitet** anger du ett nummer.
9. Valfritt: Ange ett nummer i fältet **Enhetspris.**

    Beloppet beräknas som kvantitet gånger enhetspriset. Du kan dock åsidosätta den beräkningen genom att ange ett belopp.

10. Välj **Moms** för att visa momsen som beräknas för den fakturan.

    Visa momsbeloppen på den här sidan, eller så kan du åsidosätta beloppen på fliken **Justering**.

11. Välj **OK**.
12. Klicka på **Avgifter** om du vill lägga till en avgift i din faktura.
13. Ange ett värde i fältet **Kod för avgifter**.
14. Ange ett nummer i fältet **Avgiftsvärde**.
15. Stäng sidan.
16. Välj **Summor** för att visa sammanfattande fakturadetaljer och summor.
17. Välj **Nära**.
18. Välj **Bokför** för att bokföra fakturan. Du har fortfarande möjlighet att avbryta innan du bokför.

    * DU kan ändra tidmätning för din fakturautskrift. Välj **Aktuell** om du vill skriva ut fakturor när de uppdateras. Välj **Efter** om du vill skriva ut när alla fakturor har uppdaterats.
    * Om du vill ändra hur kundens kreditgräns kontrolleras innan fakturan bokförs kan du ändra värdet i fältet **kreditgränstyp**.
    * Om du vill skriva ut fakturan, ange alternativet till **Ja**.
    * Om du vill bokföra fakturan, ange alternativet till **Ja**. Du kan skriva ut fakturan utan att bokföra den.

19. Välj **OK**.

## <a name="copy-lines"></a>Kopiera rader
För att kopiera rader på fritextfakturan, markera en eller flera rader och välj **Kopiera markerade rader**. Du kan ange hur många kopior som du vill göra och du kan också kopiera anteckningar och bifogade filer. Du kan antingen kopiera fördelningarna eller låta dem återskapas när du bokför.

När du kopierar rader kan du redigera informationen efter behov.

## <a name="create-a-free-text-invoice-from-a-template"></a>Skapa en fritextfaktura från en mall
Du kan skapa en fritextfaktura från en mall. När du väljer **Ny från mall** på fliken **Faktura** kan du välja ett mallnamn och kundkontot för den nya fritextfakturan. Standardvärden, till exempel betalningsvillkor och betalningsmetod, kan fyllas i automatiskt från kunden, eller du kan använda de värden som sparades i mallen.

En ny fritextfaktura skapas och du kan redigera värdena som du vill.
