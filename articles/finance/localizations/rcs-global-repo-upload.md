---
title: Skapa ER-konfigurationer i RCS och överföra dem till den globala databasen
description: Det här förklarar hur du skapar en elektronisk rapporteringskonfiguration (ER) i Microsoft Regulatory Configuration Services (RCS) och laddar upp den till den globala databasen.
author: JaneA07
ms.date: 01/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: eb04362d6d7261af56d2940b085fbc8d43c9d662
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/12/2022
ms.locfileid: "7965099"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Skapa ER-konfigurationer i RCS och överför dem till den globala databasen

[!include [banner](../includes/banner.md)]

Du kan använda Microsoft RCS (Regulatory Configuration Services) för att utforma konfigurationer för elektronisk rapportering (ER) och sedan publicera dem så att de kan användas i din organisation.

Följande procedurer förklarar hur en användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en härledd version av en ER-konfiguration som har konfigurerats i en RCS-instans och sedan överföra den härledda konfigurationen till den globala databasen. 

Innan du kan slutföra dessa procedurer måste du först uppfylla följande förutsättningar:

- Har åtkomst till en RCS-miljö för din organisation.
- Skapa en aktiv konfigurationsleverantör och gör den aktiv. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Du måste också säkerställa att en RCS-miljö har etablerats för ditt företag. Om du inte har någon RCS-instans har reserverats för din organisation, kan du göra det med följande steg:

1. I appen för ekonomi och drift, gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. I **relaterade länkar/externa länkar**, välj **Regulatory services – Konfiguration** och följer sedan instruktionerna för **registrera** för att tillhandahålla en.

Om en RCS-miljö redan har etablerats för ditt företag kan du använda sidans URL för att komma åt den genom att välja alternativet för **inloggning**.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Skapa en härledd version av en konfiguration i RCS

> [!NOTE]
> Om du använder RCS för första gången kommer du inte att ha någon konfiguration tillgänglig som du kan härleda från. Du måste importera en konfiguration från den globala databasen. Mer information finns i [Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

1. **Logga in** till RCS och välj arbetsyta **Elektronisk rapportering**.
2. Kontrollera att du har en aktiv konfigurationsleverantör för din organisation som är inställd på aktiv (se förutsättningar). 
3. Välj **rapporteringskonfigurationer**.
4. Välj den konfiguration som du vill härleda en ny version från. Du kan använda filterfältet ovanför trädet för att begränsa sökresultatet.
5. Välj **Skapa konfiguration** \> **Härled från namn**.
6. Ange ett namn och en beskrivning och välj sedan **Skapa konfiguration** för att skapa en ny härledd version med status Utkast.
7. Markera den nya konfiguration som är härledd och gör ytterligare ändringar i konfigurationsformatet om det behövs. 
8. När ändringarna är slutförda måste du ställa in **Ändra status** för konfigurationen till **Slutförd** för att kunna publicera den i databasen. Välj **OK**.

![Ny konfigurationsversion i RCS.](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> När konfigurationsstatusen ändras kan du få ett meddelande om valideringsfel som berör de anslutna programmen. Om du vill inaktivera valideringen grå du till åtgärdsfönstret i fliken **Konfigurationer**, väljer **Användarparametrar** och anger sedan alternativet **Hoppa över validering vid statusändring och ombasering av konfigurationsstatus** som **Ja** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Överför en konfiguration till den globala databasen

Om du vill dela en ny eller härledd konfiguration med din organisation kan du överföra den till den globala databasen genom följande steg:

1. Markera den slutförda versionen av konfigurationen och välj sedan **Överför till databas**.
2. Markera alternativet **Global (Microsoft)** och välj sedan **Överför**.

    ![Alternativ för Uppladdning till databas.](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. Markera **Ja** i bekräftelserutan som visas. 
4. Uppdatera beskrivningen av versionen efter behov och välj sedan **OK**. Om du vill kan du även överföra versionen till ett anslutet program eller till en GIT-databas.  

Konfigurationens status uppdateras till **Delas**, och konfigurationen överförs till den globala databasen. En utkastversion av konfigurationen som du överfört skapas också och kan användas om efterföljande ändringar krävs.

När konfigurationen har överförts till den globala databasen kan du arbeta med den där på följande sätt:

- Importera den till din Dynamics 365-instans. Mer information finns i [Importera konfigurationer för elektronisk rapportering (ER) från RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- För att dela den med en tredje part eller en extern organisation, se [RCS Dela konfigurationer för elektronisk rapportering (ER) med externa organisationer](rcs-global-repo-share-configuration.md)

    ![Härledd Intrastat Contoso-konfigurationsversion i den globala databasen.](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Radera en konfiguration från den globala databasen
Gör på följande sätt för att ta bort en konfiguration som din organisation har skapat.

1. I arbetsytan **Elektronisk rapportering** verifierar du att din konfigurationsleverantör är **Aktiv**. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. Välj **databas** i den aktiva konfigurationsleverantören.
3. Välj typ av databas **Global** och sedan **Öppna**.
4. På snabbfliken **Filter** hittar du den konfiguration som du vill radera med hjälp av funktionen **Filter**.
5. På snabbfliken **Version** välj den version av konfigurationen som du vill ta bort och välj sedan **Ta bort**:

    ![Radera en konfiguration från den globala databasen.](media/RCS_Delete_from_GlobalRepo.JPG)

6. Markera **Ja** i bekräftelserutan som visas.

    ![Ta bort bekräftelsemeddelande för konfigurationsversion.](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
Konfigurationsversionen tas bort och bekräftelsemeddelandet visas. 

> [!NOTE]
> Konfigurationer kan bara tas bort av den konfigurationsprovider som skapade dem. Om konfigurationen har delats med en annan organisation måste konfigurationen delas ut innan du kan ta bort den.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
