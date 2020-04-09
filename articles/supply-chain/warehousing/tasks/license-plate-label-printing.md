---
title: Aktivera utskrift av ID-nummer
description: I det här avsnittet visar vi hur du aktiverar automatisk utskrift av ett EAN-kollinummer (SSCC) efter den sista artikeln som plockas från lagret i arbetsprocessen för försäljningsplocklistan.
author: perlynne
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 545f1c15888bcd0b46e1028f58cbe3a274846c92
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146041"
---
# <a name="enable-license-plate-label-printing"></a>Aktivera utskrift av ID-nummer

[!include [banner](../../includes/banner.md)]

I det här avsnittet visar vi hur du aktiverar automatisk utskrift av ett EAN-kollinummer (SSCC) efter den sista artikeln som plockas från lagret i arbetsprocessen för försäljningsplocklistan. Du kan köra den här proceduren i demonstrationsdataföretaget USMF. Om du kör med dina egna data måste du ha en nummerserie som har ställts in för ID-nummer. Du måste konfigurera en etikettskrivare innan du börjar med den här uppgiften. Gå till Organisationsadministration > Inställningar > Nätverksskrivare. I åtgärdsfönstret klickar du på Alternativ och sedan på knappen Hämta installationsprogram för dokumentflödesagent. Kör installationsprogrammet och kontrollera att du har en nätverkskrivare som är inställd på Aktiv innan du fortsätter med proceduren.


## <a name="set-up-the-gs1-company-prefix"></a>Ställ in GS1-företagsprefix
1. Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Parametrar för lagerstyrning**.
2. Ange det sjusiffriga numret på ditt GS1-företag i fältet **GS1-företagsprefix**.
3. Välj **Spara**.
4. Stäng sidan.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Ställ in nummerserien för SSCC-ID-numret
1. Gå till **Navigeringsfönster > Moduler > Organisationsadministration > Nummerserier > Nummerserier**.
2. Välj ett alternativ i fältet **Område**.
3. Välj ett alternativ i fältet **Referens**.
4. Skriv ett värde i fältet **Företag**.
5. Expandera avsnittet **Segment**.
6. Välj **Redigera**.
7. Välj den första raden i tabellen **Segment**
8. Välj **Ta bort**.
9. Välj **Ta bort**.
10. Välj **Spara**.
11. Stäng sidan.

## <a name="create-the-document-route-layout"></a>Skapa dokumentflödeslayouten
1. Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Dokumentflöde > Dokumentflödets layouter**. Aktivera SSCC-layout.  
2. Välj **Ny**.
3. Ange ett värde i fältet **Layout-ID**.
4. I fältet **Beskrivning** anger du ett värde.
5. Välj **Infoga vid textens slut**.
6. Välj **Spara**.
7. Stäng sidan.

## <a name="set-up-the-document-routing"></a>Ställ in dokumentflödet
1. Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Dokumentflöde > Dokumentflöde**.
2. Välj ett alternativ i fältet **Arbetsordertyp**.
3. Välj **Ny**.
4. Ange ett värde i fältet **Lagerställe**.
5. Skriv ett värde i fältet **Namn**.
6. Välj **Ny**.
7. Ange eller välj ett värde i fältet **Layout-ID**.
8. I fältet **Namn**, ange printernamnet som du vill använda.
9. Välj **Spara**.
10. Stäng sidan.

## <a name="create-mobile-device-menu"></a>Skapa meny på mobil enhet
1. Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet**.
2. Välj **Ny**.
3. Ange ett värde i fältet **Menyalternativnamn**.
4. Ange ett värde i fältet **Rubrik**.
5. Välj ett alternativ i fältet **Metod**.
6. Välj **Ja** i fältet **Använd befintligt arbete**.
7. Välj **Ja** i fältet **Generera registreringsskylt**.
8. Expandera avsnittet **Arbetsklasser**.
9. Välj **Ny**.
10. Ange ett värde i fältet **Arbetsklass-ID**.
11. Välj **Spara**.
12. Stäng sidan.
13. Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Mobil enhet > Meny på mobil enhet**.
14. Välj menyalternativet som du nyss skapade i trädet.
15. Välj **Redigera**.
16. Välj pilen för att lägga till menyalternativet på menyn.
17. Välj **Spara**.
18. Stäng sidan.

## <a name="update-a-work-template"></a>Uppdatera en arbetsuppgiftsmall
1. Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Arbete > Arbetsmallar**.
2. Välj **Redigera**.
3. Välj **Ny**.
4. Välj **Skriv ut** i fältet **Arbetstyp**.
5. Ange eller välj ett värde i fältet **Arbetsklass-ID**.
6. Välj **Flytta upp**.
7. Välj **Spara**.
8. Stäng sidan.

