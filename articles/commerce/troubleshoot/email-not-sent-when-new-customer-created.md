---
title: Välkomstmeddelande via e-post skickas inte när nya kunder skapas
description: Denna artikel innehåller felsökningsvägledning som kan vara till hjälp om ett välkomstmeddelande via e-post inte skickas när en ny kund skapas i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 5aa7d864555f96194500989e2d7ad200d8892121
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219415"
---
# <a name="welcome-email-isnt-sent-when-new-customers-are-created"></a>Välkomstmeddelande via e-post skickas inte när nya kunder skapas

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan vara till hjälp om ett välkomstmeddelande via e-post inte skickas när en ny kund skapas i Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Beskrivning

När en ny kund skapas i Commerce Headquarters skickas ett välkomstmeddelande via e-post till kunden, trots att ett e-postmeddelande konfigurerats för den e-posttyp som **skapats av kunden**.

## <a name="resolution"></a>Lösning

### <a name="associate-an-email-notification-profile-under-commerce-parameters"></a>Koppla en e-postmeddelandeprofil under Handelsparametrar

1. I administration, gå till **Butik och handel \> Administrationsinställning \> Parametrar \> Handelsparametrar \> Allmänt**.
2. I listrutan **E-postmeddelandeprofil** väljer du den e-postmeddelandeprofil som innehåller en mappning mellan den skapade e-posttypen och en e-postmall som skapats av en kund.  

> [!NOTE] 
> När du aktiverar meddelanden som skapats av kunder får kunder som skapas i alla kanaler inom den juridiska personen ett e-postmeddelande som skapas av kunden. För närvarande kan meddelanden skapade av kund inte begränsas till en enda kanal.

För mer information, se [Skapa e-postmallar för transaktionshändelser](../email-templates-transactions.md). 

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en meddelandeprofil för e-post](../email-notification-profiles.md)
