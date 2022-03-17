---
title: Välkomstmeddelande via e-post skickas inte när nya kunder skapas
description: Detta ämne innehåller felsökningsvägledning som kan vara till hjälp om ett välkomstmeddelande via e-post inte skickas när en ny kund skapas i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 1a4faf6cd189f69232e7f9ab8d0e79b320cfe2d9
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349970"
---
# <a name="welcome-email-is-not-sent-when-new-customers-are-created"></a>Välkomstmeddelande via e-post skickas inte när nya kunder skapas

[!include [banner](../../includes/banner.md)]

Detta ämne innehåller felsökningsvägledning som kan vara till hjälp om ett välkomstmeddelande via e-post inte skickas när en ny kund skapas i Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Beskrivning

När en ny kund skapas i Commerce Headquarters skickas ett välkomstmeddelande via e-post till kunden, trots att ett e-postmeddelande konfigurerats för den e-posttyp som **skapats av kunden**.

## <a name="resolution"></a>Lösning

### <a name="set-the-correct-email-id-value-for-the-customer-created-email-notification-type"></a>Ställ in korrekt värde för e-post-ID för den e-postmeddelandetyp som kunden skapat

Ställ in korrekt värde för **e-post-ID** för den e-postmeddelandetyp **som har skapats av kunden** i administrationen genom att följa dessa steg.

1. Gå till **Butik och handel \> Administrationsinställning \> Meddelandeprofil för handel via e-post**.
1. I vänster navigeringsfönster väljer du önskad meddelandeprofil via e-post.
1. Under **Meddelandeinställningar för detaljhandelshändelser**, för e-postmeddelandetypen **Kundskapade**, anger du fältet **E-post-ID** som **NewCust**.

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en meddelandeprofil för e-post](../email-notification-profiles.md)
