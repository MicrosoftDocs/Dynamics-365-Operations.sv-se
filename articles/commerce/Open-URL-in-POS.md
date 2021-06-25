---
title: Öppna URL i POS
description: Det här avsnittet innehåller en översikt över de förbättringar som har gjorts i produkt- och kundsökfunktionen i Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 43f28d9b7acb05a83544b04f6786dfe91f2d9f18
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193213"
---
# <a name="open-url-in-pos"></a>Öppna URL i kassa

[!include [banner](includes/banner.md)]

Detta ämne avsnitt beskriver hur du konfigurerar en knapp i kassa (POS) i Dynamics 365 Commerce för att öppna en URL. Den här funktionen kräver inte en kodanpassning och kan konfigureras av en person i en roll som inte är utvecklare. 

Den här funktionen används för att konfigurera en knapp i POS med hjälp av knappen rutnätsdesigner för att öppna en URL. För närvarande stöds detta följande konfigurationer:

- Öppna i nytt fönster.
- Öppna i POS.
- Öppna en inbyggd app.

## <a name="open-in-new-window"></a>Öppna i nytt fönster

Den här konfigurationen definierar om du vill öppna URL i ett nytt fönster eller i appen. När du konfigurerar för att öppna en webbadress i appen visas sidonavigeringspanelen och det övre fältet av POS och är tillgängliga för användaren. När de konfigureras för att öppnas i ett nytt fönster öppnas URL i ett nytt appfönster i Modern POS för Windows och på en ny flik i webbläsaren i andra kassaklienter. Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** markerat.

## <a name="open-within-pos"></a>Öppna i POS

Öppna en URL i POS stöds för närvarande endast för Modern POS i Windows. Den här funktionen är under utveckling för andra klienter och planeras släppas i framtida uppdateringar. Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** inte markerat.

## <a name="open-a-native-app"></a>Öppna en inbyggd app

Den här funktionen låter dig också ange icke-URL om du vill öppna en inbyggd app. Du kan till exempel ange URL-protokoll såsom MailTo, SIP, IM eller MSTEAMS som sedan kan hanteras av respektive inbyggda appar på värdenheten. Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** markerat.

- Windows-datorer finns i [Exportera eller importera standardassociationer för applikationer](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) för att ange standardassociationer för protokollet om du ställer in datorn med Deployment Image Servicing and Management (DISM).
- Om du använder Mobile Device Manager, till exempel Intune för att hantera Windows-datorer, se [Policy CSP – ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults).
- Om du utvecklar en egen webbserver, se [Starta standardappen för en URI](/windows/uwp/launch-resume/launch-default-app).

## <a name="open-a-native-app-seamlessly"></a>Öppna en inbyggd app sömlöst

Windows, iOS och Android tillåter också öppning av appar mer sömlöst utifrån association av approtokoll. Om din app inte redan är konfigurerad för att hantera att öppnas från en webbläsare kanske du behöver en utvecklare för att konfigurera detta.

- For Windows, se [Aktivera appar för webbplatser som använder app-URL-hanterare](/windows/uwp/launch-resume/web-to-app-linking).
- För iOS, se [Universella länkar för utvecklare](https://developer.apple.com/ios/universal-links/).
- För Android, se [Handling Android applänkar](https://developer.android.com/training/app-links/).

| Klient                | Öppna i nytt fönster | Öppna en inbyggd app | Öppna i POS | Detaljer                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| Modern POS på Windows | ✓\*                | ✓               | ✓              | \* Öppnas i ett nytt Modern POS-fönster |
| Cloud POS             | ✓\*                | ✓               | X              | \* Öppnar i en ny webbläsarflik        |
| Modern POS på iOS     | ✓\*                | ✓               | X              | \* Öppnar i en ny webbläsarflik        |
| Modern POS på Android | ✓\*                | ✓               | X              | \* Öppnar i en ny webbläsarflik        |

## <a name="before-you-begin"></a>Innan du börjar

Innan du börjar, gå igenom hur du konfigurerar [Skärmlayouter för kassa (POS)](pos-screen-layouts.md).

## <a name="open-url-in-pos"></a>Öppna URL i POS

Gör följande om du vill konfigurera en URL-adress att öppnas i POS.

1. I huvudkontor, gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassa \> Skärmlayout**.
2. Välj **Knappraster \> Designer**.
3. Skapa en ny knapp.
4. Välj **Knappegenskaper**.
5. Välj **Öppna URL** som åtgärd.
6. Ange den URL som du vill använda.
7. Konfigurera om du vill öppna URL i ett nytt fönster.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
