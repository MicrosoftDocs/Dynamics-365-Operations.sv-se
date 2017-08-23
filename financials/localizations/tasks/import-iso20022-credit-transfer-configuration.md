--- 
title: "Importera konfiguration av ISO20022-kreditöverföring"
description: "Denna procedur visar hur du importerar en elektronisk rapporteringkonfiguration för leverantörsbetalning."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 52d502a53deb6defa619af4ca8cdc3158e086bae
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="import-iso20022-credit-transfer-configuration"></a>Importera konfiguration av ISO20022-kreditöverföring

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


