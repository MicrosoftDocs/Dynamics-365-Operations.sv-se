---
title: Skapa en obegränsad tjänstledighet
description: I den här artikeln förklaras hur du skapar en obegränsad tjänstledighet i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 08231d4139209387c3c76923fafdd2061fceb280
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805348"
---
# <a name="create-an-open-ended-leave-of-absence"></a>Skapa en obegränsad tjänstledighet

> [!IMPORTANT]
> Funktionaliteten som beskrivs i den här artikeln kommer att vara tillgänglig på finansinfrastrukturen som en del av en framtida version efter Microsoft Dynamics 365 Finance version 10.0.31.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan skicka begäran om obegränsad tjänstledighet och se statusen för din begäran om tjänstledighet i Dynamics 365 Human Resources.

## <a name="prerequisites"></a>Förutsättningar

1. Under **Funktionshantering**, se till att funktionen **Obegränsad tjänstledighet** är aktiverad.

    > [!IMPORTANT]
    > Funktionen kan inte stängas av efter att den har slagits på.

2. Skapa en tjänstledighetstyp.
3. Ange uppgifter som tjänstledighetstyp, beskrivning och arbetsflödes-ID.
4. I fältet **Begärandetyp** välj **Tjänstledighet**.
5. I avsnittet Detaljer, för obegränsad tjänstledighet, ställ in **Obegränsad** till **Ja**.
6. Ange alternativet **Meddelande om återgång till arbetet** till **Ja** eller **Nej**.
7. Ett meddelande om återgång till arbetet kan krävas för begäran om obegränsad tjänstledighet.

> [!NOTE]
> När denna funktion är aktiverad kommer funktionen **Bilaga som krävs** att aktiveras.

## <a name="request-an-open-ended-leave-of-absence"></a>Begär en obegränsad tjänstledighet

1. I arbetsyta **Självbetjäning för medarbetare**, välj **ledighetssaldon** och **Fler (...)**.
2. Om du vill skicka en begäran om frånvaro väljer du **Begäran om frånvaro**.
3. Ange information för **Tjänstledighetstyp** och **Startdatum**. Ange preliminärt slutdatum i fältet **Slutdatum**.
4. Om du måste lämna in underlag, under **Bifogade filer**, välj **Ladda upp**.
5. Om du är redo att skicka in din begäran väljer du **Skicka**. Annars väljer du **Spara utkast**.
6. För att uppdatera en begäran om obegränsad tjänstledighet, ange ett slutdatum i fältet **Slutdatum**, ange alternativet **Bekräfta slutdatum** till **Ja** och överför dokumentation.
7. Om alternativet **Meddelande om återgång till arbetet** anges till **Ja**, välj **Ladda upp** och markera sedan kryssrutan för att bekräfta att ett giltigt meddelande om återgång till arbetet har laddats upp.
8. När alla detaljer har angetts väljer du **Skicka**.
