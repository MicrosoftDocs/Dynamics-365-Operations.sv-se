---
title: Skapa ER-konfigurationer i RCS och överföra dem till den globala databasen
description: Det här förklarar hur du skapar en elektronisk rapporteringskonfiguration (ER) i Microsoft Regulatory Configuration Services (RCS) och laddar upp den till den globala databasen.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 5b2b8f35b9931f8fd1824c20e9045da68af33ad5
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834243"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Skapa ER-konfigurationer i RCS och överför dem till den globala databasen

[!include [banner](../includes/banner.md)]

Du kan använda Microsoft RCS (Regulatoryr Configuration Services) för att utforma konfigurationer för elektronisk rapportering (ER) och sedan publicera dem så att de kan användas i din organisation.

Följande procedurer förklarar hur en användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en härledd version av en ER-konfiguration som har konfigurerats i en RCS-instans och sedan överföra den härledda konfigurationen till den globala databasen. 

Innan du kan slutföra dessa procedurer måste du först uppfylla följande förutsättningar:

- Öppna en RCS-instans.
- Skapa en aktiv konfigurationsleverantör. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Du måste också säkerställa att en RCS-miljö har etablerats för ditt företag.

1. I en Finance and Operations-app går du till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. Om ingen RCS-miljö har etablerats för ditt företag väljer du **Regulatory services - extern konfiguration** och följer sedan instruktionerna för att etablera en.

Om en RCS-miljö redan har etablerats för ditt företag kan du använda sidans URL för att komma åt den genom att välja alternativet för inloggning.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Skapa en härledd version av en konfiguration i RCS

1. I arbetsytan **Elektronisk rapportering** bekräftar du att du har en aktiv konfigurationsleverantör för din organisation. 
2. Välj **rapporteringskonfigurationer**.
3. Välj den konfiguration som du vill härleda en ny version från. Du kan använda filterfältet ovanför trädet för att begränsa sökresultatet.
4. Välj **Skapa konfiguration** \> **Härled från namn**.
5. Ange ett namn och en beskrivning och välj sedan **Skapa konfiguration** för att skapa en ny härledd version.
6. Välj den nya härledda konfigurationen, lägg till en beskrivning av versionen och välj sedan **OK**. Status för konfigurationen ändras till **Slutförd**.

![Ny konfigurationsversion i RCS](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> När konfigurationsstatusen ändras kan du få ett meddelande om valideringsfel som berör de anslutna programmen. Om du vill inaktivera valideringen grå du till åtgärdsfönstret i fliken **Konfigurationer**, väljer **Användarparametrar** och anger sedan alternativet **Hoppa över validering vid statusändring och ombasering av konfigurationsstatus** som **Ja** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Överför en konfiguration till den globala databasen

Om du vill dela en ny eller härledd konfiguration med din organisation kan du överföra den till den globala databasen.

1. Markera den slutförda versionen av konfigurationen och välj sedan **Överför till databas**.
2. Markera alternativet **Global (Microsoft)** och välj sedan **Överför**.

    ![Alternativ för databasöverföring](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. Markera **Ja** i bekräftelserutan som visas. 
4. Uppdatera beskrivningen av versionen efter behov och välj sedan **OK**. 

Konfigurationens status uppdateras till **Delas**, och konfigurationen överförs till den globala databasen. Därifrån kan du arbeta med den på följande sätt:

- Importera den till din Dynamics 365-instans. Mer information finns i [Importera konfigurationer för elektronisk rapportering (ER) från RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- För att dela den med en tredje part eller en extern organisation, se [RCS Dela konfigurationer för elektronisk rapportering (ER) med externa organisationer](rcs-global-repo-share-configuration.md)

    ![Härledd Intrastat contoso-konfigurationsversion i den globala databasen](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Radera en konfiguration från den globala databasen
Gör på följande sätt för att ta bort en konfiguration som din organisation har skapat.

1. I arbetsytan **Elektronisk rapportering** verifierar du att din konfigurationsleverantör är **Aktiv**. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. Välj **databas** i den aktiva konfigurationsleverantören.
3. Välj typ av databas **Global** och sedan **Öppna**.
4. På snabbfliken **Filter** hittar du den konfiguration som du vill radera med hjälp av funktionen **Filter**.
5. På snabbfliken **Version** välj den version av konfigurationen som du vill ta bort och välj sedan **Ta bort**:

    ![Radera en konfiguration från den globala databasen](media/RCS_Delete_from_GlobalRepo.JPG)

6. Markera **Ja** i bekräftelserutan som visas.

    ![Ta bort bekräftelsemeddelande för konfigurationsversion](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
Konfigurationsversionen tas bort och bekräftelsemeddelandet visas. 

> [!NOTE]
> Konfigurationer kan bara tas bort av den konfigurationsprovider som skapade dem. Om konfigurationen har delats med en annan organisation måste konfigurationen delas ut innan du kan ta bort den.
 
