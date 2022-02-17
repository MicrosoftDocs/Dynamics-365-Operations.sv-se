---
title: Konfigurera rollen för frånvarochefen
description: Det här avsnittet innehåller information om hur du ställer in rollen som frånvaroansvarig för hantering av tjänstledighet för medarbetare.
author: hasrivas
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace, LeaveAbsenceManager
audience: Application User
ms.search.scope: Human Resources
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9f1c699358c9cc8de9e975886cfb72edfb0d3f31
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065236"
---
# <a name="configure-the-absence-manager-role"></a>Konfigurera rollen för frånvarochefen


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I vissa organisationer kanske chefer inte hanterar tjänstledigheten för teamet. I stället kan en frånvarochef hantera den här processen för gruppmedlemmar inom flera avdelningar och grupper. Frånvarochefer har följande funktioner för tjänstledighetshantering:

- Granska och godkänn ledighet, baserat på en alternativ hierarki.
- Visa saldon för gruppmedlemmar.
- Visa frånvarokalendern.

## <a name="turn-on-the-feature"></a>Aktivera en funktion

1. I arbetsytan **Systemadministration** välj **Funktionshantering**.

2. På fliken **Funktionshantering** aktiverar du funktionen **Frånvarohanteraren för att hantera tjänstledighet**.

## <a name="define-a-custom-hierarchy"></a>Definiera en anpassad hierarki

Funktionen för frånvaroansvarig använder en anpassad hierarki som måste konfigureras.

1. I arbetsytan **Organisationsadministration**, välj **Befattningshierarkityper**.

2. Skapa en befattningshierarkityp med namnet **Tjänstledighet**.

3. I arbetsytan **Tjänstledighet och frånvaro**, under **Länkar**, välj **Parametrar för tjänstledighet och frånvaro**.

4. På fliken **Allmänt** i listrutan **Tjänstledighetshierarki**, välj hierarkitypen **Tjänstledighet** som du skapade tidigare. Den här tjänstledighetshierarki association måste fyllas i för alla juridiska personer där funktionen för frånvaroansvarig ska användas.

När hierarkitypen har definierats måste rapporten för befattningshierarkin tilldelas befattningen.

1. I arbetsytan **Organisationsadministration**, välj **Alla befattningar**.

2. Välj vilken befattning du vill lägga till tjänstledighetshierarki till.

3. Välj **Relationer** på fliken **Lägg till**.

4. I **Hierarkinamn**, välj **Tjänstledighet**.

5. I fältet **Rapporter till befattning**, ange eller välj en befattning. Arbetsnamnet fylls automatiskt i efter att du har valt en befattning.

## <a name="assign-the-absence-manager-role-to-a-user"></a>Tilldela en användare rollen frånvaroansvarig

Medarbetarna måste ha rollen Frånvaroansvarig om de ska kunna godkänna eller neka tjänstledighetsansökningar.

1. I arbetsytan **Systemadministrator** välj **Länkar**.

2. I avsnittet **Användare**, välj länken **Användare**.

3. Välj den användare i användarlistan som ska tilldelas rollen Frånvaroansvarig.

4. På fliken **Användarens roll** klicka på **Tilldela roller**.

5. I listan, välj rollen **Frånvaroansvarig**. Välj sedan **OK**.

    > [!IMPORTANT]
    > Se till att medarbetarrollen också har tilldelats till användaren som du tilldelar rollen Frånvaroansvarig. I annat fall kan arbetaren inte använda funktionen.

6. När du har skapat hierarkin tjänstledighetshierarki kan du visa den så här:

    1. I arbetsytan **Organisationsadministration**, välj **Befattningshierarki**.
    
    2. I **Hierarkityp**, välj **Tjänstledighet**.

## <a name="absence-manager-workspace"></a>Arbetsyta för frånvaroansvarig

I arbetsytan **Självbetjäning för medarbetare** visar fliken **tjänstledighetshantering** visar frånvaroinformation om de anställda som är tilldelade frånvarohanteraren i ledighetshierarkin. Det finns några alternativ tillgängliga för frånvarochefen: 
 - Granska ansökningar om ledighet.</br>
 - Skicka en ledighetsansökan på uppdrag av en medarbetare.</br>
 - Visa alla medarbetare som tilldelats dem som en del av tjänstledighetshierarkin.</br>
 - Visa kalendern för frånvaroansvarig.</br>

Det finns två flikar i arbetsytan för **tjänstledighetshantering**:
 - **Ledighetsansökan**: På den här fliken visas alla pågående ledighetsansökningar som frånvarochefen kan godkänna. Frånvarochefen kan välja flera poster och vidta åtgärder på dem samtidigt. Om visning av tjänstledighet mellan företag har aktiverats, visar den här listan väntande ledighetsansökningar för alla juridiska personer som de har åtkomst till. I annat fall visas pågående förfrågningstid för den juridiska personen som är vald. </br>
 - **Alla medarbetare**: På den här fliken visas alla medarbetare som är tilldelade frånvarochefen i hierarkin Lämna hierarkin. Det finns ett par alternativ för varje medarbetare:
    - **Begära ledighet** – Skicka en ny ledigtbegäran för den valda medarbetaren.</br>
    - **Semester** – Visa saldon, godkänd semester och begäran om semester för den valda medarbetaren.</br>

## <a name="approve-time-off-requests"></a>Godkänn ansökningar om ledighet

Frånvarochefer kan godkänna eller neka ledighetsansökningar för medarbetare. 

> [!IMPORTANT]
> Innan frånvarochefer kan godkänna eller neka ledighetsansökningar måste arbetsflödet för tjänstledighetsansökningar konfigureras till att tilldela dem ledighetsansökningar för granskning.
>
> 1. På fliken **Personalarbetsflöden**, välj eller skapa arbetsflödet för förfrågan.
> 2. Välj alternativet **Associera hierarki** och sedan i fältet **Hierarkinamn**, välj **Tjänstledighet**.
> 3. Uppdatera arbetsflödet i arbetsflödesdesignern. Under **Tilldelningstyp**, välj alternativet **Hierarki** och sedan på fliken **Hierarkival** välj **Konfigurerbar hierarki**.
>
> Mer information om hur du skapar arbetsflödet för ledighetsförfrågan finns i [skapa ett arbetsflöde för tjänstledighetsbegäran](hr-leave-and-absence-workflow.md).

1. I arbetsytan **Självbetjäning för medarbetare** välj fliken **tjänstledighetshantering**.

2. På fliken **Ansökningar om ledighet**, välj begäran om ledighet som du vill vidta åtgärder. Du kan markera flera poster i listvyn.

3. Använd åtgärdsknapparna högst upp i rutnätet om du vill godkänna, neka eller delegera förfrågningen. 

Alternativt kan användaren också använda panelen **Ansökningar om ledighet** till vänster för att navigera till listan över alla lediga arbetsobjekt. 

## <a name="view-time-off-in-the-calendar"></a>Visa ledighet i kalendern

Användare med rollen Frånvaroansvarig kan visa ledighetsansökningar i sin kalender. Följ dessa steg för att komma till ledighetskalendern.

> [!IMPORTANT]
> En systemadministratör måste konfigurera visningsalternativen för frånvaroansvarigkalendern. På sidan **Parametrar för tjänstledighet och frånvaro** på fliken **Kalender** finns det alternativ för att dölja eller visa födelsedagar, frånvaro utan detaljer, frånvaro och väntande ledighetsförfrågningar. Det finns också ett alternativ för att filtrera kalendervyalternativet efter arbetstyp.

1. I arbetsytan **Självbetjäning för medarbetare**, välj **Tjänstledighetshantering** och sedan **Frånvaroansvarigkalendern**.

2. I fältet **Datum** anger du önskade datum.

3. Uppdatera visningsalternativen efter behov.

I frånvaroansvarigkalendern visas alla poster för medarbetarna som rapporterar till frånvarochefen i tjänstledighetshierarki.

## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)
- [Skapa ett arbetsflöde för ledighetsansökan](hr-leave-and-absence-workflow.md)
- [Visa team- och företagskalendrar](hr-employee-self-service-calendar.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
