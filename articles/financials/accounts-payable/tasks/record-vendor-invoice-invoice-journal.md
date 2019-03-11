---
title: Registrera en leverantörsfaktura i fakturajournalen
description: Den här uppgifthandboken visar hur du registrerar leverantörsfakturor som inte är kopplade till inköpsorder.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 775f3764d34cecbfc071ff7420d32c7832b42308
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "348950"
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

