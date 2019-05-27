---
title: Ställa in försändelse
description: Det här avsnittet beskriver hur du konfigurerar inkommande försändelselageroperationer.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 24500ff46cc77ca8fa59c0c16427d9f05f33a87e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550038"
---
# <a name="set-up-consignment"></a>Ställa in försändelse

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du konfigurerar inkommande försändelselageroperationer.

Försändelselagret är lager som ägs av en leverantör, men som lagras på din site. När du är klar att förbruka eller använda lagret, tar du över ägarskapet för lagret. I det här avsnittet beskrivs de inställningar som krävs för att aktivera försändelseprocesser. Mer information om hur du ställer in försändelseprocesser hittar du på [Försändelse](consignment.md).

## <a name="inventory-owners"></a>Lagerägare
Om du vill registrera det fysiska inkommande försändelselagret måste du definiera en leverantörsägare. Detta görs på sidan **Lagerägare**. När du väljer ett **Leverantörskonto** genererar detta förvalda värden för fälten **Namn** och **Ägare**. Värdet i fältet **Ägare** visas för leverantören, så du kanske vill ändra det om ditt leverantörkontonamn inte är svårt för externa kontakter att känna igen. Det är möjligt att redigera fältet **Ägare**, men bara fram till den punkt när du sparar posten **Lagerägare**. Fältet **Namn** fylls i med namnet på den part som leverantörskontot är kopplat till och detta kan inte ändras.

[![lagerägare](./media/inventory-owners.png)](./media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>Spårningsdimensionsgrupp
Artiklar som ska användas i försändelseprocesser, måste associeras med en **Spårningsdimensionsgrupp** där dimensionen **Ägare** är inställd på **Aktiv**. Dimensionen Ägare har alltid alternativen **Fysiskt lager** och **Ekonomiskt lager** markerade. **Disponera per dimension** markeras aldrig.

[![spårningsdimensionsgrupp](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)

## <a name="inventory-ownership-change-journal"></a>Journal för lagerägarskapsändring
Journalen **Lagerägarskapsändring**används till att bokföra överföringen av ägandeskap av försändelselager från leverantören till den nuvarande juridisk person som förbrukar den. Till skillnad från lagerjournal måste den identifieras med ett Lagerjournalnamn. Dessa namn skapas på sidan **Lagerjournalnamn** och **Journaltyp** måste ställas in på **Ägarskapsändring**.

[![journal-för-lagerägarskapsändring](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Leverantörssamarbete i försändelseprocesser
Om dina leverantörer använder leverantörsamarbetesgränssnittet, kan du använda det för att övervaka förbrukningen av lager på din site. Mer information finns i [Konfigurering av säkerhet för leverantörssamarbetesanvändare](../procurement/configure-security-vendor-portal-users.md).
