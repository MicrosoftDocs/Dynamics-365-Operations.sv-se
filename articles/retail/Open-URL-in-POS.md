---
title: "Öppna URL i kassan"
description: "Det här avsnittet innehåller en översikt över de förbättringar som har gjorts i produkt- och kundsökfunktionen i Microsoft Dynamics 365 for Retail."
author: AamirAllaq
manager: AnnBe
ms.date: 11/14/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: sericks
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: f7df0a91948a494465fbd55af99757e3890357ce
ms.openlocfilehash: 4b8a0291855460b79f3a241eccb4b55b009804bf
ms.contentlocale: sv-se
ms.lasthandoff: 12/04/2018

---

# <a name="open-url-in-pos"></a>Öppna URL i kassan

Det här avsnittet beskriver hur du konfigurerar en knapp i Butikskassa (PO) för att öppna en URL. Den här funktionen kräver inte en kodanpassning och kan konfigureras av en person i en roll som inte är utvecklare.

Den här funktionen används för att konfigurera en knapp i kassan med hjälp av knappen rutnätsdesigner för att öppna en URL. För närvarande stöds detta följande konfigurationer:

- Öppna i nytt fönster.
- Öppna i kassan.
- Öppna en inbyggd app. 

## <a name="open-in-new-window"></a>Öppna i nytt fönster

Den här konfigurationen definierar om du vill öppna URL i ett nytt fönster eller i appen. När du konfigurerar för att öppna en webbadress i appen visas sidonavigeringspanelen och det övre fältet av kassan och är tillgängliga för användaren. När de konfigureras för att öppnas i ett nytt fönster öppnas URL i ett nytt appfönster i Modern POS för Windows och på en ny flik i webbläsaren i andra kassaklienter. Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** markerat.

## <a name="open-within-pos"></a>Öppna i kassan
Öppna en URL i kassan stöds för närvarande endast för Modern POS i Windows. Den här funktionen är under utveckling för andra klienter och planeras släppas i framtida uppdateringar. Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** inte markerat.

## <a name="open-a-native-app"></a>Öppna en inbyggd app
Den här funktionen låter dig också ange icke-URL om du vill öppna en inbyggd app. Du kan till exempel ange URL-protokoll såsom MailTo, SIP, IM eller MSTEAMS som sedan kan hanteras av respektive inbyggda appar på värdenheten. Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** markerat. 

- Windows-datorer finns i [Exportera eller importera standardassociationer för applikationer](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) för att ange standardassociationer för protokollet om du ställer in datorn med Deployment Image Servicing and Management (DISM). 
- Om du använder Mobile Device Manager, till exempel Intune för att hantera Windows-datorer, se [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults). 
- Om du utvecklar en egen webbserver, se [Starta standardappen för en URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app). 

## <a name="open-a-native-app-seamlessly"></a>Öppna en inbyggd app sömlöst
Windows och iOS Android tillåter också öppning av appar mer sömlöst utifrån association av approtokoll. Om din app inte redan är konfigurerad för att hantera att öppnas från en webbläsare kanske du behöver en utvecklare för att konfigurera detta.

- For Windows, se [Aktivera appar för webbplatser som använder app-URL-hanterare](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).
- För iOS, se [Universella länkar för utvecklare](https://developer.apple.com/ios/universal-links/).
- För Android, se [Hantering av Android applänkar](https://developer.android.com/training/app-links/).  


|   Kund                |Öppna i nytt fönster |Öppna en inbyggd app | Öppna i kassan            | Detaljer                           |
|-------------------------|-------------------|----------------|--------------------------|-----------------------------------|
| Modern POS på Windows   | ✓*                |    ✓          |       ✓                  | *Öppnas i ett nytt Modern POS-fönster)   |
| Cloud POS               | ✓*                |    ✓          |       X                   |  *Öppnar i en ny webbläsarflik       |
| Modern POS på iOS       | ✓*                |    ✓          |       X                  |  *Öppnar i en ny webbläsarflik        |
| Modern POS på Android   | ✓*                |    ✓          |       X                  |  *Öppnar i en ny webbläsarflik        |

## <a name="before-you-begin"></a>Innan du börjar
Innan du börjar, gå igenom hur du konfigurerar [Skärmlayouter för kassa (POS)](pos-screen-layouts.md).

## <a name="open-url-in-pos"></a>Öppna URL i kassan
Gör följande om du vill konfigurera en URL-adress att öppnas i kassan.

1.  I huvudkontor, gå till **Butik > Kanalinställningar > Kassainställningar > POS > Skärmlayout**.
2.  Välj **knappraster > Designer**.
3.  Skapa en ny knapp.
4.  Välj **Knappegenskaper**.
5.  Välj **Öppna URL** som åtgärd.
6.  Ange den URL som du vill använda.
7.  Konfigurera om du vill öppna URL i ett nytt fönster.

