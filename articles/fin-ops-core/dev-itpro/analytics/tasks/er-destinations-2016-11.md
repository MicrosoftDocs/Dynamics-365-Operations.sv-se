---
title: ER konfigurera mål
description: Den här proceduren visar hur du ställer in och använder olika mål för utdatakomponenter för elektronisk rapportering (ER) som till exempel en mapp eller en fil.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERFormatDestinationTable, SysLookupPicklist, ERFormatDestinationSettings, ERFormatDestinationEmailSettings, ERExpressionDesignerFormula, SRSPrintDestinationTokens
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0073033454c7d3054496fe4c38cdb3cff71d8755
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681887"
---
# <a name="er-configure-destinations"></a>ER konfigurera mål

[!include [banner](../../includes/banner.md)]

Den här proceduren visar hur du ställer in och använder olika mål för utdatakomponenter för elektronisk rapportering (ER) som till exempel en mapp eller en fil. Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF. Tyskland är land/region för den juridiska personens primära adress, men du kan använda valfri juridisk person för denna procedur. 

Formatet som används i det här exemplet är kreditöverföringen ISO20022, men du kan använda valfritt format som du redan har importerat. Observera att den här proceduren är ett exempel på en enda fil och en enda målsinställning. Mer information om hantering av elektroniska rapporteringsmål finns i hjälpen för Dynamics 365 Finance.

1. Gå till Organisationsadministration > Elektronisk rapportering > Elektroniska rapporteringsmål.
2. Klicka på Ny för att skapa en ny uppsättning mål för ett format.
3. Välj ett format som du vill konfigurera för mål i fältet Referenser.
    * Om du inte har ett värde som ska markeras, innebär det att du inte har importerat några elektroniska rapporteringformatkonfigurationer. Du måste importera en formatkonfiguration innan du ställer in mål.  
4. Klicka på New om du vill skapa en ny filmål.
    * Observera att du kan skapa en filmål för varje utleveranskomponent av samma format, till exempel en mapp eller en fil. Du kommer att kunna aktivera och avaktivera mål separat i inställningarna.  
5. Ange det användarvänliga namnet på utleveranskomponenten i namnfältet.
    * Vi rekommenderar att du använder meningsfulla namn, till exempel ”betalningsfil” eller” kontrollrapport ". Dessa namn ska visas för användarna i konfigurationkörning tillsammans med målsinställningarna.  
6. Välj en fil eller en mapp som är specifik för formatet i Filnamn.
7. Klicka på Inställningar.
8. Välj Ja i fältet Aktiverad.
    * Kryssrutan Aktiverad på varje flik aktiverar och avaktiverar varje mål separat. I det här exemplet kan du aktivera att skicka en utdatafil till en e-postmottagare när filen skapas.  
9. Klicka på Edit för att konfigurera e-postmottagare.
10. Klicka på Lägg till.
11. Klicka på Print Management email.
12. Välj ett alternativ i fältet Email source.
    * Du kan välja olika typer för e-postkälla, till exempel en kund- eller leverantörstyp. Detta definierar den typ av argument som ska returneras av e-postkällans kontoformel. E-postkällans kontoformel, som beskrivs i följande steg, är platsen där du binder upp en e-postmeddelandekälla. Markera Leverantör om din formel returnerar ett leverantörskonto. Använd Leverantör om du använder exemplet ISO 20022 Kreditöverföringskonfiguration.  
13. Klicka på knappen Email source bind.
14. Ange en dokumentspecifik referens till en tidigare vald parttyp i formeln.
    * I stället för att skriva kan du hitta en datakällnod som representerar partens konto och klicka på knappen Add data source om du vill uppdatera formeln. Om du till exempel använder kreditöverföringskonfigurationen ISO 20022, är noden som representerar ett leverantörskonto '$PaymentsForCoveringLetter'.Creditor.Identification.SourceID. Ange ett strängvärde som till exempel "DE-001" om du vill spara en formel.  
15. Klicka på Spara.
16. Stäng sidan.
17. Klicka på Edit för att konfigurera kontaktinformation för parten.
18. Välj Yes i fältet Primary contact.
    * Du kan använda olika alternativ du vill ange vilken av partens kontakttyper som ska användas som en e-postadress för detta mål. Vi använder en primär kontakt i det här exemplet.  
19. Klicka på OK.
20. Klicka på OK.
21. Skriv ett värde i fältet Ämne.
22. Klicka på OK.

