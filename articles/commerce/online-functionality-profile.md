---
title: Skapa en onlinefunktionsprofil
description: I denna artikel beskrivs hur du skapar en funktionsprofil online i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 5ce81900cd0648132748167d03906afc64e97f25
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276812"
---
# <a name="create-an-online-functionality-profile"></a>Skapa en onlinefunktionsprofil

[!include [banner](includes/banner.md)]

Denna artikel innehåller en översikt över hur du konfigurerar en online-funktionsprofil för Microsoft Dynamics 365 Commerce.

Funktionsprofilen online innehåller olika inställningar som används för onlinekanaler. Varje onlinekanal måste ange en funktionsprofil online.

## <a name="create-an-online-functionality-profile"></a>Skapa en online funktionsprofil

I proceduren nedan beskrivs hur du skapar en funktionsprofil online från appen administration för Commerce.

1. I navigeringsfönstret, gå till **Moduler \> Kanalinställningar \> Online butiksinställningar \> Funktionsprofiler**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Profil** ange ett ID för profilen.
1. I fältet **Beskrivning** anger du ett värde ("Adventure Works Profile" i exempelbilden nedan).
1. I avsnittet **funktioner** ändrar du inställningarna för **KUNDVAGN**, **BUTIKSKUNDER** eller **KASSA** efter behov.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas ett exempel på funktionsprofil online.
  
![Exempel på funktionsprofiler online.](media/online-functionality-profile.png)

## <a name="functions"></a>Funktioner

- **Aggregera produkter**: när den här funktionen är aktiverad kan kundvagnen uppdatera kvantitet när samma artikel läggs till flera gånger.
- **Tillåt kassa utan betalningar**: när det här funktionen är aktiverad hanteras scenariot när artiklar som läggs till i vagnen har priset 0,00 $.
- **Skapa kund i asynkront läge**: det här är en äldre inställning som gäller näthandelskanaler från tredje part och kan inte användas på näthandelssajten Dynamics 365.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att konfigurera kanaler](channels-prerequisites.md)

[Ställ in en onlinekanal](channel-setup-online.md)

[Ställa in en butikskanal](channel-setup-retail.md)

[Ställa in en kundtjänstkanal](channel-setup-callcenter.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
