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
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 42f93e6d8fcf62babc3e3244bc1fe76d1efd9d13
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Registrera en leverantörsfaktura i fakturajournalen

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


