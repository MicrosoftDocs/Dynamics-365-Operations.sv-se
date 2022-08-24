---
title: ER Konfigurera format för inventering och summering (Del 1 - Skapa format)
description: I den här artikeln beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat för inventering och summering baserat på data i det redan genererade textutdata. (Del 1)
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form:
- ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
- ERSolutionTable
ms.openlocfilehash: b9e0128e55ba6ab356d6942020a34e5e74d6b7e2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290707"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a>ER Konfigurera format för inventering och summering (Del 1 - Skapa format)

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning. Dessa steg kan utföras på valfritt företag.

För att slutföra dessa steg måste du först slutföra stegen i proceduren "Create a configuration provider and mark it as active”.

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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
