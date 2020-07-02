---
title: Borttagna eller föråldrade funktioner i Lifecycle Services (LCS)
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e571cc26f55e0bd7a1eef301e193921e0b3f8e31
ms.sourcegitcommit: ac47e8679fb104515f7dcca509294264bd05d2b1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2020
ms.locfileid: "3454705"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a>Borttagna eller föråldrade funktioner i Lifecycle Services (LCS)

[!include[banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som har tagits bort eller är utfasad för Microsoft Dynamics Lifecycle Services (LCS).

- En *borttagen* funktion är inte längre tillgänglig i tjänsten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan tillhandahålls så att du kan ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull.

## <a name="october-2019-announcements"></a>Oktober 2019 meddelanden

### <a name="flowchart-diagrams-in-business-process-modeler"></a>Flödesscheman i affärsprocessmodelleraren

<table>
<tbody>
<tr>
<td><strong>Orsak till inaktuell/borttagning</strong></td>
<td>Vi använder inte komponenten flödesschema i Affärsprocessmodelleraren (BPM), eftersom äldre designen orsakade låg användning.</td>
</tr>
<tr>
<td><strong>Ersatt av en annan funktion?</strong></td>
<td>Nej</td>
</tr>
<tr>
<td><strong>Områden som påverkas</strong></td>
<td>Affärsprocessmodelleraren</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Inaktuell: komponenten flödesschema i BPM förväntas tas bort år 2020. Följande funktion kommer att bli otillgänglig:
<ul>
<li>Alla flödesscheman blir skrivskyddade och kan inte redigeras. Formegenskaperna som är kopplade till flödesscheman kommer heller inte att vara tillgängliga. Dessa flödesscheman innehåller både standardflödesscheman som genereras automatiskt och anpassade flödesscheman som ändras baserat på dessa standard flödesscheman.</li>
<li>Processteg blir skrivskyddade och kan inte redigeras.</li>     
<li>Den inaktuella funktionen Bristanalys kommer inte att vara tillgänglig. Därför skapas ingen lista över luckor automatiskt eller tillgänglig för export.
<p><strong>Obs!</strong> Den här funktionen hade tidigare ersatts av Microsoft Azure DevOps-integreringar.</p>
</li>
<li>Versionshistoriken för flödesschemat kommer inte att vara tillgänglig.</li>
</ul>
</td>
</tr>
</tbody>
</table>
