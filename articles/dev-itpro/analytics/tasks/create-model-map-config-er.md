--- 
title: "Skapa en konfiguration för ER-modellmappning"
description: "Använd den här proceduren för att skapa en ny elektronisk rapportering (ER)-modellmappningskonfiguration och använda inbyggda funktioner för ER för effektiv aggregerade beräkningar."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 74606b1378e94e8a6945a408520c8b68648970d8
ms.openlocfilehash: f7206126bfa6150078f1bfb4f7e07c1cf2819ce0
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---
# <a name="create-a-model-mapping-configuration-er"></a>Skapa en konfiguration för ER-modellmappning

[!include [task guide banner](../../includes/task-guide-banner.md)]

Använd den här proceduren för att skapa en ny elektronisk rapportering (ER)-modellmappningskonfiguration och använda inbyggda funktioner för ER för effektiv aggregerade beräkningar. I det här exemplet ska du skapa en konfiguration för exempelföretaget, Litware, Inc. 

Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.

Stegen kan utföras med hjälp av valfri datauppsättning. För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och markera den som aktiv”.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.  
2. Klicka på Reporting configurations.
3. Klicka på Visa filter.
4. I fältet "Namn" anger du filtervärdet, "Intrastat" och använder filteroperatören "börjar med".
    * Tillämpa det här filtret om du vill hitta datamodellkonfigurationen ”Intrastat”. Den här modellen finns redan i konfigurationsträdet. Om så är fallet kan du hoppa över nästa underaktivitet.   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a>Hämta Intrastat-modellkonfigurationerna som tillhandahålls av Microsoft
1. Stäng sidan.
2. Stäng sidan.
3. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
4. Hitta och markera önskad post i listan.
    * Välj panelen Microsoft provider.  
5. Klicka på Databaser.
    * Klicka på Databaser i panelen Microsoft-leverantör.  
6. Klicka på Visa filter.
7. I fältet "Typnamn" anger du filtervärdet, "resurser" och använder filteroperatören "innehåller". 
8. Klicka på Öppna.
9. Välj "Intrastat-modell" i trädet.
10. Klicka på Importera.
11. Klicka på Ja.
    * Du har importerat ER-modellkonfigurationen med datamodellen som ska användas för att undersöka hur de nya funktionerna för ER kan användas.  
12. Stäng sidan.
13. Stäng sidan.
14. Klicka på Reporting configurations.

## <a name="add-a-new-model-mapping-configuration"></a>Lägg till en ny konfiguration för modellmappning
1. Välj "Intrastat-modell" i trädet.
2. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
3. I fältet Nytt anger du "Modellmappning baserat på datamodell Intrastat".
4. I fältet Namn skriver du "Intrastat-exempelmappning".
    * Intrastat-exempelmappning  
5. Klicka på Skapa konfiguration.


