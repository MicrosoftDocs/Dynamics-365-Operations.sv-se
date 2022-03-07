---
title: Definiera ER‑konfigurationers beroende av andra komponenter
description: I det här avsnittet beskrivs hur du utformar en elektronisk rapporteringskonfiguration (ER) och anger sitt beroende från andra programvarukomponenter.
author: NickSelin
ms.date: 07/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2901092938dae5ae14480716eeeb2b0386848332e91ad388ce5d34437f8492ba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717604"
---
# <a name="define-the-dependency-of-er-configurations-on-other-components"></a>Definiera ER‑konfigurationers beroende av andra komponenter

[!include [banner](../../includes/banner.md)]

För att kunna genomföra stegen måste du först slutföra stegen i uppgiftsguiden ER Hantera modellmappningskonfigurationer, och ha åtkomst till Microsoft Dynamics Lifecycle Services (LCS).

I den här proceduren beskrivs hur du skapar en konfiguration för elektronisk rapportering (ER) och anger beroendet från andra programvarukomponenter, så att du kan garantera att konfigurationen hämtas korrekt till en viss version av Finance and Operations. I det här exemplet ska du skapa erforderliga ER-konfigurationer för exempelföretaget Litware, Inc. 

Den här proceduren är avsedd för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Dessa steg kan utföras i alla företag, eftersom ER-konfigurationer delas mellan företag. 

1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
    * Kontrollera att konfigurationsträdet innehåller konfigurationen Exempel på datamodell och underordnade objekt. I annat fall genomför du stegen i uppgiftsguiden ER Hantera modellmappningskonfigurationer och startar den här guiden igen.   

## <a name="define-the-dependency-of-er-configurations-from-other-components"></a>Definiera beroendet av ER-konfigurationer från andra komponenter
1. Expandera Sample data model i trädet.
2. Välj Sample data model\Sample mapping i trädet.
    * Vi har valt utkastversionen av modellmappningskonfigurationen Exempelmappning. Vi ska nu definiera beroendet från andra programvarukomponenter. Det här steget anses vara en förutsättning för att styra hämtningen av den här konfigurationens version från en ER-databas och ytterligare användning av den här versionen.   
3. Expandera avsnittet Förutsättningar.
    * Observera att gruppen för implementeringsförutsättningar har lagts till automatiskt i det stadiet. Den här gruppen innehåller den nödvändiga komponent som refererar till den datamodellkonfigurationen och har flaggan Implementering aktiverad. Den här flaggan innebär modellmappningskonfigurationen Exempelmappning tar hänsyn till implementeringen av datamodellen Exempeldatamodell. Den här komponenten tvingar ER att hämta mappningskonfigurationen Exempelmappning från en ER-databas när modellkonfigurationen Exempeldatamodell hämtas.   
4. Klicka på Redigera.
    * Du kan ange ett enstaka beroende av den aktuella versionen av en konfiguration från en programvarukomponent med definitionen för komponenttypen, och antingen versionen av komponenten eller flera olika versioner av komponenten.  
    * Önskade beroenden kan grupperas. När grupptypen Alla väljs, anses beroendevillkoret för den här gruppen vara uppfyllt när varje beroendevillkor från den här gruppen och den underordnade gruppen uppfylls. När grupptypen En av väljs, anses beroendevillkoret för den här gruppen vara uppfyllt när minst ett beroendevillkor från den här gruppen uppfylls.   
5. Klicka på Ny.
6. Välj produktförutsättningskomponenten.
7. Välj Microsoft Dynamics 365 for Operations (1611).
8. Skriv "[7.1.1541.3036,8)" i fältet Version.
    * [7.1.1541.3036,8)  
    * När den här konfigurationen har hämtats från en ER-databas utvärderas de beroenden som du anger. Den här konfigurationsversionen hämtas från ER-databasen när version 1 av konfigurationen Exempeldatamodell redan finns på plats eller har hämtats i förväg. Om den hämtas i förväg måste detta genomföras i Finance and Operations, versionen måste vara 7.1.1541.3036 eller senare och den får inte vara senare än huvudversion 8.   
9. Klicka på Spara.
10. Stäng sidan.
11. Klicka på Ändra status.
12. Klicka på Slutför.
13. Klicka på OK.
14. Välj Sample data model\Sample mapping (alternative) i trädet.
15. Klicka på Redigera.
16. Klicka på Ny.
17. Välj produktförutsättningskomponenten.
18. Välj Microsoft Dynamics AX 7.0 RTW.
19. Skriv "[7.0.1265.3015,7.1)" i fältet Version.
    * [7.0.1265.3015,7.1)  
    * Beroendena utvärderas när den här konfigurationen har hämtats från en ER-databas. Den här konfigurationsversionen hämtas från ER-databasen när version 1 av konfigurationen Exempeldatamodell redan finns på plats eller har hämtats i förväg. Om den hämtas i förväg måste detta genomföras i Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, versionen måste vara 7.0.1265.3015 eller senare och den får inte vara senare än delversion 1.   
20. Klicka på Spara.
21. Stäng sidan.
22. Klicka på Ändra status.
23. Klicka på Slutför.
24. Klicka på OK.

## <a name="configure-the-er-repository"></a>Konfigurera ER-databasen
1. Stäng sidan.
2. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Öppna listan över ER-databaser den aktuella ER-leverantören, Litware, Inc.  
3. Markera vald rad i listan.
4. Klicka på Databaser.
5. Klicka på Visa filter.
6. Ange filtervärdet "LCS" i fältet "Typnamn" med filteroperatorn "innehåller".
    * Om LCS-databasen redan är registrerad för den aktuella ER-leverantören du kan hoppa över resten av stegen i den här underaktiviteten. Om LCS-databasen inte redan är registrerad ska du utföra resten av stegen.   
7. Klicka på Lägg till för att öppna dialogrutan.
8. Skriv "LCS" i fältet Typ av konfigurationsdatabas.
9. Klicka på Skapa en databas.
10. Ange eller välj ett värde i fältet Projekt.
    * Välj önskat LCS-projekt från sökningen i fältet Projekt.  
11. Klicka på OK.
12. Stäng sidan.

## <a name="upload-configurations-to-lcs"></a>Överför konfigurationer till LCS
1. Klicka på Reporting configurations.
2. Välj "Sample data model" i trädet.
3. Välj den slutförda versionen av den här konfigurationen.
4. Klicka på Ändra status.
5. Klicka Dela.
6. Klicka på OK.
    * Version 1 av denna modellkonfiguration har överförts till LCS med hjälp av LCS-projektet för ER-databasen som konfigurerades tidigare.   
7. Expandera Sample data model i trädet.
8. Välj Sample data model\Sample mapping i trädet.
9. Välj den slutförda versionen av den här konfigurationen.
10. Klicka på Ändra status.
11. Klicka Dela.
12. Klicka på OK.
    * Version 1.1 av denna modellmappningskonfiguration har överförts till LCS med hjälp av LCS-projektet för ER-databasen som konfigurerades tidigare.   
13. Välj Sample data model\Sample mapping (alternative) i trädet.
14. Välj den slutförda versionen av den här konfigurationen.
15. Klicka på Ändra status.
16. Klicka Dela.
17. Klicka på OK.
    * Version 1.1 av denna modellmappningskonfiguration har överförts till LCS med hjälp av LCS-projektet för ER-databasen som konfigurerades tidigare.   

## <a name="evaluate-er-configuration-dependencies"></a>Utvärdera beroenden för ER-konfiguration
Vi ska ta bort de skapade konfigurationerna från systemet och hämta tillbaka dem från LCS-databasen.  
1. Välj Sample data model\Sample mapping i trädet.
2. Klicka på Ta bort.
3. Klicka på Ja.
4. Välj Sample data model\Sample mapping (alternative) i trädet.
5. Klicka på Ta bort.
6. Klicka på Ja.
7. Välj Sample data model\Sample format i trädet.
8. Klicka på Ta bort.
9. Klicka på Ja.
10. Välj "Sample data model" i trädet.
11. Klicka på Ta bort.
12. Klicka på Ja.
13. Stäng sidan.
    * Öppna listan över ER-databaser den aktuella ER-leverantören, Litware, Inc.  
14. Klicka på Databaser.
15. Klicka på Visa filter.
16. Ange filtervärdet "LCS" i fältet "Typnamn" med filteroperatorn "innehåller".
17. Klicka på Öppna.
18. Välj "Sample data model" i trädet.
    * Observera att du kan visa en utvärdering av om nödvändiga villkor är uppfyllda för varje version av ER-konfigurationerna för den aktuella databasen. Visa utvärderingen genom att klicka på Kontrollera förutsättningar.   
19. Klicka på Kontrollera förutsättningar.
20. Klicka på Importera.
21. Klicka på Ja.
22. Stäng sidan.
23. Stäng sidan.
24. Stäng sidan.
25. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
26. Expandera Sample data model i trädet.
    * Observera att modellkonfigurationen Exempelmappning har hämtats tillsammans med den valda datamodellkonfigurationen. De två filerna hämtas tillsammans eftersom Exempelmappning har definierats till att implementera den valda datamodellen, och eftersom den gäller för appen. Konfigurationen Exempelmappning (alternative) har inte hämtats eftersom villkoret för programversionen inte är uppfyllt.   
    * Om du loggar in till Finance and Operations, registrerar samma leverantör, öppnar LCS-projektet och hämtar samma datamodellkonfiguration, hämtas konfigurationen Exempelmappning (alternativ) medan konfigurationen Exempelmappning hoppas över.  

## <a name="additional-resources"></a>Ytterligare resurser

[Hantera livscykeln för konfiguration av elektronisk rapportering (ER)](../general-electronic-reporting-manage-configuration-lifecycle.md)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
