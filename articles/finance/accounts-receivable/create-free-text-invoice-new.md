---
title: Skapa en fritextfaktura
description: Det här avsnittet innehåller information om hur du skapar fritextfakturor.
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 6e9578d9b2d61f241ab5e92fc9740b88b80969f6
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2022
ms.locfileid: "8392895"
---
# <a name="create-a-free-text-invoice"></a>Skapa en fritextfaktura

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om hur du skapar fritextfakturor. För den här proceduren använder du demonstrationsföretaget **USMF**.

## <a name="create-a-free-text-invoice"></a>Skapa en fritextfaktura

1. Gå till **Kundreskontra (eller försäljningsredovisning) \> Fakturor \> Alla fritextfakturor**.
2. Välj **Ny**.
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
    * Du kan välja att stoppa bokföring av fritextfakturor när dett fel uppstår på fliken **Uppdateringar** på sidan **Parametrar för kundreskontra** (**Kundreskontra > Inställningar > Parametrar för kundreskontra**). Välj **Ja** för parametern **Stoppa bokföring av fritextfakturor vid första fel** om du vill stoppa bokföringen av fritextfakturor när ett fel inträffar. Om du bokför i batch stoppar ett fel bokföringsprocessen och batchstatusen anges som **Fel**. Om det här alternativet inte markeras hoppar bokföringsprocessen över en faktura med ett bokföringsfel och fortsätter bokföra ytterligare fakturor. Om du bokför i batch hindrar inte ett bokföringsfel andra fakturor från att bokföras. Batchstatusen blir **Avslutad**. En detaljerad bokföringsprocessrapport finns tillgänglig för granskning i batchjobbhistoriken.
    * Om du vill skriva ut fakturan, ange alternativet till **Ja**.
    * Om du vill bokföra fakturan, ange alternativet till **Ja**. Du kan skriva ut fakturan utan att bokföra den.

19. Välj **OK**.

## <a name="copy-lines"></a>Kopiera rader
För att kopiera rader på fritextfakturan, markera en eller flera rader och välj **Kopiera markerade rader**. Du kan ange hur många kopior som du vill göra och du kan också kopiera anteckningar och bifogade filer. Du kan antingen kopiera fördelningarna eller låta dem återskapas när du bokför.

När du kopierar rader kan du redigera informationen efter behov.

## <a name="create-a-free-text-invoice-from-a-template"></a>Skapa en fritextfaktura från en mall
Du kan skapa en fritextfaktura från en mall. När du väljer **Ny från mall** på fliken **Faktura** kan du välja ett mallnamn och kundkontot för den nya fritextfakturan. Standardvärden, till exempel betalningsvillkor och betalningsmetod, kan fyllas i automatiskt från kunden, eller du kan använda de värden som sparades i mallen.

En ny fritextfaktura skapas och du kan redigera värdena som du vill.

## <a name="resetting-the-workflow-status-for-free-text-invoices-from-unrecoverable-to-draft"></a>Återställer arbetsflödesstatus för fritextfakturor från Oåterkallelig till Utkast
En arbetsflödesinstans som har stoppats på grund av ett oåterkalleligt fel får arbetsflödesstatusen **oåterkalleligt**. När statusen för ett arbetsflöde för fritextfakturor för kund är **Oåterkalleligt** kan du återställa den till **Utkast** genom att välja **Återkalla** bland åtgärderna för arbetsflöde. Du kan sedan redigera kundens fritextfaktura. Den här funktionen är tillgänglig om parametern **Återställa arbetsflödesstatus för fritextfakturor från Oåterkalleligt till Utkast** på sidan **Funktionshantering** är aktiverad.

På sidan **Arbetsflödeshistorik** för leverantörsfakturor kan du återställa arbetsflödesstatusen till **utkast**. Du kan öppna den här sidan från **Fritextfaktura** eller från navigeringen **Allmänt > Förfrågningar > Arbetsflöde**. Om du vill återställa arbetsflödesstatus **utkast**, välj **återkalla**. Du kan också återställa arbetsflödesstatusen till **Utkast** genom att välja åtgärden **Återkalla** på sidan **Fritextfaktura** eller sidan **Alla fritextfakturer**. När arbetsflödesstatusen har återställts till **Utkast** blir den tillgänglig för redigering på sidan **Fritextfaktura**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
