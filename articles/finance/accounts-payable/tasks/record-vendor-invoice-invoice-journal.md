---
title: Registrera en leverantörsfaktura i fakturajournalen
description: Den här uppgifthandboken visar hur du registrerar leverantörsfakturor som inte är kopplade till inköpsorder.
author: abruer
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35862195f3c2c13711157be919956f40fea0989b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820651"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Registrera en leverantörsfaktura i fakturajournalen

[!include [banner](../../includes/banner.md)]

Den här uppgifthandboken visar hur du registrerar leverantörsfakturor som inte är kopplade till inköpsorder. Exempel på den här typen av faktura omfattar utgifter för förrådsartiklar och tjänster.  I den här registreringen används demonstrationsföretaget USMF.

1. Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Arbetsytor > Leverantörsfakturapost**.
2. Klicka på **Ny fakturajournal** i **Åtgärdsfönstret**.
3. Klicka på **Ny**.
4. Ange journalnamnet eller klicka på den nedrullningsbara knappen i fältet **Namn** för att öppna sökningen.
5. I fältet **Beskrivning** anger du ett värde.
6. Klicka på **Rader** i **åtgärdsfönstret**. Ange bokföringsdatum som ska uppdatera redovisningen i fältet **Datum**.  
7. Ange **leverantörskontot** i fältet **Konto**.
8. Ange fakturanumret i fältet **Faktura**.
9. I fältet **Beskrivning** anger du ett värde.
10. I fältet **Kredit** väljer du ett tal.
11. Ange kontonumret  eller klicka på den nedrullningsbara knappen i fältet **motkonto** för att öppna sökningen.
    * **Momsgruppen** får sin standard från leverantörskontot.  
    * **Artikelmomsgruppen** får sin standard från huvudkontot som anges i fältet **motkonto**.  
    * **Förfallodatumet** beräknas utifrån betalningsvillkoren.  
    * **Kassarabatt** får sin standard från leverantörskontot.
12. Om du har aktiverat arbetsflöde för leverantörsfakturajournal klickar du på **Arbetsflöde > Skicka**.
    * När det inskickade materialet godkänns kommer datumet att tidigareläggas till den första dagen i nästa öppna period om transaktionens bokföringsdatum infaller inom en period som har stoppats eller stängts för redovisningsbokföring.
12. Klicka på **Bokför**.
13. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]