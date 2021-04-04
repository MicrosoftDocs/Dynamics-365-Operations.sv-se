---
title: Skapa modellmappningskonfigurationer för elektronisk rapportering (ER)
description: Använd den här proceduren för att skapa en ny elektronisk rapportering (ER)-modellmappningskonfiguration och använda inbyggda funktioner för ER för effektiv aggregerade beräkningar.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c52f5d23f6c1cdad346a8a5e94535a4cba19057
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562890"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a>Skapa modellmappningskonfigurationer för elektronisk rapportering (ER)

[!include [banner](../../includes/banner.md)]

Använd den här proceduren för att skapa en ny elektronisk rapportering (ER)-modellmappningskonfiguration och använda inbyggda funktioner för ER för effektiv aggregerade beräkningar. I det här exemplet ska du skapa en konfiguration för exempelföretaget, Litware, Inc. 

Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.

Stegen kan utföras med hjälp av valfri datauppsättning. För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.

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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]