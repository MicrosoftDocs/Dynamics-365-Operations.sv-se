---
title: Tilldela en fritextfakturamall till en kund
description: Denna uppgift visar hur du tilldelar en fritextfakturamall till en kund.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d9535a4678ea0c68227a54cf3c5d1b06b116a288
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180012"
---
# <a name="assign-free-text-invoice-template-to-a-customer"></a>Tilldela en fritextfakturamall till en kund

[!include [task guide banner](../../includes/task-guide-banner.md)]

Denna uppgift visar hur du tilldelar en fritextfakturamall till en kund. I denna uppgift används USMF-demonstrationsföretaget och är avsett för den användare som ansvarar för hantering och bearbetning av kundreskontrafakturor.

1. I **navigeringsfönstret** går du till **Moduler > Kundreskontra > Kunder > Alla kunder**.
2. Hitta och markera önskad post i listan.
3. Klicka på **Faktura** i **åtgärdsfönstret**.
4. Klicka på **Återkommande fakturor**. Använd den här sidan för att tilldela fritextfakturamallar till kunder och ange hur ofta fakturor ska skickas till kunden.  
5. Klicka på **Ny** för att tilldela en ny mall till kunden.
6. I fältet **Mall**, välj den fritextfakturamall som du vill tilldela till kunden.
7. Hitta och markera önskad post i listan.
8. Klicka på länken på den valda raden i listan.
9. I fältet **Faktureringsstartdatum**, ange datumet när den första fakturan ska genereras.
10. I avsnittet **Avsluta upprepning** anger du ett slutdatum för upprepning.  
    * Välj något av följande: Inget slutdatum – Fakturor skapas utan tidsgräns tills mallen tas bort från kundkontot.
    * Faktureringsslutdatum – Välj det här alternativet för att ange för att ange det senaste datum då fakturan kan genereras.  
11. I fältet **Högsta ackumulerat belopp** anger du det högsta ackumulerade belopp efter vilket fakturangenereringen ska stoppas. Ange det maximala ackumulerade belopp som kan uppnås med den valda mallen. Om du till exempel anger 1 000,00 och genererar månatliga fakturor för 100,00 styck, kommer fakturor att upphöra att skapas efter att den tionde fakturan har genererats.  
12. I avsnittet **Skapa återkommande fakturor genom att använda standardvärdena från** väljer du fritextfakturamallen eller kundkontot. Välj om du vill använda fritextfakturamallen eller kundkontot för att bestämma standardvärdena för språk, bokföringsprofil, momsgrupp, artikelmomsgrupp, listkod, land/region för leveransen, valuta, betalningsvillkor, betalningsmetod, betalningsspecifikationer, betalningsplan, kassarabatt, ekonomiska dimensioner och gireringsblankett när fakturor skapas.  
13. I fältet **Upprepningsmönster**, välj upprepningsmönstret.
    + Dagligen – Ange det här alternativet och ange antalet dagar i fältet Per. Om du till exempel anger 15, kommer en faktura skapas var 15:e dag för den här kunden.
    + Varje vecka - Välj det här alternativet och ange antalet veckor i fältet Per. Om du till exempel anger 2, kommer en faktura skapas varannan vecka för den här kunden.
    + Varje månad - Välj det här alternativet och ange antalet månader i fältet Per. Om du till exempel anger 6, kommer en faktura skapas var sjätte månad för den här kunden.
    + Årligen - Välj det här alternativet och ange antalet år i fältet Per. Om du till exempel anger 2, kommer en faktura skapas vartannat år för den här kunden.  
14. I fältet **Per**, ange en siffra.

