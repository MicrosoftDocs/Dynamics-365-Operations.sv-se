---
title: Arbeta med serialiserade artiklar i kassa
description: I det här avsnittet beskrivs hur du hanterar serialiserade artiklar i programmet kassa (POS).
author: boycezhu
manager: annbe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: eedb64ae04345cb94bdd8cc68de833cfcfd40119
ms.sourcegitcommit: 39981582778b0a62567324452485a6721ca18284
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "3407508"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Arbeta med serialiserade artiklar i kassa

[!include [banner](includes/banner.md)]

Många återförsäljare säljer produkter som kräver seriell kontroll. Dessa artiklar kallas för *serialiserade artiklar*. En del återförsäljare kanske vill behålla serienummer för spårning. Andra återförsäljare kan vilja samla serienummer under försäljningsprocessen, för service- och garantisyften. I det här avsnittet beskrivs hur du kan hantera serialiserade artiklar i programmet Microsoft Dynamics 365 Commerce kassa (POS).

## <a name="serial-number-configurations"></a>Konfiguration av serienummer

En artikel betraktas som en serialiserad artikel om den tilldelas en spårningsdimensionsgrupp som tillåter serienummer. I Commerce-administration måste du aktivera serienummer för lagerprocessen med alternativet **Aktiv** i försäljningsprocess på sidan **Spårningsdimensionsgrupper**. För att aktivera serienummer för försäljningsprocessen väljer du alternativet **Aktiv i försäljningsprocess**.

På snabbfliken **Spårningsdimensioner**, om alternativet **Tom inleverans tillåts** är aktiverat, är serienumret valfri indata under lagerinleveransen. Om alternativet är inaktiverat är serienummer obligatoriskt.

På snabbfliken **Serienummer**, om alternativet **Serienummerkontroll** är aktiverat, måste serienumret vara unikt per enhet. Dubbletter av serienummer är alltså inte tillåtna.

## <a name="serialized-items-in-the-receiving-process"></a>Serialiserade artiklar i inleveransprocessen

Med åtgärden **Inkommande lager** i POS-programmet kan användare utföra följande uppgifter för serialiserade artiklar:

- Registrera serienummer mot serialiserade artiklar när artiklarna tas emot i butiken via en inköpsorder.
- Verifiera förregistrerade serienummer mot serialiserade artiklar när artiklarna tas emot i butiken via en inköps- eller överföringsorder.

> [!NOTE]
> För att använda åtgärden **Inkommande lager** för att registrera eller verifiera en serialiserad artikel, måste artikeln tilldelas en spårningsdimensionsgrupp som är inställd på att tillåta serienummer för alternativet **Aktiv**, inte alternativet **Aktiv i försäljningsprocess**.

För att inleveransen ska inledas kan du i åtgärden **Inkommande lager** starta i **Inleverera nu** genom att skanna artikelns streckkod eller ange artikel-ID. Du kan också starta i vyn **Fullständig orderlista** genom att manuellt välja artikeln.

Om artikeln som väljs eller inlevereras är en serialiserad artikel innehåller fönstret **Detaljer** en länk till **Hantera serienummer** som öppnar sidan för **Hantering av serienummer**. Alternativt kan du öppna sidan **Hantering av serienummer** genom att välja **Serienummer** i programfältet i vyn för orderspecifikationer eller genom att välja **Hantera serienummer** i dialogrutan som visas vid inleveransen. På sidan **Hantering av serienummer** visas alla öppna serienummerrader som väntar på registrering eller verifiering. Det kan finnas två flikar på den här sidan: en för den aktuella artikeln och en för alla serialiserade artiklar på ordern.

I fältet **Status** på sidan **Hantering av serienummer** finns information om den aktuella fas som varje serienummer är i:

- **Ej registrerat** – Serienumret har inte angetts eller så har det förregistrerade serienumret inte verifierat än.
- **Registrerar** – Serienumret har registrerats och sparats lokalt i butikens kanaldatabas, eller så har det förregistrerade serienumret verifierats. Endast serienummer med status **Registrerar** skickas till Commerce-administration när du har tagit emot det.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrera serienummer mot serialiserade artiklar

För en inköpsorder visas en dialogruta under inleverans av en serialiserad artikel med alternativet **Hantera serienummer**. Du kan välja att öppna sidan **Hantering av serienummer** och börja registrera serienummer. Du kan också hoppa över det här steget under inleveransen och ange indata senare innan inleveransen bokförs.

Som standard visas fliken för den aktuella artikeln. Alla serienummerrader har ett tomt serienummervärde och status **Inte registrerat**. Du kan skanna serienummerstreckkoder, eller välja **Serienummer** i appfältet för att kontinuerligt ange serienummer i dialogrutan. De serienummer som du anger visas i listan och status för serienummerraderna ändras till **Registrerar**. Maximalt antal serienummer som du kan registrera i listan är lika med inleveranskvantiteten. Om du gör fel kan du välja **Redigera** eller **Rensa** i fältet **Detaljer** för att ändra serienummer du har angett.

Du kan även registrera serienummer på fliken **Alla serialiserade artiklar** på sidan för **Hantering av serienummer**. I listan väljer du den artikel du vill registrera serienummer mot.

Vid registrering av serienummer på den här sidan dupliceras verifieringen. Om du försöker ange ett duplicerat serienummer mot en artikel som serienummerkontrollen är aktiverad för visas ett felmeddelande och ett annat nummer måste anges.

### <a name="validate-serial-numbers-on-serialized-items"></a>Verifiera serienummer för serialiserade artiklar

För en överföringsorder måste den utgående sidan förregistrera serienummer på de serialiserade artiklarna under leveransprocessen. För en inköpsorder kan leverantören tillhandahålla information om serienummer via leveransavisering (ASN) och du kan sedan förregistrera nummer för de artiklar som ska levereras. I båda fallen är serienumren kända före inleveransen. På inkommande sidan måste du därför bara verifiera att du har fått det du skulle ha.

Om du vill validera serienummer kan du öppna sidan **Hantering av serienummer**, antingen under inleveransen eller när som helst innan inleveransen bokförs. För alla serialiserade artiklar som har förregistrerade serienummer, ställs alla serienummer automatiskt in med ursprunglig status som **Inte registrerad** på den här sidan. Om du vill verifiera serienummer kan du skanna in eller ange dem. När serienummer anges verifierar programmet om de matchar förregistrerade serienummer. Om de matchar ändras deras status till **Registrerar**. Annars får du ett felmeddelande. Maximalt antal serienummer som du kan verifiera i listan är lika med inleveranskvantiteten

Du kan även verifiera serienummer på fliken **Alla serialiserade artiklar** på sidan för **Hantering av serienummer**. I listan väljer du den artikel du vill verifiera serienummer mot.

## <a name="additional-resources"></a>Ytterligare resurser

[Inkommande lageråtgärder i kassan](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)
