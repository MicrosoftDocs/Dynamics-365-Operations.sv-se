---
title: Informationsmodul för upphämtning
description: Det här avsnittet handlar om informationsmodulen för upphämtning och beskriver hur du lägger till den på kassasidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 61b97d72b6a397737c10476cd6c02764e60f10b1
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665358"
---
# <a name="pickup-information-module"></a>Informationsmodul för upphämtning

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om informationsmodulen för upphämtning och beskriver hur du lägger till den på kassasidorna i Microsoft Dynamics 365 Commerce.

Du kan använda modulen för upphämtningsinformation i en kassamodul för att visa information om orderupphämtning. Kunder kan visa tillgängliga datum och tidpunkter för upphämtning och sedan välja en lämplig tid att hämta sin order. En kund kan till exempel välja att hämta en order kl. 15.00 den 21 mars från butiken i San Francisco.

Upphämtningstider för relevanta butiker måste konfigureras i Commerce-administrationen. Mer information finns i [Skapa och uppdatera tidpunkter för kundupphämtning](dev-itpro/pickup-timeslots.md).

Om en modul för upphämtningsinformation skapas på en kassasida men inga tidpunkter har definierats för den butik som valts för upphämtning, visar modulen information men användaren kan inte välja några tidpunkter. Tidpunkter är valfria och krävs inte för att lägga en beställning.

Om flera artiklar har valts för upphämtning över flera butiker, kommer modulen för upphämtningsinformation att låta användaren välja en tidpunkt för respektive butik, förutsatt att det finns tillgängliga tidpunkter för densamma.

> [!NOTE]
> Stöd för tidpunkter och informationsmodulen för kassaupphämtning finns att tillgå i Dynamics 365 Commerce version 10.0.15 och senare.

I bilden nedan visas ett exempel på hur val av tidpunkter via informationsmodulen för upphämtning på en kassasida.

![Exempel på en modul för upphämtningsinformation på en kassasida](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a>Modulegenskaper

- **Rubrik** – Ange en rubrik för modulen.

## <a name="show-time-slot-information-after-an-order-is-placed"></a>Visa information om tidpunkt efter det att en order har lagts

När en order har lagts kan information om den valda tidpunkten visas i [modulen för orderbekräftelse](order-confirmation-module.md) och i [modulen för orderinformation](account-management.md#order-details-page). Båda dessa moduler har egenskapen **Visa tidpunktsinformation**. Innan de kan visa den valda tidpunkten i samband med orderprocessen måste den här egenskapen ha värdet **True**.

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a>Lägg till en informationsmodul för kassaupphämtning på en sida

Instruktioner om hur du lägger till en informationsmodul om upphämtning på en kassasida och anger erforderliga egenskaper finns i [Kassamodulen](add-checkout-module.md).

I bilden nedan visas ett exempel på en kassasida för näthandel som innehåller tidpunkter för artiklar på upphämtningsrader.

![Exempel på en kassasida för näthandel som innehåller tidpunkter för artiklar på upphämtningsrader](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa och uppdatera tidpunkter för kundavhämtning](dev-itpro/pickup-timeslots.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Orderinformationsmodul](account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]