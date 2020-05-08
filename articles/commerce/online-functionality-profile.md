---
title: Skapa en online funktionsprofil
description: I det här avsnittet beskrivs hur du skapar en funktionsprofil online i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5ecbfcf3fa78ad2909a7cc9988ab1edaf2b98376
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003382"
---
# <a name="create-an-online-functionality-profile"></a>Skapa en online funktionsprofil


[!include [banner](includes/banner.md)]

Det här ämnet innehåller en översikt över hur du konfigurerar en online funktionsprofil för Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Funktionsprofilen online innehåller olika inställningar som används för onlinekanaler. Varje onlinekanal måste ange en funktionsprofil online.

## <a name="create-an-online-functionality-profile"></a>Skapa en online funktionsprofil

I proceduren nedan beskrivs hur du skapar en funktionsprofil online från appen administration för Handel.

1. I navigeringsfönstret, gå till **Moduler \> Kanalinställningar \> Online butiksinställningar \> Funktionsprofiler**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Profil** ange ett ID för profilen.
1. I fältet **Beskrivning** anger du ett värde ("Adventure Works Profile" i exempelbilden nedan).
1. I avsnittet **funktioner** ändrar du inställningarna för **KUNDVAGN**, **BUTIKSKUNDER** eller **KASSA** efter behov.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas ett exempel på funktionsprofil online.
  
![Exempel på funktionsprofiler online](media/online-functionality-profile.png)

## <a name="functions"></a>Funktioner

- **Aggregera produkter**: när den här funktionen är aktiverad kan kundvagnen uppdatera kvantitet när samma artikel läggs till flera gånger.
- **Tillåt utcheckning utan betalningar**: när det här funktionen är aktiverad hanteras scenariot när artiklar som läggs till i vagnen har priset 0,00 $.
- **Skapa kund i asynkront läge**: det här är en äldre inställning som gäller näthandelskanaler från tredje part och kan inte användas på e-handelsplatsen Dynamics 365.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att ställa in kanaler](channels-prerequisites.md)

[Ställ in en onlinekanal](channel-setup-online.md)

[Ställa in en butikskanal](channel-setup-retail.md)

[Ställa in en kundtjänstkanal](channel-setup-callcenter.md)