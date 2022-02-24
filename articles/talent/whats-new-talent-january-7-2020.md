---
title: Nyheter och ändringar i Dynamics 365 Talent (7 januari 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
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
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462597"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a>Nyheter och ändringar i Dynamics 365 Talent (7 januari 2020)

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2697. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a>Det går inte att radera arbetare som inte har anställningsposter - (386157)

Denna ändring lägger till ett borttagningsalternativ i formuläret **arbetare utan anställning**. Arbetare visas i det här formuläret när det inte finns några framtida, aktiva eller historiska anställningar för arbetaren. I den här versionen är ta bort endast aktiverad för systemadministratörer. Under nästa veckas utgivning kommer dock säkerhet att uppdateras så att alla användare med rollen personalassistent kan ta bort medarbetare utan anställning. Du kan även göra dessa ändringar manuellt genom att följa stegen nedan.

1. Gå till **Säkerhetskonfiguration**.
2. På fliken **behörigheter** filtrera listan **behörigheter** till **Underhåll arbetare**.
3. I kolumnen **Referenser**, välj **Visa menyobjekt**.
4. I kolumnen **Visa menyobjekt**, välj **HcmWOrkersWithoutEmployment**.
5. Ange behörigheten **Ta bort** till Bevilja.
6. Välj fliken **Opublicerade objekt**.
7. Markera **Publicera alla**.
