---
title: Skapa konfigurationsregler
description: Den här proceduren skapar konfigurationsregler som kan användas för dimensionsbaserad konfiguration för att framtvinga eller förhindra vissa kombinationer av strukturlisterader.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bc0af4d95e9430d0b5c8b7fc9a4ade076802044
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437672"
---
# <a name="create-configuration-rules"></a>Skapa konfigurationsregler

[!include [banner](../../includes/banner.md)]

Den här proceduren skapar konfigurationsregler som kan användas för dimensionsbaserad konfiguration för att framtvinga eller förhindra vissa kombinationer av strukturlisterader. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Detta är den första proceduren utav sju som förklarar hur du ställer upp kombinationer för dimensionsbaserad konfiguration.

1. Gå till Produktinformationshantering > Strukturlistor och formler > Strukturlistor.
2. Hitta och markera önskad post i listan.
    * Hitta och välj strukturlistan för den dimensionsbaserade konfigurationen.  
3. Klicka på Alternativ i åtgärdsfönstret.
4. Klicka på Ändra vy.
5. Klicka på Huvudvy.
    * Öppna huvudvyn för åtkomst till snabbfliken Konfigurationsflöde.  
6. Visa eller dölj avsnittet Konfigureringsflöde.
    * Snabbfliken Konfigurationsflöde måste vara i det expanderade läget.  
7. Klicka på konfigurationsregler.
8. Klicka på Ny.
9. Markera vald rad i listan.
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
    * Artiklarna i den aktuella konfigurationsgruppen visas. Välj den som representerar villkoret i regeln.  
11. Klicka på länken på den valda raden i listan.
12. Markera ett alternativ i fältet Metod.
    * Det går att framtvinga antingen en markering eller en avmarkering av en artikel från en annan konfigurationsgrupp.  
13. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Härledd grupp.
14. Hitta och markera önskad post i listan.
15. Klicka på länken på den valda raden i listan.
    * Markera den valda konfigurationsgruppen.  
16. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Härlett artikelnummer.
17. Klicka på länken på den valda raden i listan.
    * Välj det artikelnummer som ska markeras eller avmarkeras beroende på vilken metod som har valts.  
18. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]