---
title: Statusar om transporthantering
description: I det här avsnittet beskrivs hur du skapar en transportstatus och kopplar statusen till ett transportföretagsstatus.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: f3a2b9e50dddf0f015cdd3f16d6d93fcc03d464d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807618"
---
# <a name="transportation-management-statuses"></a>Statusar om transporthantering

[!include [banner](../includes/banner.md)]

Ställa in huvudkoder för att transportstatus ska tolka koder som tillhandahålls av transportföretag. På så sätt kan du integrera med transportföretag som ger status. Den transportstatus du anger som huvudkod för transportstatus kan hjälpa dig att följa statusen för en last, försändelse eller container. Den specifika transportstatusen för en last, försändelse eller container kan bara uppdateras genom data integration och inte manuellt via användargränssnittet.

## <a name="create-a-transportation-status"></a>Skapa en transportstatus

Följ dessa steg för att skapa en transportstatus:

1. Gå till **Transporthantering \> Inställningar \> Transportstatusmallar**.
1. Klicka på **Ny** om du vill skapa en transportstatusmall.
1. I fältet **Transportstatusmall** anger du en unik kod för transportstatus.
1. I fältet **Transporttyp** väljer du antingen *Transportföretag* eller *Nav* som typ av transport
1. Ange ett namn och en transportstatus.
1. Stäng sidan.

## <a name="map-a-transportation-status-to-a-carrier-status"></a>Mappa en transportstatus till ett transportföretags status

För att mappa en transportstatus till ett transportföretags status följer du dessa steg:

1. Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportföretagets transportstatus**.
1. Klicka på **Ny** om du vill mappa en kod från ett transportföretag till en huvudkod för transportstatus.
1. Välj den unika ID:t för transportföretaget och transportföretagstjänsten.
1. Välj den transportstatuskoden som du vill mappa till det valda transportföretagets kod.
1. Ange den externa kod som används av transportföretaget.
1. Stäng sidan.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]