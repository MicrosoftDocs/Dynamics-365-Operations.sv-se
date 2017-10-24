--- 
title: "Överföra en konfiguration till Lifecycle Services för elektronisk rapportering (ER)"
description: "I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny formatkonfiguration för elektronisk rapportering (ER) och överföra den till Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: d24679a380ec824fe08c56aacb4bc348ff40440a
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="upload-a-configuration-into-lifecycle-services-for-electronic-reporting-er"></a>Överföra en konfiguration till Lifecycle Services för elektronisk rapportering (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny formatkonfiguration för elektronisk rapportering (ER) och överföra den till Microsoft Lifecycle Services (LCS).

I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. och överföra den till LCS. Dessa steg kan utföras i alla företag eftersom ER-konfigureringar delas mellan företag. För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”. Åtkomst till LCS krävs även för att slutföra dessa steg.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Välj Litware, Inc. och ställ in som aktiv
3. Klientkonfigurationer.

## <a name="create-a-new-data-model-configuration"></a>Skapa en ny datamodellskonfiguration
1. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
    * Du skapar en konfiguration som innehåller en exempeldatamodell för elektroniska dokument. Denna konfiguration av datamodellen ska överföras till LCS senare.  
2. Skriv "Konfiguration av exempelmodell" i fältet Namn.
    * Konfiguration av exempelmodell.  
3. Skriv "Konfiguration av exempelmodell" i fältet Beskrivning.
    * Konfiguration av exempelmodell.  
4. Klicka på Skapa konfiguration.
5. Klicka på Modelldesigner.
6. Klicka på Ny.
7. Skriv "Startpunkt" i fältet Namn.
    * Startpunkt  
8. Klicka på Lägg till.
9. Klicka på Spara.
10. Stäng sidan.
11. Klicka på Ändra status.
12. Klicka på Slutför.
13. Klicka på OK.

## <a name="register-a-new--repository"></a>Registrera ett nytt databas
1. Stäng sidan.
2. Klicka på Databaser.
    * Detta låter dig öppna listan över databaser för konfigurationsleverantören Litware, Inc.  
3. Klicka på Lägg till för att öppna dialogrutan.
    * Detta låter dig lägga till en ny databas.  
4. I fältet Typ av konfigurationsdatabas, välj LCS.
5. Klicka på Skapa en databas.
6. Ange eller välj ett värde i fältet Projekt.
    * Välj önskat LCS-projekt. Du måste ha åtkomst till projektet.  
7. Klicka på OK.
    * Avsluta en ny databaspost.  
8. Markera vald rad i listan.
    * Välj LCS-databasposten.  
    * Observera att en registrerad databas markeras av den aktuella leverantören vilket betyder att de enda konfigurationerna som ägs av den leverantören, kan läggas till denna databas och därmed överföras till det valda LCS-projektet.  
9. Klicka på Öppna.
    * Öppna databasen om du vill visa listan över ER-konfigurationer. Den kommer att vara tom om ett sådant projekt ännu inte har använts för delning av ER-konfigurationer.  
10. Stäng sidan.
11. Stäng sidan.

## <a name="upload-configuration-into-lcs"></a>Överför konfigurationen i LCS
1. Klientkonfigurationer.
2. Välj "Konfiguration av exempelmodell" i trädet.
    * Välj en skapad konfiguration som redan har slutförts.  
3. Hitta och markera önskad post i listan.
    * Välj vilken version av den valda konfigurationen med statusen "Avslutade".  
4. Klicka på Ändra status.
5. Klicka Dela.
    * Konfigurationstatusen ändras från "Avslutade” till "Delade" när den publiceras i LCS.  
6. Klicka på OK.
7. Hitta och markera önskad post i listan.
    * Välj konfigurationsversionen som har statusen "Delad".  
    * Observera att statusen för den valda versionen har ändrats från "Slutförd till "Delad".  
8. Stäng sidan.
9. Klicka på Databaser.
    * Detta låter dig öppna listan över databaser för konfigurationsleverantören Litware, Inc.  
10. Klicka på Öppna.
    * Välj LCS-databasen och öppna den.  
    * Observera att den valda konfigurationen visas som en tillgång för det valda LCS-projektet.  
    * Öppna LCS via https://lcs.dynamics.com. Öppna ett projekt som använts tidigare för förvaringsregistrering, öppna projektets "Tillgångsbibliotek" och expandera innehållet i tillgångstypen "GER-konfiguration" – den uppladdade ER-konfigurationen blir tillgänglig. Observera att den överförda LCS-konfigurationen kan importeras till en annan Microsoft Dynamics 365 for Finance and Operations, Enterprise edition-instans, om leverantörerna har tillgång till det LCS-projektet.  


