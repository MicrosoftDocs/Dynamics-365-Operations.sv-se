---
title: "Återanvänd produktkonfigurationer"
description: "Du kan ange att du automatiskt vill återanvända en befintlig konfiguration för en produkt. När en användare sedan har slutfört en konfigurationssession, kontrollerar systemet om en konfiguration som matchar användarens val redan finns. Om en matchande konfiguration hittas, kommer konfigurationens ID, motsvarande strukturlista och flöde att återanvändas."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: a846c5fee2736fb8f137f7c2bdd759be43220d14
ms.lasthandoff: 03/31/2017


---

# <a name="reuse-product-configurations"></a>Återanvänd produktkonfigurationer

Du kan ange att du automatiskt vill återanvända en befintlig konfiguration för en produkt. När en användare sedan har slutfört en konfigurationssession, kontrollerar systemet om en konfiguration som matchar användarens val redan finns. Om en matchande konfiguration hittas, kommer konfigurationens ID, motsvarande strukturlista och flöde att återanvändas.

<a name="requirements-for-reusing-configurations"></a>Krav på att återanvända konfigurationer
---------------------------------------

Om du vill aktivera konfigurationer som ska återanvändas, måste du ange följande information för komponenter och attribut på sidan **Product configuration model details **:

-   **Komponenter och delkomponenter** – På snabbfliken **General** i fältet **Reuse configurations** väljer du **Yes**.
-   **Attribut** – På snabbfliken **Attributes** väljer du alternativet **Include in reuse**. Detta alternativ visas endast om den relaterade komponenten aktiveras för återanvändning. Om du inte väljer några attribut för återanvändning kommer komfigurationen alltid att återanvändas, oavsett användarens val under en konfigurationssession. Attributvärdena i den befintliga konfigurationen måste matcha användarens val. Om användaren till exempel väljer **blå** som färg under en konfigurationssession, kontrollerar systemet om en befintlig konfiguration av komponenten har färgen blå.

## <a name="resetting-configuration-reuse"></a>Återställa konfigurationsåteranvändning
Tidigare skapade konfigurationer beaktas inte längre när du återställer återanvändningen av konfigurationen. Du kanske vill återställa återanvändningen av konfigurationen om strukturlistan eller flödet har ändrats, men inga relaterade attribut ändrades. Du återställer konfigurationen för komponenten på snabbfliken **General**.


