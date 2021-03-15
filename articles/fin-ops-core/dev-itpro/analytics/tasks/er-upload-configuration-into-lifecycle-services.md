---
title: Överför en konfiguration till Lifecycle Services
description: Detta avsnitt förklarar hur du skapar en ny elektronisk rapportkonfiguration (ER) och laddar upp den till Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92fc6d7a8b2508c9a1f7b56ca8115adbd6ae00ea
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092551"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a>Överför en konfiguration till Lifecycle Services

[!include [banner](../../includes/banner.md)]

Detta ämne förklarar hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny [konfiguration för elektronisk rapportering (ER)](../general-electronic-reporting.md#Configuration) och ladda upp den i [Tillgångsbibliotek på projektnivå](../../lifecycle-services/asset-library.md) i Microsoft Dynamics Lifecycle Services (LCS).

I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. och överföra den till LCS. Dessa steg kan slutföras i alla företag eftersom ER-konfigureringar delas mellan företag. För att slutföra dessa steg måste du först slutföra stegen i [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md) Du måste också ha tillgång till LCS.

1. Logga in på programmet med någon av följande roller:

    - Utvecklare för elektronisk rapportering
    - Systemadministratör

2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. Välj **Litware, Inc.** och markera den som **Aktiv**.
4. Välj **konfigurationer**.

<a name="accessconditions"></a>
> [!NOTE]
> Kontrollera att den aktuella Dynamics 365 Finance användaren är medlem i det LCS-projekt som innehåller [Tillgångsbibliotek](../../lifecycle-services/asset-library.md#asset-library-support) till för att importera ER-konfigurationer.
>
> Du har inte åtkomst till ett LCS-projekt från en ER-databas som representerar en annan domän än den domän som används i Finance. Om du försöker kommer en tom lista med LCS-projekt att visas, och du kan inte importera ER-konfigurationer från tillgångsbiblioteket på projektnivå i LCS. Om du vill komma åt tillgångsbibliotek på projektnivå från en ER-databas som används för att importera ER-konfigurationer loggar du in på Finance genom att använda referenserna för en användare som tillhör den innehavare (domän) som den aktuella Finance-instansen har etablerats för.

## <a name="create-a-new-data-model-configuration"></a>Skapa en ny datamodellskonfiguration

1. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
2. På sidan **konfiguration** välj **Skapa konfiguration** om du vill öppna dialogrutan.

    I detta exempel skapar du en konfiguration som innehåller en exempeldatamodell för elektroniska dokument. Denna konfiguration av datamodellen ska överföras till LCS senare.

3. I fältet **Namn** ange **Konfiguration av exempelmodell**.
4. I fältet **Beskrivning** ange **Konfiguration av exempelmodell**.
5. Välj **Skapa konfiguration**.
6. Välj **modelldesign** .
7. Välj **Ny**.
8. I fältet **Namn** anger du **Startpunkt**.
9. Markera **Lägg till**.
10. Välj **Spara**.
11. Stäng sidan.
12. Välj **Ändra status**.
13. Välj **Slutför**.
14. Välj **OK**.
15. Stäng sidan.

## <a name="register-a-new-repository"></a>Registrera ett nytt databas

1. Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.

2. I avsnittet **Konfigurationsleverantörer** väljer du panelen **Litware, Inc.**.

3. I panelen **Litware, Inc.** väljer du **Databaser**.

    Du kan nu öppna listan över databaser för konfigurationsleverantören Litware, Inc.

4. Välj **Lägg till** för att öppna listrutan.

    Nu kan du lägga till en ny lagringsplats.

5. I **konfigurationsdatabas** välj **LCS**.
6. Välj **Skapa databas**.
7. Ange eller välj ett värde i fältet **Projekt**.

    I det här exemplet väljer du önskat LCS-projekt. Du måste ha [åtkomst](#accessconditions) till projektet.

8. Välj **OK**.

    Avsluta en ny databaspost.

9. Markera vald rad i listan.

    I det här exemplet väljer du databasposten **LCS**.

    Observera att en registrerad databas har markerats av den aktuella providern. Med andra ord kan endast konfigurationer som ägs av den providern placeras i den här databasen och därför överföras till det valda LCS-projektet.

10. Välj **Öppen**.

    Du öppnar databasen om du vill visa listan över ER-konfigurationer. Om det valda projektet ännu inte har använts för delning av ER-konfigurationer kommer listan att vara tom.

11. Stäng sidan.
12. Stäng sidan.

## <a name="upload-a-configuration-into-lcs"></a>Överför konfigurationer till LCS

1. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Konfiguration av exempelmodell**.

    Du måste välja en skapad konfiguration som redan har slutförts.

3. Hitta och markera önskad post i listan.

    I det här exemplet väljer du den version av den valda konfigurationen som har status **Slutförd**.

4. Välj **Ändra status**.
5. Välj **dela**.

    Konfigurationens status ändras från **slutförd** till **delad** när konfigurationen publiceras i LCS.

6. Välj **OK**.
7. Hitta och markera önskad post i listan.

    I det här exemplet väljer du den version av konfigurationen som har status **Delad**.

    Observera att statusen för den valda versionen har ändrats från **Slutförd** till **Delad**.

8. Stäng sidan.
9. Välj **Databaser**.

    Du kan nu öppna listan över databaser för konfigurationsleverantören Litware, Inc.

10. Välj **Öppen**.

    I det här exemplet väljer du databasen **LCS** och öppnar den.

    Observera att den valda konfigurationen visas som en tillgång för det valda LCS-projektet.

11. Öppna LCS genom att gå till <https://lcs.dynamics.com> .
12. Öppna ett projekt som tidigare användes för registrering av databasen.
13. Öppna resursbiblioteket för projektet.
14. Välj tillgångstypen **GER-konfiguration**.

    Den ER-konfiguration som du överförde ska visas i listan.

    Observera att den överförda LCS-konfigurationen kan importeras till en annan instans om leverantörerna har tillgång till det här LCS-projektet.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]