---
title: "Måttenheten och lagerpolicyer"
description: "Den här artikeln beskriver hur standardenheter, enhetssekvenser och enhetskonverteringar används i lagerprocesser."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResProductDetails, EcoResProductDetailsExtended, EcoResStorageDimensionGroup, InventItemOrderSetup, UnitOfMeasureConversion, WHSRFMenuItem, WHSUOMSeqGroupTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29611
ms.assetid: 4b5ca875-9a06-416d-9ac0-cc3ab8f7338e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 82cf9147c050ec661bb2518b2af4e832f8cc480f
ms.lasthandoff: 03/31/2017


---

# <a name="unit-of-measure-and-stocking-policies"></a>Måttenheten och lagerpolicyer

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver hur standardenheter, enhetssekvenser och enhetskonverteringar används i lagerprocesser.

Enhetssekvensgrupper definierar den sekvens av enheter som kan användas i lageroperationer. De skapas på sidan **Enhetssekvensgrupper**. Sekvensen visar förhållandet mellan de olika enheterna. Till exempel lagrar du lastpallar som innehåller kartonger, som innehåller enskilda delar av artiklar. I detta fall måste du tillhandahålla de tre olika enheterna och den logiska ordningen för skikten. I Enhetsekvensgrupper kan du definiera policyer för gruppering av registreringsskyltar och de standardenheter som ska användas för flera lagerställeprocesser. Denna artikel gäller både den avancerade lagerställelösningen som är tillgängliga i Lagerstyrning och den mer grundläggande lagerställelösningen, som är tillgänglig i Lagerhantering.

## <a name="unit-sequence-groups-for-released-products"></a>Enhetssekvensgrupper för frisläppta produkter
Om du vill använda frisläppta produkter i lagerställearbeteprocesser, måste en enhetssekvensgrupp tilldelas till dem. Om du validerar en produkt som är kopplad till en Lagringsdimensionsgrupp och alternativet **Använd lagerstyrningsprocesser** för lagringsdimensiongruppen är inställd på **Ja** får du ett felmeddelande om ett enhetssekvensgrupp-ID inte har definierats för produkten. Om enhetssekvensgruppen som du använder innehåller flera rader (och därför flera enheter), måste du ställa in en enhetskonvertering mellan enheterna. Du slutför den här inställningen på sidan **Enhetskonverteringar**. Den minsta enheten i en sekvensgrupp, som du kopplar till en frisläppt produkt måste matcha den lagerenhet som definieras för motsvarande produkt. Lagerenheten är den enhet som används för basberäkningar av lagerbehållning. Du kan även ställa in måttenhetkonverteringar för produktvarianter av produktmallar, genom att använda alternativet **Aktivera måttenhetkonverteringar**.

## <a name="license-plate-grouping"></a>Registreringsskyltsgruppering
Du kan ange om inleveranser av mindre än eller fler än en specifik enhet ska grupperas till en registreringsskylt eller delas upp på flera skyltar. För att ställa in det här beteendet använder du alternativet **Gruppering av registreringsskyltar **på fliken **Radinformation** på sidan **Enhetssekvensgrupper** . Om du vill använda registreringsskyltsgruppering när arbete bearbetas med en mobil enhet, måste du välja alternativet **ID-gruppering** på menyalternativet **Mobil enhet**. Du kan till exempel använda en mobil enhet för att registrera en artikel som är kopplad till en enhetssekvensgrupp, som har två rader. Första raden är för Enheter och alternativet **ID-gruppering** är inställt på **Ja**. Den andra raden är för Lastpallsenhet och alternativet **ID-gruppering** är inställt på **Nej**. I det här fallet kan systemet automatiskt guida delningen och skapandet av registreringsskyltar per 100 enheter.

## <a name="units-for-cycle-counting"></a>Enheter för rullande inventering
För att definiera vilka enheter som ska användas som en del av processen för rullande inventering väljer du alternativet **Använd enhet för rullande inventering** på sidan **Enhetssekvensgrupper** . Du kan välja maximalt fyra enheter i sekvensgruppen. Om du väljer fler än fyra enheter, kommer de ytterligare enheterna inte att visas i den mobila enheten.

## <a name="default-units-for-mobile-device-receiving-processes"></a>Inleveransprocesser för standardenheter för mobila enheter
Om du vill ställa in standardenheter som ska användas för inleveransprocesser på mobila enheter, aktiverar du alternativen **Standardenhet för inköp och överföring** och **Standardenhet för produktion** på sidan **Enhetssekvensgrupper** . Du kan till exempel ange att systemet som standard ska använda lastpallkvantiteter när inköpsorderlagerbehållningen tas emot genom att använda en mobil enhet, men att lagerhållningenheten ska vara Enheter. Om du vill få konverteringen för det antal enheter, som varje lastpall innehåller måste du definiera en enhetskonvertering, till exempel 100 st = 1 PL.

## <a name="default-order-settings"></a>Standardorderinställningar
Som en del av genereringen av en frisläppt produkter måste du välja standardenheter för inköp, försäljning och lager för att bearbeta olika order. Du kan ange standardenheterna och kvantiteterna för de olika källdokumenten genom att använda sidorna **Standardorderinställningar** och **Platsspecifika orderinställningar** . Du öppnar dessa sidor från sidan **Frisläppta produkter**.




