---
title: Synkronisering av resurskapacitet
description: I det här avsnittet finns information om hur du synkroniserar en resurskapacitet för kalendrar och projekt.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760662"
---
# <a name="synchronize-resource-capacity"></a>Synkronisering av resurskapacitet

[!include [banner](../includes/banner.md)]

Processerna för synkronisering av resurser hjälper till att garantera att information till kalendern och baskalendern sipprar ned i tidsplaneringen av projektresurser. Om kalendern ändras gör processerna de nödvändiga uppdateringarna av planeringen av projektresurser. Processerna kan även förbättra prestanda, detta eftersom resursinformationen i kalendern synkroniseras i förväg. Därför sker uppdateringar för resursplaneringsinformation snabbare. Vi rekommenderar att du planerar processer som en batch i stället för en i taget. Annars finns det en risk att någon glömmer inklusive datum när informationen synkroniserades senast. Om inklusive datum inte används, luckor kan inträffa under datumsynkronisering.

![Kalendersynkronisering](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a>Synkronisera kapacitetsuppföljningar för resurs

Synkroniseringsprocessen har utformats för att synkronisera all information om resurskalendrarna. Informationen omfattar baskalenderinformation om alla ändringar i kapacitetsregistret för projektets resurskalender. Om nya resurser läggs till i projektet, synkroniseringen hjälper till att garantera att den uppdaterade kalenderinformationen är tillgänglig. Den här synkroniseringen kan göras när som helst.

Vi rekommenderar att du använder en batch. Alternativen är tillgängliga i samband med synkronisering av kapacitetsreservationer.

1. Markera **Projekthantering och redovisning** &gt; **Periodisk** &gt; **Kapacitetssynkronisering** &gt; **Synkronisera kapacitetsuppföljningar för resurs**.
2. I följande tabell ställer du in alternativen.

    | Alternativ      | beskrivning |
    |-------------|-------------|
    | Periodkod | Markera vid behov datumintervallkod Redovisning för att ange start- och slutdatum för synkroniseringen av resurskapacitetssummeringen. |
    | Startdatum  | Ange startdatum för synkroniseringen för resurskapacitetssummeringen. |
    | Slutdatum    | Ange slutdatum för synkroniseringen för resurskapacitetssummeringen. |

[![Synkroniseringsprocess](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)
