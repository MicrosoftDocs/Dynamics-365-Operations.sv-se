---
title: Begäran om frånvaro
description: Skicka in en begäran om frånvaro.
author: twheeloc
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveofAbsenceRequestEntry, EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6c98246e94670dd5f882fcbbd1f269e57f66faf
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805298"
---
# <a name="request-a-leave-of-absence"></a>Begäran om frånvaro

>[!Important]
>Funktionen som anges i den här artikeln är för närvarande tillgänglig för kunder med fristående Dynamics 365 Human Resources. Vissa eller alla funktionerna kommer att vara tillgängliga i en kommande version av Finance-infrastrukturen efter Finance version 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan skicka en begäran om frånvaro och se statusen för din begäran om frånvaro i Dynamics 365 Human Resources.

## <a name="request-a-leave-of-absence"></a>Begäran om frånvaro

1. I arbetsyta **Självbetjäning för medarbetare**, välj **Fler** (...) panelen **ledighetssaldon**.

2. Om du vill skicka en begäran om frånvaro väljer du **Begäran om frånvaro**.

3. Ange information för **Tjänstledighetstyp**, **Startdatum** och **Slutdatum**.

4. Om du behöver skicka in någon underlagsdokumentation väljer du **Överför** under **Bifogade filer**.

5. Ange information i **kommentar** om det behövs.

6. Välj **skicka** när du är redo att skicka din begäran. Annars väljer du **Spara utkast**.


## <a name="view-leave-of-absence-request-status"></a>Visa status för begäran om frånvaro

1. I arbetsyta **Självbetjäning för medarbetare**, välj **Fler** (...) panelen **ledighetssaldon**.

2. Om du vill visa din begäran om frånvaro, välj **Visa begäran om frånvaro**.

## <a name="update-a-leave-of-absence-request"></a>Uppdatera en begäran om frånvaro

1. I arbetsytan **Självbetjäning för medarbetare** på panelen **Tjänstledighet** välj **Fler (...)**.
2. Välj den tjänstledighetsbegäran som ska uppdateras och välj sedan **Uppdatera tjänstledighet**.
3. Uppdatera värdet i fältet **Slutdatum** om du vill utöka eller korta tjänstledigheten.
4. Om slutdatumet har bekräftats ställer du in alternativet **Bekräfta slutdatum** till **Ja**.
5. När alternativet **Bekräfta slutdatum** har ställts in som **Ja**, kan du föra över ett meddelande om att återgå till arbete. Markera sedan kryssrutan för att bekräfta att ett meddelande om att återgå till arbete har överförts.
6. Välj **Skicka** för att uppdatera tjänstledigheten.

## <a name="cancel-a-leave-of-absence-request"></a>Avbryt en begäran om frånvaro

1. I arbetsytan **Självbetjäning för medarbetare** på panelen **Tjänstledighet** välj **Fler (...)**.
2. Välj den tjänstledighetsbegäran som ska avbrytas och välj sedan **Uppdatera tjänstledighet**.
3. Ange alternativet **Avbryta tjänstledighet** till **Ja**.
4. Välj **Skicka** för att avbryta tjänstledigheten.

## <a name="importing-leave-requests-from-other-systems-or-older-systems"></a>Importera tjänstledighetsansökningar från andra system eller äldre system

Om du vill importera tjänstledighetsansökningar från ett annat system måste du gå igenom det vanliga arbetsflödet för att skapa lämpliga tjänstledighetstransaktioner. Du kan också importera tjänstledighetstransaktionerna och tjänstledighetsansökningarna i en slutförd status. Observera att det inte skapas några banktransaktioner automatiskt om du bara importerar tjänstledighetsansökningar.

## <a name="see-also"></a>Se även

[Skjut upp tjänstledighet](hr-leave-and-absence-suspend-leave.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
