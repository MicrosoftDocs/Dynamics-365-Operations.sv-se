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
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 964f396625340d593a2fe3dd5be5a1b7da795e9a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218768"
---
# <a name="import-iso20022-direct-debit-configuration"></a>Importera konfiguration för ISO20022-autogiro

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]