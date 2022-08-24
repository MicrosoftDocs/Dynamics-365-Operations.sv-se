---
title: Hantera ER-modellmappning i separata ER-konfigurationer
description: Den här avsnittet beskriver hur du hanterar ER-modellmappningar för elektronisk rapportering i separata ER-konfigurationer.
author: kfend
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 23ac14ba06b6ab535545bacbafe90a4a3c946476
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290257"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a>Hantera ER-modellmappning i separata ER-konfigurationer

[!include [banner](../../includes/banner.md)]

I följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan hantera ER-modellmappningar (elektronisk rapportering) i separata ER-konfigurationer. I den här uppgiftsguide skapar du de ER-konfigurationer som krävs för exempelföretaget Litware, Inc. För att slutföra uppgiftsguiden måste du först slutföra stegen i uppgiftsguiden ”ER skapa en konfigurationsleverantör” och markera den som aktiv. 

Eftersom ER-konfigurationer delas mellan företag kan du genomföra den här uppgiftsguiden med valfri företagsdatauppsättning. Funktionen för den här uppgiften är tillgänglig om du har installerat någon av följande snabbkorrigeringar: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 för Dynamics AX 7.0 version eller https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 för Dynamics 365 for Operations version.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Kontrollera att konfigurationsleverantören för provföretaget "Litware, Inc." är markerad som aktiv och tillgänglig. Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i uppgiftsguiden Skapa en konfigurationsleverantör och välja den som aktiv.   

## <a name="add-a-new-er-model-configuration"></a>Lägg till en ny konfiguration för ER-modell
1. Klicka på Reporting configurations.
    * Lägg till en ny modellkonfiguration. Namnet måste vara unikt i konfigurationsträdet.  
2. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
3. Skriv "Sample data model" i namnfältet.
    * Exempel på datamodell  
4. Klicka på Skapa konfiguration.
5. Klicka på Designer.
6. Klicka på Nytt om du vill öppna dialogrutan.
7. Ange "Root" i namnfältet.
    * Rot  
8. Klicka på Lägg till.
9. Klicka på Nytt om du vill öppna dialogrutan.
10. Skriv "Företag" i fältet Namn.
    * Företag  
11. Klicka på Lägg till.
12. Gå till beskrivningsfältet och skriv texten "Description of the legal entity or company in which a user logged at run-time". 
    * Beskrivning av den juridiska personen eller företaget som en användare loggat in till under körning.  
13. Klicka på Rotreferens.
14. Klicka på OK.
15. Klicka på Spara.
16. Stäng sidan.
17. Klicka på Ändra status.
18. Klicka på Slutför.
19. Klicka på OK.

## <a name="add-a-new-er-model-mapping-configuration"></a>Lägg till en ny konfiguration för ER-modellmappning
1. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
2. Skriv "Model Mapping based on data model Sample data model" i fältet Ny.
3. Skriv "Sample mapping" i namnfältet.
    * Exempelmappning  
4. Klicka på Skapa konfiguration.
5. Expandera avsnittet Förutsättningar.
    * Gruppen för implementeringsförutsättningar har lagts till automatiskt. Gruppen innehåller den nödvändiga komponent som refererar till den överordnade datamodellkonfigurationen och markeras som Implementering. Detta innebär den här Sample-mapping av modellmappningskonfiguration tar hänsyn till implementering av datamodellen, Sample data model. Den här komponenten tvingar därför ER att hämta modellmappningskonfigurationen, Sample mapping, från en ER-databas när modellkonfigurationen, Sample data model, hämtas.   
6. Klicka på Designer.
    * Observera att den skapade modellmappningskonfigurationen innehåller en tom ny mappning med samma namn som den skapade konfigurationen. När en vald överordnad modellkonfiguration innehåller modellmappningar kopieras de till en ny modellmappningskonfiguration.   
7. Klicka på Designer.
8. Välj "Dynamics 365 for Operations\Table" i trädet.
9. Klicka på Lägg till rot.
10. Skriv "Företag" i fältet Namn.
    * Företag  
11. Skriv "CompanyInfo" i fältet Tabell.
    * CompanyInfo  
12. Klicka på OK.
13. Expandera "Company" i trädet.
14. Expandera Company\find() i trädet.
15. Välj Company\find()\Name i trädet.
16. Klicka på Bind.
17. Klicka på Spara.
18. Stäng sidan.
19. Stäng sidan.
20. Klicka på Configurations i åtgärdsfönstret.
21. Klicka på User parameters.
22. Välj Yes i fältet Run settings.
23. Klicka på OK.
24. Klicka på Redigera.
25. Välj Yes i fältet Run Draft.

## <a name="add-a-new-er-format-configuration"></a>Lägg till en ny konfiguration för ER-format
1. Välj "Sample data model" i trädet.
2. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
3. Skriv "Format based on data model Sample data model" i fältet Ny.
4. Skriv "Sample format" i namnfältet.
    * provformat  
5. Klicka på Skapa konfiguration.
6. Klicka på Designer.
7. Klicka på Lägg till rot för att öppna dialogrutan.
8. Välj "Text\Sträng" i trädet.
9. Klicka på OK.
10. Klicka på fliken Mappning.
11. Expandera "modell" i trädet.
12. Välj model\Company i trädet.
13. Klicka på Bind.
14. Klicka på Spara.
15. Stäng sidan.
    * Kör utkastversionen av det skapade formatet i testsyfte.  
16. Klicka på Kör.
    * Klicka på Kör på snabbfliken Versioner.  
17. Klicka på OK.
    * Granska utdata som innehåller namnet på det företaget där användaren som kör den här formatkonfigurationen är inloggad i. Den skapade konfigurationen för modellmappning används av denna formatkonfiguration eftersom det bara finns en konfigurationsnyckel som innehåller nödvändiga modellmappningar.   

## <a name="add-alternative-er-model-mapping-configuration"></a>Lägg till en alternativ konfiguration för ER-modellmappning
1. Välj "Sample data model" i trädet.
2. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
3. Skriv "Model Mapping based on data model Sample data model" i fältet Ny.
4. Skriv "Sample mapping (alternative)" i namnfältet.
    * Exempelmappning (alternativ)  
5. Klicka på Skapa konfiguration.
6. Klicka på Designer.
7. Klicka på Designer.
8. Välj "Dynamics 365 for Operations\Table" i trädet.
9. Klicka på Lägg till rot.
10. Skriv "Företag" i fältet Namn.
    * Företag  
11. Skriv "CompanyInfo" i fältet Tabell.
    * CompanyInfo  
12. Klicka på OK.
13. Klicka på Redigera.
14. Välj "Sträng\SAMMANFOGA" i trädet.
15. Klicka på funktionen Lägg till.
16. Expandera "Company" i trädet.
17. Expandera Company\find() i trädet.
18. Välj Company\find()\Name i trädet.
19. Klicka på Lägg till datakälla.
20. Skriv ett värde i fältet Formel.
    * CONCATENATE(Company.'find()'.Name, ";",  
21. Välj Company\find()\Company(DataArea) i trädet.
22. Klicka på Lägg till datakälla.
23. Skriv ett värde i fältet Formel.
    * CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)  
24. Klicka på Spara.
25. Stäng sidan.
26. Klicka på Spara.
27. Stäng sidan.
28. Stäng sidan.
29. Välj Yes i fältet Run Draft.

## <a name="use-an-existing-er-model-mapping-configuration"></a>Använd en befintlig konfiguration för ER-modellmappning
1. Välj Sample data model\Sample format i trädet.
2. Klicka på Kör.
    * Den valda utkastversionen av ER-formatkonfigurationen inte kan köras eftersom det finns mer än en modellmappningskonfiguration för den odefinierade datamodellen som har valts som datakälla för ER-formatet som körs.   
    * Härnäst ska du definiera den alternativa modellmappningskonfigurationen som den varifrån modellmappningar ska användas som datakällor för ER-formatet som körs.   
3. Välj Sample data model\Sample mapping (alternative) i trädet.
4. Välj Ja i fältet Standard för modellmappning.
5. Välj Sample data model\Sample format i trädet.
6. Klicka på Kör.
7. Klicka på OK.
    * Standardmodellmappningskonfigurationen används i den här formatkonfigurationen för att generera det elektroniska dokumentet (de utdata som skapas innehåller företagskoden).  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
