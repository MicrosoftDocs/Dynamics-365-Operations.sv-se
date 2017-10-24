---
title: Konfigurationsregler
description: "Den här artikeln innehåller allmän information om konfigurationsregler. Konfigurationsregler definierar relationer mellan artiklar i en strukturlista (BOM) för produkter som använder dimensionsbaserad konfigurationsteknik."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 72395b5068f0893d79be6f8095dae988c224d0aa
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="configuration-rules"></a>Konfigurationsregler

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller allmän information om konfigurationsregler. Konfigurationsregler definierar relationer mellan artiklar i en strukturlista (BOM) för produkter som använder dimensionsbaserad konfigurationsteknik.

Konfigurationsregler är tillgängliga när du definierar dimensionsbaserade konfigurationmodeller. Konfigurationsregler används för att antingen framtvinga eller förbjuda specifika artikelkombinationer i en strukturlista. När en strukturlista har skapats, och de relevanta artiklarna har tilldelats till respektive konfigurationsgrupper, kan en eller flera konfigurationsregler definieras. Om två artiklar hör ihop, används operatorn **Välj** för att säkerställa inkludering. Om två artiklar är ömsesidigt uteslutande används operatorn **Avmarkera** för att säkerställa uteslutande.  

**Obs!** Den här informationen gäller endast för produktmallar som använder dimensionsbaserad konfigurationteknik.  

Befintliga konfigurationer påverkas inte av senare ändringar av konfigurationsreglerna. Det är dock viktigt att du ställer in reglerna innan du definierar en ny konfiguration eller att du kontrollerar reglerna om du tror att de har ändrats.  

**Obs!** För metoden **Markera** väljs den härledda konfigurationsgruppen, artikelnumret eller konfigurationen automatiskt. För metoden **Avmarkera** kan den härledda konfigurationsgruppen, artikelnumret eller konfigurationen inte kan väljas.

<a name="see-also"></a>Se även
--------

[Dimensionsbaserad produktkonfiguration](dimension-based-product-configuration.md)




