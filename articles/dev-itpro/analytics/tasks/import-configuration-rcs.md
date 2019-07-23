---
title: (ER) Importera konfigurationer från RCS
description: I det här avsnittet finns information om hur en användare kan importera en ny version av en återställningskonfiguration från RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c458cf815837fb7e4688c4c0443b7962cac403a5
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/04/2019
ms.locfileid: "1727016"
---
# <a name="er-import-configurations-from-rcs"></a>(ER) Importera konfigurationer från RCS

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan importera en ny version av en konfiguration för elektronisk rapportering (ER) från Microsoft Regulatory Configuration Services (RCS). I det här exemplet ska du välja den version av ER-konfiguration som har konfigurerats i en RCS-instans och importera den till den aktuella Finance and Operations-instansen för exempelföretaget Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigurationer delas mellan företag. För att slutföra dessa steg måste du först slutföra stegen i ämnet [Skapa en konfigurationsleverantör och välj den som aktiv](er-configuration-provider-mark-it-active-2016-11.md) För att kunna utföra de här stegen måste du också ha till gång till en RCS-instans som innehåller minst en ER-konfiguration med antingen status **slutförd** eller **delad**.

1. Gå till **Organisationsadministration** > **Arbetsytor** > **Elektronisk rapportering**. 
2. Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i avsnittet [Skapa en konfigurationsleverantör och välj den som aktiv](er-configuration-provider-mark-it-active-2016-11.md). 
3. Om du inte har någon RCS-miljö etablerad till ditt företag klickar du på den externa länken **Regulatory services - konfiguration** och följer instruktionerna för att etablera en RCS-miljö. 
4. Klicka på **parametrar för elektronisk rapportering** 
5. Klicka på fliken **RCS**. 
6. Om RCS-miljön redan har etablerats till ditt företag, använder du sidans URL:er för att komma åt den. 
7. Stäng sidan. 

## <a name="register-a-new-er-repository"></a>Registrera en ny ER-databas. 
1. Markera vald rad i listan. 
2. Välj leverantören Litware, inc. 
3. Klicka på Databaser. 
4. Klicka på Lägg till för att öppna dialogrutan. 
5. Skriv "RCS" i fältet Typ av konfigurationsdatabas. 
6. Klicka på Skapa en databas. 
7. Ange eller välj ett värde i namnfältet RCS-miljö. 
8. Välj önskat RCS-instans. Observera att du kan använda flera av dem. 
9. Klicka på OK. 

## <a name="import-er-configurations-from-rcs-based-repository"></a>Importera ER-konfigurationer från RCS-baserad databas
1. Klicka på **Visa filter** 
2. Ange filtervärdet "RCS" i fältet **Namn** med filteroperatorn **börjar med**. 
3. När du öppnar den markerade databasen, på sidan **Anslut till Regulatory Configuration Services**, klicka på länken **Klicka här för att ansluta till Regulatory Configuration Services**. 
4. Klicka på **Öppna.** 
5. Klicka på **Stäng**. 
6. Markera önskad version av ER-konfigurationen och klicka på **importera** för att ta med den aktuella Finance and Operations-instansen.

