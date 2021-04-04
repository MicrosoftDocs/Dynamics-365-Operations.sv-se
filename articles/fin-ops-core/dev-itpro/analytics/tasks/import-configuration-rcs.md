---
title: (ER) Importera konfigurationer från RCS
description: I det här avsnittet finns information om hur en användare kan importera en ny version av en återställningskonfiguration från RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 799abeafe5f0929e6dd2f8a5f437f3c10b3b06d9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570546"
---
# <a name="er-import-configurations-from-rcs"></a>(ER) Importera konfigurationer från RCS

[!include [banner](../../includes/banner.md)]

I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan importera en ny version av en konfiguration för elektronisk rapportering (ER) från Microsoft Regulatory Configuration Services (RCS). I det här exemplet ska du välja den version av ER-konfiguration som har konfigurerats i en RCS-instans och importera den till den aktuella instansen för exempelföretaget Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigurationer delas mellan företag. För att slutföra dessa steg måste du först slutföra stegen i ämnet [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md) För att kunna utföra de här stegen måste du också ha till gång till en RCS-instans som innehåller minst en ER-konfiguration med antingen status **slutförd** eller **delad**.

1. Gå till **Organisationsadministration** > **Arbetsytor** > **Elektronisk rapportering**. 
2. Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i ämnet [Skapa konfigurationsleverantörer och välj dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md). 
3. Om du inte har någon RCS-miljö etablerad till ditt företag kan du välja den externa länken **Regulatory services - konfiguration** och följa instruktionerna för att etablera en RCS-miljö. 
4. Välj **Parametrar för elektronisk rapportering**. 
5. Välj fliken **RCS**. 
6. Om RCS-miljön redan har etablerats till ditt företag, använder du sidans URL:er för att komma åt den. 
7. Stäng sidan. 

## <a name="register-a-new-er-repository"></a>Registrera en ny ER-databas. 
1. Markera vald rad i listan. 
2. Välj leverantören Litware, inc. 
3. Välj Databaser. 
4. Välj Lägg till för att öppna dialogrutan. 
5. Skriv "RCS" i fältet Typ av konfigurationsdatabas. 
6. Välj Skapa databas. 
7. Ange eller välj ett värde i namnfältet RCS-miljö. 
8. Välj önskat RCS-instans. Du kan använda flera av dem. 
9. Välj OK. 

## <a name="import-er-configurations-from-rcs-based-repository"></a>Importera ER-konfigurationer från RCS-baserad databas
1. Välj **Visa filter**. 
2. Ange filtervärdet "RCS" i fältet **Namn** med filteroperatorn **börjar med**. 
3. När du öppnar den markerade databasen, på sidan **Anslut till Regulatory Configuration Services**, väljer du länken **Markera här för att ansluta till Regulatory Configuration Services**. 
4. Välj **Öppen**. 
5. Välj **Nära**. 
6. Markera önskad version av ER-konfigurationen och välj **importera** för att ta med den aktuella instansen.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]