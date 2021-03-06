---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (23 januari 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f97462f088fc1a3cb94f2a34204fc09f1cd66fb0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462538"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-23-2019"></a>Nyheter och ändringar i Dynamics 365 Talent - Core HR (23 januari 2019)

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

### <a name="platform-update-23-for-finance-and-operations"></a>Plattformsuppdatering 23 för Finance and Operations
Mindre felkorrigeringar ingår i plattformsuppdatering 23 för Finance and Operations. Mer information finns i [vad är nya eller ändrade i Dynamics 365 Finance and Operations plattformsuppdatering 23 (januari 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]