---
title: Du kan inte bekräfta en försändelse på grund av att arbetet inte är slutförd eller saknas
description: Du kan inte bekräfta en försändelse på grund av att arbetet inte är slutförd eller saknas
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: beef0909d41e69f3e7bcc1021527be35b7e6fd44
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123853"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a>Du kan inte bekräfta en försändelse på grund av att arbetet inte är slutförd eller saknas

Felkod: WAX515

## <a name="symptoms"></a>Symtom

När du försöker bekräfta en leverans visas följande felmeddelande i systemet:

> Det gick inte att bekräfta leveransen av lasten %1 eftersom alla arbetsuppgifter för lasten måste slutföras.

Du kan därför inte bekräfta leveransen för beläggningen.

## <a name="cause"></a>Orsak

Beläggningen eller leveransen befinner sig för närvarande i ett skick där leveransbekräftelsen misslyckas. Innan du kan bekräfta leveransen måste det minst finnas arbete för beläggningen, och allt detta arbete måste ha statusen *Stängd* eller *Annullerad*.

## <a name="resolution"></a>Upplösning

Kontrollera relaterade försäljnings- eller överföringsorder för beläggningen eller försändelsen, och se till att allt relaterat arbete har slutförts eller annullerats.

Du kan arbeta med försändelser och beläggningar på flera sidor. Följande delavsnitt ger några exempel.

### <a name="all-loads-page"></a>Sida för samtliga beläggningar

1. Gå till **Lagerstyrning \> Laster \> Alla laster**.
1. Välj den beläggning som leveransen inte kan bekräftas för.
1. I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.
1. Inspektera statusen för respektive arbets-ID. Följ upp varje arbets-ID som inte har statusen *Stängd* eller *Annullerad*.
1. Om varje arbets-ID har statusen *Stängd* eller *Annullerad* ska du försöka igen för att bekräfta försändelsen.

### <a name="all-shipments-page"></a>Sida för alla leveranser

1. Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.
1. Välj den försändelse som inte kan bekräftas.
1. I åtgärdsfönstret, på fliken **Försändelser**, i gruppen **Arbete**, väljer du **Arbetsdetaljer**.
1. Inspektera statusen för respektive arbets-ID. Följ upp varje arbets-ID som inte har statusen *Stängd* eller *Annullerad*.
1. Om varje arbets-ID har statusen *Stängd* eller *Annullerad* ska du försöka igen för att bekräfta försändelsen.

### <a name="all-work-page"></a>Sia för alla arbeten

1. Gå till **Lagerstyrning \> Arbete\> Allt arbete**.
1. Välj arbetet för det ordernummer som försändelsen inte kan bekräftas för.
1. I åtgärdsfönstret: På fliken **Försändelse**, i gruppen **Försändelse**, väljer du **Bekräfta försändelse**.
1. Inspektera statusen för respektive arbets-ID. Följ upp varje arbets-ID som inte har statusen *Stängd* eller *Annullerad*.
1. Om varje arbets-ID har statusen *Stängd* eller *Annullerad* ska du försöka igen för att bekräfta försändelsen.
