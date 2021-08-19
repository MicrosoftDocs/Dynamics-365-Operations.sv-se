---
title: Konfigurationsregler
description: Den här artikeln innehåller allmän information om konfigurationsregler. Konfigurationsregler definierar relationer mellan artiklar i en strukturlista (BOM) för produkter som använder dimensionsbaserad konfigurationsteknik.
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 90a9c4fe7ad8508a393ab4947340f77576627711042c6d2798be614a48971680
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715828"
---
# <a name="configuration-rules"></a>Konfigurationsregler

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller allmän information om konfigurationsregler. Konfigurationsregler definierar relationer mellan artiklar i en strukturlista (BOM) för produkter som använder dimensionsbaserad konfigurationsteknik.

Konfigurationsregler är tillgängliga när du definierar dimensionsbaserade konfigurationmodeller. Konfigurationsregler används för att antingen framtvinga eller förbjuda specifika artikelkombinationer i en strukturlista. När en strukturlista har skapats, och de relevanta artiklarna har tilldelats till respektive konfigurationsgrupper, kan en eller flera konfigurationsregler definieras. Om två artiklar hör ihop, används operatorn **Välj** för att säkerställa inkludering. Om två artiklar är ömsesidigt uteslutande används operatorn **Avmarkera** för att säkerställa uteslutande.  

**Obs!** Den här informationen gäller endast för produktmallar som använder dimensionsbaserad konfigurationteknik.  

Befintliga konfigurationer påverkas inte av senare ändringar av konfigurationsreglerna. Det är dock viktigt att du ställer in reglerna innan du definierar en ny konfiguration eller att du kontrollerar reglerna om du tror att de har ändrats.  

**Obs!** För metoden **Markera** väljs den härledda konfigurationsgruppen, artikelnumret eller konfigurationen automatiskt. För metoden **Avmarkera** kan den härledda konfigurationsgruppen, artikelnumret eller konfigurationen inte kan väljas.

## <a name="additional-resources"></a>Ytterligare resurser

[Dimensionsbaserad produktkonfiguration – översikt](dimension-based-product-configuration.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]