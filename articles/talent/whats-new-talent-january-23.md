---
title: Nyheter och ändringar i Dynamics 365 for Talent Core HR (23 januari 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 135be837a82af8cee22d83c015a78da3b89b7978
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "306202"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-23-2019"></a>Nyheter och ändringar i Dynamics 365 for Talent Core HR (23 januari 2019)

[!include [banner](includes/banner.md)]

**Skapa 8.1.2121**

Det här ämnet beskriver nya eller ändrade funktioner i Core HR.

## <a name="changes"></a>Ändringar

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a>Import av medarbetarens fasta kompensation inte fungerar när du skapar nya fasta kompensationsposter
En har ändrats till entitetens medarbetarens fasta kompensation för att hämta kompensationsnivån vid importen. Innan den här versionen visades ett meddelande som anger hur krävdes.

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a>Ta bort fältet minimisaldo från dialogrutan begäran om ledighet
Fältet **minimisaldo** från dialogrutan **begäran om ledighet**. Denna ändring påverkar överallt där ledig tid kan begäras.

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a>Datauppgradering för uppdateras inte i samtliga fall kompensationsnivåer
En ändring har gjorts för att uppdatera kompensationsnivån på fasta kompensationsplaner. Den här ändringen fyller kompensationsnivån på fasta planer för projektet som hör till medarbetaren.

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a>Löneinformation på sidan Hantera ändringar gäller endast inloggad som systemadministratör.
Ändringen kan anställda med lön administratören åtkomst till löneinformationen på de **Ändrar tidslinje > Hantera ändringar** för befattningen.

### <a name="job-fields-default-to-positions"></a>Fältet anpassas till befattningar för jobbet
När du byter jobb på befattning, jobbfält överförs som standard till befattningen. Ett varningsmeddelande visas som du kan acceptera standardvärdena eller behålla de befintliga värdena för fälten.

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a>Provanställning och kalender visas inte för framtida anställda.
Förutom denna skillnad fält **provanställning** och **kalender** har lagts till i sida **hantera ändringar** om du vill tillåta för datainmatning för tidigare och framtida anställda.

### <a name="platform-update-23"></a>Plattform update 23
Mindre felkorrigeringar har ingår i plattformsuppdatering 23. Mer information finns i [vad är nya eller ändrade i Dynamics 365 for Finance and Operations plattformsuppdatering 23 (januari 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23). 
