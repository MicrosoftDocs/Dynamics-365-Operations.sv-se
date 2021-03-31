---
title: Ställ in en produktkonfigurationsmodell
description: Den här artikeln beskriver hur du ställer in och skapar en modell för produktkonfiguration.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 4051
ms.assetid: 00df5537-b148-4e32-a248-3e35876ad4e1
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0ad6b8b7f3111f44b725de07d2541411e4145884
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204650"
---
# <a name="set-up-a-product-configuration-model"></a>Ställ in en produktkonfigurationsmodell

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur du ställer in och skapar en modell för produktkonfiguration.

| Uppgift                                                        | beskrivning                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Skapa en produktmall.                                    | Skapa en produktmall från listan **Produktmall**. Frisläpp produktmallen till alla berörda företag. För en produktmall som används som en version för en produktkonfigurationsmodell eller som en delkomponent. **Begränsningsbaserad konfiguration** måste markeras som konfigurationteknologi och konfigurationsdimensionen måste bara väljas för produktdimensiongruppen. |
| Skapa komponenter.                                          | Skapa komponenter på sidan **Komponenter**. Komponenterna är byggblocken av en produktkonfigurationsmodell och kan återanvändas i flera produktkonfigurationsmodeller.                                                                                                                                                                                                                      |
| Skapa attributstyper.                                     | Skapa attributtyper på sidan **Attributtyper**. Attributtyper anger de uppsättning datatyper för attribut som används i en modell för produktkonfigurationsmodeller. Attribut av **Booleskt**, **Text** med en fast lista och **Heltal** med en intervalltyplista är uppsättning värden som är tillgängliga när du konfigurerar en produktvariant som baseras på en produktkonfigurationsmodell.       |
| Skapa en ny produktkonfigurationsmodell.                       | Skapa en produktkonfigurationsmodell på sidan **Ny produktkonfigurationsmodell**.                                                                                                                                                                                                                                                                                                              |
| Lägg till attribut till produktkonfigurationsmodell.            | Skapa ett attribut på snabbfliken **Attribut** på sidan **Detaljer för begränsningsbaserad produktkonfigurationsmodell**. Attribut beskriver alla funktioner för modellen för produktkonfiguration.                                                                                                                                                                                                       |
| Lägg till begränsningar till produktkonfigurationsmodell.           | Skapa ett begränsningar på snabbfliken **Begränsningar** på sidan **Detaljer för begränsningsbaserad produktkonfigurationsmodell**. Begränsningar är begränsningar som en produktkonfiguration måste uppfylla. Det kan antingen vara uttryckbegränsningar eller registret begränsningar:                                                                                                                                 |
| Lägg till delkomponenter i en produktkonfigurationsmodell.         | Skapa delkomponenter på snabbfliken **Delkomponenter** på sidan **Detaljer för begränsningsbaserad produktkonfigurationsmodell**. Delkomponenter är kopplade till komponenter och är länkade till artiklar som utgör delkomponenten.                                                                                                                                                                       |
| Lägg till användarkrav i en produktkonfigurationsmodell.     | Användarkrav liknar delkomponenter, men refererar inte till en artikel. Du kan tänka på användarkrav som en fiktiv strukturlista. Vissa strukturlisterader eller flödesoperationer som placeras direkt under användarkravet, kommer att döljas i den överordnade komponenten.                                                                                                                       |
| Lägg till strukturlisterader till produktkonfigurationsmodell.             | Skapa strukturlisterader på snabbfliken **Strukturlisterader** på sidan **Detaljer för begränsningsbaserad produktkonfigurationsmodell**. Strukturlisterader representerar en del som krävs för att bygga en variant av produkten.                                                                                                                                                                                                 |
| Lägg till flödesoperationer i en produktkonfigurationsmodell.      | Skapa flödesoperationer på snabbfliken **Flödesoperationer** på sidan **Detaljer för begränsningsbaserad produktkonfigurationsmodell**. Flödesoperationer representerar ett steg i en sekvens med steg som utförs för att göra en variant av produkten.                                                                                                                                                    |
| Skapa en aktiv version för en produktkonfigurationsmodell. | Skapa en aktiv version av produktkonfigurationsmodellen på sidan **Versioner**. En version är relationen mellan en produktkonfigurationsmodell och en produktmall. En produktkonfigurationsmodell som har en aktiv version kan konfigureras från en försäljningsorder, försäljningsoffert, inköpsorder eller produktionsorder.                                                               |
| Testa en produktkonfigurationsmodell.                         | Testa produktkonfigurationsmodell antingen från sidan **Detaljer för begränsningsbaserad produktkonfigurationsmodell** eller sidan **Lista över produktkonfigurationsmodeller**. Test av produktkonfigurationsmodellerna simulerar produktmodellkonfigurationprocessen som inträffar under orderhantering.                                                                                                |
| Skapa mallar för produktkonfigurationsmodeller                | Skapa en mall för produktkonfigurationsmodell på sidan **Konfigurationsmallar**. En konfigurationsmall innehåller värden för attribut i produktkonfigurationsmodellen. Välj attributvärdena på sidan **Konfigurera rad**. Du kan välja om du vill läsa in en konfigurationsmall för produktmodell under produktmodellkonfigurationen.                                                   |
| Konfigurera en artikel.                                          | Produktkonfigurationsmodeller kan konfigureras från en försäljningsorder, försäljningsoffert, inköpsorder eller produktionsorder.                                                                                                                                                                                                                                                                           |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]