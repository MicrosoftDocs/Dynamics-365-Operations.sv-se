---
title: Säkerhets- och rollhantering i Attract
description: Det här avsnittet innehåller information om rollsäkerhet i Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: ad94a7511afef0c68fb8f2a70402babb80b0f9ad
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024216"
---
# <a name="set-user-permissions"></a>Ställ in användarbehörigheter

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 Talent: Attract använder rollbaserad säkerhet. Med andra ord ges inte åtkomst till enskilda användare, utan till de säkerhetsroller som har tilldelats användare. En användare som har tilldelats en säkerhetsroll har åtkomst till den uppsättning behörigheter som associeras med rollen.

Attract innehåller fem grundläggande användarroller:

- Administratör
- Anställande chef
- Rekryterare
- Intervjuare
- Skrivskydd

Administratörsrollen är den enda rollen som har behörighet att lägga till andra användare och ändra deras behörigheter.

- **Lägga till** – i Administrationscenter på fliken **användarbehörigheter**, välj **tilldela roller**, sök efter användare att lägga till och tilldela behörigheter till användaren.
- **Redigera** - Sök efter användare eller hitta användare i listan och välj sedan **redigera** för att ändra hans/hennes behörigheter.
- **Ta bort** – om du tar bort en användares behörigheter tar du inte bort användaren från systemet. Men du begränsar användarens åtkomst och behörigheter i Attract. Exempelvis Hilda har tilldelats till rollen Anställande chef och hon läggs till ett jobb som anställande chef. Om Hilda senare tas bort från rollen Anställande chef, hon förblir anställande chef för jobbet och fortfarande har tillgång till jobbet. Hon kan emellertid inte skapa andra jobb.

Följande avsnitt innehåller en högnivåbeskrivning av varje roll. Tabellerna längre fram i det här avsnittet innehåller mer detaljerad information.

> [!NOTE]
> Vissa funktioner finns tillgängliga med tillägget för omfattande anställning för Attract.

## <a name="administrator"></a>Administratör

Användare som tilldelats administratörsrollen kan komma åt och ändra alla data i Attract. Administratörer kan skapa, läsa, uppdatera och ta bort data. De har även tillgång till administratörscentret där de kan konfigurera Attract och konfigurera användarinformation. Vi rekommenderar att minst en person tilldelas rollen Administratör. Som standard är miljöadministratör i Microsoft PowerApps inställd som en administratör i Attract. Om du har registrerat dig för en utvärderingsversion av Attract tilldelas rollen Systemadministratör automatiskt till dig. För närvarande måste användare som har rollen Administratör också ha rollen rekryterare eller rollen anställande chef för att kunna skapa jobb.

## <a name="hiring-manager"></a>Anställande chef

Användare som tilldelas rollen anställande chef kan skapa jobb och uppdatera jobb som de har skapat tidigare. Anställande chefer kan endast utföra en begränsad uppsättning åtgärder för ett jobb och i ansökningarna som är associerade med jobbet. Användare som tilldelats rollen Anställande chef kan läggas till ett anställningsteam som anställande chefer.

## <a name="recruiter-role"></a>Rollen Rekryterare

Användare som tilldelas rollen Rekryterare har fullständiga behörigheter för att läsa, skapa, uppdatera och ta bort för de jobb som de har skapat. De också har fullständig behörighet att skapa, läsa, uppdatera och ta bort behörigheter för de ansökningar som är associerade med jobb som de äger. Endast användare som tilldelats rollen Rekryterare kan läggas till ett anställningsteam som rekryterare.

## <a name="interviewer"></a>Intervjuare

Alla användare som har ett konto i Azure Active Directory (Azure AD) i organisationen kan läggas till ett anställningsteam som intervjuare. Användare som tilldelas rollen Intervjuare kan visa jobbinformation och data om sökande för jobb som de är i anställningsteamet. För dessa jobb kan intervjuare också göra anställningsrekommendationer och ge feedback om kandidater. Emellertid kan inte de uppdatera jobbinformation eller data om sökande.

## <a name="read-only"></a>Skrivskydd

Användare som tilldelas rollen Skrivskyddad har skrivskyddad åtkomst till alla data i en Attract-miljö. Men kan inte de skapa eller redigera data.

## <a name="find-out-which-roles-you-have"></a>Ta reda på vilka roller du har

1.  I Attract klickar du på frågetecknet (**?**) i det övre högra hörnet på sidan.

2.  Klicka på **Om**.

    Du kommer att se vilka roller du har för Attract i fönstret som visas:

    ![Visa din Attract licenstyp](media/attract-license-types.png)
    
## <a name="delegated-roles"></a>Delegerade roller

För alla projekt som de är i anställningsteamet för kan rekryterare och anställande chefer utse ett eller flera ombud för sig själva. Men kan inte de utse ombud för andra i anställningsteamet.

Ombud har samma behörighet som den person som utsetts för dem.. Om en anställningschefen utser ett ombud för sig själv för ett jobb, kommer ombudet ha samma behörigheter som den anställande chef för jobbet. Ombud kan inte ta bort andra ombud från anställningsteamet. De kan inte heller ta bort de personer som utser dem till ombud.

## <a name="job-details-and-actions"></a>Jobbdetaljer och åtgärder

Användare som har rollen Rekryterare eller Anställande chef kan skapa jobb. Följande behörigheter gäller jobbinformationen och åtgärder som kan vidtas för jobb.

| Data eller åtgärd    | Rekryterare | Anställande chef | Intervjuare |
|-------------------|-----------|----------------|-------------|
| Jobbdetaljer       | Skapa, läsa, uppdatera och ta bort jobb som användaren är i anställningsteamet för | Skapa, läsa, uppdatera och ta bort jobb som användaren är i anställningsteamet för | Skrivskydd |
| Anställningsteam       | Skapa, läsa, uppdatera och ta bort jobb som användaren är i anställningsteamet för | Skapa, läsa, uppdatera och ta bort jobb som användaren är i anställningsteamet för | Skrivskydd |
| Jobbpublicering       | Skapa, läsa, uppdatera och ta bort jobb som användaren är i anställningsteamet för | Skrivskydd | Skrivskydd |
| Process           | Skapa, läsa, uppdatera och ta bort jobb som användaren är i anställningsteamet för | Skapa, läsa, uppdatera och ta bort jobb som användaren är i anställningsteamet för | Skrivskydd |
| Lägg till sökande    | Lägg till sökande för jobb som användaren är i anställningsteamet för | Lägg till sökande för jobb som användaren är i anställningsteamet för | Tillåts inte |
| Lägg till potentiella kandidater     | Lägg till potentiella kandidater för jobb som användaren är i anställningsteamet för | Ett konfigurationsalternativ i [potentiella kandidaters aktivitetsinställningar](./activities-attract.md#prospect-activity) kontrollerar om intervjuare kan lägga till och visa potentiella kandidater. | Tillåts inte |
| Aktivera jobb      | Aktivera jobb som användaren är i anställningsteamet för | Aktivera jobb som användaren är i anställningsteamet för | Tillåts inte |
| Stäng jobb         | Stänga jobb som användaren är i anställningsteamet för | Tillåts inte | Tillåts inte |
| Radera jobb        | Radera jobb som användaren är i anställningsteamet för | Endast om inga sökanden har lagts till i jobbet | Tillåts inte |
| Ta bort sökande | Radera sökande om användaren är i anställningsteamet | Tillåts inte | Tillåts inte |

## <a name="application-details-and-actions"></a>Detaljer om ansökan och åtgärder

Följande behörigheter gäller jobbspecifika data för sökande och de åtgärder som kan vidtas för ansökningar.

| Data eller åtgärd          | Rekryterare | Anställande chef | Intervjuare |
|-------------------------|-----------|----------------|-------------|
| Ansökningsdokument   | Skapa, läsa, uppdatera och ta bort jobb som användaren är i anställningsteamet för | Skapa, läsa, uppdatera och ta bort jobb som användaren är i anställningsteamet för | Skrivskydd |
| Ansökningsanteckningar       | Skapa, läsa, uppdatera och ta bort jobb som användaren är i anställningsteamet för | Skapa, läsa, uppdatera och ta bort jobb som användaren är i anställningsteamet för | Skrivskydd|
| Ansökningsaktivitet    | Visa om sökande är i anställningsteamet | Visa om sökande är i anställningsteamet | Skrivskydd |
| Feedback om ansökan    | Lägga till och visa all feedback om användaren finns med i anställningsteamet | Lägga till och visa all feedback om användaren finns med i anställningsteamet | Kan lägga till feedback\*\* |
| Avvisa ansökning      | Kan avvisa om användaren är i anställningsteamet | Tillåts inte | Tillåts inte |
| Flytta fram ett stadium           | Kan avvisa om användaren är i anställningsteamet | Kan avancera om användaren är i anställningsteamet | Tillåts inte |
| Starta erbjudandehantering | Kan starta erbjudandehantering | Det finns ett konfigurationsalternativ för erbjudandeaktivitet. | Tillåts inte |


\*\* Ett konfigurationsalternativ i [inställning av feedback-aktivitet](./activities-attract.md) kontrollerar om intervjuare ser varandras feedback.


## <a name="process-templates"></a>Processmallar

Följande behörigheter gäller anställningsprocessmallar. Teammedlemmarnas förmåga att skapa och redigera mallar som har konfigurerats i **Mallhantering** i Administrationscenter. Om mallhantering är aktiverad kan rekryterare och anställande chefer skapa och redigera egna processmallar. Om mallhantering inaktiveras kan endast administratörer skapa och redigera processmallar. Följande tabell förutsätter att mallhantering har aktiverats.

| Data              | Rekryterare                                           | Anställande chef                                      | Intervjuare |
|-------------------|-----------------------------------------------------|-----------------------------------------------------|-------------|
| Processmallar | Fullständig behörighet för mallar som skapas av användaren | Fullständig behörighet för mallar som skapas av användaren | Ingen åtkomst   |

## <a name="email-and-email-templates"></a>E-post och e-postmallar

Följande behörigheter gäller e-postmallar och åtgärder som kan vidtas för e-post. Endast administratörer kan skapa och redigera e-postmallar.

| Data eller åtgärd     | Rekryterare          | Anställande chef     | Intervjuare |
|--------------------|--------------------|--------------------|-------------|
| E-postmallar    | Skrivskyddad åtkomst   | Skrivskyddad åtkomst   | Ingen åtkomst   |
| Skicka e-post         | Skicka per aktivitet  | Skicka per aktivitet  | Ingen åtkomst   |
| Redigera e-postinnehåll | Redigera e-postinnehåll | Redigera e-postinnehåll | Ingen åtkomst   |

## <a name="talent-pools"></a>Talangpooler

Följande behörigheter gälla talangpooler. Talangpooler visas bara för den person som skapade dem, om inte denna person väljer att dela dem. Kandidatsökning kan användas för att söka efter kandidater som inte har lagts till i en namngiven pool.

| Data eller åtgärd   | Rekryterare                                       | Anställande chef                                  | Intervjuare |
|------------------|-------------------------------------------------|-------------------------------------------------|-------------|
| Namngiven pool       | Fullständiga behörigheter som skapas av användaren | Fullständiga behörigheter som skapas av användaren | Ingen åtkomst   |
| Dela pool       | Endast pooler som användaren skapar                | Endast pooler som användaren skapar                | Ingen åtkomst   |
| Kandidatsökning | Fullständiga sökfunktioner                        | Fullständiga sökfunktioner                        | Ingen åtkomst   |

## <a name="candidates"></a>Kandidater

Kandidater är personer som har lagts till i en talangpool men som inte har kopplats till ett jobb.

| Data                        | Rekryterare                        | Anställande chef                   | Intervjuare |
|-----------------------------|----------------------------------|----------------------------------|-------------|
| Profil - information om kandidat | Skapa, läsa, uppdatera och ta bort | Skapa, läsa, uppdatera och ta bort | Ingen åtkomst   |
| Dokument                   | Skapa, läsa, uppdatera och ta bort | Skapa, läsa, uppdatera och ta bort | Ingen åtkomst   |
