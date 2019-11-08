---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 1 - Förbered datamodellen)
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 29c13e729223a98d7f45244c5a796bca6e3baaf3
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550843"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a>ER Använd dokumenthanteringsfiler i formatutmatningar (Del 1 - Förbered datamodellen)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar. Dessa steg kan utföras på valfritt företag.

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

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a>Skaffa modellkonfigurationerna för kundfakturor som tillhandahålls av Microsoft
1. Klicka på Visa filter.
2. Använd följande filter: Ange filtervärdet "Operations resources" på fältet "Name" med filteroperatorn "begins with"; ange filtervärdet "" på fältet "Description" med filteroperatorn "begins with".
3. Klicka på Visa filter.
4. Klicka på Öppna.
5. Välj "Customer invoice model" i trädet.
    * Välj modellkonfigurationen "Customer invoice model" för att importera den.  
6. Klicka på Importera.
    * Klicka på Import for version 1 för den valda konfigurationen.  
7. Klicka på Ja.
8. Stäng sidan.
9. Stäng sidan.
10. Klicka på Reporting configurations.
11. Välj "Customer invoice model" i trädet.

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a>Skapa den härledda modellen så att denna stöder åtkomst till dokumenthanteringsfilerna.
    * Du kan skapa en egen konfiguration av kundfakturamodellen baserat på den konfiguration som tillhandahålls av Microsoft. Du använder den här konfigurationen för att implementera åtkomst till dokumenthanteringsfilerna och göra dem tillgängliga för elektroniska dokument som du skapar baserat på denna modell.  
1. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
2. Ange "Derive from Name: Customer invoice model, Microsoft" i fältet New.
3. Ange "Customer invoice model (custom)" i namnfältet.
    * Fakturamodell för kund (anpassad)  
4. Klicka på Skapa konfiguration.
