---
title: Återanvända produktkonfigurationer
description: Du kan ange att du automatiskt vill återanvända en befintlig konfiguration för en produkt. När en användare sedan har slutfört en konfigurationssession, kontrollerar systemet om en konfiguration som matchar användarens val redan finns. Om en matchande konfiguration hittas, kommer konfigurationens ID, motsvarande strukturlista och flöde att återanvändas.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0898bd1832fa7007fc3aa265beee2e930f157a39
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577418"
---
# <a name="reuse-product-configurations"></a>Återanvända produktkonfigurationer

[!include [banner](../includes/banner.md)]

Du kan ange att du automatiskt vill återanvända en befintlig konfiguration för en produkt. När en användare sedan har slutfört en konfigurationssession, kontrollerar systemet om en konfiguration som matchar användarens val redan finns. Om en matchande konfiguration hittas, kommer konfigurationens ID, motsvarande strukturlista och flöde att återanvändas.

## <a name="requirements-for-reusing-configurations"></a>Krav på att återanvända konfigurationer

Om du vill aktivera konfigurationer som ska återanvändas, måste du ange följande information för komponenter och attribut på sidan **Information om produktkonfigurationsmodell**:

-   **Komponenter och delkomponenter** – På snabbfliken **Allmänt** i fältet **Återanvänd konfigurationer** väljer du **Ja**.
-   **Attribut** – På snabbfliken **Attribut** väljer du alternativet **Inkludera i återanvändning**. Detta alternativ visas endast om den relaterade komponenten aktiveras för återanvändning. Om du inte väljer några attribut för återanvändning kommer komfigurationen alltid att återanvändas, oavsett användarens val under en konfigurationssession. Attributvärdena i den befintliga konfigurationen måste matcha användarens val. Om användaren till exempel väljer **blå** som färg under en konfigurationssession, kontrollerar systemet om en befintlig konfiguration av komponenten har färgen blå.

## <a name="resetting-configuration-reuse"></a>Återställa konfigurationsåteranvändning
Tidigare skapade konfigurationer beaktas inte längre när du återställer återanvändningen av konfigurationen. Du kanske vill återställa återanvändningen av konfigurationen om strukturlistan eller flödet har ändrats, men inga relaterade attribut ändrades. Du återställer konfigurationen för komponenten på snabbfliken **Allmänt**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]