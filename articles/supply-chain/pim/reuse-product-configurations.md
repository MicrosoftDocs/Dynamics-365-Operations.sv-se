---
title: "Återanvända produktkonfigurationer"
description: "Du kan ange att du automatiskt vill återanvända en befintlig konfiguration för en produkt. När en användare sedan har slutfört en konfigurationssession, kontrollerar systemet om en konfiguration som matchar användarens val redan finns. Om en matchande konfiguration hittas, kommer konfigurationens ID, motsvarande strukturlista och flöde att återanvändas."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: c447440c33c1f80c6056974086b90d3b43e8499e
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---

# <a name="reuse-product-configurations"></a>Återanvända produktkonfigurationer

[!include [banner](../includes/banner.md)]

Du kan ange att du automatiskt vill återanvända en befintlig konfiguration för en produkt. När en användare sedan har slutfört en konfigurationssession, kontrollerar systemet om en konfiguration som matchar användarens val redan finns. Om en matchande konfiguration hittas, kommer konfigurationens ID, motsvarande strukturlista och flöde att återanvändas.

<a name="requirements-for-reusing-configurations"></a>Krav på att återanvända konfigurationer
---------------------------------------

Om du vill aktivera konfigurationer som ska återanvändas, måste du ange följande information för komponenter och attribut på sidan **Information om produktkonfigurationsmodell**:

-   **Komponenter och delkomponenter** – På snabbfliken **Allmänt** i fältet **Återanvänd konfigurationer** väljer du **Ja**.
-   **Attribut** – På snabbfliken **Attribut** väljer du alternativet **Inkludera i återanvändning**. Detta alternativ visas endast om den relaterade komponenten aktiveras för återanvändning. Om du inte väljer några attribut för återanvändning kommer komfigurationen alltid att återanvändas, oavsett användarens val under en konfigurationssession. Attributvärdena i den befintliga konfigurationen måste matcha användarens val. Om användaren till exempel väljer **blå** som färg under en konfigurationssession, kontrollerar systemet om en befintlig konfiguration av komponenten har färgen blå.

## <a name="resetting-configuration-reuse"></a>Återställa konfigurationsåteranvändning
Tidigare skapade konfigurationer beaktas inte längre när du återställer återanvändningen av konfigurationen. Du kanske vill återställa återanvändningen av konfigurationen om strukturlistan eller flödet har ändrats, men inga relaterade attribut ändrades. Du återställer konfigurationen för komponenten på snabbfliken **Allmänt**.




