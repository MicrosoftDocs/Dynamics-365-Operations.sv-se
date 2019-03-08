---
title: Importera konfiguration för ISO20022-autogiro
description: Denna procedur demonstrerar hur du importerar en elektronisk rapporteringkonfiguration för kundbetalning.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1757a1477e46f71e327bb70cf4780767b7509e55
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "333080"
---
# <a name="import-iso20022-direct-debit-configuration"></a>Importera konfiguration för ISO20022-autogiro

[!include [task guide banner](../../includes/task-guide-banner.md)]

Denna procedur demonstrerar hur du importerar en elektronisk rapporteringkonfiguration för kundbetalning. I den här proceduren används formatet ISO 20022 för autogiro som exempel. 



Denna procedur skapades med hjälp av demonstrationdataföretaget DEMF, men du kan använda valfritt demonstrationsdataföretag för detta syfte.



Detta är den första av fem procedurer av fem som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. I listan över tillgängliga konfigurationsleverantörer väljer du Microsoft.
3. Klicka på Ställ in aktiv.
4. Klicka på Databaser.
5. Klicka på Öppna.
6. Klicka på Visa filter.
7. Använd följande filter: I fältet ”Configuration name” anger du filtervärdet "ISO20022 Direct debit (DE)" med hjälp av filteroperatorn ”begins with”.
    * Du kan också hitta konfigurationen i listan, välja den och hoppa över det här steget.  
8. Klicka på Importera.
    * Om importknappen inte är tillgänglig innebär det att konfigureringen redan har importerats.  
9. Klicka på Ja.

