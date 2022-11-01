---
title: Översikt över kurser
description: Denna artikel förklarar hur personalresursadministratörer och chefer kan använda kursfunktionerna för att underhålla information om kurser som ges till arbetare.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a1fd00fb9feea9ab426f67095770389696452215
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/25/2022
ms.locfileid: "9716344"
---
# <a name="courses-overview"></a>Översikt över kurser

Microsoft Dynamics 365 Human Resources tillhandahåller en lösning för din organisations utbildningsbehov. Den här lösningen ger två utbildningssökvägar: *virtuella* och *instruktörsledda*.

*Virtuell utbildning* är en inlärningsupplevelse som förbättras med hjälp av onlineresurser. I *instruktörsledd utbildning* underlättar en instruktör en utbildningssession för en grupp av arbetare eller lärare.

I vår modul för inlärning kan personalchefer, administratörer, utbildningschefer och chefer skapa och tilldela både utbildningskurser för medarbetare.

> [!NOTE]
> För att använda virtuella kurser måste du aktivera funktionen **Kursförbättringar** i funktionshantering.

## <a name="set-up-virtual-courses"></a>Ställa in virtuella kurser

För att konfigurera virtuella kurser måste du aktivera funktionen **Kursförbättringar** i funktionshantering. Gå till **Kurser \> Ny** och ställ in alternativet **Virtuell** till **Ja**. När funktionen är aktiverad krävs en kurslänk. Fältet **Kursstatus** ställs in som **Öppet**. Alternativet **Tillåt medarbetaren att självregistrera** anges som **Ja**, men kan ställas in på **Nej**.

När funktionen **Kursförbättringar** har aktiverats i Funktionshantering sker följande ändringar:

- Ett förfallodatum måste definieras för kurstilldelningen.
- Det krävs en kurslänk.
- **Självbetjäning för medarbetare** visar en medarbetaröversikt i **kurser**. Användaren kan visa kurser som är försenade, förfallna eller tilldelade.
- Arbetare kan slutföra virtuella kurser och självbekänna till dem.

## <a name="set-up-instructor-led-courses"></a>Ställ in instruktörsledda kurser

Kurser som är instruktörsledda behöver inte konfigureras innan de används.

Följande information är valfri information och kan anges för kurser. Om den här informationen anges för kurser bör den ställas in innan kursposterna skapas:

- Kurstyp
- Klassrumsgrupper
- Kursgrupper
- Kursplatser
- Klassrum
- Lärare
- Kurstyper

Du kan använda *kurstyper* för att kategorisera kurser enligt strukturen eller innehållet. Du kan skapa kurstyper på sidan  **Kurstyper** .

Det minsta och det högsta antalet deltagare som du kan registrera för en kurs definieras på snabbfliken  **Allmänt**  på sidan  **Kurser** .

### <a name="course-setup-type"></a>Kursinställningstyp 

*Inställningstyper* bestämmer strukturen för kursen. Det finns tre inställningstyper för kurser.

| Inställningstyp | Beskrivning |
|------|--------|
| Standard | Kurser av den här inställningstypen har ingen daglig agenda. Detta är standardinställningen när du skapar en ny kurs. |
| Agenda | Välj den här inställningstypen för att planera information om varje dag i en kurs som hålls över flera dagar. |
| Agenda + session | <p>Välj den här inställningstypen för mer komplexa de kurser. Du kan till exempel dela in kursprogrammet i *spårningar* och *sessioner*:</p><ul><li>*Spår* är specifika ämnesområden för en kurs.</li><li>*Sessioner* delar upp spår och kan omfatta specifika processer eller tekniker som är relevanta för varje spår.</li></ul> |

### <a name="course-tasks"></a>Kursuppgifter

Du kan utföra följande uppgifter för varje kurs:

- Registrera deltagare.
- Ange en deadline för registreringen.
- Ange lägsta och högsta antal deltagare.
- Tilldela en plats och ett klassrum för kursen.
- Rekommendera hotell för kursdeltagare.
- Skapa en kursbeskrivning som du sedan kan bokföra i  **Självbetjäning för medarbetare**.

> [!NOTE]
> Du kan bara ta bort en kurs om ingen har registrerat sig för den.

### <a name="course-statuses"></a>Kursstatus

I följande tabell visas kursstatus och de åtgärder som har slutförts för var och en.

| Status | Åtgärder |
|------|--------|
| Skapad | <ul><li>Ange och ändra kursinformation.</li><li>Ändra kursstatus till  **Öppen** så att arbetare kan registrera sig för kursen.</li></ul> | 
| Öppna | <ul><li>Registrera deltagare till kursen.</li><li>Ta bort deltagare från kursen.</li><li>Bekräfta deltagare för kursen.</li><li>Ändra kursens status till **Stängd** eller **Annullerad** för deltagare vars status är **Bekräftad**.</li></ul>|
| Stängt | Du kan öppna kursen igen. |
| Avbrutet | Du kan öppna kursen igen. |

### <a name="course-participants"></a>Kursdeltagare

*Kursdeltagare* är arbetare som deltar i en utbildningskurs eller en händelse. Du kan bara registrera deltagare för öppna kurser.

### <a name="workflow"></a>Arbetsflöde

Medarbetare som registrerar sig för en kurs via sidan  **Självbetjäning för medarbetare**  kan få sin registrering skickad via arbetsflödet för godkännande. Du kan tilldela ett arbetsflöde till en kurs i snabbfliken  **Allmänt**  på sidan  **Kurser** .
