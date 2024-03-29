---
title: Rekrytera jobbkandidater
description: Den här artikeln beskriver hur du rekryterar kandidater i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 743c78d3526db2707630229d4cf21531f9641dd6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879262"
---
# <a name="recruit-job-candidates"></a>Rekrytera jobbkandidater


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources hjälper dig att hantera rekryteringsförfrågningar. Den hjälper dig också att på ett smidigt sätt överföra jobbkandidater till medarbetare. Om din organisation använder ett separat rekryteringsprogram kan din rekryteringsprocess innehålla följande steg:<!--note from editor: Should this be a numbered list? These steps do seem to follow a particular order.-->

- Ange din rekryteringsbegäran i Personal.
- Ta emot kandidathänvisningar i Personal från programmet för rekrytering.
- Slutför godkännandeprocessen för kandidater i Personal.

Om du inte använder ett separat rekryteringsprogram kan du även hantera kandidater manuellt i Personal.

> [!NOTE]
> Om du är administratör eller utvecklare och vill integrera Personal med ett rekryteringsprogram från tredje part, se [Konfigurera Dataverse-integrering](hr-admin-integration-common-data-service.md) och [Konfigurera virtuella Dataverse-register](hr-admin-integration-common-data-service-virtual-entities.md)
>
> Du kan också hitta integrationsappar för rekrytering på [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).
>
## <a name="enable-recruiting-requests-on-the-merged-infrastructure"></a>Aktivera rekryteringsbegäranden i sammanslagen infrastruktur

Om du vill skicka rekryteringsförfrågningar i HR-rekrytering måste du först aktivera funktionerna för **användarupplevelse för personal** och **Hantering av rekryteringsprocess**.

När funktionerna har aktiverats ska du välja funktionen med följande steg: 
1. Gå till **Personal** > **Konfigurera** > **Personalparametrar**.
2. På fliken  **Rekrytering** , ställ in **Rekrytering har aktiverats** till **Ja**.
3. I listan **Rekryteringsupplevelse**, välj **HR-rekrytering**.  
4. Klicka på **Spara**. 

> [!Note] 
> När **HR-rekrytering** har valts blir **Rekryteringsprojekt** (äldre) inte tillgängliga. 


## <a name="add-a-recruiting-request-location"></a>Lägg till en plats för rekryteringsbegäran

Om din organisation har flera platser kan du lägga till dem så att de kan välja en plats där den nya rekryteringen ska fungera. Platsen tas med i jobbpubliceringen.

1. I sökfältet anger du **Plats för rekryteringsbegäran**.
2. Välj **Ny**.
3. I fältet **Plats för rekryteringsbegäran** anger du platsens namn.

    ![Lägg till en plats för rekryteringsbegäran.](./media/hr-recruit-0a-add-location.png)

4. För **Beskrivning** anger du en beskrivning av platsen.
5. Under **Plats**, välj **Lägg till**. Om dialogrutan **Ny adress** visas anger du platsens adress.<!--note from editor: Please make the address in this image less plausible. Via the fictitious guidelines on CELAweb: For street addresses, you should use sequential numbers, common street names, and incorrect zip codes (e.g., 4567 Main St Buffalo, NY 98052). (See https://microsoft.sharepoint.com/sites/CELAWeb-Copyrights-Trademarks-And-Patents/SitePages/trademarks-fictitious-names.aspx)-->

    ![Ange adress.](./media/hr-recruit-0b-address.png)

6. Under **Kontaktuppgifter** anger du uppgifterna för platsens kontaktperson.
7. Välj **Spara**.

## <a name="add-a-recruiting-request"></a>Lägg till en rekryteringsbegäran

Chefer kan skicka in rekryteringsförfrågningar till Personal. Om du använder ett separat rekryteringsprogram skickar du en rekryteringsbegäran och startar rekryteringsprocessen i det programmet. I annat fall måste du utföra den här proceduren för att starta arbetsflödet för din interna rekryteringsprocess.

1. Välj **Självbetjäning för medarbetare**.
2. Välj fliken **Mitt team**.
3. Välj **Begär att rekrytera**.

    ![Starta en rekryteringsbegäran.](./media/hr-recruit-1-request-to-recruit.png)

4. Fyll i fälten **Beskrivning**, **Jobb** och **Uppskattat startdatum**.

    ![Slutför rekryteringsbegäran.](./media/hr-recruit-2-request-to-recruit.png)

5. Välj **Fortsätt**. Rekryteringsbegäran för din befattning visas.
6. Under **Allmänt** väljer du en rekryterare från listrutan **Rekryterare** och väljer sedan en plats från listrutan **Plats för rekryteringsbegäran**.
7. Under **Jobb** ändrar du informationen efter behov och väljer sedan **Skapa information från jobb**.

    ![Skapa information från jobb.](./media/hr-recruit-3-create-details-from-job.png)

    Resten av din rekryteringsbegäran fylls i med standardinformation för det jobb som du har angett.

8. Under **Extern beskrivning** anger du en jobbeskrivning som är riktad utåt.
9. Under **Befattningar** väljer du **Lägg till** och sedan en befattning för den här rekryteringsbegäran.<!--note from editor: In all of these images, are they approved fictitious names, or do they come from sample data included with the app?-->

    ![Lägg till en befattning.](./media/hr-recruit-4-select-position.png)

10. Under **Färdigheter** väljer du **Lägg till** och sedan en färdighet.
11. Under **Utbildningsmässiga krav** väljer du **Lägg till** och sedan värden från listrutorna **Utbildning** och **Utbildningsnivå**.

    ![Lägg till utbildningsmässiga krav.](./media/hr-recruit-5-select-educational-requirements.png)

12. Under **Kommentar** lägger du till kommentarer efter behov.
13. Under **Kompensation** väljer du en nivå från listrutan **Nivå** och justerar sedan **Låg tröskel**, **Kontrollpunkt** och **Hög tröskel** efter behov.
14. När din rekryteringsbegäran är slutförd och du är redo att starta rekryteringsprocessen väljer du **Aktivera** på menyraden.

    ![Aktivera rekryteringsbegäran.](./media/hr-recruit-6-activate-recruit-request.png)

15. Välj **Spara**.

## <a name="view-and-edit-your-recruiting-requests"></a>Visa och redigera dina rekryteringsförfrågningar

Om du är chef och vill visa dina egna begäranden:

1. Välj **Självbetjäning för medarbetare**.
2. Välj fliken **Mitt team**.
3. Under fliken **Information om mitt team**, välj fliken **Rekryteringsförfrågningar**.

    ![Välj fliken Rekryteringsförfrågningar.](./media/hr-recruit-7-recruiting-requests.png)

4. Om du vill visa eller redigera en rekryteringsbegäran väljer du den i rutnätet.

Om du är HR Pro och vill visa alla rekryteringsförfrågningar:

1. Välj **Personalhantering**.
2. Välj **Rekryteringsförfrågningar**.

    ![Visa rekryteringsförfrågningar i Personalhantering.](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. Om du vill visa eller redigera en rekryteringsbegäran väljer du den i rutnätet.

## <a name="add-or-edit-a-candidate-profile"></a>Lägga till eller redigera en kandidatprofil

Om din organisation har integrerats med ett annat program för att kunna hantera rekryteringsförfrågningar, vidarebefordras rekryteringsförfrågningar till programmet. Programmet för rekrytering skickar sedan tillbaka informationen till Personal. I annat fall kan du följa dina interna rekryteringsprocesser och ange kandidatinformation manuellt.

1. Välj **Personalhantering**.
2. Markera **länkar**
3. Under **Rekrytering** väljer du **Kandidater**.

    ![Visa kandidater.](./media/hr-recruit-9-candidates.png)

4. Om du vill lägga till en kandidat väljer du **Ny**. Om du vill redigera en befintlig kandidat väljer du kandidaten från listan och väljer sedan **Redigera**. Kandidatprofilen visas.
5. Under **Kandidatsammanfattning** anger eller redigerar du kandidatinformationen efter behov.
6. Under **Rekryteringsbegäran** väljer du en rekryteringsbegäran som kandidaten ska kopplas till. Fyll sedan i fälten **Uppskattat startdatum**, **Anställande chef**, **Befattning** och **Beskrivning**.

    ![Länka till rekryteringsbegäran.](./media/hr-recruit-10-link-to-recruiting-request.png)

7. Fyll i all information i följande områden som du vill inkludera i kandidatens post:

    - **Kommentarer**
    - **Yrkeserfarenhet**
    - **Kontaktinformation**
    - **Utbildning**
    - **Kompetenser**
    - **Intyg**
    - **Kontroller**

8. Välj **Spara**.

## <a name="hire-a-candidate"></a>Anställa en kandidat

När du är redo att anställa en kandidat följer du den här proceduren för att överföra kandidaten till medarbetare.

1. På sidan **Kandidat** väljer du **Anställ**.

    ![Anställa en kandidat.](./media/hr-recruit-11-hire.png)

2. På sidan **Anställ ny medarbetare**, under **Detaljer**, fyller du i samtliga fält.

    ![Ange ny anställningsinformation.](./media/hr-recruit-12-hire-new-worker.png)

3. Under **Befattningsdetaljer** verifierar och ändrar du information efter behov.
4. Under **Checklistor för registrering** väljer du relevanta registreringschecklistor för medarbetaren.
5. Välj **Fortsätt** om du vill skapa medarbetarposten.

    > [!NOTE]
    > Beroende på din organisations arbetsflöden kan kandidatposten gå igenom ytterligare godkännandesteg innan det blir en medarbetarpost.

## <a name="decide-not-to-hire-a-candidate"></a>Besluta att inte anställa en kandidat

Om du väljer att inte anställa en kandidat följer du den här proceduren för att ta bort dem från granskningsprocessen. 

1. På sidan **Kandidat** väljer du **Anställ ej**.

    ![Anställ inte kandidat.](./media/hr-recruit-13-do-not-hire.png)

2. Välj en **orsakskod** och ta med eventuella kommentarer.
3. Välj **OK**.

## <a name="dismiss-a-candidate"></a>Avvisa en kandidat

Vid behov kan du avvisa en kandidat när du har anställt den. En kandidat kan till exempel avvisa erbjudandet eller inte komma till arbetet den första dagen.

- På sidan **Kandidat** väljer du **Avvisa kandidat**.

    ![Avfärda kandidat.](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a>Se även

[Konfigurera virtuella Dataverse-register](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Organisera personalen](hr-personnel-departments-jobs-positions.md)<br>
[Ställa in komponenter för ett jobb](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
