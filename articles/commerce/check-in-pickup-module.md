---
title: Incheckning för upphämtningsmodul
description: Denna artikel beskriver incheckningen för plockmodul samt förklarar hur du konfigurerar denna i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 7002db893da1802063148a9b800ffa92f3e5f065
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885485"
---
# <a name="check-in-for-pickup-module"></a>Incheckning för upphämtningsmodul

[!include [banner](includes/banner.md)]

Denna artikel beskriver incheckningen för plockmodul samt förklarar hur du konfigurerar denna i Microsoft Dynamics 365 Commerce.

Incheckningen för upphämtningsmodulen innehåller en bekräftelsesida för kunder som använder incheckningsfunktionerna för kunder i Dynamics 365 Commerce och informerar en butik om att de är inkommande. Med incheckningen för upphämtningsmodulen kan du även konfigurera ett formulär som samlar in ytterligare information från kunder i syfte att underlätta orderleveransen. Denna information inkluderar en kunds nummer på parkeringsplatsen samt fordonets märke och modell. 

## <a name="module-properties"></a>Modulegenskaper

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Bekräftelsetext | Textsträng | Innehåll för rubriken som visas på incheckningsbekräftelsesidan. |
| Visa QR-kod | **Sant** eller **falskt** | När egenskapen har värdet **True** (sant) visar incheckningsbekräftelsesidan en QR-kod som representerar orderbekräftelse-ID:t. |
| Ytterligare informationsrubrik | Textsträng | Innehåll för rubriken som visas när ytterligare informationsfält har konfigurerats. |
| Ytterligare informationsnycklar | Resurs-ID/resursvärdepar | Varje nyckel skapar ett formulärfält och en tillhörande etikett som används för att samla in ytterligare information från kunder. |
| Ytterligare informationsnycklar \> Resurs-ID | Textsträng | Varje informationsnyckel skapar ett formulärfält och en tillhörande etikett som används för att samla in ytterligare information från kunder. Denna egenskap identifierar den ytterligare informationsnyckeln. I uppgiften som skapas i kassan (POS) visas värdet för den här egenskapen som etiketten i instruktionsfältet. |
| Ytterligare informationsnycklar \> Resursvärde | Textsträng | Etiketten för textfältet i uppgiften i kassan (POS). |
| Ytterligare informationsnycklar \> Krävs | **Sant** eller **falskt** | Denna egenskap anger om kunderna måste fylla i formulärfältet innan de kan fortsätta. När denna egenskap är inställt på **True** visas en asterisk bredvid formulärsetiketten, och en "null"-kontroll sker i syfte att förhindra att kunden fortsätter om inget värde har angetts. |

## <a name="add-the-check-in-for-pickup-module-to-a-page"></a>Lägga till incheckningen för upphämtningsmodulen på en sida

Incheckningen för upphämtningsmodulen ska läggas till på den nya sidan som du skapar för incheckningsbekräftelsen. Den sidan fungerar som incheckningsbekräftelseupplevelse för kunder som väljer länken **Jag är här** i e-postmeddelandet. 

## <a name="configure-the-additional-information-form"></a>Konfigurera det ytterligare informationsformuläret

Om inga ytterligare informationsnycklar har konfigurerats visar modulen bekräftelsesidan för incheckning för kunderna. När incheckningsbekräftelsen visas skapas en uppgift i kassan (POS) för butiken där ordern hämtas.

När en eller flera ytterligare informationsnycklar konfigureras uppmanas kunder först att ange information. När de väljer **Skicka** visas incheckningsbekräftelsen och en uppgift skapas i kassan (POS). 

## <a name="additional-resources"></a>Ytterligare resurser

[Aktivera incheckningsmeddelanden för kunder i kassan (POS)](enable-customer-check-in.md)
