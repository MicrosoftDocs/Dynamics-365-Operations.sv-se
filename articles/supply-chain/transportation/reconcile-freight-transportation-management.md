---
title: Stäm av frakt i transporthantering
description: Det här avsnittet ger en beskrivning av fraktavstämningsprocessen.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d523af235d645bd282af07d6a1f617bca5fba2dc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809096"
---
# <a name="reconcile-freight-in-transportation-management"></a>Stäm av frakt i transporthantering

[!include [banner](../includes/banner.md)]

Det här avsnittet ger en beskrivning av fraktavstämningsprocessen.

Fraktavstämning kan utföras manuellt eller ställas in för att utföras automatiskt. Om du vill använda automatisk fraktavstämning måste du ställa in en granskningsmall där du kan definiera kriterierna som avgör vilka fraktväxlar som matchas automatiskt.

## <a name="the-freight-reconciliation-process"></a>Fraktavstämningsprocessen

Fraktsatser beräknas med hjälp av tariffmotorer som kopplas till relevanta transportföretag. När en last bekräftas genereras en fraktsedel och fraktsatser överförs till den. Fraktsatser fördelas som tilläggsavgifter till det aktuella källdokumentet (inköpsorder, försäljningsorder och/eller överföringsorder) beroende på inställningarna som används för den vanliga faktureringsprocessen. Fraktavstämningsprocessen (som också kallas matchande processen) kan starta så snart fraktfakturan inkommer från transportföretaget. Fakturan kan tas emot elektroniskt eller som pappersfaktura. Om det är en pappersfaktura kan du generera en elektronisk faktura med hjälp av fraktsedeln som mall.

[![Fraktavstämningsprocess](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Manuell avstämning

Om du stämmer av frakten manuellt måste du matcha varje fakturarad med fraktsedelns rad eller rader för lasten som faktureras. Du utför den här matchningen på sidan **Fraktsedel och fakturamatchning**. Om beloppet på fakturaraden inte överensstämmer med beloppet på fraktsedeln måste du välja en orsak till avstämningsavvikelsen. Om det finns flera skäl för avstämning kan du dela upp omatchade belopp över dem. Avstämningsorsaken avgör hur de avvikande beloppen bokförs i redovisningen. När avstämningen av hela fakturabeloppet redovisas skickas den för godkännande och sedan bokförs.journalen. I bilden nedan visas hur du skapar en fraktfaktura och utför fraktavstämning.

[![Fraktavstämningsuppgifter](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)

## <a name="automatic-reconciliation"></a>Automatisk avstämning

Du måste ange tidsplanen för avstämning, fakturorna och vilket transportföretag som ska användas om du vill använda automatisk avstämning. Matchningen av fakturarader och fraktsedlarna utförs enligt inställningarna för granskningsmallen och fraktsedelstypen. När du har kört automatisk avstämning måste du hantera alla fakturor som systemet inte kan matcha. Du måste sedan behandla dessa fakturor manuellt innan du kan bokföra alla fakturor för betalning.

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a>Matcha fraktfakturor med fraktfakturor med automatisk eller manuell avstämning

*Matchning* är processen att hitta de fraktsedlar som motsvarar respektive fraktfaktura. Detta kan göras genom att fakturaraderna matchas en efter en (manuell matchning) eller genom att alla tillgängliga fakturor matchas samtidigt (automatchning).

### <a name="auto-matching"></a>Automatchning

När du matchar flera fraktfakturor på samma fraktsedel fungerar processen för automatchning på följande sätt:

1. Alla fraktfakturor som inte matchas sorteras efter belopp, med det största beloppet först.
1. Fraktfakturor matchas en efter en tills fraktsedeln inte har något positivt belopp kvar.
1. Beroende på inställningarna för revisionsmallen och resten av beloppet på fraktfakturor, anges resten av beloppet.

### <a name="manual-matching"></a>Manuell matchning

Alla fraktsedlar med positiva belopp går att matcha. Liknande automatchning kommer att användaren bara kunna matcha fraktfakturor med negativa belopp mot fraktsedlar som inte är helt matchade.

### <a name="example"></a>Exempel

Anta att du har en fraktsedel (FB) i beloppet 1 500 och att du har skapat tre fraktfakturor för fraktsedeln med en fakturarad för varje faktura med följande inställningar:

- Ursprunglig fraktsedel (FB): Belopp 1 500
- Faktura 1 (Inv1): Belopp 1 000
- Faktura 2 (Inv2): Belopp 600
- Faktura 3 (Inv3): Belopp -100

#### <a name="automatic-matching-result"></a>Automatiskt matchningsresultat

Automatchning utförs i följande ordning:

1. Sortera alla fraktfakturor fallande efter belopp: Inv1 -> Inv2 -> Inv3.
1. Matcha Inv1 med FB. Inv1 har 1 000 matchade och FB har 500 belopp kvar, så statusen anges till *Delvis matchad*.
1. Matcha Inv2 med FB. Inv2 har 500 matchade och FB har 0 kvar, så statusen anges till *Helt matchad*.
1. Eftersom FB nu är helt matchad kommer Inv3 inte att bearbetas.

#### <a name="manual-matching-result"></a>Manuellt matchningsresultat

För manuell matchning varierar resultaten beroende på matchningens ordning, vilket visas i följande exempel.

##### <a name="manual-matching-case-1"></a>Manuell matchning ärende 1

Ett sätt att skapa manuell matchning för det här exemplet är att fortsätta enligt följande:

1. Matcha FB med Inv1. FB har 500 matchade kvar, så statusen anges till *Delvis matchad*.
1. Matcha Inv2 med FB. Inv2 har 500 matchade och FB har 0 kvar, så statusen anges till *Helt matchad*.
1. När du matchar Inv3 manuellt hittar du inga omatchade fraktsedlar.

I det här fallet är det i grund och botten samma som automatchning

##### <a name="manual-matching-case-2"></a>Manuell matchning ärende 2

Ett sätt att skapa manuell matchning för det här exemplet är att fortsätta enligt följande:

1. Matcha Inv3 med FB. Nu har FB resterande 1 600 belopp, vilket är samma som att subtrahera negativa 100 ovanpå 1 500. Både FB och Inv3 har en matchad kvantitet på -100.
1. Matcha Inv1 och Inv 2 med FB en efter en. FB matchas fullständigt.

Som det här exemplet visar bör matchande fraktfakturor med negativa belopp endast göras manuellt. Då går det alltid att matcha fraktfakturor med negativa belopp mot en fraktsedel helt och hållet matchad eftersom du då kan styra matchningssekvensen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]