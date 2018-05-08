--- 
title: "Kör formatet för att utföra inventering och summering"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e3569e48bcc063b2423a60038732e8e53dbea2cb
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="run-the-format-to-do-counting-and-summing"></a>Kör formatet för att utföra inventering och summering

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning. Dessa steg kan utföras i DEMF-företaget.

För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 3: Use computations to make the output)".

Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a>Testa denna konfiguration för att generera Intrastat-rapporterna
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klicka på Reporting configurations.
3. Expandera "Intrastat model" i trädet.
4. Expandera "Intrastat model\Intrastat (DE)" i trädet.
5. Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.
6. Klicka på Configurations i åtgärdsfönstret.
7. Klicka på User parameters.
8. Välj Yes i fältet Run settings.
9. Klicka på OK.
10. Klicka på Redigera.
11. Välj Yes i fältet Run Draft.
12. Klicka på Spara.
13. Gå till Moms > Inställningar > Utländsk handel > Utländska handelsparametrar.
14. Expandera avsnittet Elektronisk rapportering.
15. Välj konfigurationen "Intrastat (DE) with counting & summing".
16. Välj konfigurationen "Intrastat (DE) with counting & summing".
17. Klicka på Spara.
18. Stäng sidan.
19. Gå till Moms > Deklarationer > Utländsk handel > Intrastat.
20. Klicka på Utdata.
21. Klicka på Rapport.
    * Kör rapportgenereringsprocessen för Intrastat.  
22. Ange datumet till "2000-01-01" i fältet Från datum.
    * Definiera start- och slutdatum för den rapporteringsperiod som innehåller befintliga formulärtransaktioner.  
23. Ange datumet till "2022-12-31" i fältet Till datum.
    * Definiera start- och slutdatum för den rapporteringsperiod som innehåller befintliga formulärtransaktioner.  
24. Välj "Arrivals" i fältet Directions.
25. Välj Ja i fältet Generera fil.
26. Klicka på OK.
    * Granska den skapade utleveransen med sammanfattningsraderna i slutet.  
27. Klicka på Ny.
28. Markera vald rad i listan.
29. Välj "Dispatches" i fältet Direction.
30. Ange eller välj ett värde i fältet Artikelnummer.
31. Ange eller välj ett värde i fältet Artikel.
32. Ange Weight som "10".
33. Ange Invoice amount som "10000".
34. Ange Statistical amount som "10000".
35. Klicka på Utdata.
36. Klicka på Rapport.
37. Välj "Dispatches" i fältet Direction.
38. Klicka på OK.
    * Granska den skapade utleveransen med sammanfattningsraderna i slutet. Observera att den har ändrats i jämförelse med den första körningen.  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a>Kör denna konfiguration i felsökningsläge för att granska insamlade inventerings- och summeringsdata
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Expandera "Intrastat model" i trädet.
3. Expandera "Intrastat model\Intrastat (DE)" i trädet.
4. Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.
5. Klicka på Configurations i åtgärdsfönstret.
6. Klicka på User parameters.
7. Välj Yes i fältet Run in debug mode.
8. Klicka på OK.
9. Stäng sidan.
10. Gå till Moms > Deklarationer > Utländsk handel > Intrastat.
11. Klicka på Utdata.
12. Klicka på Rapport.
13. Klicka på OK.
14. Stäng sidan.
15. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
16. Expandera "Intrastat model" i trädet.
17. Expandera "Intrastat model\Intrastat (DE)" i trädet.
18. Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.
19. Klicka på Debug logs.
    * Observera att en post för loggfelsökning har skapats för utförandeprocessen för den valda konfigurationen.  
20. Klicka på Koppla.
21. Klicka på Öppna.
    * Förhandsvisa den skapade XML-filen som innehåller inventerings- och summeringsinformation som samlades in i samband med körningen av den valda konfigurationen.  


