---
title: Visuell och samarbetsinriktad körning
description: I den här artikeln beskrivs hur du övervakar din efterfrågebaserade materialbehovsplanerings (Demand Driven Material Requirements Planning, DDMRP) avdelningspunkter, buffertzoner, planerade order och historik.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqDDMRPWorkspace, ReqDecouplingPointsStatusByNetFlow, ReqDecouplingPointStatusByOnHand, ReqPlannedOrderForm, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: ce32a4449da8e85f958f212f2c2dfd2841ca6887
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740834"
---
# <a name="visual-and-collaborative-execution"></a>Visuell och samarbetsinriktad körning

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

I den här artikeln beskrivs hur du övervakar din efterfrågebaserade materialbehovsplanerings (Demand Driven Material Requirements Planning, DDMRP) avdelningspunkter, buffertzoner, planerade order och historik.

## <a name="visually-track-buffers-and-quantities-for-a-selected-item"></a>Spåra buffertar och kvantiteter visuellt för en vald artikel

I Microsoft Dynamics 365 Supply Chain Management kan du visuellt spåra hur buffertar, lagerhållningskvantiteter och nettoflödesnivåer ändras över tid för en viss vald, frisläppt produkt. Följ de här stegen när du vill öppna och granska diagrammen.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj en frisläppt artikel som har konfigurerats som en avdelningspunkt. (Mer information finns i [Lagerplacering](ddmrp-inventory-positioning.md).)
1. I åtgärdsfönstret, på fliken **Plan**, väljer du **Artikeldisponering**.
1. På sidan **Artikeldisponering** väljer du en post för artikeldisponering som skapar en avdelningspunkt. (Den här posten visar namnet på en disponeringsgrupp som har konfigurerats för att skapa avdelningspunkter.)
1. Välj fliken **Behållning**. På den här fliken visas ett diagram som visar hur lagerbehållningskvantiteter ändras över tiden, tillsammans med värdet på lagerbehållningsnivån som registreras för en viss period varje gång huvudplaneringen körs. Fliken innehåller även en tabell som visar vilken av följande kategorier som respektive registrerad behållningsnivå hamnar i:

    - **Kritiskt låg** – Mindre än hälften av minimum för perioden.
    - **Låg** – Mellan minimum och minimum.
    - **Genomsnittlig behållning** – Mellan minimum och minimum plus den gröna zonen.
    - **Högre än genomsnittet** – Högre än genomsnittet.

    ![Historiska nivåer av behållning på fliken Behållning.](media/ddmrp-on-hand-graph.png "Historiska behållningsnivåer på fliken Behållning")

    > [!NOTE]
    > Färgerna som används på fliken **Behållning** representerar andra intervall än de liknande färger som används på fliken **Buffertvärden**.

1. Om du vill visa hur dina buffertvärden förändrat över tid och hur de kan jämföras med nivåer för behållning och nettoflöde, väljer du fliken **Buffertvärden**.

    ![Historiska nivåer för behållning och nettoflöde på fliken Buffertvärden.](media/ddmrp-buffer-values-graph.png "Historiska nivåer för behållning och nettoflöde på fliken Buffertvärden")

## <a name="track-the-status-and-planned-orders-for-all-decoupling-points"></a>Spåra status och planerade order för alla avdelningspunkter

Arbetsytan **Efterfrågestyrd MRP** innehåller flera verktyg tillsammans med KPI:er (Key Performance Indicators) samt översikter över statusen för dina avdelningspunktsartiklar och relaterade planerade order. Du öppnar den genom att gå till **Huvudplanering \> Arbetsytor \> Efterfrågestyrd MRP**.

![Efterfrågestyrd MRP-arbetsyta](media/ddmrp-workspace.png "Efterfrågestyrd MRP-arbetsyta")

## <a name="get-overviews-of-decoupling-points-and-planned-orders"></a>Få översikter över avdelningspunkter och planerade order

Förutom den **efterfrågestyrda MRP-arbetsytan** innehåller Supply Chain Management flera sidor där du kan visa information om dina DDMRP-inställningar, avdelningspunkter samt planerade order. Vissa av dessa sidor har även praktiska knappar i åtgärdsfönstret som gör att du kan hantera buffertar, köra huvudplanering och öppna andra relaterade vyer.

- Om du vill visa status för avdelningspunkt efter nettoflödesnivå går du till **Huvudplanering \> Huvudplanering \> DDMRP \> Status för avdelningspunkter efter nettoflöde**.
- Om du vill visa status för avdelningspunkt efter lagerbehållningsnivåer går du till **Huvudplanering \> Huvudplanering \> DDMRP \> Status för avdelningspunkter efter lagerbehållning**.
- Om du vill visa planerade order för avdelningspunkter går du till **Huvudplanering \> Huvudplanering \> DDMRP \> Planerade order för avdelningspunkter**.
- Om du vill visa avdelade ledtider går du till **Huvudplanering \> Huvudplanering \> DDMRP \> Avdelad ledtid**.

## <a name="clean-up-decoupling-point-buffer-values"></a>Rensa buffertvärden för avdelningspunkt

Med tiden kommer ditt system att ansamla en stor mängd historiska data som hör till pågående buffertberäkningar. Dessa historiska data gör att datavolymen ökar och så småningom kan komma att påverka systemets prestanda. Vi rekommenderar därför att du ibland rensar de gamla buffertvärdena för avdelningspunkt.

> [!WARNING]
> Rensningsjobbet tar bort historiska inställningar för buffertvärde och historisk information om behållning/nettoflöde. Detta går inte att ångra.

Följ dessa steg om du vill rensa dina buffertvärden för avdelningspunkt.

1. Gå till **Huvudplanering \> Huvudplanering \> DDMRP \> Rensa buffertvärden för avdelningspunkt**.
1. I dialogrutan **Rensa buffertvärden för avdelningspunkt** ställer du in följande fält:

    - **Radera poster som är äldre än (dagar)** – Ange åldern för de yngsta poster som ska behållas (i dagar). Alla buffertvärdesposter för avdelningspunkt som är äldre än detta värde kommer att raderas.
    - **Huvudplan** – Välj en huvudplan som inkluderar de artiklar som troligtvis kommer att påverkas av denna rensning. Rensningen gäller för alla artiklar i planen efter att de **filterinställningar** som du anger i den här dialogrutan tillämpas.

1. För att begränsa mängden poster som batchjobbet ska köras på: På snabbfliken **Poster som ska inkluderas** väljer du **Filter** för att öppna dialogrutan **Förfrågan**. Denna dialogruta fungerar precis som den gör för andra typer av [bakgrundsjobb](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.
1. På snabbfliken **Kör i bakgrunden** anger du hur, när och hur ofta rensningen ska utföras. Fälten fungerar precis som de gör för andra typer av [bakgrundsjobb](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.
1. Välj **OK** om du vill lägga till det nya jobbet i en batchkö för körning.
