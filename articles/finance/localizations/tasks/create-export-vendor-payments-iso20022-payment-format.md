---
title: Skapa och exportera leverantörbetalningar med ett ISO20022-betalningsformat
description: Den här proceduren visar hur du kan skapa betalningsrader i leverantörbetalningsjournalen och generera en leverantörbetalningsfil med ett ISO2022-kreditöverföringsexempel.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c3d538a4e032ca9cfafff3232ad235019654ed7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231486"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Skapa och exportera leverantörsbetalningar med ett ISO20022-betalningsformat

[!include [banner](../../includes/banner.md)]

Det här avsnittet förklarar hur du kan skapa betalningsrader i leverantörbetalningsjournalen och generera en leverantörbetalningsfil med ett ISO2022-kreditöverföringsexempel.

Detta är den femte proceduren av fem som illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer. Använd demonstrationsdataföretaget DEMF för att slutföra det här exemplet.

## <a name="example"></a>Exempel

1.    Gå till **Leverantörsreskontra > Betalningar > Betalningsjournal.**
2.    Klicka på **Ny**.
3.    I fältet **Namn** anger eller väljer du ett värde.
4.    Klicka på **Rader > Betalningsförslag > Skapa betalningsförslag**.
5.    Expandera avsnittet **Poster som ska ingå**.
6.    Klicka på **Filter**.
7.    I listan markerar du raden för **leverantörsregister** och **fältet för leverantörskonto**.
8.    I fältet **Kriterier** anger du eller väljer ett värde. Du kan använda vissa kriterier för urval av leverantörstransaktioner för betalning ‒ för detta exempel, använd DE-001 som leverantörskonto.
12.    Klicka på **OK**.
13.    Klicka på **OK**.
14.    Klicka på **Skapa betalningar.**
15. Skapa en ISO20022-betalningsfil
    1.    Klicka på **Generera betalningar**
    2.    I fältet **Betalningsmetod** anger du eller väljer ett värde.
    3.    I fältet **Filnamn** anger du eller väljer ett värde. I det här exemplet på grund av betalningar i EUR blir den genererade filen SEPA-kompatibel. ISO20022 kreditöverföring samt andra leverantörsbetalningsformat kan också användas för att generera betalningar i andra valutor.
    4.    I fältet **Bankkonto** anger du eller väljer ett värde.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]