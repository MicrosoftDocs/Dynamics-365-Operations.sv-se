--- 
title: "Registrera en leverantörsfaktura i fakturajournalen"
description: "Den här uppgifthandboken visar hur du registrerar leverantörsfakturor som inte är kopplade till inköpsorder."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 127875443da1d43783440083b11afd423f2a12fe
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Registrera en leverantörsfaktura i fakturajournalen

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här uppgifthandboken visar hur du registrerar leverantörsfakturor som inte är kopplade till inköpsorder. Exempel på den här typen av faktura omfattar utgifter för förrådsartiklar och tjänster.  I den här registreringen används demonstrationsföretaget USMF.

1. Gå till Leverantörsreskontra > Arbetsytor > Leverantörsfakturaregistrering.
2. Klicka på Ny fakturajournal.
3. Klicka på Ny.
4. Ange journalnamnet eller klicka på den nedrullningsbara knappen i fältet Namn för att öppna sökningen.
5. Ange ett värde i fältet Beskrivning.
6. Klicka på Rader.
    * Ange bokföringsdatum som ska uppdatera redovisningen i datumfältet.  
7. Ange leverantörskontot i fältet Konto.
8. Ange fakturanumret i fältet Faktura.
9. Skriv ett värde i fältet Beskrivning.
10. Välj ett tal i fältet Kredit.
11. Ange kontnumret eller klicka på den nedrullningsbara knappen i motkontofältet för att öppna sökningen.
    * Momsgruppen får sin standard från leverantörskontot.  
    * Artikelmomsgruppen får sin standard från huvudkontot som anges i motkontofältet.  
    * Förfallodatumet beräknas utifrån betalningsvillkoren.  
    * Kassarabatt får sin standard från leverantörskontot.  
12. Klicka på Bokför.
13. Stäng sidan.


