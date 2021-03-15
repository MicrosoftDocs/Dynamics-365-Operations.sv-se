---
title: Skapa och bearbeta en överensstämmelse
description: Det här avsnittet förklarar hur du utför avvikelsehantering baserat på en befintlig kvalitetsorder.
author: perlynne
manager: tfehr
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4525e79cb388cc9bbcfe1d038a53cf53916a678c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008110"
---
# <a name="create-and-process-a-conformance"></a>Skapa och bearbeta en överensstämmelse

[!include [banner](../../includes/banner.md)]

Det här avsnittet förklarar hur du utför avvikelsehantering baserat på en befintlig kvalitetsorder. Du kan köra denna registrering i USMF-demonstrationsföretaget och kan använda det föreslagna värdet. Vanligtvis utförs den här proceduren av en kontorist.  Slutför först instruktionerna i [Kontrollera kvaliteten på varor](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md). För att bearbeta godkännandet av en avvikelse måste användaren som utför uppgiftsregistreringen ha ett "namn"-värde tilldelat på användarsidan. För att använda dokumentanteckningar måste användaren även ha Dokumenthantering aktiverat i användaralternativen.


## <a name="select-a-quality-order"></a>Välj en kvalitetsorder.
1. I navigeringsfönstret gå till **Moduler > Lagerhantering > Periodiska uppgifter > Kvalitetshantering > Kvalitetsorder**.
2. I listan, välj kvalitetsordern som skapades i [Kontroller kvaliteten på varor](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).  

## <a name="create-a-nonconformance"></a>Skapa en avvikelse
1. Välj **Förfrågningar** i åtgärdsfönstret.
2. Välj **Avvikelser**.
3. Välj **Ny**.
4. Välj det problem som hittades under inspektionsprocessen på den nedrullningsbara menyn i fältet **Problemtyp**.  
5. Välj **OK**.

## <a name="approvereject-a-nonconformance"></a>Godkänn/avvisa en avvikelse
1. Välj **Funktioner**.
2. Välj **Godkänn avvikelsen**. I detta exempel godkänner du avvikelsen. Godkända avvikelser kan associeras med tillhörande åtgärder om du vill registrera arbete som utförs som en del av avvikelsehanteringen och, som i det här avsnittet, bearbetningen av korrigeringshanteringen.  
3. Välj **Ja**.

## <a name="create-a-correction-action"></a>Skapa en korrigeringsåtgärd
1. Välj **Korrigeringar**.
2. Välj **Ny**.
3. I fältet **Personalnummer** för den nya raden väljer du den önskade posten från den nedrullningsbara menyn.
4. Klicka på **Välj**.
5. Välj **Bifoga**. Skapa en notering om korrigeringen. För det här exemplet är åtgärden att kontakta leverantören för att diskutera avvikelsen.  
6. Välj **Ny**.
7. Välj **Notering**. Beroende på rapportinställningarna, olika dokumenttyper kan skrivas ut på rapporter som är relaterade till avvikelsehanteringen.  
8. I fältet **Beskrivning** anger du ett värde.
9. Stäng sidan.

## <a name="maintain-a-correction"></a>Underhåll en korrigering
1. Välj **Markera som slutförd**.
2. Välj **OK**.
3. Stäng sidan.

## <a name="close-a-nonconformance"></a>Stäng en avvikelse
1. Välj **Funktioner**.
2. Välj **Stäng avvikelsen**.
3. Välj **Ja**.
4. Stäng sidorna.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]