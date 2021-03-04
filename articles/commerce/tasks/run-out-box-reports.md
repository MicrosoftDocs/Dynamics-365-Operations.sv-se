---
title: Skapa och köra färdiga rapporter
description: Använd den här uppgiftsguiden för att köra färdiga rapporter på huvudkontoret från olika arbetsytor och förfrågningar och försäljningsrapporter som finns under Handel.
author: ashishmsft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailCategoryAndProductWorkspace, RetailOrgHierarchyTreeLookup, SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d148fa36a116860af8c44043d90759b8a2d76fb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415863"
---
# <a name="generate-and-run-out-of-box-reports"></a>Skapa och köra färdiga rapporter

[!include [banner](../includes/banner.md)]

Använd den här uppgiftsguiden för att köra färdiga rapporter på huvudkontoret från olika arbetsytor och förfrågningar och försäljningsrapporter som finns under Handel.

Det demonstrationsdataföretag som används för att skapa den här registreringen är USRT. Den här registreringen är avsedd för systemadministratörsrollen.

## <a name="launch-reports-from-workspaces"></a>Starta rapporter från arbetsytor
1. Gå till Butik och handel > Produkter och kategorier > Kategori- och produkthantering.
2. Klicka på pilen för att utöka eller komprimera avsnittet Rapporter.
3. Klicka på Rapport över topprodukter.
4. Ange ett datum i fältet Från datum.
5. Ange ett datum i fältet Till datum.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kanal.
7. I trädet, välj Contoso Retail\Contoso Retail USA\Central\Houston.
    * Här visas standardorganisationshierarkin för handelrapporteringsyfte.   Gå till Organisationsadministration > Organisationer > Syften för organisationshierarki, välj handelsrapportering och under Tilldelade hierarkier, kontrollera det hierarkinamn för vilket standardkolumnen är markerad. Som en del av demodata (som används för registreringen av den här uppgiften) bör du märka att Butiker efter region är standardorganisationshierarki för syftet med rapportering.     
8. Klicka på OK.
9. Markera ett alternativ i fältet Visa.
10. Markera ett alternativ i fältet Efter.
11. Klicka på OK.

## <a name="launch-reports-from-the-inquiries-and-sales-reports"></a>Starta rapporter från förfrågningar och försäljningsrapporter
1. Gå till Butik och handel > Förfrågningar och rapporter > Försäljningsrapporter > Kategoriförsäljning – rapport.
2. Ange ett datum i fältet Från datum.
3. Ange ett datum i fältet Till datum.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kanal.
5. I trädet, välj Contoso Retail\Contoso Retail USA\West\Seattle.
    * Här visas standardorganisationshierarkin för handelrapporteringsyfte. Gå till Organisationsadministration > Organisationer > Syften för organisationshierarki, välj handelsrapportering och under Tilldelade hierarkier, kontrollera det hierarkinamn för vilket standardkolumnen är markerad. Som en del av demodata (som används för registreringen av den här uppgiften) bör du märka att Butiker efter region är standardorganisationshierarki för syftet med rapportering.     
6. Klicka på OK.
7. Klicka på OK.

## <a name="export-an-hq-reports"></a>Exportera en HQ-rapport
1. Gå till Butik och handel > Förfrågningar och rapporter > Försäljningsrapporter > Organisationsförsäljning – rapport.
2. Ange ett datum i fältet Från datum.
3. Ange ett datum i fältet Till datum.
4. Klicka på OK.
5. Klicka på Exportera.
6. Klicka på PDF.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]