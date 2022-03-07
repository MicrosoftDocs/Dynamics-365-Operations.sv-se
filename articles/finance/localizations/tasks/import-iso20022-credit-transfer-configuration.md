---
title: Importera konfiguration av ISO20022-kreditöverföring
description: Denna procedur visar hur du importerar en elektronisk rapporteringkonfiguration för leverantörsbetalning.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 38e3c5b3b85eb9ad17270cf7002046896d305548
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988274"
---
# <a name="import-iso20022-credit-transfer-configuration"></a>Importera konfiguration av ISO20022-kreditöverföring

[!include [banner](../../includes/banner.md)]

Denna procedur visar hur du importerar en elektronisk rapporteringkonfiguration för leverantörsbetalning. Det tyska ISO 20022-formatet för kreditöverföring används som exempel. Denna procedur kan användas för andra tillgängliga, elektroniska rapporteringsformat. 

Denna uppgift skapades med hjälp av demonstrationdataföretaget DEMF, men du kan använda valfritt demonstrationsdataföretag för att slutföra uppgiften.

Detta är den första av fem uppgifter som tillsammans illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. I listan över tillgängliga konfigurationsleverantörer väljer du Microsoft.
3. Klicka på Ställ in aktiv.
4. Klicka på Databaser.
5. Klicka på Öppna.
6. Klicka på Visa filter.
7. Använd följande filter: I fältet ”Configuration name” anger du filtervärdet "ISO20022 Credit transfer (DE)" med hjälp av filteroperatorn ”begins with”.
    * Du kan också söka efter konfigurationen i listan, markera den och sedan flytta den till importuppgiften.  
8. Klicka på Importera.
    * Om importknappen inte är tillgänglig innebär det att konfigureringen redan har importerats.  
9. Klicka på Ja.

