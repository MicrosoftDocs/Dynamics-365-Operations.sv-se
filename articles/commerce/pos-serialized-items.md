---
title: Arbeta med serialiserade artiklar i kassa
description: I det här avsnittet beskrivs hur du hanterar serialiserade artiklar i programmet kassa (POS).
author: boycezhu
manager: annbe
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 6ba01abc3d1a4496ec586a621aa03b4981f84d76
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415945"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Arbeta med serialiserade artiklar i kassa

[!include [banner](includes/banner.md)]

Många återförsäljare säljer produkter som kräver seriell kontroll. Dessa produkter kallas för *serialiserade artiklar*. En del återförsäljare kanske vill behålla serienummer i butik eller på lagerplats för spårning. Andra återförsäljare kan vilja samla serienummer under försäljningsprocessen, för service- och garantisyften. I det här avsnittet beskrivs hur du kan hantera serialiserade artiklar i programmet Microsoft Dynamics 365 Commerce kassa (POS).

## <a name="serial-number-configurations"></a>Konfiguration av serienummer

En artikel betraktas som en serialiserad artikel om den tilldelas en spårningsdimensionsgrupp som tillåter serienummer. I Commerce-administration på sidan **spårningsdimensionsgrupper** välj alternativet **aktiv** för att aktivera serienummer för lagerprocessen, eller välj alternativet **aktiv i försäljningsprocess** för att aktivera serienummer för försäljningsprocessen.

På snabbfliken **Spårningsdimensioner** aktivera parametern **Tom inleverans tillåten** för att tillåta serienumret vara valfri indata under lagerinleveransen. Om du inaktiverar den här parametern tvingas serienummer att vara en obligatorisk inmatning. På samma sätt kontrollerar parametern **Tom utleverans tillåten** om serienummer krävs under lagerförsändningsprocess.

> [!NOTE]
> För att använda kassaåtgärderna **Inkommande lager** och **Utgående lager** för att registrera eller verifiera en serialiserad artikel, måste artikeln tilldelas en spårningsdimensionsgrupp som är inställd på att tillåta serienummer för alternativet **Aktiv** eller alternativet **Aktiv i försäljningsprocess**.

## <a name="serial-number-management-page"></a>Sidan för hantering av serienummer

I kassaåtgärderna **Inkommande lager** och **Utgående lageråtgärder** om artikeln som väljs, tas emot eller skickas är en serieartikel innehåller **Detaljer** innehåller ett alternativ för **Hantera serienummer** som länkar till sidan **hantering av serienummer** där du kan registrera eller validera artikelns serienummer. Alternativt kan du öppna sidan **Hantering av serienummer** genom att välja åtgärd **Serienummer** i programfältet i vyn för orderspecifikationer eller genom att välja **Hantera serienummer** i dialogrutan som visas vid inleveransen. 

På sidan **Hantering av serienummer** visas alla öppna serienummerrader som väntar på registrering eller verifiering. Det kan finnas två flikar på den här sidan: en för den aktuella artikeln och en för alla serialiserade artiklar på ordern.

I fältet **Status** på sidan **Hantering av serienummer** finns information om den aktuella fas som varje serienummer är i:

- **Ej registrerat** – Serienumret har inte angetts eller så har det förregistrerade serienumret inte verifierat än (i inleveransprocessen).
- **Registrerar** – Serienumret har registrerats och sparats lokalt i butikens kanaldatabas, eller så har det förregistrerade serienumret verifierats. Endast serienummer med status **Registrerar** skickas till Commerce-administration när du har tagit emot det eller uppfyllelse.

## <a name="receive-serialized-items"></a>Inleverera serialiserade artiklar

Med åtgärden **Inkommande lager** i kassaåtgärden kan användare utföra följande uppgifter för serialiserade artiklar:

- Registrera serienummer mot serialiserade artiklar när artiklarna tas emot i butiken via en inköpsorder.
- Verifiera förregistrerade serienummer mot serialiserade artiklar när artiklarna tas emot i butiken via en inköps- eller överföringsorder.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrera serienummer mot serialiserade artiklar

För en inköpsorder kommer du att uppmanas med en dialogruta med alternativet **Hantera serienummer** under mottagningsprocessen för en serieartikel. Du kan välja att öppna sidan **Hantering av serienummer** och börja registrera serienummer. Du kan också hoppa över det här steget under inleveransen och ange indata senare innan inleveransen bokförs.

Som standard visas fliken för den aktuella artikeln. Alla serienummerrader har ett tomt serienummervärde och status **Inte registrerat**. Du kan skanna serienummerstreckkoder, eller välja **Serienummer** i appfältet för att kontinuerligt ange serienummer. Serienumren som du anger visas i listan och deras status ändras till **Registrerar**. Maximalt antal serienummer som du kan registrera i listan är lika med inleveranskvantiteten. Om du gör fel kan du välja **Redigera** eller **Rensa** i fältet **Detaljer** för att ändra serienummer du har angett.

Du kan även registrera serienummer på fliken **Alla serialiserade artiklar** på sidan för **Hantering av serienummer**. I listan väljer du den artikel du vill registrera serienummer mot.

### <a name="validate-serial-numbers-on-serialized-items"></a>Verifiera serienummer för serialiserade artiklar

För en överföringsorder måste den utgående sidan förregistrera serienummer på de serialiserade artiklarna under leveransprocessen. För en inköpsorder kan leverantören tillhandahålla information om serienummer via leveransavisering (ASN) och du kan sedan förregistrera nummer för de artiklar som ska levereras. I båda fallen är serienumren kända före inleveransen. På inkommande sidan måste du därför bara verifiera att du har fått det du skulle ha.

Om du vill validera serienummer kan du öppna sidan **Hantering av serienummer**, antingen under inleveransen eller när som helst innan inleveransen bokförs. För alla serialiserade artiklar som har förregistrerade serienummer, ställs alla serienummer automatiskt in med ursprunglig status som **Inte registrerad** på den här sidan. Om du vill verifiera serienummer kan du skanna in eller ange dem. När serienummer anges verifierar programmet om de matchar förregistrerade serienummer. Om de matchar ändras deras status till **Registrerar**. Annars får du ett felmeddelande. Alternativt kan du välja ett serienummer direkt och sedan välja alternativet **Validera serienummer** i fönstret **Detaljer** för att snabbt markera serienumret som validerat. Maximalt antal serienummer som du kan verifiera i listan är lika med inleveranskvantiteten

Du kan även verifiera serienummer på fliken **Alla serialiserade artiklar** på sidan för **Hantering av serienummer**. I listan väljer du den artikel du vill verifiera serienummer mot.

## <a name="ship-serialized-items"></a>Leverera serialiserade artiklar

Du kan använda den **Utgående lageråtgärder** kassaåtgärden för att registrera serienummer mot serialiserade artiklar när de levereras ut ur den aktuella butiken via en överföringsorder.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrera serienummer mot serialiserade artiklar

För en överför kommer du att uppmanas med en dialogruta med alternativet **Hantera serienummer** under leveransprocess för en serieartikel. Du kan välja att öppna sidan **Hantering av serienummer** och börja registrera serienummer. Du kan också hoppa över det här steget under leveransprocess och ange indata senare innan leverans bokförs.

Som standard visas fliken för den aktuella artikeln. Alla serienummerrader har ett tomt serienummervärde och status **Inte registrerat**. Du kan skanna serienummerstreckkoder, eller välja **Serienummer** i appfältet för att kontinuerligt ange serienummer. Serienumren som du anger visas i listan och deras status ändras till **Registrerar**. Maximalt antal serienummer som du kan registrera i listan är lika med leveranskvantiteten. Om du gör fel kan du välja **Redigera** eller **Rensa** i fältet **Detaljer** för att ändra serienummer du har angett.

Du kan även registrera serienummer på fliken **Alla serialiserade artiklar** på sidan för **Hantering av serienummer**. I listan väljer du den artikel du vill registrera serienummer mot.

Om du vill kan du aktivera serienummer för tillgänglighetsvalidering under serienummer registreringen på en utgående överföringsorder. Om du försöker leverera ett serienummer som inte är tillgängligt i lagret för det här godkännandet, visas ett felmeddelande och du måste ange ett annat nummer.

Om du vill aktivera en sådan validering måste du schemalägga följande jobb så att de körs regelbundet:

- **Retail och Commerce** > **Retail och Commerce IT** > **Produkter och lager** > **Produkttillgänglighet med spårningsdimension**
- **Retail och Commerce** > **Distributionsscheman** > **1130** (**Produkttillgänglighet**)

## <a name="additional-resources"></a>Ytterligare resurser

[Inkommande lageråtgärder i kassan](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)

[Utgående lageråtgärder i kassan](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation)
