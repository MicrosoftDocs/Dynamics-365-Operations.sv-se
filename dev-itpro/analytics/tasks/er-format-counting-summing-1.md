--- 
title: "Skapa format för inventering och summering för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: a52aade62b0d05a41e22aa9e9a474999af725606
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-formate-for-counting-and-summing-for-electronic-reporting-er"></a>Skapa format för inventering och summering för elektronisk rapportering (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning. Dessa steg kan utföras på valfritt företag.

För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.

Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Få åtkomst till listan med konfigurationer som tillhandahålls av Microsoft
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Kontrollera att ”Litware Inc."-leverantören är tillgänglig och markerats som aktiv.  
2. Välj Litware, Inc. leverantör.
3. Klicka på Databaser.
    * Om en databas av typen "Operations resources" redan finns, hoppa då över återstående steg för den aktuella underuppgiften.  
4. Klicka på Lägg till för att öppna dialogrutan.
5. Ange "Operations resources" i fältet Configuration repository type.
6. Klicka på Skapa en databas.
7. Klicka på OK.

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a>Hämta Intrastat-konfigurationerna som tillhandahålls av Microsoft
1. Klicka på Öppna.
2. Välj "Intrastat modell\Intrastat (DE)" i trädet.
3. Klicka på Importera.
    * Klicka på Import for version 1.1 för den valda konfigurationen.  
4. Klicka på Ja.
5. Stäng sidan.
6. Stäng sidan.
7. Klicka på Reporting configurations.
8. Expandera "Intrastat model" i trädet.
9. Välj "Intrastat modell\Intrastat (DE)" i trädet.


