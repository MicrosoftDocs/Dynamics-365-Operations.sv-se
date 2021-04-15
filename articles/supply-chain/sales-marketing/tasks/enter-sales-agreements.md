---
title: Ange försäljningsavtal
description: I det här avsnittet visas hur du skapar en försäljningsavtal där en av dina kunder åtar sig att köpa en produkt för ett avtalat belopp över tid i utbyte mot speciella rabatter.
author: omulvad
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm, SalesAgreementCustomerReferencesPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Service industries
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 675eeda04880601f0261c6ae5e5a49de38f75a7c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810856"
---
# <a name="enter-sales-agreements"></a>Ange försäljningsavtal

[!include [banner](../../includes/banner.md)]

I det här avsnittet visas hur du skapar en försäljningsavtal där en av dina kunder åtar sig att köpa en produkt för ett avtalat belopp över tid i utbyte mot speciella rabatter. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.


## <a name="set-up-sales-agreement-header"></a>Ställ in försäljningsavtalshuvudet
1. I navigeringsfönstret, gå till **Moduler > Försäljning och marknadsföring > Försäljningsavtal > Försäljningsavtal**.
2. Välj **Ny**.
3. I fältet **Kundkonto** välj önskad post i den nedrullningsbara menyn.
4. I fältet **Klassificering av försäljningsavtal** välj önskad post i den nedrullningsbara menyn.
5. Expandera den **allmänna** delen.
6. I fältet **Standardutfästelse**, välj **Utfästelse för produktvärde**. En utfästelsetyp är ett obligatoriskt kriterium som du måste tilldela till avtalet för att definiera hur avtalskontraktet uppfylls. De fyra fördefinierade typer kan du ställa in kundens åtagande mål, uttryckt som en kvantitet eller ett värde. Kvantitetutfästelsetypen kan endast tillämpas på en specifik produkt, men de hierarkibaserade typerna kan användas för både försäljning och icke-specifika produkter.  
7. I fältet **Utgångsdatum**, ange datumet till ett framtida datum när du vill att avtalet ska upphöra.
8. Välj **OK**.

## <a name="set-up-product-value-commitment-lines"></a>Ställ in utfästelserader för produktvärde
1. Välj **Markera rad**.
2. I fältet **Artikelnummer** välj önskad post i den nedrullningsbara menyn. Typen av åtagande som du har valt för avtalet påverkar den typ av information som du kan ange för avtalsraderna. För exempelvis en värde-baserade avtal måste du ange det totala nettobeloppet (i den överenskomna valuta) för vilken kunden förbinder sig att köpa varor från dig. I det här exemplet är fälten **Kvantitet** och **Enhet** på raden inte tillgängliga eftersom du skapar ett avtal för att kunden om att köpa för ett visst värde av en produkt.   
3. I fältet **Nettobelopp**, ange penningbeloppet som kunden har åtagit sig att köpa för.
4. I fältet **Rabatt i procent**, ange en procentsats som ska användas för kundens försäljningsorderrader, som är kopplade till detta avtal.
5. Visa avsnittet **Raddetaljer**.
6. Välj **Ja** i fältet **Max framtvingas**.
    - Om du väljer **Max framtvingas** innebär att det totala beloppet för alla försäljningsorderrader som använder utfästelsens särskilda priser, rabatter och/eller betalningsvillkor inte får överstiga beloppet som anges på utfästelsen.  
    - Minsta och högsta frisläppningsbeloppen anger ett värdeintervall som måste säljas på varje försäljningsorder som använder det valda avtalet.   
7. Expandera avsnittet **Försäljningsavtalshuvud**. Om inte status för avtalet är **Giltig**, beställningar kan inte associeras med avtalet och kan därför inte bidra till uppfyllandet av avtalet. Du kan ändra status manuellt i detta skede. Emellertid ändras statusen normalt när du bekräftar avtalet för kunden.  
8. Välj **Försäljningsavtal** i åtgärdsfönstret.
9. VäljSelect **Bekräftelse**. Se till att alternativet **Markera avtal som giltigt** har inställningen **Ja**.  
10. Välj **Ja** i fältet **Skriv ut rapport**.
11. Välj **OK**.
12. Stäng sidan. Avtalet är nu giltigt. Du kan börja att länka kundens order till avtalet för att motboka mot det utfästa målet.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]