---
title: ER Mappa komponenter för det skapade till datamodellelement (november 2016)
description: I den här artikeln beskrivs hur du mappar datamodellelement till komponenter i den elektroniska rapporteringskonfigurationen (ER).
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
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
ms.openlocfilehash: d1dee2a26edd5a2162bb8c5cebaf014825f4e5a2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290227"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a>ER Mappa komponenter för det skapade till datamodellelement (november 2016)

[!include [banner](../../includes/banner.md)]

I följande procedur beskrivs hur en användare med roll som systemadministratör eller utvecklare elektronisk rapportering kan mappa datamodellelement med komponenter i den skapade elektroniska rapporteringskonfigurationen (ER), som definierar ett elektroniskt dokumentformat för affärsdomänen för betalningar. Detta format används senare för att skapa elektroniska dokument för att bearbeta betalningar. I det här exemplet skapar du en formatkonfiguration för exempelföretaget "Litware, Inc.". Dessa steg kan utföras i alla företag, eftersom ER-konfigurationer delas mellan alla företag. För att slutföra dessa steg måste du först slutföra stegen i uppgiftsguiden "Skapa en formatkonfiguration".


## <a name="select-a-format-configuration"></a>Välj en formatkonfiguration
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klicka på Reporting configurations.
3. Visa "Betalningar (förenklad modell)" i trädet.
4. Välj "Betalningar (förenklad modell)\BACS (UK fiktivt)" i trädet.
5. Klicka på Designer.

## <a name="map-format-components-to-data-model-elements"></a>Mappa formatkomponenter till datamodellelement
1. Klicka på Expandera/Komprimera.
2. Klicka på fliken Mappning.
3. Expandera "modell" i trädet.
4. Välj "Xml\Message\ProcessingDate\DateTime" i trädet.
5. Välj "model\ProcessingDateTime" i trädet.
6. Klicka på Bind.
7. Välj "Xml\Message\MessageId\String" i trädet.
8. Välj "model\MessageIdentification" i trädet.
9. Klicka på Bind.
10. Expandera "modell\Betalningar" i trädet.
11. Välj "Xml\Message\Payments\Item\Amount\String" i trädet.
12. Välj "model\Payments\InstructedAmount" i trädet.
13. Klicka på Bind.
14. Välj "Xml\Message\Payments\Item\TransDate\DateTime" i trädet.
15. Välj "model\Payments\TransactionDate" i trädet.
16. Klicka på Bind.
17. Välj "Xml\Message\Payments\Item\Description\String" i trädet.
18. Välj "modell\Betalningar\Beskrivning" i trädet.
19. Klicka på Bind.
20. Välj "Xml\Message\Payments\Item\Currency\String" i trädet.
21. Välj "modell\Betalningar\Valuta" i trädet.
22. Klicka på Bind.
23. Välj "Xml\Message\Payments\Item\Id" i trädet.
24. Välj "model\Payments\End2EndID" i trädet.
25. Klicka på Bind.
26. Expandera "modell\Betalningar\Betalningsmottagare" i trädet.
27. Expandera "modell\Betalningar\Betalningsmottagare\Konto" i trädet.
28. Expandera "modell\Betalningar\Betalningsmottagare\Agent" i trädet.
29. Välj "Xml\Message\Payments\Item\Vendor\Name\String" i trädet.
30. Välj "modell\Betalningar\Betalningsmottagare\Namn" i trädet.
31. Klicka på Bind.
32. Välj "Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String" i trädet.
33. Välj "model\Payments\Creditor\Agent\RoutingNumber" i trädet.
34. Klicka på Bind.
35. Välj "Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String" i trädet.
36. Välj "modell\Betalningar\Betalningsmottagare\Konto\Nummer" i trädet.
37. Klicka på Bind.
38. Välj "Xml\Message\Payments\Item\Payer\Name\String" i trädet.
39. Expandera "modell\Betalningar\Betalare" i trädet.
40. Expandera "modell\Betalningar\Betalare\Konto" i trädet.
41. Expandera "modell\Betalningar\Betalare\Agent" i trädet.
42. Välj "modell\Betalningar\Betalare\Namn" i trädet.
43. Klicka på Bind.
44. Välj "Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String" i trädet.
45. Välj "model\Payments\Debtor\Agent\RoutingNumber" i trädet.
46. Klicka på Bind.
47. Välj "Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String" i trädet.
48. Välj "modell\Betalningar\Betalare\Konto\Nummer" i trädet.
49. Klicka på Bind.
50. Välj "Xml\Message\Payments\Item" i trädet.
51. Välj "modell\Betalningar" i trädet.
52. Klicka på Bind.
53. Klicka på Spara.

## <a name="validate-format-mapping"></a>Validera formatmappning
1. Klicka på Validera.
    * Bekräfta den nya mappningen för att säkerställa att alla bindningar är korrekta.  
2. Stäng sidan.

## <a name="change-status-of-the-current-version-of-format-configuration"></a>Ändra status för den aktuella versionen av formatkonfigurationen
I följande steg ändrar du status för formatkonfigurationen från Utkast till Slutförd för att göra den tillgänglig för genereringen av betalningsdokument.  
1. Klicka på Ändra status.
2. Klicka på Slutför.
3. Ange ett värde i fältet Beskrivning.
    * Till exempel "Version 1".  
4. Klicka på OK.
5. Välj den slutförda versionen av den aktuella versionen.
    * Observera att konfigurationen sparas som slutförd version 1.1: version 1 av formatet, vilket baseras på version 1 av datamodellen.  

## <a name="define-effective-date-for-completed-version-of-format"></a>Definiera giltighetsdatumet för slutförd version av formatet
Varje formatversion kan konfigureras som tillgänglig för användning med start från ett visst datum. När mer än en formatversion är aktiv på att visst datum, kommer det senaste formatet (utifrån versionsnumret) att väljas för användning. Värdet för sessionsdatumet används för ett korrekt versionsurval.  

## <a name="restrict-access-to-created-format-from-companies"></a>Begränsa åtkomsten till det skapade formatet från företag
1. Visa eller dölj avsnittet om ISO-koder för land/region.
    * Varje formatåtkomst kan begränsas genom att identifiera särskilda länder/regioner som ett format kan tillämpas på. När listan över länder/regioner för ett visst format är tomt, kan formatet användas i alla företag. När vissa ISO-koder för land/region infogas i listan över länder/regioner kan formatet endast användas i företag vars primära adress ligger i landet/regionen.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
