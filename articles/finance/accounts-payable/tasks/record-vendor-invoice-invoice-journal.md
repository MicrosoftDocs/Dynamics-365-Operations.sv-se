---
title: Registrera en leverantörsfaktura i fakturajournalen
description: Den här uppgifthandboken visar hur du registrerar leverantörsfakturor som inte är kopplade till inköpsorder.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 97dd03a96389ab22e441acd0af1ad35852570be4
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180027"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Registrera en leverantörsfaktura i fakturajournalen

[!include [task guide banner](../../includes/task-guide-banner.md)]

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
12. Klicka på **Bokför**.
13. Stäng sidan.

