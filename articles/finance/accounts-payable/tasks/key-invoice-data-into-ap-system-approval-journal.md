---
title: Mata in fakturadata i leverantörsreskontra genom att använda en godkänd journal
description: Det här avsnittet visas hur du använder fakturaregister om du vill skapa fakturor och sedan använda godkännandejournalen för att uppdatera utgiftskontona.
author: abruer
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f0fee32d9fd1ab89b1a8cedb2e1965674586d4e7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227194"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>Mata in fakturadata i leverantörsreskontra genom att använda en godkänd journal

[!include [banner](../../includes/banner.md)]

Det här avsnittet visas hur du använder fakturaregister om du vill skapa fakturor och sedan använda godkännandejournalen för att uppdatera utgiftskontona.

## <a name="create-and-post-and-invoice"></a>Skapa och bokför och fakturera
1. I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturaregister**.
2. Välj **Ny**.
3. Välj namnet på det fakturaregister som du vill använda.
4. Välj **Rader** om du vill öppna registret och ange utgiftsrader.
5. Välj en leverantör. Ange eller välj `US-104`, till exempel
6. Ange ett värde i fältet **Faktura**.
7. I fältet **Beskrivning** anger du ett värde.
8. I fältet **Kredit** väljer du ett tal.
9. I fältet **Godkänd av** väljer du en godkännare i den nedrullningsbara menyn.
10. Vald **bokföring**

## <a name="approve-an-invoice"></a>Godkänn en faktura
1. I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturagodkännande**.
2. Välj **Ny**.
3. Välj namnet på fakturagodkännandejournalen som du vill använda.
4. Klicka på **Rader** om du vill visa en sida där du kommer att vara i stånd till att välja fakturorna, som du vill godkänna.
5. Välj **Sök efter verifikationer** om du vill visa alla fakturor som är klara för godkännande.
6. Markera fakturan du skapat och klicka sedan på **Välj.** Verifikationerna, som du valde ovan, flyttas till listan när du har markerat dem.  
7. Välj **OK**.
8. Välj **kontonummerfältet** om du vill lägga till ett utgiftskonto i fakturan.
9. Ange ett kontonummer och gå till nästa fält. Ange exempelvis `600120`.
10. Vald **bokföring**
11. Välj **Verifikation** om du vill visa poster som bokfördes. Kontot för godkännande av pågående fakturor motbokas och ersätts med det verkliga utgiftskontot.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]