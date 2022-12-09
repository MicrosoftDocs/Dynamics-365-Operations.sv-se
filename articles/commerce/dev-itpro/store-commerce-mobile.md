---
title: Store Commerce-app för mobila plattformar
description: I den här artikeln beskrivs hur du kommer igång med hjälp av Microsoft Dynamics 365 Commerce Store Commerce-app för Android och iOS.
author: stuharg
ms.date: 11/30/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2018-10-29
ms.openlocfilehash: dc952698a2a3301aff312e8310c58cbbb9cfe290
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815794"
---
# <a name="store-commerce-app-for-mobile-platforms"></a>Store Commerce-app för mobila plattformar

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

I den här artikeln beskrivs hur du kommer igång med hjälp av Microsoft Dynamics 365 Commerce Store Commerce-appar för Android och iOS.

Med Dynamics 365 Commerce mobilapparna för Android och iOS distribueras alla enheter för mobil kassa (POS) för din butiksmiljö enkelt. I Store Commerce-mobilappar levereras nästan alla möjligheter och fördelar med [Store Commerce-app för Windows](store-commerce.md), och presterar bra på ett brett utbud av iOS och Android telefoner och surfplattor. Store Commerce mobilappar apps kan installeras direkt från Apples och Google Play appbutiker och kräver inte att en utvecklare skapar ett nytt applikationspaket för att distribuera eller uppdatera dem. 

Store Commerce mobilapparna behåller fullständig funktionell paritet med aktuella Retail hybrida appar. Dessutom omfattar Store Commerce för iOS stöd för en dedicerad maskinvara så att iOS-enheter kan kommunicera med anslutna betalningsterminaler, kvittoskrivare och kassalåda utan att en delad maskinvara krävs. 

> [!IMPORTANT]
> Store Commerce-appar för Windows, Android och och iOS är nästa generering av kassaprogram för Dynamics 365 Commerce. Store Commerce-apparna innehåller många förbättringar vad gäller prestandan samtidigt som de behåller full funktionalitet och paritet. Microsoft kommer att avskriva MPOS och Android och iOS Retail POS hybrida appar sent under 2023 och rekommenderar att du använder Store Commerce eller Cloud POS (CPOS) för alla nya kassadistributioner. Befintliga kunder ska planera att flytta från Retail hybridapp till Store Commerce. Mer information finns i [Flytta modern POS till Store Commerce](pos-extension/migrate-mpos-store-commerce.md). 

## <a name="app-architecture"></a>Apparkitektur

Store Commerce mobilappar använder samma topologi som Store Commerce-appen för Windows när den distribueras hybridläge. Store Commerce mobilappar är skalprogram som återger CPOS direkt från Commerce Scale Unit (CSU) och ansluter till fjärradministrerad handel och Commerce headquarters via CSU. Med modellen skalprogram kan Store Commerce-appar stödja en dedikerad maskinvarustation för direkt integration med en betalterminal, skrivare, kassalåda och annan kringutrustning. Du behöver inte ställa in en delad maskinvarustation för att använda maskinvaruenheter. 

Om du vill uppdatera en Store Commerce mobilapp, behöver du bara uppdatera CSU. Alla nya POS-funktioner och funktioner plockas automatiskt av programmet. Mer information om hur du uppdaterar CSU finns i [Tillämpa uppdateringar och tillägg på Commerce Scale Unit (moln)](../../fin-ops-core/dev-itpro/deployment/update-retail-channel.md).

Skalprogrammen betjänas genom appbutiksuppdateringar. När en mindre version uppnår allmän tillgänglighet (GA) publicerar Microsoft den i appbutikerna. Microsoft kan även publicera korrigeringar mellan mindre versionsuppdateringar för att frisläppa snabbkorrigeringar med hög prioritet.

## <a name="prerequisites"></a>Förutsättningar

Store Commerce mobilappar kräver Dynamics 365 Commerce, särskilt Commerce headquarters och CSU-komponenter. I följande tabell visas en lista över de lägsta operativsystemets (OS) och CSU-versioner som krävs av Android- och iOS-mobilapparna. 

| Förutsättning | Android      | iOS  |
| ------------ | ------------ | ---- |
| OS-version   | 7.0          | 15.0 |
| CSU-version  | 9.38.22266.8 | Ska definieras  |

## <a name="install-the-app"></a>Installera appen

Du kan installera Store Commerce mobilappar från Google Play Store eller Apple App Store. 

- [Store Commerce-appen för Android](https://aka.ms/storecommerceandroid)
- [Store Commerce-appen för iOS](https://aka.ms/storecommerceios)

Paketen Android-app (.apk) och Apple-app (.ipa) kan också hämtas från biblioteket gemensam tillgång i Microsoft Dynamics Lifecycle Services. 

## <a name="device-and-register-setup"></a>Inställningar för enhet och kassa

Innan en kassa kan aktiveras i Store Commerce mobilappar måste du ställa in en enhet och registrera den i Commerce headquarters. Mer information finns i [Enheter och kassa](../implementation-considerations-devices.md). 

### <a name="device-setup"></a>Enhetsinställning

Följ dessa steg för att skapa och konfigurera en ny enhet.

1. I Commerce headquarters, gå till **Butik och handel \> Kanalinställning \> Kassainställning \> Enheter**. 
1. Skapa en ny enhet och välj antingen **Modern POS – Android** eller **Modern POS – iOS** som programtyp, beroende på vilken mobilapp du distribuerar. 

    > [!NOTE] 
    > Programtyperna **Modern POS – Android** och **Modern POS – iOS** används också för att distribuera de aktuella hybridapparna för Android och iOS. Efter avskaffandet av MPOS kommer etiketterna för dessa applikationstyper att uppdateras till **Store Commerce – Android** och **Modern POS – iOS**. 

### <a name="register-setup"></a>Kassainställningar

Du kan skapa en ny kassa och koppla den till enheten du skapat, eller koppla ett befintligt kassaregister till den nya enheten. Mer information om kassor finns i [Skapa och associera kassor](../tasks/create-associate-registers.md).

### <a name="screen-layout-setup"></a>Inställning av skärmlayout

Om du återanvänder en skärmlayout som ingår i demodata som tillhandahålls med din Dynamics 365 Commerce licens, kommer Store Commerce-appen automatiskt att välja den medföljande kompakta layouten om skärmupplösningen på din enhet är mindre än 480 &times; 853 pixlar i stående orientering. Om du skapar en skärmlayout från början, eller om din mobila enhet använder en större upplösning än layouten har stöd för, måste du dock se till att du skapar en lösning och associerade knapprutor som passar för den telefon eller surfplatta som du planerar att distribuera till. Mer information om konfigurationer av skärmlayouter finns i [visuella konfigurationer av användargränssnitt i POS](../pos-screen-layouts.md). 

När enheter och kassor har konfigurerats i Commerce headquarters, gå till **Butik och handel \> Butik och handel ID \> Distributionsscheman** och kör kassajobb.

## <a name="activate-a-device"></a>Aktivera enhet

Aktivera en enhet i en Store Commerce mobilapp genom att följa dessa steg.

1. Öppna appen på din mobila enhet.
1. Ange CPOS URL, som du kan hitta på sidan med miljödetaljer i Lifecycle Services eller på **Kanalprofiler** i Commerce headquarters (**Butik och handel \> Kanalinställning \> Kanalprofiler**).
1. Logga in med autentiseringsuppgifterna för en arbetare som har behörighet att hantera enheter.
1. Välj den butik som är kopplad till kassan som du skapat eller återanvände i Commerce headquarters.
1. Välj kassan som du kopplade till enheten som du skapade i Commerce headquarters.
1. Din enhet bör nu vara aktiverad. Du kan logga in i kassan med operatörs-ID och lösenord för arbetare som är associerad med den butik som du valt. 

Mer information om enhetsaktivering finns i [Aktivering av (POS) kassaenhet](retail-device-activation.md#activate-a-modern-pos-or-cloud-pos-device-by-using-guided-activation).

## <a name="feature-parity-with-store-commerce-for-windows"></a>Funktionsparitet med Store Commerce för Windows

I tabellen nedan jämförs funktionerna i Store Commerce-appen över Windows, Android och iOS-plattformarna.

| Funktion                                                                               | Windows | Android | iOS |
| ------------------------------------------------------------------------------------- | ------- | ------- | --- |
| Dedikerad maskinvarustation                                                            | Ja     | Ja     | Ja |
| Delad maskinvarustation                                                               | Ja     | Ja     | Ja |
| Kommunikation med kringutrustning i nätverk (betalningsterminal, skrivare och kassalåda) | Ja     | Ja     | Ja |
| OLE för kassakringutrustning (OPOS) via en lokal maskinvarustation             | Ja     | Nej      | Nej  |
| Offlineläge                                                                          | Ja     | Nej      | Nej  |

## <a name="additional-resources"></a>Ytterligare resurser

[Appen Store Commerce](store-commerce.md)

[Välja mellan Store Commerce och molnbaserad kassa](../mpos-or-cpos.md)

[Felsöka problem vid konfiguration och installation av Store Commerce](../troubleshoot/store-commerce-setup-installation.md)
